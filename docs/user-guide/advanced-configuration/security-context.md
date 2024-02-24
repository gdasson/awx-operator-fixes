#### Service Account

It is possible to modify some `SecurityContext` properties of the various deployments and stateful sets if needed.

| Name                               | Description                                                          | Default |
| ---------------------------------- | -------------------------------------------------------------------- | ------- |
| security_context_settings          | Pod Level SecurityContext for Task and Web deployments               | {}      |
| postgres_security_context_settings | SecurityContext for Task and Web deployments                         | {}      |
| web_security_context_settings      | Container Level SecurityContext for Web deployment                   | {}      |
| redis_security_context_settings    | Redis Container Level SecurityContext for Task and Web deployments   | {}      |
| rsyslog_security_context_settings  | Rsyslog Container Level SecurityContext for Task and Web deployments | {}      |
| ee_security_context_settings       | EE Container Level SecurityContext for Task deployments              | {}      |
| task_security_context_settings     | Container Level SecurityContext for Task deployment                  | {}      |
| init_security_context_settings     | Init Container Level SecurityContext for Task and Web deployments    | {}      |


Example configuration securityContext for the Task and Web deployments:

```yaml
spec:
  security_context_settings:
    allowPrivilegeEscalation: false
    capabilities:
        drop:
        - ALL
```


```yaml
spec:
  postgres_security_context_settings:
    runAsNonRoot: true
```
