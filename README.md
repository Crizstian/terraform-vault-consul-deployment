# Veridian Dynamics

<img src="http://www.veridian-dynamics.org/image/logo.png" width="300"><br>
<img src="https://www.digitalonus.com/wp-content/uploads/2019/06/digital_on_us_logo.png" width="300"><br>
<img src="https://cdn.worldvectorlogo.com/logos/hashicorp.svg" width="150">
<br><br>
[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Documentation Sections

### Provisioning and Architecture

| Asset Name | Region 
| ------ | ------ |
| Primary Cluster | us-east-2 | 
| PR Cluster 1 | us-west-1 | 
| PR Cluster 2 | eu-central-1 | 
| DR Cluster 1 | eu-west-1 |
| DR Cluster 2 | ap-southeast-1 |

From an architectural viewpoint us-east-1 was discarded as the primary region and the most practical decision was to use us-east-2.

### Basic Accsess Catalog

| Asset Name | IP/Hostname
| ------ | ------ 
| Flask App | http://18.228.155.206:8000/ |


### Vault Auto-Unseal with AWS KMS / Vault initialization

```
$ vault operator init -recovery-pgp-keys=keybase:cramirez92,keybase:arielazem,keybase:richp -recovery-shares=3 -recovery-threshold=3

Recovery Key 1: wcFMA9eitC21gF+DARAAC1y8eq/GL1NvyQtEsUpB3Zz/YvVDTBU/4dP1aku7CJdmYqdNJlGS12p1wuOUP2SqiQaK6tnF519q+kH4aW5NcgL0AAbDI6dKeOUno8LZ8GC0/qKQW58tLqHHPi2rVmEeBxQKE/mZ1Y6vsMj/Rlt/gGuEk1iCVkvAkC7Tm8TaFuvgOo7RQSGBsFZCHq+xxsDtnCWYeluMEY4KCqR0x/LqioFsCuR+5GqqLMI4xIBip2u1wsanWZXo5puJvc5x1EzbOcBCJ5rSt9l3w/vE//yJdWz985+kGqVJtcFfee1N5vyr/tY9S54BKU/5GQVcXCzwaq/R/DVo2Yf0gUh8CRAkaA1D7OwE3SVJmt7F7PHJRCLf3HGei97onbz2XMrUrHH2qN3/Ry9fZrhCrvl6b2XeECbxYpt0wiUQMt+2Y3OK1B6LfmCMZP4FhtnPChkNZGZz9BObY0ubhCwz7082hOJ9EOTsYNqCUtDM0BZ/bWgskm6KNqWh/8iEIGKTpptGIH7tVFiVw7LHnmUqwlkwv4MHKWbS9o4NTH0vROzEhumH5joEfLZ5X2altlYR3Yphbbzrn7RHOa6qHZdniIQ7Q0Yh3hXwnuDEqy0oVomzDJB7X9sCgnKK5dLzN35mguwxQdrdu+p/Nr7cea985LCzmyTCZkXoRphTCN0VfiqMq0AM8czS4AHkP8HeJONuTd9NwVJpFdgwW+HPzuCK4MjhEmXgzuKVbXIW4DfmP9p6Fdq+BAW6Uy+eY9dlGD6o1Euu7dcXB08vZWcM2nXzDbmj8waZxZ3cyi8QX2RZzShu0Rb5ClIPpqykCZp70OCN4Tak4Kjk0q5jmMk7IHdvy9fhw9lE4+IwIX6o4fF2AA==
Recovery Key 2: wcFMA5p3UuqMCQ1fARAAiX7Z9ChEiiBE0XcABJAZBz1OZMpZORWdwW5rYQ75bKmWdlGlLagoOH410/aNzC/JpRqpvOFjjHHPVfP2m73D/47MKLpm5+XiYm3q98rluK5+O+T42jkhDSB6/fgFF1wjgX8ZZ0nVttCQ/voSWOvVgouo+zIhj6LBO0GEWm5PA/si/ktr06Vv8guVgVXfL6RBBNOSRfSfJ7VLXpGoLm+j96AUBrJFo3AQhnIsfJiJuPXmisHr/oDmz5GeeNjYlWVPKCsPLj3UM1Py6aACys7UGbhlWGr5SXNpWX5/gidS0VM6FGW06qceRVJ0/MmJSfApR4zWjMkbthM52PrCD1kNyy+2KIDsUFNaLf5R/Wbc43lNBaGTLuwXNo1hb8RyvBWHOBWrJgrkpiUnRhqwGxnRVk7YxO0GKIyV8JXoLJBHEvCI6sdNUskTRfB5tk63ZbhRcqUZR7RMcG3zswotc3QzG944WlHbABhTau2EtZJxxp0CagikmtfMiH99FVEgxzZRLTaOP3SY/+6bFSuljj29Ipe0vdepT6ZG0BO4GeDKwpDdnmn9/wmEoX1Z9Auvt+P8Lvkx3RFI8iuP0AEsa4Mp8BMOGYLj/3hIWWhzn4BrPt5/SeI+dD3G7bU2sqgFADBSTcIBLtud67KyZzAK/oAO1E6w5zh+x78IgGVYg3LQ6c7S4AHkqlcZP9XslpaGPDQTM3qKF+GJ8uAL4MThXkfgYeJOPEGv4IPmViS7kUQLH1QI54a54xrUtLvI7ybc2zKSpV7TIStqYzWZLkg+mHHVj2uJIsdaUJUV6GOMk5kPkhFP8ElhdmTmWOD/4eFW4LzkkaAFO+hR9BV/TU6XXQmrH+KnxJ4D4RgYAA==
Recovery Key 3: wcFMAzcRSDoJGe96ARAAe1wMXY5MusJTJD9uIW8olJDujpwawh1bTtAEZ5LVqiFNIcjNSdxbbAuaIU1CTVD9G+KzOzHpLC8w9Mj3yJwCrDhiDT1MpUOp7EhbGZOoEc+hufBs4ZV2oHyvXHGvYi6RtKifhF70YaIGovAsh4eepXQkBcJq85JjpRgLb1CkNUeQc425Sydqd+/ppbRdpwsPBVynk7Nkj1xqxU4D/CuIBAQtue6Y3V5k/bQR1SfXxAZ295OaZoyCSsSB9zSzJrOobLLQQAfAi6p5hKG72d6ScpA8K793DShB5OGhLEFQXqgXtLPz08BQGqmyeLpxonVyuJxJpGZCIlGhhQLn3v1dYhN+HKBkghoDhrGX1UQ7ydnQfqU75pQdSTWSMi1wDUXwMp5+3E/tjUQA7YPUf/Z9YcPCjeFxzNExqZcS14bEKTlmmkdLbO4Ks15z64j5ZuRKYR30JPMAKf9R4y6nzLM9J08dzA+5UT8KikBifeuj4g2ZY8L7IXiNWWEaIeucwNwfy8RAQIcDT211BDaNGtzi/G7UF5mDOwJWaNKqSVwNXN82QJaTTDFz5bhY8kI9IzPrB4xJBqb/pVCrJaUrJop3+rUFAkTTgxJP49kDc/lIcUNGlZakiv0AnHmKgYyqF3BD6E1alFqE8L2a37eeBOLqYsolN4FbU0m98yfjBy28Lw7S4AHkchUyN+/fSswTuSf6Pv050OGgvuAr4InhB0zgreJ41QgI4DbmBxM2P28jeDw9kHmGAsfAg/kreKx4MI0VbiZht6JMVmSb0b2nhQede1QS1yIE/zXLxgo4qiP1nLM3WLWcLx6lxeB54eL/4HXkS1Dq05rgrZxfNzgxge71LuL1PuK84ZJVAA==
Initial Root Token: s.0AvlBwJJQdIqPklj1ZH586jc
``

### Enabling Audit Log File device

```
vault audit enable syslog tag="vault" facility="LOCAL7"
Success! Enabled the syslog audit device at: syslog/
```

### Database Dynamic Secrets Configuration
Database Dynamic secrets were enabled in order to work with the flask application following the steps below, for the MySQL/MariaDB database.

Database secrets were enabled:
```sh
vault secrets enable database
```
MySQL database configuration:
```sh
vault write database/config/my-mysql-database \
    plugin_name=mysql-database-plugin \
    connection_url="foo:foobarbaz@tcp(terraform-20200206144544828600000005.ccj5pugkq6mw.sa-east-1.rds.amazonaws.com:3306)/" \
    allowed_roles="my-role"
```
Role Map configuration
```sh
vault write database/roles/my-role \
    db_name=my-mysql-database \
    creation_statements="CREATE USER '{{name}}'@'%' IDENTIFIED BY '{{password}}';GRANT SELECT ON *.* TO '{{name}}'@'%';" \
    default_ttl="1h" \
    max_ttl="24h"
```
Testing can be done with the next command
```sh
vault read database/creds/my-role
```

### Vault Agent Configuration
Enable App Role on Vault Cluster
```sh
vault auth enable approle
vault policy write token_update token_update.hcl
vault write auth/approle/role/apps policies="token_update"
vault read -format=json auth/approle/role/apps/role-id \
         | jq  -r '.data.role_id' > /opt/vault/config/roleID
vault write -f -format=json auth/approle/role/apps/secret-id \
         | jq -r '.data.secret_id' > /opt/vault/config/secretID
```
Policy (token_update.hcl)  
Define policy to allow token creation:
```sh
path "auth/token/create" {
  capabilities = ["update"]
}
path "database/creds/*" {
  capabilities = ["read"]
}
path "aws/creds/*" {
  capabilities = ["update", "read", "create"]
}
path "transit/+/orders" {
 capabilities = ["update", "read", "create", "delete"]
}
```
### Configure Vault Transit Engine
```sh
vault secrets enable transit
vault write -f transit/keys/orders
```

Modifications on flask app to support EaaS
```
sh
#!/bin/bash
command=$1
shift 1
text=$@
export VAULT_ADDR=http://localhost:8007
if [ $command = "encrypt" ]; then
   vault write -format=json transit/encrypt/my-key plaintext=`base64 <<< "$text"` |jq -r ".data.ciphertext"
else
   vault write -format=json transit/decrypt/my-key ciphertext=$text |jq -r ".data.plaintext"|base64 --decode
fi
```

### Configure Vault Agent
Config File (/opt/vault/config/agent-config.hcl)
```sh
xit_after_auth = false
pid_file = "./pidfile"
auto_auth {
   method "approle" {
       mount_path = "auth/approle"
       config = {
           role_id_file_path = "/opt/vault/config/roleID"
           secret_id_file_path = "/opt/vault/config/secretID"
           remove_secret_id_file_after_reading = false
       }
   }
   sink "file" {
       config = {
           path = "/opt/vault/config/approleToken"
       }
   }
}
cache {
    use_auto_auth_token = true
}

listener "tcp" {
  address = "0.0.0.0:8007"
}
vault {
   address = "http://internal-a3970b95-vault-lb-1327631726.sa-east-1.elb.amazonaws.com:8200"
}
# Consul Template block for database configuration
template {
  source      = "/opt/flask/mysqldbcreds.json.ctmpl"
  destination = "/opt/flask/mysqldbcreds.json"
}
# Consul Template block for s3 bucket configuration
template {
  source      = "/opt/flask/awscreds.json.ctmpl"
  destination = "/opt/flask/awscreds.json"
}
```

### Create ConsulTemplate
````
Template in /opt/flask/mysqldbcreds.json.ctmpl
{{ with secret "database/creds/my-role" }}
{
  "username": "{{ .Data.username }}",
  "password": "{{ .Data.password }}",
  "hostname": "terraform-20200206144544828600000005.ccj5pugkq6mw.sa-east-1.rds.amazonaws.com"
}
{{ end }}
````

### S3 Bucket Configuration
Consul Template awscreds.json.ctmpl
```sh
{{ with secret "aws/creds/my-role" }}
{
  "ACCESS_KEY": "{{ .Data.access_key }}",
  "SECRET_KEY": "{{ .Data.secret_key }}"
}
{{ end }}
```

### Run agent
```sh
vault agent -config=agent-config.hcl -log-level=debug
```
