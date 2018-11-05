# packstack-challenge
This is the repository for solving the challenge [packstack-vagrant](https://github.com/raserma/packstack-vagrant). 

On the markdown [file](decisions-taken.md), I will explain the important decisions that I had to take during the development of this project.

In a summary, the challenge consists of four main tasks:
 1. Bring openstack up using Packstack and Vagrant.
 1. Open an endpoint for public connections.
 1. Create an ansible project to orchestrate VMs creations / role to manage Openstack operations.
 1. Create a dynamic Ansible inventory.
 
Let's start it.

## Deploying Packstack using Vagrant 
