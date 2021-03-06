# Add PROXY protocol support to Caddy

[![Build Status](https://travis-ci.org/mastercactapus/caddy-proxyprotocol.svg?branch=master)](https://travis-ci.org/mastercactapus/caddy-proxyprotocol)

## Syntax

```
proxyprotocol *cidr* ... {
    timeout *val*
}
```

- **cidr** CIDR ranges to process PROXY headers from
- **val** duration value (e.g. 5s, 1m)

The default timeout is `5s`. Set to `0` or `none` to disable the timeout.

## Examples

```
# Enable from any source 
proxyprotocol

# Enable from local subnet and fixed IP
proxyprotocol 10.22.0.0/16 10.23.0.1/32

# Set header timeout
proxyprotocol 10.22.0.0/16 10.23.0.1/32 {
    timeout 5s
}

```
