# bearded-octo-batman

An experimental Vagrant setup for docker based development

To see how using something like this for docker-based development on my mac
works.

The idea is for this to be at a top level and different docker-based projects
can live inside the code directory.  These will then share this vagrant
instance (so save spinning up new ones) and hence will share the same docker
image library (so I don't have to download the base images for each project -
they'll already be there...

Might work out or it might not.....
