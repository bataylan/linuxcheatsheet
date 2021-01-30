#Fedora

**docker and docker-compose**
If you are using docker-compose and get error, you need to change cggroup to v1 in fedora, for doing that
``sudo grubby --update-kernel=ALL --args="systemd.unified_cgroup_hierarchy=0"``
