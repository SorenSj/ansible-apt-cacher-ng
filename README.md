Role Name
=========

An Ansible role to install and configure apt-cacher-ng. With teardown task.

Requirements
------------

None

Role Variables
--------------

### Required variables
apt_cacher_ng_bind_address: "0.0.0.0"
apt_cacher_ng_report_page: "acng-report.html"
apt_cacher_ng_cache_dir: "/var/cache/apt-cacher-ng"
### Optional variables
apt_cacher_ng_port: 3142
apt_cacher_ng_log_dir: "/var/log/apt-cacher-ng"
apt_cacher_ng_verbose_log: 0
apt_cacher_ng_local_dirs: "acng-doc /usr/share/doc/apt-cacher-ng"
apt_cacher_ng_support_dir: "/usr/lib/apt-cacher-ng"
apt_cacher_ng_pid_file: "/var/run/apt-cacher-ng/pid"
apt_cacher_ng_ex_treshold: 4
### apt_cacher_ng_proxy: "https://username:proxypassword@proxy.example.net:3129"
apt_cacher_ng_security_user: "admin"
apt_cacher_ng_security_password: "p@55w0rd"

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: sorensj.apt-cacher-ng }

If you wish to uninstall and completely remove everything, run this playbook:

    ---
    - hosts: proxy_machine
      become: true
      gather_facts: true
      tasks:
        - name: Uninstall apt-cacher-ng and remove configuration and data
          ansible.builtin.include_role:
            name: apt-cacher-ng
            tasks_from: teardown

License
-------

MIT

Author Information
------------------

Author: Søren Sjøstrøm (soren.sjostrom@hotmail.com)
