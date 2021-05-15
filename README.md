# Ansible Role Hetzner DNS
Manages DNS records with [Hetzner DNS Public API](https://dns.hetzner.com/api-docs)

## Role Variables

- `hetzner_dns_api_token`
the API token for authorizing access

- `hetzner_dns_zone_name`
the name of the zone (the domain)

- `hetzner_dns_record_name`
the name for the dns record (typically the subdomain)

- `hetzner_dns_record_type`: "A"
the type for the dns record

- `hetzner_dns_record_value`
the value for the dns record (typically the ipv4 address)

- `hetzner_dns_record_ttl`: 600
the ttl for the dns record


## Create or update
The dns record is identified by
- `hetzner_dns_api_token`
- `hetzner_dns_zone_name`
- `hetzner_dns_record_name`
- `hetzner_dns_record_type`

If the dns record is found, it will be updated, otherwise it will be created.