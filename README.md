# collections
Network collections redirection

Steps to test:
1) (optional) Update routing.yml in `lib/ansible/config/rotuing.yml` (only to test redirection in ansible core)

```
plugin_routing:
  connection:
    network_cli:
      redirect: ansible.netcommon.network_cli
    persistent:
      redirect: ansible.netcommon.persistent
  terminal:
    eos:
      redirect: arista.eos.eos
  cliconf:
    eos:
      redirect: arista.eos.eos
  modules:
    eos_new_command:
      redirect: arista.eos.eos_new_command
    eos_acl_interfaces:
      redirect: arista.eos.eos_acl_interfaces
```


2) Install paramiko

```
pip3 install paramiko
```


3) Clone the repository

```
git clone https://github.com/ganeshrn/network_collections.git
cd network_collections
```

4) Update inventory file

5) Run test (failing)

```
ansible-playbook redirect_test_failing.yml -vvvvv
```

6) Run test (working)

```
ansible-playbook redirect_test_working.yml -vvvvv
```
