This setup for [Vagrant][vagrant] creates a complete build environment for [OpenGeoSys](http://www.opengeosys.org).

### Requirements

- [Vagrant][vagrant]
- Ruby >= 1.9.3
  - [Bundler](http://gembundler.com)

### Installation

Download the precise64-box:

```bash
vagrant box add precise64 http://files.vagrantup.com/precise64_vmware.box # for VMWare Fusion
vagrant box add precise64 http://files.vagrantup.com/precise64.box # for Virtual Box
```

```bash
git clone https://github.com/bilke/ogs-vagrant.git
cd ogs-vagrant
bundle install --path .bundle --binstubs
librarian-chef install
vagrant up
```
### Optional configuration

Add this to the `config.vm.provision`-block:

```ruby
chef.json = {
  "ogs" => {
    "svn_user"     => "username",
    "svn_password" => "password",
    "branch"       => "your/branch", # Checks out another branch
    "gui"          => true,          # Should the GUI-dependencies be installed?
    "benchmarks"   => true           # Should the benchmarks be checked out
  }
}
```
[vagrant]: http://www.vagrantup.com
