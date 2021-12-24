# Ansible Role Hetzner DNS
Manages DNS records with [Hetzner DNS Public API](https://dns.hetzner.com/api-docs)

Because the role is only using [ansible.builtin.uri](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/uri_module.html), [ansible.builtin.debug](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/debug_module.html) and [ansible.builtin.set_fact](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/set_fact_module.html)
it can be used with localhost.

## Role Variables

| group | variable | default | description |
| --- | --- | --- | --- |
| access | `dns_api_token` | | the API token for authorizing access |
| content | `dns_zone_name` | | the name of the zone (the domain) |
| content | `dns_record_name` | | the name for the dns record (typically the subdomain) |
| content | `dns_record_type` | `"A"` | the type for the dns record |
| content | `dns_record_value` | | the value for the dns record (typically the ipv4 address) |
| content | `dns_record_ttl` | `60` | the ttl for the dns record |
| control | `dns_record_delete` | `no` | if the record should be deleted instead of creating |
| control | `dns_debug` | `no` | if debug information should be printed |
| control | `dns_dry_run` | `no` | if a dry run with no changes should be executed |
| control | `dns_dry_run_fail` | `yes` | if a dry run (s. `dns_dry_run`) should fail, to prevent continuing CI |

## Create, delete or update
The dns record is identified by
- `dns_api_token`
- `dns_zone_name`
- `dns_record_name`
- `dns_record_type`

If the dns record is found, it will be updated, otherwise it will be created or deleted depending on `dns_record_delete`.