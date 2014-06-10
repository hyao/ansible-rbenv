Ansible Rbenv 
==============

Ansible role to deploy rbenv and rbenv plugins (https://github.com/sstephenson/rbenv); You can also use to install ruby using ruby-build plugin, and select which rbenv plugins to install.

Requirements
------------

Tested on Ubuntu Trusty LTS.

Role Variables
--------------

```
rbenv_user: user to deploy rbenv and plugins

# select which plugins to install; set True to enable and False to disable
rbenv_ruby_build: True
rbenv_vars: True
rbenv_gem_rehash: True
rbenv_binstubs: False

# ruby installation; set True to install; rbenv_ruby_version to set ruby version to install
rbenv_install_ruby: False 
rbenv_ruby_version: 2.1.2
rbenv_ruby_make_opts: "-j 2"

rbenv_install_bundler: True
```

Example Playbook
-------------------------

    - hosts: servers
      sudo: yes
      sudo_user: deploy    # should be same as rbenv_user 
      roles:
         - { role: hyao.rbenv, rbenv_install_ruby: True }

License
-------

MIT

Author Information
------------------

https://github.com/hyao
