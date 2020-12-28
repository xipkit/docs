---
description: A quick primer of the various pieces that comprise Xip Kit.
---

# Basics

## Anatomy of a Xip Bot

## Life of an Incoming Message

## Directory Structure

When you use the generator `xip new` to instantiate a new bot, here is the directory structure that will be created:

```text
├── Gemfile
├── Procfile.dev
├── README.md
├── Rakefile
├── bot
│   ├── controllers
│   │   ├── bot_controller.rb
│   │   ├── catch_alls_controller.rb
│   │   ├── concerns
│   │   ├── goodbyes_controller.rb
│   │   ├── hellos_controller.rb
│   │   ├── interrupts_controller.rb
│   │   └── unrecognized_messages_controller.rb
│   ├── helpers
│   │   └── bot_helper.rb
│   ├── models
│   │   ├── bot_record.rb
│   │   └── concerns
│   └── replies
│       ├── catch_alls
│       │   └── level1.yml
│       ├── goodbyes
│       │   └── say_goodbye.yml
│       └── hellos
│           └── say_hello.yml
├── config
│   ├── boot.rb
│   ├── database.yml
│   ├── environment.rb
│   ├── flow_map.rb
│   ├── initializers
│   │   ├── autoload.rb
│   │   └── inflections.rb
│   ├── puma.rb
│   ├── services.yml
│   └── sidekiq.yml
├── config.ru
└── db
    └── seeds.rb
```

