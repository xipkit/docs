---
description: ✨✨✨
---

# Hot-Code Reloading

Hot-code reloading is one of the more enjoyable features of using Xip Kit to create your bots. As you make changes to your bot, your source code is automatically loaded into memory without having to stop and start your bot!

There is nothing you need to turn on to start using this feature. As long as you are in the `development` [environment](../basics.md#environments). You may however wish to customize which files are watched for changes as you add your own custom directories, service objects, etc.

## Customizing Hot-Reload Paths

By default, these are paths and files that Xip will watch for changes:

```text
bot/controllers/conerns/*.*
bot/controllers/*.*
bot/models/concerns/*.*
bot/models/*.*
bot/helpers/*.*
config/*.*
```

In addition to your Ruby code in these directories, all reply files are automatically included since Xip reads their contents for each message.

### Adding a File or Path to Watch

As you add your own directories to your bot, you'll want to add them to your `autoload_path` so that they can be hot-reloaded while in `development`. 

{% hint style="info" %}
In `production` Xip will pre-load all files in the `autoload_paths` array to improve performance.
{% endhint %}

#### Adding a Single File

To add the file `lib/some_file.rb` to the `autoload_path`, add this line to `config/autoload.rb`:

```ruby
Xip.config.autoload_paths << File.join(Xip.root, 'lib', 'some_file')
```

{% hint style="info" %}
You don't need to include the `.rb` extension to the filename.
{% endhint %}

#### Adding a Directory

To add the entire `lib` directory to the `autoload_path`, add this line to `config/autoload.rb`:

```ruby
Xip.config.autoload_paths << File.join(Xip.root, 'lib')
```

