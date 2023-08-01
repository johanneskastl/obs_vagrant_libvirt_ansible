# obs_vagrant_libvirt_ansible

This Vagrant setup creates a VM and configures [a OBS
server](https://openbuildservice.org).

Default OS is openSUSE Leap 15.3. Although that can be changed in the
Vagrantfile, the OBS project only supports 15.3 with 15.4 being worked on
currently.

There is a branch that uses 15.4 as the base OS, if you are willing to try out.

## Vagrant

1. You need vagrant obviously. And ansible. And git...
1. Fetch the box, per default this is `opensuse/Leap-15.3.x86_64`, using
   `vagrant box add opensuse/Leap-15.3.x86_64`.
1. Make sure the git submodules are fully working by issuing `git submodule init
   && git submodule update`
1. Run `vagrant up`
1. Find out the obs-server-153 VM's IP (e.g. `vagrant address obs-server-153`,
   if you have vagrant address installed) and connect to `http://IP:80`. You
   should get the overview page.
1. You can connect to the repos (HTTP on port 82) and the WebUI (HTTPS on port
   443).  You will need to make an exception for the self-signed TLS certificate
   used by default.
1. Follow the
   [documentation](https://openbuildservice.org/help/manuals/obs-admin-guide/obs.cha.installation_and_configuration.html#_online_configuration)
1. Party!

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via kastl@b1-systems.de.
