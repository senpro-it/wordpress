# wordpress
Configuration snippet for NixOS to spin up a wordpress container using Podman.

## :tada: `Getting started`

Clone the repository into the directory `/srv/podman/wordpress`. The path can't be changed for now!

Add the following statement to your `imports = [];` in `configuration.nix` and do a `nixos-rebuild`:

```
/srv/podman/wordpress/default.nix {
  senpro.oci-containers.wordpress = {
    exampleSite = {
      traefik.fqdn = "<your-fqdn>";
      mariadb.password = "<your-mariadb-password>";
    };
  };
}
```

It it possible to deploy multiple instances on a machine by extending the set with additional entries of the same structure.
