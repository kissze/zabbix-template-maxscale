# MariaDB MaxScale Zabbix template

The template is designed to monitor MariaDB MaxScale servers trough the HTTP API. The template needs to set url, access credentials via its macros.

Currently some basic elements are implemented, but improvements, additional metrics are welcome :)

## Setup

Install MaxScale server as specified in the documentation. (<https://mariadb.com/kb/en/mariadb-maxscale-2302-mariadb-maxscale-installation-guide/>)

Open firewall if any for the API service, its need to be reachable from the Zabbix server itself, because the monitoring is done via HTTP requests.

Create user for monitoring, for example 'zabbix' with the basic role in MaxAdmin (or CLI).

If MaxScale is prepared, then you can add the Template to the host, then you have to setup three macros:

- {$MAXSCALE_URL} - The URL of the admin API (for example: htts://mymaxscale1.company.com)
- {$MAXSCALE_USER} - The created API user
- {$MAXSCALE_PASS} - Password for the user
