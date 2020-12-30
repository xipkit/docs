# Catch-Alls

Xip Catch-Alls are designed to handle the error cases within bots. Either the bot doesn't understand what a user typed or an error occurred. If this were a webpage, we'd see the dreaded HTTP 500 error page. 

Catch-Alls are designed to move beyond simple "I don't understand" messages and help users get back on track. The better your CatchAlls, the better your bot.

### Triggering

The `catch_all` flow is automatically triggered when either of two things happens within a controller action:

1. [Fails to progress a user](controller-overview.md#failing-to-progress-a-user).
2. An Exception is raised.

### Multi-Level

Stealth keeps track of how many times a CatchAll is triggered for a given session. This allows you to build experiences in which the user is provided different responses for subsequent failures. Once a session progresses past a failing state, the CatchAll counter resets.

### Retrying

By default, a Stealth bot comes with the first level CatchAll already defined. Here is the `CatchAllsController` action and associated reply:

```ruby
class CatchAllsController < BotController

  def level1
    send_replies

    if fail_session.present?
      step_to session: fail_session
    else
      step_to session: previous_session - 2.states
    end
  end

private

   def fail_session
     previous_session.flow.current_state.fails_to
   end

end
```

```text
- reply_type: text
  text: Oops. It looks like something went wrong. Let's try that again
```

In the controller action, we check if the `previous_session` \(the one that failed\) specified a `fails_to` state. If so, we send the user there. Otherwise, we send the user back 2 states.

Sending a user back two states is a pretty good generic action. Going back 1 state takes us back to the action that failed. Since the actions most likely to fail are `get` actions, or actions that deal with user responses, going back 2 states usually takes us back to the original "question".

### Adding More Levels

If you would like to expand the experience, simply add a `level2` controller action and associated reply \(and update the `FlowMap`\). You can go as far as you want. CatchAlls have no limit, just make sure you increment using the standardized method names of `level1`, `level2`, `level3`, `level4`, etc.

If a user has encountered the maximum number of CatchAll levels as you have defined, the user's session will remain at the last CatchAll state.

### Caveats

#### Triggering Catch-Alls within the `CatchAllsController`

In order to prevent infinite loops, starting in Stealth 2.0, errors raised within the `catch_all` flow will be ignored.

