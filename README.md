# collections
Network collections redirection

Steps to test:
1) Update routing.yml in `lib/ansible/config/rotuing.yml`

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


2) Clone the repository

```
git clone https://github.com/ganeshrn/network_collections.git
cd network_collections
```

3) Update inventory file

4) Run test (failing)

```
ansible-playbook redirect_test_failing.yml -vvvvv
```

5) Run test (working)

```
ansible-playbook redirect_test_working.yml -vvvvv
```
