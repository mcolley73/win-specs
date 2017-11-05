## win-specs
A simple Ansible repository to build out a Windows 2012R2 instance in AWS with
an extra 4 mounted drives of specific sizes.

---

## Organization
Just two simple playbooks and two Ansible Roles.

### Playbooks
* `build-win-instance.yml` - Will create a Security Group and the Windows instance
* `get-instance-password.yml` - Will fetch the Administrator password of the new instance

### Roles
* `win-instance`
* `win-security-groups`

### Inventories
There is a Sandbox inventory included. Of note are the variables for the `target_vpc` and `target_subnet`,
among others, as it's left to the reader to create their own VPC and Subnet outside of this repo.

---

## Ansible devel
There was a bug in the `ec2_win_password` module when decrypting a Key Pair that had a null passphrase. This meant I needed a `devel` build, which had a fix for this issue.

```sh
$ sudo pip install git+https://github.com/ansible/ansible.git@devel
```
