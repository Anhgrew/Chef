# Cookbook to install nginx - Chef

This cookbook installs and configures a simple web
site using nginx web server.
---
- [x] Requirements

# Install chef-workstation

```
wget https://packages.chef.io/files/stable/chef-workstation/23.4.1032/ubuntu/22.04/chef-workstation_23.4.1032-1_amd64.deb

dpkg -i chef-workstation_23.4.1032-1_amd64.deb 
```
---

Supports only CentOS or other RHEL variants for now.

# Run cookbook

```
git clone https://github.com/Anhgrew/Chef.git anhgrew && cd anhgrew

kitchen create 

kichen login 

kitchen converge 

kitchen verify

```

# Destroy kitchen container 
```
kitchen destroy
```

# Testing
---

A `.kitchen.yml` file is provided. Run `kitchen test` to verify this cookbook.

---


# Chef Cookbook - Source Code Organization:
```
# Cookbook source organization
.
├── attributes
│   └── default.rb
├── CHANGELOG.md
├── chefignore
├── compliance
│   ├── inputs
│   ├── profiles
│   ├── README.md
│   └── waivers
├── files
│   └── default
│       └── motd.sh
├── kitchen.yml
├── LICENSE
├── metadata.rb
├── Policyfile.lock.json
├── Policyfile.rb
├── README.md
├── recipes
│   ├── default.rb
│   └── student.rb
├── spec
│   ├── spec_helper.rb
│   └── unit
│       └── recipes
│           └── student_spec.rb
├── templates
│   ├── index.html.erb
│   └── motd.erb
├── test
    └── integration
        └── default
            ├── default_test.rb
            └── student_test.rb




# Generator To Generate Bare Cookbook
|── test-gen
    ├── files
    │   └── default
    │       ├── Berksfile
    │       ├── chefignore
    │       ├── cookbook_readmes
    │       │   ├── README.md
    │       │   └── README-policy.md
    │       ├── gitignore
    │       ├── repo
    │       │   ├── cookbooks
    │       │   │   └── example
    │       │   │       ├── attributes
    │       │   │       │   └── default.rb
    │       │   │       ├── metadata.rb
    │       │   │       ├── README.md
    │       │   │       └── recipes
    │       │   │           └── default.rb
    │       │   ├── data_bags
    │       │   │   ├── example
    │       │   │   │   └── example_item.json
    │       │   │   └── README.md
    │       │   ├── dot-chef-repo.txt
    │       │   ├── environments
    │       │   │   ├── example.json
    │       │   │   └── README.md
    │       │   ├── policyfiles
    │       │   │   └── README.md
    │       │   ├── README.md
    │       │   └── roles
    │       │       ├── example.json
    │       │       └── README.md
    │       ├── spec_helper_policyfile.rb
    │       └── spec_helper.rb
    ├── metadata.rb
    ├── recipes
    │   ├── attribute.rb
    │   ├── cookbook_file.rb
    │   ├── cookbook.rb
    │   ├── helpers.rb
    │   ├── input.rb
    │   ├── policyfile.rb
    │   ├── profile.rb
    │   ├── recipe.rb
    │   ├── repo.rb
    │   ├── resource.rb
    │   ├── template.rb
    │   └── waiver.rb
    └── templates
        └── default
            ├── attribute.rb.erb
            ├── CHANGELOG.md.erb
            ├── compliance_dir_README.md.erb
            ├── compliance_profile_control.rb.erb
            ├── compliance_profile_inspec.yml.erb
            ├── cookbook_file.erb
            ├── helpers.rb.erb
            ├── input.yml.erb
            ├── inspec_default_test.rb.erb
            ├── kitchen_policyfile.yml.erb
            ├── kitchen.yml.erb
            ├── LICENSE.all_rights.erb
            ├── LICENSE.apachev2.erb
            ├── LICENSE.gplv2.erb
            ├── LICENSE.gplv3.erb
            ├── LICENSE.mit.erb
            ├── metadata.rb.erb
            ├── Policyfile.rb.erb
            ├── README.md.erb
            ├── recipe.rb.erb
            ├── recipe_spec.rb.erb
            ├── recipe.yml.erb
            ├── repo
            │   └── gitignore.erb
            ├── resource.rb.erb
            ├── template.erb
            └── waiver.yml.erb
```
---

# Chef command
chef-apply file.rb

inspec exec file.rb

cookstyle file.rb

# Kitchen command
---
# kitchen init --driver=kitchen-dokken --provisioner=dokken
---
File: kitchen.yml 
---
driver:
  name: dokken
  chef_version: latest

provisioner:
  name: dokken

transport:
  name: dokken

platforms:
  - name: centos73
    driver: 
      image: centos:7.3.1611

verifier:
  name: inspec

suites:
  - name: default
    run_list:
    attributes:

Command
kitchen create <name of kitchen list out> --log_level=debug
---
# Kitchen commands flow:
kitchen create -> kitchen login -> kitchen converge -> kitchen verify -> kitchen test -> kitchen destroy 
# Install chef-client

https://docs.chef.io/chef_install_script/

---
chef-zero = chef-solo: run on in-mem local
chef-client -> default on many node servers

# Ohai - collect system log
# Ohai collect info command:
/opt/chef/bin/ohai memory/total -> get total_mem

# Chef commands
chef generate template/recipe/file <cookbook>

---
# Inspec harden framework checking docker node:
docker run -it -d --name test centos:7.3.1611 /bin/bash

git clone https://github.com/dev-sec/linux-baseline.git

--> Docker on local
inspec exec linux-baseline --target docker://test

-->VM node on Digital Ocean
inspec exec linux-baseline -t ssh://centos@167.99.69.96 --key-files ~/.ssh/id_rsa --sudo

--> Show clear output:
inspec exec linux-baseline -t ssh://centos@167.99.69.96 --key-files ~/.ssh/id_rsa --reporter=progress | documentation | json | html2


- [x] Know more about inspec resource from shell: 
-> Command: inspec shell ----> help <resource>

controls = many describe + title + ...

---
- [x] Check after execute on product: Using autdit cookbook 
