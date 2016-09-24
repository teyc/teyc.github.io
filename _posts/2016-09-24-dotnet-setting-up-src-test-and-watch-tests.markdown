---
published: true
title: dotnet - setting up src, test and watch tests
layout: post
---
How to set up a multi-project solution using dotnet cli, with xunit and a test watcher configured.

Create the basic directories

    mkdir src\Something
    pushd src\Something
    dotnet new -t lib
    popd

    mkdir test\Something.Test
    pushd test\Something.Test
    dotnet new -t lib
    # Add dependency on `dotnet watch` in project.json
    #
    #  "dependencies": {},
    #  "tools": {
    #   "Microsoft.DotNet.Watcher.Tools": "1.0.0-*"
    #   },
    #  "frameworks": {
    #    ...
    #
    popd

Add `global.json`

    {
      projects: [
        "src/Something",
        "test/Something.Test"
      ]
    }
    


   