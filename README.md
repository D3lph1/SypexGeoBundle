# Modification of SypexGeoBundle requirements for Symfony 6

For the bundle documentation itself see the [original repository](https://github.com/yamilovs/SypexGeoBundle).

## Installation of fork

Change `composer.json`'s `minimum-stability` and `repositories` section:
```diff
{
+   "minimum-stability": "dev",
+   "repositories": [
+       {
+           "type": "vcs",
+           "url": "https://github.com/D3lph1/SypexGeoBundle.git"
+       },
+       {
+           "type": "vcs",
+           "url": "https://github.com/gam6itko/SypexGeo.git"
+       }
+   ]
}
```

Run command to install bundle:
```bash
composer require yamilovs/sypex-geo-bundle
```

Composer will install version from `dev-master` branch of this repository. It also will use [patch-1#e441244ef17bd6c602d11a2b1c3de7c04fda46ff](https://github.com/gam6itko/SypexGeo/commit/e441244ef17bd6c602d11a2b1c3de7c04fda46ff) version (enables PHP 8+ support) of [yamilovs/sypex-geo](https://github.com/yamilovs/SypexGeo).

## Configuration

Do not forget to create configuration file `config/packages/yamilovs_sypex_geo.yaml` with the following content:

```yaml
yamilovs_sypex_geo:
    mode: FILE # FILE (default) | BATCH | MEMORY
    database_path: "%kernel.project_dir%/var/sypex_geo_database/sx_geo_city.dat"
```
