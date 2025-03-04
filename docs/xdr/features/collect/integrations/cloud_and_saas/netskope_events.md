uuid: de9ca004-991e-4f5c-89c5-e075f3fb3216
name: Netskope Events
type: intake


## Overview

[Netskope](https://www.netskope.com/) is a cybersecurity company that provides solutions to protect data in cloud apps and network security while applying zero trust principles.

This integration will collect events from your netskope's tenant to monitor authentications and activities in your Cloud applications.

!!! warning
    This format is still in beta, please use it wisely.


{!_shared_content/operations_center/detection/generated/suggested_rules_de9ca004-991e-4f5c-89c5-e075f3fb3216_do_not_edit_manually.md!}

{!_shared_content/operations_center/integrations/generated/netskope-events_do_not_edit_manually.md!}

## Configure

This setup guide will lead you into forwarding netskope's events to SEKOIA.IO.

### Generate API token

Please follow [this guide](https://docs.netskope.com/en/rest-api-v2-overview-312207.html) to create an API token.

### Create the intake in SEKOIA.IO

Go to the [intake page](https://app.sekoia.io/operations/intakes) and create a new intake from the format `Netskope events`. Copy the intake key.

### Pull events

To start to pull events, you have to:

1. Go to the [playbooks page](https://app.sekoia.io/operations/playbooks) and create a new playbook with the [Fetch new events from Netskope](../../../automate/library/netskope.md) trigger
2. Set up the module configuration with the base URL of your Netskope instance. Set up the trigger configuration with the API token and the intake key
3. Start the playbook and enjoy your events

## Further Readings

- [Netskope documentation - create an API token](https://docs.netskope.com/en/rest-api-v2-overview-312207.html)
