## VirtualBox + Vagrant + Landrush; running Ubuntu 14.04 LTS w/ a full LAMP stack. Includes a tutorial!

- See full tutorial: <http://jaswsinc.com/vagrant-ubuntu-lamp/>
- Instructions specifically for this package: <http://jaswsinc.com/vagrant-ubuntu-lamp/#-lamp>

![](http://cdn.websharks-inc.com/jaswsinc/uploads/2015/03/os-x-vagrant-virtualbox.png?v=1)

---

### Instructions for My Vagrant LAMP Stack Project

#### Step 1: Satisfy Software Requirements

You need to have VirtualBox, Vagrant, and Landrush installed. See [full tutorial](http://jaswsinc.com/vagrant-ubuntu-lamp/).

```bash
$ brew cask install virtualbox
$ brew cask install vagrant
$ vagrant plugin install landrush
```

You need to install the `ubuntu/trusty64` Box. See [full tutorial](http://jaswsinc.com/vagrant-ubuntu-lamp/).

```bash
$ vagrant box add ubuntu/trusty64
```

#### Step 2: Clone my GitHub Repo (Ubuntu LAMP Stack)

```bash
$ mkdir ~/Projects && cd ~/Projects
$ git clone https://github.com/jaswsinc/vagrant-ubuntu-lamp
```

#### Step 3: Vagrant Up!

```bash
$ cd ~/Projects/vagrant-ubuntu-lamp
$ vagrant up # Boot-up the Box with LAMP ready-to-go!
```

#### Step 4: Confirm it is Working!

- HTTP: Open <http://ubuntu-lamp.vm>. You should see a `phpinfo()` page.
- HTTPS: Open <https://ubuntu-lamp.vm>. You should get an SSL security warning. Please bypass this self-signed certificate warning and proceed. You should again see the `phpinfo()` page. SSL is working as expected!

#### Step 5: Add Files to: `~/Projects/vagrant-ubuntu-lamp/htdocs/`

The is the web root. Add your application files. e.g., WordPress, Drupal, Joomla, etc.

#### Step 6: Learn to Use the Tools That I've Bundled

A username/password is required to access each of these tools. It is always the same thing.

- Username: `vagrant` Password: `vagrant`

Available Tools (Using Any of These is Optional):

- <https://ubuntu-lamp.vm/tools/pma> PhpMyAdmin  
  DB name: `vagrant`, DB username: `vagrant`, DB password: `vagrant`
- <https://ubuntu-lamp.vm/tools/opcache> PHP OPCache extension status and management page.
- <https://ubuntu-lamp.vm/tools/php.php> PHP info (i.e., `phpinfo()`) page.
- <https://ubuntu-lamp.vm/tools/php5-fpm-status/> PHP5-FPM status page.
- <https://ubuntu-lamp.vm/tools/apache-status/> Apache status page.
- <https://ubuntu-lamp.vm/tools/apache-info/> Apache info page.

#### Step 7: Tear it Down and Customize

```bash
$ cd ~/Projects/vagrant-ubuntu-lamp
$ vagrant destroy # Tear it down and customize.
```

In the project directory you'll find `bootstrap.bash`. At the top there are some configurable parameters that you can tune-in if you like. You may also want to tweak the `Vagrantfile` for the project; e.g., to change the `config.vm.hostname` or `config.landrush.tld`. Enjoy! <i class="fa fa-smile-o"></i>

```bash
$ vagrant up # Bring it back up after you are done customizing.
```