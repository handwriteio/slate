Getting Started with our Docs
------------------------------

### Prerequisites

You're going to need:

 - **Linux or macOS** — Windows may work, but is unsupported.
 - **Ruby, version 2.3.1 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

1. Clone this repo to your hard drive
2. `cd` into the directory
3. Initialize and start the app. You can either do this locally:

```shell
bundle install
bundle exec middleman server
```

You can now see the docs at http://localhost:4567. Whoa! That was fast!

### Deploying

This is the easy part, simply run `./deploy.sh` and it will automagically be deployed.

View the live docs at [https://documentation.handwrite.io/](https://documentation.handwrite.io/)


### Note on JavaScript Runtime

For those who don't have JavaScript runtime or are experiencing JavaScript runtime issues with ExecJS, it is recommended to add the [rubyracer gem](https://github.com/cowboyd/therubyracer) to your gemfile and run `bundle` again.

### Thanks to Slate
This repo was built using [Slate](https://github.com/slatedocs/slate). For more in depth info, visit the docs. 
