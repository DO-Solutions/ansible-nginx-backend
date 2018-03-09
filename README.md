ansible-nginx-backend
=========
Configure nginx backends on DigitalOcean Droplets that are configured to listen on the private network (eth1)

Requirements
------------
Be sure to place your content in a directory in the role's **files/** directory.

Role Variables
--------------
The following dictionary can be set in either the **defaults/main.yml** or **group_vars/*group-name*/vars.yml**.

* *nginx_sync_files*: Name of the directory holding your site's content.
* *example1*: This is used as the configuration file name used by nginx in site-{available,enabled}.
* *doc_root*: Location for your site's document root.
* *server_name*: This will be what nginx uses to determine what server block to use.


    sites:
      example1:
        doc_root: /var/www/vhosts/example.com
        server_name: example.com

    nginx_sync_files: "example.com"


Example Playbook
----------------

    ansible-galaxy install -r requirements.yml

or

    ansible-galaxy install cmndrsp0ck.ansible-nginx-backend

Once it's installed in your **roles** directory, you can use the following in your playbook.

    - hosts: web_node
      roles:
         - { role: cmndrsp0ck.ansible-nginx-backend }
      become: True

License
-------

GPL-3.0
