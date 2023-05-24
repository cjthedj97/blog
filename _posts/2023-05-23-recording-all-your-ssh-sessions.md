---
layout: post
title: "Recording SSH sessions with asciinema"
tags: SSH bash function asciinema
---

{% include warning.html content="This is a Draft post." %}

So your looking for a way to record you SSH sessions.

Here is an example of a simple bash function that will allow you to record you ssh session with no additional work.

You can SSH like normal and let the function start the recording.

It even stops the recording after your ssh session is disconnected.

```
function ssh {

  ssh=$(whereis -b ssh | cut -d' ' -f2)
  SESSION_NAME="ssh-$(date +%Y%m%d-%H%M%S)"

 # Create asciinema recording (for users not using sshrc)
 asciinema rec -y "$HOME/asciinema/$SESSION_NAME.cast" --command "$ssh $@"

}
```

A bit more advanced would be to call sshrc rather than SSH so you can being scripts, functions, etch over to the server you are logging into.

Note: This assumes you have sshrc in your home directory at bin/sshrc.

```
function ssh {
  SESSION_NAME="ssh-$(date +%Y%m%d-%H%M%S)"

 # Create asciinema recording (for use with sshrc)
asciinema rec "$HOME/asciinema/$SESSION_NAME.cast" --command "/bin/bash $HOME/bin/sshrc $@"
    
}
```
