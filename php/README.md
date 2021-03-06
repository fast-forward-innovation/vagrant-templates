# PHP Vagrant box for development

This is a basic Debian Linux-box for PHP and WordPress development. It's by no means complete, but still a work in progress. It uses Ansible playbooks for provisioning, using roles from the shared `ansible` directory.

## Features

 - PHP 5.6
 - configurable with Apache (mod_php) or Nginx (php-fpm) web server
 - customizable provision with Ansible variables and playbooks
 - can include MySQL and MongoDB
 - works with Slim framework

## Known Issues

 - not yet tested with Simphony
 - missing PHP7 support, see <https://www.linuxbabe.com/linux-server/upgrade-to-php7-on-linux-server-ubuntu-debian>
 - not fully tested with Nginx, see <https://www.nginx.com/resources/wiki/start/topics/examples/phpfcgi/>

## Customizations

You can share your whole home directory with:

```ruby
if $share_home
  config.vm.synced_folder ENV['HOME'], ENV['HOME'], id: "home", :nfs => true, :mount_options => ['nolock,vers=3,udp']
end
```
