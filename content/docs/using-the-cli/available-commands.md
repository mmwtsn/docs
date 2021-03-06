---
tags: cli
---

## Overview of Available commands

The wercker command line interface comes with the following commands:

```no-highlight
COMMANDS:
   build, b     build a project
   dev          build a local project
   check-config check the project's yaml
   deploy, d    deploy a project
   detect, de   detect the type of project
   login, l     log into wercker
   logout, l    logout from wercker
   pull, p      pull a build result
   version, v   display version information
   help, h      Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --environment "ENVIRONMENT"   specify additional environment variables in a file
   --verbose                     print more information
   --no-colors                   wercker output will not use colors (does not apply to step output)
   --debug                       print additional debug information
   --journal                     Send logs to systemd-journald. Suppresses stdout logging.
   --auth-token                  authentication token to use
   --help, -h                    show help
   --version, -v                 print the version
```

### Detect

The *detect* command introspects your projects and generates
[wercker.yml](/learn/wercker-yml/introduction.html) files for your
projects.

> Currently go, python, nodejs and ruby are supported in the detect
> command

### Build and Deploy

The *build* and *deploy* commands execute these pipelines locally. Using
the *pull* command you can download a container from the wercker
platform after which you can use Docker commands to debug this container locally.

### Logging in

You can log into wercker with your username and password as follows:

```no-highlight
wercker login
```

This will save a token in your `$HOME/.wercker` folder, so you don't
have to login the next time.

Note that if you've signed up with GitHub you will need a password for the CLI
which you can create on your profile page on wercker.

### Update

You can check if you're running the latest version of the CLI by
running:

```no-highlight
> wercker version

Version: 1.0.54
Git commit: dabc15876b877209047fa926774f97f001afbf43
No new version available
```

When not up to date the CLI will nudge you to download a newer version
of the CLI.
