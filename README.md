# packstack-challenge
This is the repository for solving the challenge [packstack-vagrant](https://github.com/raserma/packstack-vagrant). 

On the markdown [file](decisions-taken.md), I will explain the important decisions that I had to take during the development of this project.

In a summary, the challenge consists of four main tasks:
 1. Bring openstack up using Packstack and Vagrant.
 1. Open endpoints for public connections.
 1. Create an ansible project to orchestrate VMs creations / role to manage Openstack operations.
 1. Create a dynamic Ansible inventory.
 
Let's start it.

## Status
 * Task 1: done.
 * Task 2: done.
 * Task 3: done
 * Task 4: done (**but there is no connectivity with the instances**)
 * Task 5: 
    * 1 st part: done ("cheating")
    * 2 nd part: not done (maybe theoretically)
 * Infrastructure tests: not done 

## Simulate environment
If you want to set up my own environment, you can do so by:

### Task 1, 2 and 3
   `$ git clone https://github.com/raserma/packstack-challenge.git`

   `$ cd packstack-challenge/packstack-vagrant`

   `$ vagrant up` 
   
   `$ vagrant ssh`

   `$ cd /vagrant/ `
   
### Task 4
Download openrc.sh file and:

   `$ chmod +x admin-openrc.sh && source admin-openrc.sh` 

   `$ cd ansible/ && ansible-playbook site.yml`

will execute playbook and provision the stack.

### Task 5
In order to query VM specs, you can use `openstack_inventory.py`:

List all the hosts with all metadata:

    `$ ./openstack_inventory.py --list`

Or list all the data for a specific host:

    `$ ./openstack_inventory.py --host <hostname>`

## How to orchestrate creation of VMs
You can define how many VMs you want and what resources they have by specifying
everything on file `ansible/vars.yml`. It is not the most effective way of
doing it, as you need to repeat the data many times. 

## Lessons learned
A lot of lessons learned with this simple exercise. From my local development
environment, Vagrant and Openstack & Ansible relationship. It feels like a 
failure but I guess the only way to learn is by failing. 

A lot of things I would do totally different if I had the opportunity.  
