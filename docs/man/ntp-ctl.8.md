<!-- ---
title: NTP-CTL(8) ntpd-rs 0.3.6 | ntpd-rs
--- -->

# NAME

`ntp-ctl` - management client for the ntpd-rs ntp-daemon process

# SYNOPSIS

`ntp-ctl` validate [`-c` *path*] \
`ntp-ctl` status [`-f` *format*] [`-c` *path*] [`-o` *path*] \
`ntp-ctl` `-h` \
`ntp-ctl` `-v`

# DESCRIPTION

The `ntp-ctl` management client allows management of some aspects of the
ntpd-rs daemon. Currently the management client only allows displaying the
current status of the daemon and validating a configuration file for usage
with the daemon.

# OPTIONS

`-c` *path*, `--config`=*path*
:   Path to the configuration file from which the observation socket address
    will be retrieved. If not specified this defaults to `/etc/ntp.toml`.

`-f` *format*, `--format`=*format*
:   The output format for the status command. If not specified this defaults to
    *plain*. Alternatively the format *prometheus* is available to display the
    output in an OpenMetrics/Prometheus compatible format.

`-h`, `--help`
:   Display usage instructions.

`-o` *path*, `--observation-socket`=*path*
:   Direct path to the observation unix socket where the client can connect to
    the ntp-daemon. If not specified the observation socket path is retrieved
    from the configuration file.

`-v`, `--version`
:   Display version information.

# COMMANDS

`validate`
:   Checks if the configuration specified (or `/etc/ntp.toml` by default) is
    valid.

`status`
:   Returns status information about the current state of the ntp-daemon that
    the client connects to.

# SEE ALSO

[ntp-daemon(8)](ntp-daemon.8.md),
[ntp-metrics-exporter(8)](ntp-metrics-exporter.8.md),
[ntp.toml(5)](ntp.toml.5.md)