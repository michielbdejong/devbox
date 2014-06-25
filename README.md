# My devbox

This is the Docker image I use as my development environment. It has node, git, vim, and a few other tools.

Whenever I need to install something, I edit `devbox/Dockerfile`, and then build it with:

    docker build -t devbox devbox/

I shell into it with:

    docker run -i -t --volumes-from michiel-data devbox /bin/bash

and after I did the work I wanted to do, and pushed my changes to github, I exit again by typing 'exit'.

On my data container (called 'michiel-data' on my VPS), I have an ssh key at /data/.ssh, to which this
image softlinks, so that I can push to github.com and to 5apps.com. I check out all repos I want to
work on to /data/code, so that even if I exit the container without pushing my changes, they will still
be there the next time, because they are saved on my data container.
