# windows_disable_ipv6

[![Build Status](https://travis-ci.org/martezr/puppet-windows_disable_ipv6.svg?branch=master)](https://travis-ci.org/martezr/puppet-windows_disable_ipv6)

#### Table of Contents

1. [Description](#description)
2. [Setup - The basics of getting started with windows_disable_ipv6](#setup)
    * [What windows_disable_ipv6 affects](#what-windows_disable_ipv6-affects)
    * [Setup requirements](#setup-requirements)
    * [Beginning with windows_disable_ipv6](#beginning-with-windows_disable_ipv6)
3. [Usage - Configuration options and additional functionality](#usage)
4. [Reference - An under-the-hood peek at what the module is doing and how](#reference)
5. [Limitations - OS compatibility, etc.](#limitations)
6. [Development - Guide for contributing to the module](#development)

## Description

The windows_disable_ipv6 module disables IPv6 networking on Windows based operating systems.

## Setup

### Requirements

* N/A

### Installation

```puppet
puppet module install martezr-windows_disable_ipv6
```

### Beginning with windows_disable_ipv6

To perform a basic windows_disable_ipv6 deployment, declare the windows_disable_ipv6 class.

```puppet
include windows_disable_ipv6
```

## Usage

### Disable IPv6 networking and restart

```puppet
class { 'windows_disable_ipv6':
  ipv6_disable => true,
  ipv6_reboot  => true,
}
```

### Basic install using hiera

```yaml
windows_disable_ipv6::ipv6_disable: true
windows_disable_ipv6::ipv6_reboot: true
```

## Reference

The windows_disable_ipv6 module comes with a number of options to interface with the system to disable IPv6.

**Classes:**

* windows_disable_ipv6: The main class

###Parameters

### `ipv6_disable`

Disables the IPv6 network protocol. Valid options: boolean. Default: 'false'.

### `ipv6_reboot`

Reboot the machine after the ipv6_disable setting has been changed in order for the setting to take effect.
Valid options: boolean. Default: 'false'.

## Limitations

Currently, the windows_disable_ipv6 module is tested to work on the following operating systems:

 * Windows Server 2008
 * Windows Server 2008 R2
 * Windows Server 2012
 * Windows Server 2012 R2

## Development

Contributions to the module are welcome and appreciated. The following guidelines are required
for any code to be merged.

* All code must have corresponding rspec tests where possible.
* Any additional variables or classes that are added must be documented in the readme.
* All TravisCI tests must pass.
