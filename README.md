# ans-sat-patch
ans-sat-patch

Simple patching playbooks for Satellite.  These playbooks talk to Satellite API or use the Satellite Ansible Collection to talk to the Satellite to kick off a patching job rather than using the yum module.

Under the vars/sat.yml there is an ansible-vault encrypted file in the following format: 

```
sat_host: https://sat611.lab.example.com
sat_user: sat-ans-user
sat_pass: SuperSecretPassword!
```

Update this file as per your requirements and encypt with your own password:

```
ansible-vault encrypt vars/sat.yml
```

To Run the playbook:

```
ansible-playbook --ask-vault-pass playbooks/patch.yml -e host_to_patch=rhel8-katello.lab.example.com
```
