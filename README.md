# Plesk Onyx Custom Template for Shopware with nginx/FPM - incl. Stageware Support.

This is a plesk onyx nginx conf template adaption of bcremer nginx configuration setup.

## Reference: NGINX Shopware configuration by bcremer
[https://github.com/bcremer/shopware-with-nginx](https://github.com/bcremer/shopware-with-nginx)

## Customization
- Added WebP Support - static files
- Added woff2 Support - cache
- Refactor nginx location configuration to match custom theme fonts - regex
- Fixed issue with Shopware One-File Installer / initial Shopware installation
- Fixed issue with Shopware Updates via Backend (404 not found)
- Added Support for Stageware by TC-Innovations

## Tested on
- Plesk Onyx 17.8.11
- CentOS 7.6

## How to use

First of all: **YOU NEED ROOT ACCESS**  
If you have for example a managed VPS or a Managed Server without root access you need to contact your hoster support for help.

```bash
cd /usr/local/psa/admin/conf/templates/
mkdir custom
cd ./custom
```

```bash
git clone https://github.com/AIXPRO/plesk-onyx-nginx-shopware-with-stageware-support.git ./
```

In case you want to use wget or curl instead of git:
```bash
cd /tmp
```
```bash
wget -O - https://github.com/AIXPRO/plesk-onyx-nginx-shopware-with-stageware-support/tarball/master | tar xz
```
```bash
curl -L https://github.com/AIXPRO/plesk-onyx-nginx-shopware-with-stageware-support/tarball/master | tar xz
```
```bash
cd AIXPRO/plesk-onyx-nginx-shopware-with-stageware-support-*
cp -r ./domain /usr/local/psa/admin/conf/templates/custom/
```

Templates placed in /usr/local/psa/admin/conf/templates/custom/ overrides templates in /usr/local/psa/admin/conf/templates/default/.

Of course the additional nginx directives can still be used.

## Plesk panel - activate custom template

The custom template is triggered by ***Index Files*** and ***Proxy mode*** configuration under **Apache & nginx Settings**.
Just add ***shopware.php*** and uncheck ***Proxy mode*** to activate custom template blocks.

![Index Files config](plesk-panel-screenshot-01.png?raw=true)
![Index Files config](plesk-panel-screenshot-02.png?raw=true)
