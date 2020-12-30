# handle\_message

The `handle_message` method is one of the most fundamental controller methods in Xip. It enables you to succinctly handle messages without needing long `if/else` or `case` statements.

## Example

Here's an example of what it looks like:

```ruby
def get_call_response
  handle_message(
    :yes             => proc { step_to state: :say_yes },
    'Not available'  => proc { step_to state: :say_no_problem },
    :no              => proc { step_to state: :say_no_problem },
    :call            => proc { step_to state: :say_call_later }
  )
end
```

In this example, the `handle_message` method has four different "match arms". Each arm is just `key => value` pair since it's all  just a hash. The keys are the `match expressions`. The values are `procs` that serve as the action to take if the match arm is matched.

Xip accepts match expressions in five different ways:

1. [A string](string-mather.md) \(like Line 4\)
2. An [alpha ordinal](alpha-ordinal-matcher.md)
3. A [symbol](nlp-matcher.md) \(like Lines 3, 5, and 6\)
4. A [regex](regex-matcher.md)
5. [nil](nil-matcher.md)

{% hint style="info" %}
The `procs` can be multi-line and thus perform more than one action. In the docs for the match expressions we'll include some of those examples.
{% endhint %}

