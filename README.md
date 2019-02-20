Ansible - HPNA SOAP Snapshot
=========

This role sends sends snapshot requests to HPNA via the SOAP API. Once the request is received and queued, HPNA sends back a Task ID which is then monitored by the role until the task reports back a "completeDate".

Requirements
------------

Ansible.

Role Variables
--------------

`HPNA_USER` = Your service account username for HPNA

`HPNA_PASS` = Your service account password for HPNA

`HPNA_API_URL` = What enpoint URL you wish to use. (There are multiples). `/hpna_snapshot/vars/main.yml`

Dependencies
------------

None

Example Playbook
----------------

```
 - hosts: all
   connection: local
   gather_facts: no
   vars_prompt:
    - name: "HPNA_USER"
      prompt: "Service Account Username?"
      private: no
    - name: "HPNA_PASS"
      prompt: "Service Account Password?"
      private: yes

   tasks:
    - import_role:
      name: hpna-snapshot
```

License
-------

BSD

Author Information
------------------

Andrew Grabbs

Andrew@AndrewGrabbs.com
