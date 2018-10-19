[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = ISALAH89.SG
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d 0h 0m 0s
 forwardable = true
 renewable = true

[realms]
 ISALAH89.SG = {
  kdc = im1.imenedomain
  admin_server = im1.imenedomain
 }

[domain_realm]
 .imenedomain = ISALAH89.SG
 imenedomain = ISALAH89.SG
