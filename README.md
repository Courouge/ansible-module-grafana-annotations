# Ansible module grafana_annotations

Publish annotations in grafana from ansible playbooks/roles.

# Examples

```
- name: Create a global annotation without time information
  grafana_annotations:
    addr: "127.0.0.1:3000"
    user: "ansible"
    passwd: "ansible"
    text: "This is an annotation with automatic time value"

- name: Create a global annotation with time annotation
  grafana_annotations:
    addr: "127.0.0.1:3000"
    user: "ansible"
    passwd: "ansible"
    time: 1514822276
    text: "This is an annotation explicitly set at 1514822276"

- name: Test idempotence on region annotation
  grafana_annotations:
    addr: "127.0.0.1:3000"
    user: "ansible"
    passwd: "ansible"
    time: 1514822276
    timeEnd: 1514830000
    text: "This is a global region annotation"
```

# Advices

* Do not use the admin user to plublish your annotations.
  Create a dedicated user for ansible.
* Store the password in an ansible vault to avoid use of password in clear in the playbooks. 
