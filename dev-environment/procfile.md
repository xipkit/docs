---
description: Examining the contents of the Procfile
---

# Procfile

If you used the generator to instantiate your bot, you'll find a `Procfile.dev` in the root directory of your bot. Here are the contents:

```text
web: bundle exec puma -C config/puma.rb
sidekiq: bundle exec sidekiq -C config/sidekiq.yml -q xip_webhooks -q xip_replies -r ./config/boot.rb
```

If you're not familiar with Procfiles, each line specifies a process name and command for the process. So in this default Procfile, we've specified 2 processes, `web` and `sidekiq`.

### Sidekiq

Currently, Xip uses Sidekiq for processing background jobs. It is configured to monitor 2 queues by default: `xip_webhooks` and `xip_replies`. You can specify additional queues as needed by your bot by adding `-q <queue_name>` to the `sidekiq` Procfile entry.

{% hint style="success" %}
You can even use Sidekiq Pro and Sidekiq Enterprise if you have a license
{% endhint %}

