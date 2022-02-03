# Ansible Role Certbot automated renewal

configure certbot automated renewal

The role assumes the directories

- `/etc/letsencrypt/renewal-hooks/post/`

## Role Variables

| group | variable | default | description |
| --- | --- | --- | --- |
| cron | `certbot_automated_renewal_cron_hour` | `0,12` | the schedule hour |
| cron | `certbot_automated_renewal_cron_minute` | `0` | the schedule minute |
| hooks | `certbot_automated_renewal_post_renewal_hooks` | `[]` | the list of post renewal hooks as list of dicts `certbot_automated_renewal_post_renewal_hook` |

```yaml
  - file_name: systemctl_restart_nginx.sh
    file_content: |
      #!/bin/sh
      systemctl restart nginx
```

| dict | element | default | description |
| --- | --- | --- | --- |
| `certbot_automated_renewal_post_renewal_hook` | `file_name` | | the name for the hook script |
| `certbot_automated_renewal_post_renewal_hook` | `file_content` | | the content for the hook script |
