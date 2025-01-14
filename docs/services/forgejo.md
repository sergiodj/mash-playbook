# Forgejo

[Forgejo](https://forgejo.org/) is a painless self-hosted Git service, an alternative fork to [Gitea](https://gitea.io/) (that this playbook also [supports](gitea.md)).


## Dependencies

This service requires the following other services:

- a [Postgres](postgres.md) database
- a [Traefik](traefik.md) reverse-proxy server


## Configuration

To enable this service, add the following configuration to your `vars.yml` file and re-run the [installation](../installing.md) process:

```yaml
########################################################################
#                                                                      #
# forgejo                                                              #
#                                                                      #
########################################################################

forgejo_enabled: true

# Forgejo uses port 22 by default.
# We recommend that you move your regular SSH server to another port,
# and stick to this default.
#
# If you wish to use another port, uncomment the variable below
# and adjust the port as you see fit.
# forgejo_ssh_port: 222

forgejo_hostname: mash.example.com
forgejo_path_prefix: /forgejo

########################################################################
#                                                                      #
# /forgejo                                                             #
#                                                                      #
########################################################################
```

In the example configuration above, we configure the service to be hosted at `https://mash.example.com/forgejo`.

You can remove the `forgejo_path_prefix` variable definition, to make it default to `/`, so that the service is served at `https://mash.example.com/`.


## Usage

After installation, you should be able to access your new Forgejo instance at the configured URL (see above).

Going there, you'll be taken to the initial setup wizard, which will let you assign some paswords and other configuration.


## Recommended other services

You may also wish to look into [Woodpecker CI](woodpecker-ci.md), which can integrate nicely with Forgejo.
