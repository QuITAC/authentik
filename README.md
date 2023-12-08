# authentik_docker

Docker compose files and Config for [Authentik](https://goauthentik.io/).

The final service should run on `sso.queerreferat.ac`

## Notes

* When freshly installing a new instance you need to populate the .env file as per <https://goauthentik.io/docs/installation/docker-compose>. A dummy .env is provided in `template.env`
* The mail setup is taken from <https://help.itc.rwth-aachen.de/service/1jefzdccuvuch/article/4751eb1afce9413187dd60ab9ce1c711/>
  * startls means tls is true and ssl is false in the env file. port is 587 and server @ mail.rwth-aachen.de
  * credentials are in the list.
