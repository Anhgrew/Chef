# Cookbook to install nginx - Chef

This cookbook installs and configures a simple web
site using the anhgrew web server.

- [x] Usage
---

Add `Anhgrew` to your node's run list.

- [x] Requirements
---

Supports only CentOS or other RHEL variants for now.

- [x] Testing
---

A `.kitchen.yml` file is provided. Run `kitchen test` to verify this cookbook.
---
# Chef Cookbook - Source Code Organization:
```
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
