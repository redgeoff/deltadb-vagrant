# deltadb-vagrant

Install Vagrant, VirtualBox and git
---
* http://www.vagrantup.com
* https://www.virtualbox.org (don't worry about setting up any VMs as the steps below will cover this)
* http://git-scm.com


Set Up DeltaDB
---
    $ git clone https://github.com/delta-db/deltadb-vagrant.git
    $ cd deltadb-vagrant
    $ vagrant up
    $ vagrant ssh
    $ cd /vagrant/app
    $ git clone https://github.com/delta-db/deltadb-server.git
    $ cd deltadb-server
    $ cp config-default.js config.js
    $ npm install



Launching VM & Testing
---
    $ cd deltadb-vagrant
    $ vagrant up
    $ vagrant ssh
    $ cd /vagrant/app/deltadb-server
    
and then to test in node
    
    $ npm run test-node
    
or, to test in the browser

    $ npm run test-phantomjs
    
or, you can test with a browser on your *host* machine

    $ npm run dev
    Run a browser such as Firefox or Chrome and go to http://127.0.0.1:8001/test/index.html
    
Unfortunately, [watchify doesn't work in the VM](http://stackoverflow.com/questions/27619248/watchify-update-event-never-fires) so you either need to use `touch` in the VM on files that you change or rerun `npm run dev` each time you change a file.

Launch psql
---
    $ vagrant ssh
    $ sudo -u postgres psql
