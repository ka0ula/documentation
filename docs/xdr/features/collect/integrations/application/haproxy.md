uuid: ff1873e7-8757-4b1a-b0ca-b33f9b27f3d9
name: HAProxy
type: intake

## Overview
HAProxy is a free, open source software that provides a high availability load balancer and proxy server for TCP and HTTP-based applications that spreads requests across multiple servers. HAProxy has a lot of features and because it is located between your infrastructure and your clients, it can give you a lot of information about either of them.

{!_shared_content/operations_center/detection/generated/suggested_rules_ff1873e7-8757-4b1a-b0ca-b33f9b27f3d9_do_not_edit_manually.md!}

{!_shared_content/operations_center/integrations/generated/haproxy_do_not_edit_manually.md!}

## Configure
As of now, the main solution to collect HAProxy logs leverages the Rsyslog recipe. Please share your experiences with other recipes by editing this documentation.

### Rsyslog

The reader is invited to consult the [Rsyslog Transport](../../../ingestion_methods/rsyslog/) documentation to forward these logs to SEKOIA.IO.

## Further Reading
- [HAProxy Official Documentation](http://www.haproxy.org/#docs)
