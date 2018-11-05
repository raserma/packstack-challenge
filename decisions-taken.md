# Decisions Taken on the challenge
This file describes the reasons why I decided to go on a specific direction.
I will try to collect only the important choices taken. I have four evenings
to finish the challenge, therefore time is a constant to take into account.


Once that I got the challenge from Richard, I started studying the tasks and
requirements. We need to use Vagrant to deploy Openstack with POC tool called
Packstack. I never used it before but I have had used DevStack so I guessed
it would be similar. 
An ansible project must be created, with a role to automate openstack 
operations and a playbook to orchestrate VMs creation. Input to these ops must
be on YAML format.
Finally, I need to create a dynamic inventory in ansible to query environment
information and group VMs based on attributes.

## Decision 00
Before to start deploying anything, I check the files of the project:
 - Vagrantfile: recipe used by Vagrant to spin Centos up and execute Packstack.
 - answers.txt: recipe used by Packstack to spin OST environment up.

Going through the Vagrantfile, on line #31, packstack needs answers.txt, and 
this file is not added anywhere on the Vagrantfile, Vagrant will fail.

Going through answers.txt, on line #32, Nova component appears as "n", which
means that will not be installed. This is definitely the second step fix.

## Decision 01
 * Git workflow to use: on the first steps, I will be commiting and pushing
on the master branch, as it is easier and faster for me. There is no CI in
place nor collaboration with other people needed. Therefore, I have taken
the decision to only push to `master` for now. If situation changes, I will
adapt.

## Decision 02
 * Install pre-commit githook: I am going to be working with Ansible a lot, 
therefore I want to be sure that my code is Lint compliant and syntax clean. 
I could set a .travis.yml file for that but I have not used Travis before and
it is too much work for the same results. Also, I am not collaborating with
anyone so integration is not much needed at this point.
For that, I installed a pre-commit hook on the repository, so it is triggered 
before commiting a change. 

## Decision 03
 * Add infrastructure tests: I am going to use Ansible to modify the state
of OST environment, therefore I need to test the infrastructure deployments.
I am not sure yet which tool/platform to use for this matters as I am not very
familiart with OST. Also, it is not a mandatory task, so I will not waste all 
my time here. Something simple and effective should work.

