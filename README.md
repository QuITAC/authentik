# Authentik docker web service for Queerreferat Aachen
Authentik, a service that provides user management and Single Sign-On should be
accessible at `sso.queerreferat.ac`.

## Deploy
To deploy Authentik, make sure the Traefik reverse proxy is already running.
Then simply run
```
chmod +x ./startup.sh
./startup.sh
```
Additionally, a lot of configuration needs to be performered within the UI (as a
next step we try to automate this):
- Setup Nextcloud using [this guide](https://goauthentik.io/integrations/services/nextcloud/)
- To apply the Queerreferat Aachen Branding
  - navigate to `System -> Tenants` and set
    - `Title` to `Queerreferat Aachen`
    - `Logo` to `/static/dist/custom_assets/logo.png`
    - `Favicon` to `/static/dist/custom_assets/favicon.ico`
  - navigate to `Flows and Stages -> Flows`. Edit each flow and upload the a
    background image. There are efforts to also make this a global settings,
    let's hope the best.

## Notes
- When freshly installing a new instance you need to populate the .env file as
  described [here](https://goauthentik.io/docs/installation/docker-compose). A
  dummy .env is provided in `template.env`
- The mail setup is taken from [here](https://help.itc.rwth-aachen.de/service/1jefzdccuvuch/article/4751eb1afce9413187dd60ab9ce1c711/)
  - `startls` means `tls` is `true` and `ssl` is `false` in the `template.env`
    file. `port` is `587` and `server` is `mail.rwth-aachen.de
  - credentials are in the list.
