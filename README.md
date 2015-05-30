## Sensu-Plugins-php-fpm

[![Build Status](https://travis-ci.org/sensu-plugins/sensu-plugins-php-fpm.svg?branch=master)](https://travis-ci.org/sensu-plugins/sensu-plugins-php-fpm)
[![Gem Version](https://badge.fury.io/rb/sensu-plugins-php-fpm.svg)](http://badge.fury.io/rb/sensu-plugins-php-fpm)
[![Code Climate](https://codeclimate.com/github/sensu-plugins/sensu-plugins-php-fpm/badges/gpa.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-php-fpm)
[![Test Coverage](https://codeclimate.com/github/sensu-plugins/sensu-plugins-php-fpm/badges/coverage.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-php-fpm)
[![Dependency Status](https://gemnasium.com/sensu-plugins/sensu-plugins-php-fpm.svg)](https://gemnasium.com/sensu-plugins/sensu-plugins-php-fpm)
[![Codeship Status for sensu-plugins/sensu-plugins-php-fpm](https://codeship.com/projects/427ed6d0-dc04-0132-8e5a-1e3fe125131b/status?branch=master)](https://codeship.com/projects/79856)

## Functionality

## Files
 * bin/check-php-fpm.rb
 * bin/metrics-php-fpm.rb

## Usage

This check use a nginx config in default vhost like :

```
set $pool "www-data";
if ($arg_pool) {
  set $pool $arg_pool;
}
location ~ "/fpm-(status|ping)" {
  include       /etc/nginx/fastcgi_params;
  fastcgi_pass  unix:/var/run/php-$pool.sock;
  fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
  access_log off;
  allow 127.0.0.1;
  deny all;
}
```

## Installation

[Installation and Setup](https://github.com/sensu-plugins/documentation/blob/master/user_docs/installation_instructions.md)

## Notes
