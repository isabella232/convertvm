<!--
    This Source Code Form is subject to the terms of the Mozilla Public
    License, v. 2.0. If a copy of the MPL was not distributed with this
    file, You can obtain one at http://mozilla.org/MPL/2.0/.
-->

<!--
    Copyright (c) 2014, Joyent, Inc.
-->

# convertvm

This repository is part of the Joyent SmartDataCenter project (SDC).  For
contribution guidelines, issues, and general documentation, visit the main
[SDC](http://github.com/joyent/sdc) project page.


# NAME

convertvm - Convert VM images into Smart Datacenter dataset manifests.


# SYNOPSIS

    convertvm [-dhnouv] inputvm.ovf-directory


# DESCRIPTION

Virtual Machine images may be represented by various formats. `convertvm`
takes as input a VM (virtual machine) or VA (or virtual appliace) and can
output a binary dataset that can be imported into SDC (Smart Data Center).

`convertvm` accepts as input OVF (Open Virtualization Format) files. It
outputs a .dsmanifest and .zfs.bz2 file to the `output-directory` specified at
invocation.


# OPTIONS

## General options

    -a/--assets-url <assets-url>
         Set the location where this dataset's file will be available.
         (ie. http://10.99.99.6/datasets/)


## Dataset Override Options

    -n/--ds-manifest <name>
         (Mandatory): Set the dataset name. (ie. myvm)

    -o/--ds-os <os>
         (Mandatory): Set the dataset operating system. (ie. linux, windows, smartos, etc.)

    -v/--ds-version <version>
         Set the dataset version. (ie. 1.0.0)

    -d/--ds-description <description>
         Set the dataset description. Maximum of 256 characters.

    -N/--ds-nic-driver <pcnet|e1000|...>
         Set the nic driver.

    -D/--ds-disk-driver <virtio|ide|...>
         Set the dataset disk driver


# CAVEATS

- Only OVF-1.0 is supported.
- Only one VM per OVF file is supported.
- Only one Disk per OVF VM is supported.


# REFERENCES

- http://www.vmware.com/appliances/getting-started/learn/ovf.html
- http://www.dmtf.org/standards/published_documents/DSP0243_1.1.0.pdf

# LICENSE

MPL-2.0 (See LICENSE file)
