uuid: eb727929-6a06-4e68-a09d-cf0e5daf3ccd
name: Postfix
type: intake

## Overview
Postfix is a free and open-source mail transfer agent that routes and delivers electronic mail.


{!_shared_content/operations_center/detection/generated/suggested_rules_eb727929-6a06-4e68-a09d-cf0e5daf3ccd_do_not_edit_manually.md!}

{!_shared_content/operations_center/integrations/generated/paloalto_do_not_edit_manually.md!}

## Configure

As of now, the main solution to collect POstfix logs leverages the Rsyslog recipe. Please share your experiences with other recipes by editing this documentation.

### Rsyslog

Please refer to the documentation of Postfix to forward events to your rsyslog server. The reader can consult the [Rsyslog Transport](../../../ingestion_methods/rsyslog/) documentation to forward these logs to SEKOIA.IO.
