# ERPNext for Gavety

Based on `pwd.yml` from https://github.com/frappe/frappe_docker (ERPNext v16.53.0).

Changes from upstream:
- the Administrator and database passwords come from Gavety (`gavety.yaml`) instead of the fixed `admin`
- the long-running services restart after a reboot (the `on-failure` blocks were removed)
- the two one-time setup jobs (`configurator`, `create-site`) still run once

Deploy from Gavety's Custom Deployment tab, port 8080.
The first start creates the site and can take 10 minutes or more on a Raspberry Pi.
Watch it with: `docker logs -f <app>-create-site-1`.
Log in as `Administrator`. The password is the app's `ERP_ADMIN_PASSWORD` setting.
Open it with "Open on its own address" (home network): ERPNext cannot live under a sub-path.
