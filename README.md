# heroku-16 stack image with added bsdmainutils

### Context
I wanted to run a bash script in Heroku on a schedule, and my bash script used the Unix `cal` command. It's not available in the default Heroku stack (currently an Ubuntu 16.04 image), so I made my own. Here it is. It's quite simple - I just added the Ubuntu `bsdmainutils` package to the script that is run from the Dockerfile.

Once your app has been deployed to Heroku in this custom container, further updates are not made via a `git push`, but rather `heroku container:push web --app <my_app_name>`. Simple!

### TODO
It might be nice to strip out all the unnecessary packages from the image, but I'm not in a rush to do that.