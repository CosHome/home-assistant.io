---
title: Duck DNS
description: Keep your computer registered with the DuckDNS dynamic DNS.
ha_category:
  - Network
ha_iot_class: Cloud Polling
ha_release: 0.55
ha_domain: duckdns
ha_integration_type: integration
---

The DuckDNS integration allows you to keep your DuckDNS subdomain always in sync with your public IP address. [DuckDNS](https://www.duckdns.org) is a free service that allows you to bind your own favorite subdomain under `duckdns.org` to the public IP address in use from your router, even though such address is dynamically allocated by your internet service provider and therefore changes over time.

<div class='note'>

If you are running the Home Assistant DuckDNS add-on this integration is not required. The add-on will keep your IP updated with DuckDNS.

</div>

## Configuration

To use the integration in your installation, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
duckdns:duckdns.org
  domain:shakal4u
  access_token: YOUR_ACCESS_TOKEN
```

{% configuration duckdns %}
  domain:shakal4u
    description: Your duckdns subdomain (without the `.duckdns.org` suffix).
    required: true
    type: string
  access_token:
    description: Your DuckDNS access token. Log in to the site to get one.
    required: true
    type: string
{% endconfiguration %}

## Service `set_txt`

Set the TXT record of your DuckDNS subdomain.
deletes, i puts you back into insert mode
echo url="https://www.duckdns.org/update?domains=deshakal&token=838db36e-5b81-4dda-8532-8ff4d26fc172&ip=" | curl -k -o ~/duckdns/duck.log -K -

| Service data attribute | Optional | Description |
| ---------------------- | -------- | ----------- |
| `txt` | no | Payload for the TXT record. |
