
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Web logs` | Microsoft Azure Front Door act as a proxy and provide associated traffic logs |
| `Web application firewall logs` | Microsoft Azure Front Door protect web application with its web application firewall and provide associated traffic logs |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `network` |
| Type | `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "test_accesslog.json"

    ```json
	
    {
        "message": "{\"time\":\"2022-08-29T15:03:25.4715017Z\",\"resourceId\":\"/SUBSCRIPTIONS/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/RESOURCEGROUPS/YYYYYYYYYYYYYYYYY/PROVIDERS/MICROSOFT.CDN/PROFILES/ZZZZZZZZZZZZZZZ\",\"category\":\"FrontDoorAccessLog\",\"operationName\":\"Microsoft.Cdn/Profiles/AccessLog/Write\",\"properties\":{\"trackingReference\":\"0PdUMYwAAAAAA35SK7dpvSZxm/Y92xsH7UEFSMjAxMDgwMzg1MDQ5ADkxZjFmYTAyLWMzZGEtNDBlMi04ZWM2LWQ0OTQ1OWJiNzc5OQ==\",\"httpMethod\":\"GET\",\"httpVersion\":\"1.1.0.0\",\"requestUri\":\"http://example.1.azurefd.net:80/\",\"requestBytes\":\"109\",\"responseBytes\":\"221\",\"userAgent\":\"curl/7.77.0\",\"clientIp\":\"1.2.3.4\",\"socketIp\":\"1.2.3.4\",\"clientPort\":\"53170\",\"timeToFirstByte\":\"0.002\",\"timeTaken\":\"0.002\",\"requestProtocol\":\"HTTP\",\"securityProtocol\":\"\",\"endpoint\":\"example.1.azurefd.net\",\"routingRuleName\":\"example.1.azurefd.net\",\"rulesEngineMatchNames\":[\"DefaultHttpsRedirectRule\"],\"httpStatusCode\":\"307\",\"httpStatusDetails\":\"307\",\"pop\":\"PAR\",\"cacheStatus\":\"CONFIG_NOCACHE\",\"ErrorInfo\":\"NoError\",\"hostName\":\"example.1.azurefd.net\",\"originUrl\":\"N/A\",\"originIp\":\"N/A\",\"originName\":\"N/A\",\"referer\":\"\",\"clientCountry\":\"France\",\"domain\":\"example.1.azurefd.net:80\",\"securityCipher\":\"\"}}\n",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ],
            "action": "Microsoft.Cdn/Profiles/AccessLog/Write",
            "dataset": "access"
        },
        "@timestamp": "2022-08-29T15:03:25.4715017Z",
        "observer": {
            "vendor": "Microsoft",
            "product": "Azure Front Door",
            "hostname": "example.1.azurefd.net"
        },
        "source": {
            "ip": "1.2.3.4",
            "port": 53170,
            "address": "1.2.3.4"
        },
        "http": {
            "request": {
                "method": "GET",
                "bytes": 109
            },
            "response": {
                "status_code": 307,
                "bytes": 221
            },
            "version": "1.1"
        },
        "url": {
            "original": "http://example.1.azurefd.net:80/",
            "domain": "example.1.azurefd.net",
            "top_level_domain": "net",
            "subdomain": "example.1",
            "registered_domain": "azurefd.net",
            "scheme": "http",
            "port": 80,
            "path": "/"
        },
        "user_agent": {
            "original": "curl/7.77.0"
        },
        "network": {
            "protocol": "HTTP"
        },
        "azure_front_door": {
            "resource_id": "/SUBSCRIPTIONS/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/RESOURCEGROUPS/YYYYYYYYYYYYYYYYY/PROVIDERS/MICROSOFT.CDN/PROFILES/ZZZZZZZZZZZZZZZ",
            "category": "FrontDoorAccessLog"
        },
        "related": {
            "hosts": [
                "example.1.azurefd.net"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "test_healthprobe.json"

    ```json
	
    {
        "message": "{\"time\":\"2022-08-28T13:01:19.0427677Z\",\"resourceId\":\"/SUBSCRIPTIONS/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/RESOURCEGROUPS/YYYYYYYYYYYYYYYYY/PROVIDERS/MICROSOFT.CDN/PROFILES/ZZZZZZZZZZZZZZZ\",\"category\":\"FrontDoorHealthProbeLog\",\"operationName\":\"Microsoft.Cdn/Profiles/FrontDoorHealthProbeLog/Write\",\"properties\":{\"healthProbeId\":\"A07EBB1B3DF34A71A8AC75CBA4C33607\",\"POP\":\"BUD\",\"httpVerb\":\"HEAD\",\"result\":\"OriginError\",\"httpStatusCode\":\"301\",\"probeURL\":\"http://example.azurestaticapps.net:80/\",\"originName\":\"example.azurestaticapps.net\",\"originIP\":\"1.2.3.4\",\"totalLatencyMilliseconds\":\"97\",\"connectionLatencyMilliseconds\":\"24\",\"DNSLatencyMicroseconds\":\"48133\"}}",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ],
            "action": "Microsoft.Cdn/Profiles/FrontDoorHealthProbeLog/Write",
            "dataset": "health"
        },
        "@timestamp": "2022-08-28T13:01:19.0427677Z",
        "observer": {
            "vendor": "Microsoft",
            "product": "Azure Front Door"
        },
        "source": {
            "ip": "1.2.3.4",
            "address": "1.2.3.4"
        },
        "http": {
            "request": {
                "method": "HEAD"
            },
            "response": {
                "status_code": 301
            }
        },
        "url": {
            "original": "http://example.azurestaticapps.net:80/",
            "domain": "example.azurestaticapps.net",
            "top_level_domain": "net",
            "subdomain": "example",
            "registered_domain": "azurestaticapps.net",
            "scheme": "http",
            "port": 80,
            "path": "/"
        },
        "azure_front_door": {
            "resource_id": "/SUBSCRIPTIONS/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/RESOURCEGROUPS/YYYYYYYYYYYYYYYYY/PROVIDERS/MICROSOFT.CDN/PROFILES/ZZZZZZZZZZZZZZZ",
            "health_probe_id": "A07EBB1B3DF34A71A8AC75CBA4C33607",
            "category": "FrontDoorHealthProbeLog"
        },
        "related": {
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`azure_front_door.cache_status` | `keyword` | The status code of the cache of the CDN |
|`azure_front_door.category` | `keyword` | The category of the event |
|`azure_front_door.health_probe_id` | `keyword` | The identifier of the health probe |
|`azure_front_door.resource_id` | `keyword` | The identifier of the Microsoft Azure resource |
|`azure_front_door.route_name` | `keyword` | The name of the route that the request matched |
|`azure_front_door.rule.names` | `keyword` | The names of rules that handled the request |
|`error.code` | `keyword` | Error code describing the error. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`http.request.bytes` | `long` | Total size in bytes of the request (body and headers). |
|`http.request.method` | `keyword` | HTTP request method. |
|`http.request.referrer` | `keyword` | Referrer for this HTTP request. |
|`http.response.bytes` | `long` | Total size in bytes of the response (body and headers). |
|`http.response.status_code` | `long` | HTTP response status code. |
|`http.version` | `keyword` | HTTP version. |
|`network.protocol` | `keyword` | Application protocol name. |
|`observer.hostname` | `keyword` | Hostname of the observer. |
|`observer.product` | `keyword` | The product name of the observer. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`source.ip` | `ip` | IP address of the source. |
|`source.port` | `long` | Port of the source. |
|`tls.cipher` | `keyword` | String indicating the cipher used during the current connection. |
|`tls.version` | `keyword` | Numeric part of the version parsed from the original string. |
|`tls.version_protocol` | `keyword` | Normalized lowercase protocol name parsed from original string. |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

