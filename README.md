A role to setup letsencrypt SSL certificates on a server. Uses Cloudflare DNS as authorization method. 


## Example playbook:

* Replace dns_cloudflare_api_token.
* The example shows 3 FQDNs that SSL certificates will be requested for. These will be created in /etc/letsencrypt/live/ directory.

```
- hosts: server.example.com
  become: true
  remote_user: ansible
  gather_facts: no
  vars:
    dns_cloudflare_api_token: <CLOUDFLARE_API_TOKE>
    cloudflare_email: cloud-admin@example.com
    letsencrypt_domains:
      - webserver-1.example.com
      - webserver-2.example.com
      - another-server.example.com

  roles:
    - letsencrypt-cloudflare

```


