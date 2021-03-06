# Katello-backup-restore-test #
For testing of foreman-maintain [backup/restore](https://github.com/theforeman/foreman_maintain)

## Prerequisites ##
- Ansible 2.5+
- A production Katello instance (latest version)

## Quick Setup ##
*Its a good idea to snapshot your machine before running tests, you can always revert it to have a clean environment*
1. on the system you are running the machine, copy your ssh key to the katello system: `ssh-copy-id root@<katello_machine>`
2. `cp inventory.sample inventory` and add the ip of the katello system under `[katello]` and the ip of the foreman-proxy under `[foreman-proxy]`.
3. Update the inventory file with the pr number you want to test using `pr_number`. If you want to test the master branch, change `use_master_branch` to `True` (This will override the pr_number)
4. run `ansible-playbook test-backup-restore.yml`
