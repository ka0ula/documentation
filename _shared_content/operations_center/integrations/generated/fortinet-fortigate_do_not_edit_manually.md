
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Network device logs` | Fortigates can record traffic logs flowing through their firewall. |
| `Network intrusion detection system` | Security logs provided by Fortigates include intrusion prevention related records. |
| `Web application firewall logs` | Fortiweb appliances and virtual appliances record WAF information. |
| `Web logs` | WAF information produces by Fortiweb units can record permited URL access. |
| `DNS records` | Both DNS queries and responses handled by the Fortigate domain name servers can be recorded. |








## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "Configuration_changed.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.2.9|32102|event:system|7|deviceExternalId=FGVM2V0000171868 FortinetFortiGatelogid=0100032102 cat=event:system FortinetFortiGatesubtype=system FortinetFortiGatelevel=alert FortinetFortiGatevd=root FortinetFortiGateeventtime=1637681708541881380 FortinetFortiGatetz=+0100 FortinetFortiGatelogdesc=Configuration changed duser= sproc=console msg=Configuration is changed in the admin session",
        "event": {
            "code": "0100032102",
            "reason": "Configuration is changed in the admin session",
            "timezone": "+0100",
            "dataset": "event:system",
            "category": "event"
        },
        "@timestamp": "2021-11-23T14:35:08.541882Z",
        "log": {
            "level": "alert"
        },
        "observer": {
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.2.9"
        },
        "action": {
            "type": "system",
            "outcome_reason": "Configuration is changed in the admin session",
            "target": "network-traffic"
        }
    }
    	
	```


=== "DLP.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|24576|utm:dlp dlp block|4|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0954024576 cat=utm:dlp FTNTFGTsubtype=dlp FTNTFGTeventtype=dlp FTNTFGTlevel=warning FTNTFGTvd=vdom1 FTNTFGTeventtime=1545949776 FTNTFGTfilteridx=1 FTNTFGTdlpextra=test-dlp3 FTNTFGTfiltertype=file-type FTNTFGTfiltercat=file FTNTFGTseverity=medium FTNTFGTpolicyid=1 externalId=12680 FTNTFGTepoch=418303178 FTNTFGTeventid=0 duser=bob src=10.1.100.11 spt=33638 deviceInboundInterface=port12 FTNTFGTsrcintfrole=undefined dst=172.18.62.158 dpt=80 deviceOutboundInterface=port11 FTNTFGTdstintfrole=undefined proto=6 app=HTTP FTNTFGTfiletype=gif deviceDirection=0 act=block dhost=172.18.62.158 request=/dlp/flower.gif requestClientApplication=curl/7.47.0 fname=flower.gif fsize=1209 FTNTFGTprofile=test-dlp",
        "event": {
            "action": "block",
            "code": "0954024576",
            "dataset": "utm:dlp",
            "category": "utm"
        },
        "@timestamp": "2018-12-27T22:29:36.000000Z",
        "destination": {
            "address": "172.18.62.158",
            "domain": "172.18.62.158",
            "port": 80,
            "ip": "172.18.62.158",
            "user": {
                "name": "bob"
            }
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "severity": "medium"
                }
            }
        },
        "file": {
            "name": "flower.gif",
            "size": 1209
        },
        "log": {
            "level": "warning"
        },
        "network": {
            "transport": "tcp",
            "application": "HTTP",
            "protocol": "http",
            "direction": "inbound"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "port": 33638,
            "ip": "10.1.100.11",
            "address": "10.1.100.11"
        },
        "url": {
            "original": "/dlp/flower.gif",
            "path": "/dlp/flower.gif"
        },
        "user_agent": {
            "original": "curl/7.47.0"
        },
        "action": {
            "name": "block",
            "type": "dlp - dlp",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "user": [
                "bob"
            ],
            "hosts": [
                "172.18.62.158"
            ],
            "ip": [
                "10.1.100.11",
                "172.18.62.158"
            ]
        }
    }
    	
	```


=== "DNS.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|54802|dns:dns-response pass|3|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=1501054802 cat=dns:dns-response FTNTFGTsubtype=dns-response FTNTFGTlevel=notice FTNTFGTvd=vdom1 FTNTFGTeventtime=1545950726 FTNTFGTpolicyid=1 externalId=13355 duser=bob src=10.1.100.11 spt=54621 deviceInboundInterface=port12 FTNTFGTsrcintfrole=lan dst=172.16.200.55 dpt=53 deviceOutboundInterface=port11 FTNTFGTdstintfrole=wan proto=17 FTNTFGTprofile=default FTNTFGTsrcmac=a2:e9:00:ec:40:01 FTNTFGTxid=5137 FTNTFGTqname=detectportal.firefox.com FTNTFGTqtype=A FTNTFGTqtypeval=1 FTNTFGTqclass=IN FTNTFGTipaddr=104.80.89.26, 104.80.89.24 msg=Domain is monitored act=pass FTNTFGTcat=52 FTNTFGTcatdesc=Information Technology",
        "event": {
            "action": "pass",
            "code": "1501054802",
            "reason": "Domain is monitored",
            "dataset": "dns:dns-response",
            "category": "dns"
        },
        "@timestamp": "2018-12-27T22:45:26.000000Z",
        "destination": {
            "address": "172.16.200.55",
            "port": 53,
            "ip": "172.16.200.55",
            "user": {
                "name": "bob"
            }
        },
        "log": {
            "level": "notice"
        },
        "network": {
            "transport": "udp"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "port": 54621,
            "ip": "10.1.100.11",
            "address": "10.1.100.11"
        },
        "action": {
            "name": "pass",
            "type": "dns-response",
            "outcome_reason": "Domain is monitored",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "user": [
                "bob"
            ],
            "ip": [
                "10.1.100.11",
                "172.16.200.55"
            ]
        }
    }
    	
	```


=== "DNS.STANDARD.json"

    ```json
	
    {
        "message": "time=15:51:59 devname=\"my-device\" devid=\"1111111111111111\" eventtime=1668001919663486001 tz=\"+0100\" logid=\"1500054000\" type=\"utm\" subtype=\"dns\" eventtype=\"dns-query\" level=\"information\" vd=\"root\" policyid=1685 poluuid=\"4470d4c5-7e12-4a8f-a369-08eff4a43b5b\" policytype=\"policy\" sessionid=933308058 srcip=1.2.3.4 srcport=35305 srccountry=\"Reserved\" srcintf=\"INTF-1\" srcintfrole=\"undefined\" dstip=8.8.8.8 dstport=53 dstcountry=\"Reserved\" dstintf=\"INTF-2\" dstintfrole=\"lan\" proto=17 profile=\"DNS Filtering Normal\" xid=42240 qtype=\"NS\" qtypeval=2 qclass=\"IN\"",
        "event": {
            "code": "1500054000",
            "timezone": "+0100",
            "category": "utm"
        },
        "@timestamp": "2022-11-09T12:51:59.663486Z",
        "destination": {
            "address": "8.8.8.8",
            "port": 53,
            "ip": "8.8.8.8"
        },
        "dns": {
            "question": {
                "type": "NS",
                "class": "IN"
            },
            "rrtype": "NS"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "utm"
                },
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "information",
            "hostname": "my-device"
        },
        "observer": {
            "hostname": "my-device",
            "serial_number": "1111111111111111",
            "egress": {
                "interface": {
                    "name": "INTF-2"
                }
            },
            "ingress": {
                "interface": {
                    "name": "INTF-1"
                }
            }
        },
        "network": {
            "transport": "udp"
        },
        "rule": {
            "ruleset": "policy"
        },
        "source": {
            "port": 35305,
            "ip": "1.2.3.4",
            "address": "1.2.3.4"
        },
        "action": {
            "type": "dns",
            "target": "network-traffic"
        },
        "related": {
            "hosts": [
                "my-device"
            ],
            "ip": [
                "1.2.3.4",
                "8.8.8.8"
            ]
        },
        "host": {
            "name": "my-device"
        }
    }
    	
	```


=== "DNS2.STANDARD.json"

    ```json
	
    {
        "message": "time=15:58:39 devname=\"dev-name\" devid=\"1111111111111111\" eventtime=1668002319383195535 tz=\"+0100\" logid=\"1500054000\" type=\"utm\" subtype=\"dns\" eventtype=\"dns-query\" level=\"information\" vd=\"root\" policyid=770 poluuid=\"f2aef0f2-a721-49cf-9dd3-b27f7f5b90bc\" policytype=\"policy\" sessionid=933538554 user=\"agt\" srcip=1.2.3.4 srcport=45362 srccountry=\"Reserved\" srcintf=\"intf-1\" srcintfrole=\"undefined\" dstip=8.8.8.8 dstport=53 dstcountry=\"Reserved\" dstintf=\"intf-2\" dstintfrole=\"undefined\" proto=17 profile=\"DNS Filtering Normal\" xid=32649 qname=\"['fr.pool.ntp.org']\" qtype=\"A\" qtypeval=1 qclass=\"IN\"",
        "event": {
            "code": "1500054000",
            "timezone": "+0100",
            "category": "utm"
        },
        "@timestamp": "2022-11-09T12:58:39.383196Z",
        "destination": {
            "address": "8.8.8.8",
            "port": 53,
            "ip": "8.8.8.8"
        },
        "dns": {
            "question": {
                "name": "'fr.pool.ntp.org'",
                "type": "A",
                "class": "IN",
                "subdomain": "'fr.pool.ntp"
            },
            "rrname": "'fr.pool.ntp.org'",
            "rrtype": "A"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "utm"
                },
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "information",
            "hostname": "dev-name"
        },
        "observer": {
            "hostname": "dev-name",
            "serial_number": "1111111111111111",
            "egress": {
                "interface": {
                    "name": "intf-2"
                }
            },
            "ingress": {
                "interface": {
                    "name": "intf-1"
                }
            }
        },
        "network": {
            "transport": "udp"
        },
        "rule": {
            "ruleset": "policy"
        },
        "source": {
            "port": 45362,
            "ip": "1.2.3.4",
            "user": {
                "name": "agt"
            },
            "address": "1.2.3.4"
        },
        "action": {
            "type": "dns",
            "target": "network-traffic"
        },
        "related": {
            "hosts": [
                "dev-name"
            ],
            "ip": [
                "1.2.3.4",
                "8.8.8.8"
            ],
            "user": [
                "agt"
            ]
        },
        "host": {
            "name": "dev-name"
        }
    }
    	
	```


=== "IPS.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|16384|utm:ips signature reset|7|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0419016384 cat=utm:ips FTNTFGTsubtype=ips FTNTFGTeventtype=signature FTNTFGTlevel=alert FTNTFGTvd=vdom1 FTNTFGTeventtime=1545938887 FTNTFGTseverity=info src=172.16.200.55 FTNTFGTsrccountry=Reserved dst=10.1.100.11 deviceInboundInterface=port11 FTNTFGTsrcintfrole=undefined deviceOutboundInterface=port12 FTNTFGTdstintfrole=undefined externalId=901 act=reset proto=6 app=HTTP FTNTFGTpolicyid=1 FTNTFGTattack=Eicar.Virus.Test.File spt=80 dpt=44362 dhost=172.16.200.55 request=/virus/eicar.com deviceDirection=0 FTNTFGTattackid=29844 FTNTFGTprofile=test-ips FTNTFGTref=http://www.fortinet.com/ids/VID29844 duser=bob FTNTFGTincidentserialno=877326946 msg=file_transfer: Eicar.Virus.Test.File,",
        "event": {
            "action": "reset",
            "code": "0419016384",
            "reason": "file_transfer: Eicar.Virus.Test.File,",
            "dataset": "utm:ips",
            "category": "utm"
        },
        "@timestamp": "2018-12-27T19:28:07.000000Z",
        "destination": {
            "address": "10.1.100.11",
            "domain": "172.16.200.55",
            "port": 44362,
            "ip": "10.1.100.11",
            "user": {
                "name": "bob"
            }
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "severity": "info"
                }
            }
        },
        "log": {
            "level": "alert"
        },
        "network": {
            "transport": "tcp",
            "application": "HTTP",
            "protocol": "http",
            "direction": "inbound"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port12"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port11"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "port": 80,
            "ip": "172.16.200.55",
            "address": "172.16.200.55"
        },
        "url": {
            "original": "/virus/eicar.com",
            "path": "/virus/eicar.com"
        },
        "action": {
            "name": "reset",
            "type": "signature - ips",
            "outcome_reason": "file_transfer: Eicar.Virus.Test.File,",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "user": [
                "bob"
            ],
            "hosts": [
                "172.16.200.55"
            ],
            "ip": [
                "10.1.100.11",
                "172.16.200.55"
            ]
        }
    }
    	
	```


=== "IP_SEC.STANDARD.json"

    ```json
	
    {
        "message": "time=17:24:16 devname=\"abc\" devid=\"1\" logid=\"0101037130\" type=\"event\" subtype=\"vpn\" level=\"error\" vd=\"root\" eventtime=1580142256 logdesc=\"Progress IPsec phase 2\" msg=\"progress IPsec phase 2\" action=\"negotiate\" remip=1.1.1.1 locip=93.187.43.9 remport=500 locport=500 outintf=\"N/A\" cookies=\"07f928d94dd975ea/89b1d990f54f0b82\" user=\"N/A\" group=\"N/A\" xauthuser=\"N/A\" xauthgroup=\"N/A\" assignip=N/A vpntunnel=\"VPN-FOOBAR\" status=\"failure\" init=\"local\" exch=\"CREATE_CHILD\" dir=\"inbound\" role=\"initiator\" result=\"ERROR\" version=\"IKEv2\"",
        "event": {
            "action": "negotiate",
            "code": "0101037130",
            "reason": "progress IPsec phase 2",
            "dataset": "event:vpn",
            "category": "event"
        },
        "@timestamp": "2020-01-27T16:24:16.000000Z",
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "event"
                },
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "error",
            "description": "Progress IPsec phase 2",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1"
        },
        "source": {
            "ip": "1.1.1.1",
            "user": {
                "name": "N/A"
            },
            "address": "1.1.1.1"
        },
        "action": {
            "name": "negotiate",
            "type": "vpn",
            "outcome": "failure",
            "outcome_reason": "progress IPsec phase 2",
            "target": "network-traffic"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "user": [
                "N/A"
            ],
            "ip": [
                "1.1.1.1"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "LOGOUT.STANDARD.json"

    ```json
	
    {
        "message": "time=16:48:00 devname=\"abc\" devid=\"1\" logid=\"0100032003\" type=\"event\" subtype=\"system\" level=\"information\" vd=\"root\" eventtime=1619621280 logdesc=\"Admin logout successful\" sn=\"1619620402\" user=\"test\" ui=\"jsconsole\" method=\"jsconsole\" srcip=1.1.1.1 dstip=2.2.2.2 action=\"logout\" status=\"success\" duration=878 reason=\"exit\" msg=\"Administrator test logged out from jsconsole\"",
        "event": {
            "action": "logout",
            "code": "0100032003",
            "reason": "exit",
            "dataset": "event:system",
            "category": "event",
            "provider": "jsconsole"
        },
        "@timestamp": "2021-04-28T14:48:00.000000Z",
        "destination": {
            "address": "2.2.2.2",
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "event"
                },
                "virtual_domain": "root"
            }
        },
        "http": {
            "request": {
                "method": "jsconsole"
            }
        },
        "log": {
            "level": "information",
            "description": "Admin logout successful",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1"
        },
        "source": {
            "ip": "1.1.1.1",
            "user": {
                "name": "test"
            },
            "address": "1.1.1.1"
        },
        "action": {
            "name": "logout",
            "type": "system",
            "outcome": "success",
            "outcome_reason": "Administrator test logged out from jsconsole",
            "target": "network-traffic"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ],
            "user": [
                "test"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "ROLL-LOG.STANDARD.json"

    ```json
	
    {
        "message": "time=16:23:50 devname=\"abc\" devid=\"1\" logid=\"0100032011\" type=\"event\" subtype=\"system\" level=\"notice\" vd=\"PRX1-AA\" eventtime=1619619830 logdesc=\"Disk log rolled\" action=\"roll-log\" reason=\"file-size\" log=\"tlog\" msg=\"Disk log has rolled.\"",
        "event": {
            "action": "roll-log",
            "code": "0100032011",
            "reason": "file-size",
            "dataset": "event:system",
            "category": "event"
        },
        "@timestamp": "2021-04-28T14:23:50.000000Z",
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "event"
                },
                "virtual_domain": "PRX1-AA"
            }
        },
        "log": {
            "level": "notice",
            "description": "Disk log rolled",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1"
        },
        "action": {
            "name": "roll-log",
            "type": "system",
            "outcome_reason": "Disk log has rolled.",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "SSH.CEF-2.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|61002|utm:ssh ssh-command passthrough|3|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=1600061002 cat=utm:ssh FTNTFGTsubtype=ssh FTNTFGTeventtype=ssh-command FTNTFGTlevel=notice FTNTFGTvd=vdom1 FTNTFGTeventtime=1545950175 FTNTFGTpolicyid=1 externalId=12921 duser=bob FTNTFGTprofile=test-ssh src=10.1.100.11 spt=56698 dst=172.16.200.55 dpt=22 deviceInboundInterface=port12 FTNTFGTsrcintfrole=lan deviceOutboundInterface=port11 FTNTFGTdstintfrole=wan proto=6 act=passthrough FTNTFGTlogin=root FTNTFGTcommand=ls FTNTFGTseverity=low",
        "event": {
            "action": "passthrough",
            "code": "1600061002",
            "dataset": "utm:ssh",
            "category": "utm"
        },
        "@timestamp": "2018-12-27T22:36:15.000000Z",
        "destination": {
            "address": "172.16.200.55",
            "port": 22,
            "ip": "172.16.200.55",
            "user": {
                "name": "bob"
            }
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "severity": "low"
                }
            }
        },
        "log": {
            "level": "notice"
        },
        "network": {
            "transport": "tcp"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "port": 56698,
            "ip": "10.1.100.11",
            "address": "10.1.100.11"
        },
        "action": {
            "name": "passthrough",
            "type": "ssh-command - ssh",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "user": [
                "bob"
            ],
            "ip": [
                "10.1.100.11",
                "172.16.200.55"
            ]
        }
    }
    	
	```


=== "VoIP.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|44032|utm:voip voip permit start|2|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0814044032 cat=utm:voip FTNTFGTsubtype=voip FTNTFGTeventtype=voip FTNTFGTlevel=information FTNTFGTvd=vdom1 FTNTFGTeventtime=1545958028 externalId=18975 FTNTFGTepoch=0 FTNTFGTevent_id=6857 src=10.1.100.11 spt=5060 dst=172.16.200.55 dpt=5060 proto=17 deviceInboundInterface=port12 deviceOutboundInterface=port11 FTNTFGTpolicy_id=1 FTNTFGTprofile=default FTNTFGTvoip_proto=sip FTNTFGTkind=call act=permit outcome=start FTNTFGTduration=0 FTNTFGTdir=session_origin FTNTFGTcall_id=3444-13134@127.0.0.1 suser=sip:sipp@127.0.0.1:5060 duser=sip:service@172.16.200.55:5060",
        "event": {
            "action": "permit",
            "code": "0814044032",
            "dataset": "utm:voip",
            "category": "utm"
        },
        "@timestamp": "2018-12-28T00:47:08.000000Z",
        "destination": {
            "address": "172.16.200.55",
            "port": 5060,
            "ip": "172.16.200.55",
            "user": {
                "name": "sip:service@172.16.200.55:5060"
            }
        },
        "log": {
            "level": "information"
        },
        "network": {
            "transport": "udp"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "port": 5060,
            "ip": "10.1.100.11",
            "user": {
                "name": "sip:sipp@127.0.0.1:5060"
            },
            "address": "10.1.100.11"
        },
        "action": {
            "name": "permit",
            "type": "voip - voip",
            "outcome": "start",
            "target": "network-traffic"
        },
        "related": {
            "user": [
                "sip:service@172.16.200.55:5060",
                "sip:sipp@127.0.0.1:5060"
            ],
            "ip": [
                "10.1.100.11",
                "172.16.200.55"
            ]
        }
    }
    	
	```


=== "WAD.STANDARD.json"

    ```json
	
    {
        "message": "time=15:29:39 devname=\"abc\" devid=\"1\" logid=\"0105048039\" type=\"event\" subtype=\"wad\" level=\"error\" vd=\"PRX1-AA\" eventtime=1619616579 logdesc=\"SSL fatal alert sent\" session_id=473f963d policyid=0 srcip=2.2.2.2 srcport=47782 dstip=1.1.1.1 dstport=8002 action=\"send\" alert=\"2\" desc=\"illegal parameter\" msg=\"SSL Alert sent\"",
        "event": {
            "action": "send",
            "code": "0105048039",
            "reason": "SSL Alert sent",
            "dataset": "utm:wad",
            "category": "event",
            "type": "illegal parameter"
        },
        "@timestamp": "2021-04-28T13:29:39.000000Z",
        "destination": {
            "address": "1.1.1.1",
            "port": 8002,
            "ip": "1.1.1.1"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "event",
                    "desc": "illegal parameter"
                },
                "virtual_domain": "PRX1-AA"
            }
        },
        "log": {
            "level": "error",
            "description": "SSL fatal alert sent",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1"
        },
        "source": {
            "port": 47782,
            "ip": "2.2.2.2",
            "address": "2.2.2.2"
        },
        "action": {
            "name": "send",
            "type": "wad",
            "outcome_reason": "SSL Alert sent",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "WAF.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|30258|utm:waf waf-http-constraint passthrough|4|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=1203030258 cat=utm:waf FTNTFGTsubtype=waf FTNTFGTeventtype=waf-http-constraint FTNTFGTlevel=warning FTNTFGTvd=vdom1 FTNTFGTeventtime=1545951320 FTNTFGTpolicyid=1 externalId=13614 duser=bob FTNTFGTprofile=waf_test src=10.1.100.11 spt=57304 dst=172.16.200.55 dpt=80 deviceInboundInterface=port12 FTNTFGTsrcintfrole=lan deviceOutboundInterface=port11 FTNTFGTdstintfrole=wan proto=6 app=HTTP request=http://172.16.200.55/index.html?a\\=0123456789&b\\=0123456789&c\\=0123456789 FTNTFGTseverity=medium act=passthrough deviceDirection=0 requestClientApplication=curl/7.47.0 FTNTFGTconstraint=url-param-num FTNTFGTrawdata=Method\\=GET|User-Agent\\=curl/7.47.0",
        "event": {
            "action": "passthrough",
            "code": "1203030258",
            "dataset": "utm:waf",
            "category": "utm"
        },
        "@timestamp": "2018-12-27T22:55:20.000000Z",
        "destination": {
            "address": "172.16.200.55",
            "port": 80,
            "ip": "172.16.200.55",
            "user": {
                "name": "bob"
            }
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "severity": "medium"
                }
            }
        },
        "log": {
            "level": "warning"
        },
        "network": {
            "transport": "tcp",
            "application": "HTTP",
            "protocol": "http",
            "direction": "inbound"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "port": 57304,
            "ip": "10.1.100.11",
            "address": "10.1.100.11"
        },
        "url": {
            "original": "http://172.16.200.55/index.html?a\\=0123456789&b\\=0123456789&c\\=0123456789",
            "full": "http://172.16.200.55/index.html?a\\=0123456789&b\\=0123456789&c\\=0123456789",
            "domain": "172.16.200.55",
            "path": "/index.html",
            "query": "a\\=0123456789&b\\=0123456789&c\\=0123456789",
            "scheme": "http",
            "port": 80
        },
        "user_agent": {
            "original": "curl/7.47.0"
        },
        "action": {
            "name": "passthrough",
            "type": "waf-http-constraint - waf",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "user": [
                "bob"
            ],
            "ip": [
                "10.1.100.11",
                "172.16.200.55"
            ]
        }
    }
    	
	```


=== "anomaly.CEF-2.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|18433|utm:anomaly anomaly clear_session|7|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0720018433 cat=utm:anomaly FTNTFGTsubtype=anomaly FTNTFGTeventtype=anomaly FTNTFGTlevel=alert FTNTFGTvd=vdom1 FTNTFGTeventtime=1545939604 FTNTFGTseverity=critical src=10.1.100.11 FTNTFGTsrccountry=Reserved dst=172.16.200.55 deviceInboundInterface=port12 FTNTFGTsrcintfrole=undefined externalId=0 act=clear_session proto=1 app=PING cnt=1 FTNTFGTattack=icmp_flood FTNTFGTicmpid=0x3053 FTNTFGTicmptype=0x08 FTNTFGTicmpcode=0x00 FTNTFGTattackid=16777316 FTNTFGTpolicyid=1 FTNTFGTpolicytype=DoS-policy FTNTFGTref=http://www.fortinet.com/ids/VID16777316 msg=anomaly: icmp_flood, 51 > threshold 50 FTNTFGTcrscore=50 FTNTFGTcrlevel=critical",
        "event": {
            "action": "clear_session",
            "code": "0720018433",
            "reason": "anomaly: icmp_flood, 51 > threshold 50",
            "dataset": "utm:anomaly",
            "category": "utm"
        },
        "@timestamp": "2018-12-27T19:40:04.000000Z",
        "destination": {
            "address": "172.16.200.55",
            "ip": "172.16.200.55"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "severity": "critical"
                }
            }
        },
        "log": {
            "level": "alert"
        },
        "network": {
            "transport": "icmp",
            "application": "PING",
            "protocol": "ping"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "ip": "10.1.100.11",
            "address": "10.1.100.11"
        },
        "action": {
            "name": "clear_session",
            "type": "anomaly - anomaly",
            "outcome_reason": "anomaly: icmp_flood, 51 > threshold 50",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "10.1.100.11",
                "172.16.200.55"
            ]
        }
    }
    	
	```


=== "anomaly.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v5.6.0|18433|anomaly:anomaly clear_ session|7|FTNTFGTlogid=0720018433 cat=anomaly:anomaly FTNTFGTsubtype=anomaly FTNTFGTlevel=alert FTNTFGTvd=vdom1 FTNTFGTseverity=critical src=1.1.1.1 dst=2.2.2.2 deviceInboundInterface=port15 externalId=0 act=clear_session proto=1 app=icmp/146/81 cnt=306 FTNTFGTattack=icmp_flood dpt=20882 FTNTFGTicmptype=0x92 FTNTFGTicmpcode=0x51 FTNTFGTattackid=16777316 FTNTFGTprofile=DoS-policy1 cs2=http://www.fortinet.com/ids/VID16777316 cs2Label=Reference msg=anomaly: icmp_flood, 34 > threshold 25, repeats 306 times FTNTFGTcrscore=50 FTNTFGTcrlevel=critical",
        "event": {
            "action": "clear_session",
            "code": "0720018433",
            "reason": "anomaly: icmp_flood, 34 > threshold 25, repeats 306 times",
            "dataset": "anomaly:anomaly",
            "category": "anomaly"
        },
        "destination": {
            "address": "2.2.2.2",
            "port": 20882,
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "severity": "critical"
                }
            }
        },
        "log": {
            "level": "alert"
        },
        "network": {
            "transport": "icmp",
            "application": "icmp/146/81",
            "protocol": "icmp/146/81"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "port15"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v5.6.0"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "clear_session",
            "type": "anomaly",
            "outcome_reason": "anomaly: icmp_flood, 34 > threshold 25, repeats 306 times",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "anomaly.CSV.json"

    ```json
	
    {
        "message": "date=2016-02-12,time=14:10:42,logid=0720018433,type=anomaly,subtype=anomaly,level=alert,vd=\"vdom1\",severity=critical,srcip=1.1.1.1,dstip=2.2.2.2,srcintf=\"port15\",sessionid=0,action=clear_session,proto=1,service=\"icmp/146/81\",count=306,attack=\"icmp_ flood\",dstport=20882,icmptype=0x92,icmpcode=0x51,attackid=16777316,profile=\"DoS-policy1\",ref=\"http://www.fortinet.com/ids/VID16777316\",msg=\"anomaly: icmp_flood, 34 > threshold 25, repeats 306 times\",crscore=50,crlevel=critical",
        "event": {
            "action": "clear_session",
            "code": "0720018433",
            "reason": "anomaly: icmp_flood, 34 > threshold 25, repeats 306 times",
            "dataset": "utm:anomaly",
            "category": "anomaly"
        },
        "destination": {
            "address": "2.2.2.2",
            "port": 20882,
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "anomaly",
                    "severity": "critical"
                },
                "virtual_domain": "vdom1",
                "icmp": {
                    "request": {
                        "type": "0x92",
                        "code": "0x51"
                    }
                }
            }
        },
        "log": {
            "level": "alert"
        },
        "network": {
            "transport": "icmp",
            "protocol": "icmp/146/81"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "port15"
                }
            }
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "clear_session",
            "type": "anomaly",
            "properties": {
                "icmp_code": "0x51",
                "icmp_type": "0x92"
            },
            "outcome_reason": "anomaly: icmp_flood, 34 > threshold 25, repeats 306 times",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "anomaly.STANDARD.json"

    ```json
	
    {
        "message": "date=2016-02-12 time=14:10:42 logid=0720018433 type=anomaly subtype=anomaly level=alert vd=\"vdom1\" severity=critical srcip=1.1.1.1 dstip=2.2.2.2 srcintf=\"port15\" sessionid=0 action=clear_session proto=1 service=\"icmp/146/81\" count=306 attack=\"icmp_ flood\" dstport=20882 icmptype=0x92 icmpcode=0x51 attackid=16777316 profile=\"DoS-policy1\" ref=\"http://www.fortinet.com/ids/VID16777316\" msg=\"anomaly: icmp_flood, 34 > threshold 25, repeats 306 times\" crscore=50 crlevel=critical",
        "event": {
            "action": "clear_session",
            "code": "0720018433",
            "reason": "anomaly: icmp_flood, 34 > threshold 25, repeats 306 times",
            "dataset": "utm:anomaly",
            "category": "anomaly"
        },
        "destination": {
            "address": "2.2.2.2",
            "port": 20882,
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "anomaly",
                    "severity": "critical"
                },
                "virtual_domain": "vdom1",
                "icmp": {
                    "request": {
                        "type": "0x92",
                        "code": "0x51"
                    }
                }
            }
        },
        "log": {
            "level": "alert"
        },
        "network": {
            "transport": "icmp",
            "protocol": "icmp/146/81"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "port15"
                }
            }
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "clear_session",
            "type": "anomaly",
            "properties": {
                "icmp_code": "0x51",
                "icmp_type": "0x92"
            },
            "outcome_reason": "anomaly: icmp_flood, 34 > threshold 25, repeats 306 times",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "antivirus.CEF-2.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|08192|utm:virus infected blocked|4|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0211008192 cat=utm:virus FTNTFGTsubtype=virus FTNTFGTeventtype=infected FTNTFGTlevel=warning FTNTFGTvd=vdom1 FTNTFGTeventtime=1545938448 msg=File is infected. act=blocked app=HTTP externalId=695 src=10.1.100.11 dst=172.16.200.55 spt=44356 dpt=80 deviceInboundInterface=port12 FTNTFGTsrcintfrole=undefined deviceOutboundInterface=port11 FTNTFGTdstintfrole=undefined FTNTFGTpolicyid=1 proto=6 deviceDirection=0 fname=eicar.com FTNTFGTquarskip=File-was-not-quarantined. FTNTFGTvirus=EICAR_TEST_FILE FTNTFGTdtype=Virus FTNTFGTref=http://www.fortinet.com/ve?vn\\=EICAR_TEST_FILE FTNTFGTvirusid=2172 request=http://172.16.200.55/virus/eicar.com FTNTFGTprofile=g-default duser=bob requestClientApplication=curl/7.47.0 FTNTFGTanalyticscksum=275a021bbfb6489e54d471899f7db9d1663fc695ec2fe2a2c4538aabf651fd0f FTNTFGTanalyticssubmit=false FTNTFGTcrscore=50 FTNTFGTcrlevel=critical",
        "event": {
            "action": "blocked",
            "code": "0211008192",
            "reason": "File is infected.",
            "dataset": "utm:virus",
            "category": "utm"
        },
        "@timestamp": "2018-12-27T19:20:48.000000Z",
        "destination": {
            "address": "172.16.200.55",
            "port": 80,
            "ip": "172.16.200.55",
            "user": {
                "name": "bob"
            }
        },
        "file": {
            "name": "eicar.com"
        },
        "log": {
            "level": "warning"
        },
        "network": {
            "transport": "tcp",
            "application": "HTTP",
            "protocol": "http",
            "direction": "inbound"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "port": 44356,
            "ip": "10.1.100.11",
            "address": "10.1.100.11"
        },
        "url": {
            "original": "http://172.16.200.55/virus/eicar.com",
            "full": "http://172.16.200.55/virus/eicar.com",
            "domain": "172.16.200.55",
            "path": "/virus/eicar.com",
            "scheme": "http",
            "port": 80
        },
        "user_agent": {
            "original": "curl/7.47.0"
        },
        "action": {
            "name": "blocked",
            "type": "infected - virus",
            "outcome_reason": "File is infected.",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "user": [
                "bob"
            ],
            "ip": [
                "10.1.100.11",
                "172.16.200.55"
            ]
        }
    }
    	
	```


=== "antivirus.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v5.6.0|08192|utm:virus infected blocked|4|FTNTFGTlogid=0211008192 cat=utm:virus FTNTFGTsubtype=virus FTNTFGTeventtype=infected FTNTFGTlevel=warning FTNTFGTvd=vdom1 msg=File is infected act=blocked app=HTTP externalId=56633 src=1.1.1.1 dst=2.2.2.2 spt=45719 dpt=80 deviceInboundInterface=port15 deviceOutboundInterface=port19 proto=6 deviceDirection=0 fname=eicar.com FTNTFGTchecksum=1dd02bdb FTNTFGTquarskip=No-skip cs1=EICAR_TEST_FILE cs1Label=Virus FTNTFGTdtype=Virus cs2=http://www.fortinet.com/ve?vn\\=EICAR_TEST_FILE cs2Label=Reference FTNTFGTvirusid=2172 request=http://2.2.2.2/eicar.com FTNTFGTprofile=default duser= requestClientApplication=Wget/1 10 2 FTNTFGTanalyticscksum=131f95c51cc819465fa1797f6ccacf9d494aaaff46fa3eac73ae63ffbdfd8267 FTNTFGTanalyticssubmit=false FTNTFGTcrscore=50 FTNTFGTcrlevel=critical",
        "event": {
            "action": "blocked",
            "code": "0211008192",
            "reason": "File is infected",
            "dataset": "utm:virus",
            "category": "utm"
        },
        "destination": {
            "address": "2.2.2.2",
            "port": 80,
            "ip": "2.2.2.2"
        },
        "file": {
            "name": "eicar.com"
        },
        "log": {
            "level": "warning"
        },
        "network": {
            "transport": "tcp",
            "application": "HTTP",
            "protocol": "http",
            "direction": "inbound"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port19"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port15"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v5.6.0"
        },
        "source": {
            "port": 45719,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "url": {
            "original": "http://2.2.2.2/eicar.com",
            "full": "http://2.2.2.2/eicar.com",
            "domain": "2.2.2.2",
            "path": "/eicar.com",
            "scheme": "http",
            "port": 80
        },
        "user_agent": {
            "original": "Wget/1 10 2"
        },
        "action": {
            "name": "blocked",
            "type": "infected - virus",
            "outcome_reason": "File is infected",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "application.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|28704|utm:app-ctrl app-ctrl-all pass|2|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=1059028704 cat=utm:app-ctrl FTNTFGTsubtype=app-ctrl FTNTFGTeventtype=app-ctrl-all FTNTFGTlevel=information FTNTFGTvd=vdom1 FTNTFGTeventtime=1545949688 FTNTFGTappid=34050 src=10.1.100.11 dst=104.80.89.24 spt=56826 dpt=80 deviceInboundInterface=port12 FTNTFGTsrcintfrole=undefined deviceOutboundInterface=port11 FTNTFGTdstintfrole=undefined proto=6 app=HTTP deviceDirection=1 FTNTFGTpolicyid=1 externalId=12567 FTNTFGTapplist=g-default FTNTFGTappcat=Web.Client FTNTFGTapp=HTTP.BROWSER_Firefox act=pass dhost=detectportal.firefox.com FTNTFGTincidentserialno=1702350499 request=/success.txt msg=Web.Client: HTTP.BROWSER_Firefox, FTNTFGTapprisk=elevated suser=Domain\\\\alice",
        "event": {
            "action": "pass",
            "code": "1059028704",
            "reason": "Web.Client: HTTP.BROWSER_Firefox,",
            "dataset": "utm:app-ctrl",
            "category": "utm"
        },
        "@timestamp": "2018-12-27T22:28:08.000000Z",
        "destination": {
            "address": "104.80.89.24",
            "domain": "detectportal.firefox.com",
            "port": 80,
            "ip": "104.80.89.24"
        },
        "log": {
            "level": "information"
        },
        "network": {
            "transport": "tcp",
            "application": "HTTP",
            "protocol": "http",
            "direction": "outbound"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "port": 56826,
            "ip": "10.1.100.11",
            "user": {
                "name": "alice",
                "domain": "Domain"
            },
            "address": "10.1.100.11"
        },
        "url": {
            "original": "/success.txt",
            "path": "/success.txt"
        },
        "action": {
            "name": "pass",
            "type": "app-ctrl-all - app-ctrl",
            "outcome_reason": "Web.Client: HTTP.BROWSER_Firefox,",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "detectportal.firefox.com"
            ],
            "ip": [
                "10.1.100.11",
                "104.80.89.24"
            ],
            "user": [
                "alice"
            ]
        }
    }
    	
	```


=== "dns.CSV.json"

    ```json
	
    {
        "message": "date=2018-12-27,time=14:45:26,logid=\"1501054802\",type=\"dns\",subtype=\"dns-response\",level=\"notice\",vd=\"vdom1\",eventtime=1545950726,policyid=1,sessionid=13355,user=\"bob\",srcip=1.1.1.1,srcport=54621,srcintf=\"port12\",srcintfrole=\"lan\",dstip=2.2.2.2,dstport=53,dstintf=\"port11\",dstintfrole=\"wan\",proto=17,profile=\"default\",srcmac=\"00:00:00:00:00:00\",xid=5137,qname=\"detectportal.firefox.com\",qtype=\"A\",qtypeval=1,qclass=\"IN\",ipaddr=\"104.80.89.26, 104.80.89.24\",msg=\"Domain is monitored\",action=\"pass\",cat=52,catdesc=\"Information Technology\"",
        "event": {
            "action": "pass",
            "code": "1501054802",
            "reason": "Domain is monitored",
            "dataset": "dns:dns-response",
            "category": "dns"
        },
        "@timestamp": "2018-12-27T22:45:26.000000Z",
        "destination": {
            "address": "2.2.2.2",
            "port": 53,
            "ip": "2.2.2.2"
        },
        "dns": {
            "question": {
                "name": "detectportal.firefox.com",
                "type": "A",
                "class": "IN",
                "top_level_domain": "com",
                "subdomain": "detectportal",
                "registered_domain": "firefox.com"
            },
            "rrname": "detectportal.firefox.com",
            "rrtype": "A"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "dns"
                },
                "virtual_domain": "vdom1"
            }
        },
        "log": {
            "level": "notice"
        },
        "network": {
            "transport": "udp"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            }
        },
        "rule": {
            "category": "Information Technology"
        },
        "source": {
            "mac": "00:00:00:00:00:00",
            "port": 54621,
            "ip": "1.1.1.1",
            "user": {
                "name": "bob"
            },
            "address": "1.1.1.1"
        },
        "action": {
            "name": "pass",
            "type": "dns-response",
            "outcome_reason": "Domain is monitored",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ],
            "user": [
                "bob"
            ]
        }
    }
    	
	```


=== "email-spamfilter.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|20503|utm:emailfilter smtp log-only|2|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0508020503 cat=utm:emailfilter FTNTFGTsubtype=emailfilter FTNTFGTeventtype=smtp FTNTFGTlevel=information FTNTFGTvd=vdom1 FTNTFGTeventtime=1545939418 FTNTFGTpolicyid=1 externalId=1135 duser=bob src=10.1.100.11 spt=35969 deviceInboundInterface=port12 FTNTFGTsrcintfrole=undefined dst=172.18.62.158 dpt=25 deviceOutboundInterface=port11 FTNTFGTdstintfrole=undefined proto=6 app=SMTP FTNTFGTprofile=test-spam act=log-only suser=testpc1@qa.fortinet.com duser=test1@server88.qa.fortinet.com FTNTFGTsender=testpc1@qa.fortinet.com FTNTFGTrecipient=test1@server88.qa.fortinet.com deviceDirection=1 msg=general email log FTNTFGTsubject=hello_world2 FTNTFGTsize=216 FTNTFGTattachment=no",
        "event": {
            "action": "log-only",
            "code": "0508020503",
            "reason": "general email log",
            "dataset": "utm:emailfilter",
            "category": "utm"
        },
        "@timestamp": "2018-12-27T19:36:58.000000Z",
        "destination": {
            "address": "172.18.62.158",
            "port": 25,
            "ip": "172.18.62.158",
            "user": {
                "name": "bob"
            }
        },
        "log": {
            "level": "information"
        },
        "network": {
            "transport": "tcp",
            "application": "SMTP",
            "protocol": "smtp",
            "direction": "outbound"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "port": 35969,
            "ip": "10.1.100.11",
            "user": {
                "name": "testpc1@qa.fortinet.com"
            },
            "address": "10.1.100.11"
        },
        "action": {
            "name": "log-only",
            "type": "smtp - emailfilter",
            "outcome_reason": "general email log",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "user": [
                "bob",
                "testpc1@qa.fortinet.com"
            ],
            "ip": [
                "10.1.100.11",
                "172.18.62.158"
            ]
        }
    }
    	
	```


=== "event_log_system_subtype.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|32002|event:system login failed|7|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0100032002 cat=event:system FTNTFGTsubtype=system FTNTFGTlevel=alert FTNTFGTvd=vdom1 FTNTFGTeventtime=1545938140 FTNTFGTlogdesc=Admin login failed FTNTFGTsn=0 duser=admin1 sproc=https(172.16.200.254) FTNTFGTmethod=https src=172.16.200.254 dst=172.16.200.1 act=login outcome=failed reason=name_invalid msg=Administrator admin1 login failed from https(172.16.200.254) because of invalid user name",
        "event": {
            "action": "login",
            "code": "0100032002",
            "reason": "name_invalid",
            "dataset": "event:system",
            "category": "event"
        },
        "@timestamp": "2018-12-27T19:15:40.000000Z",
        "destination": {
            "address": "172.16.200.1",
            "ip": "172.16.200.1",
            "user": {
                "name": "admin1"
            }
        },
        "log": {
            "level": "alert"
        },
        "observer": {
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "ip": "172.16.200.254",
            "address": "172.16.200.254"
        },
        "action": {
            "name": "login",
            "type": "system",
            "outcome": "failed",
            "outcome_reason": "Administrator admin1 login failed from https(172.16.200.254) because of invalid user name",
            "target": "network-traffic"
        },
        "related": {
            "user": [
                "admin1"
            ],
            "ip": [
                "172.16.200.1",
                "172.16.200.254"
            ]
        }
    }
    	
	```


=== "event_log_user_subtype.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|43008|event:user authentication success|3|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0102043008 cat=event:user FTNTFGTsubtype=user FTNTFGTlevel=notice FTNTFGTvd=vdom1 FTNTFGTeventtime=1545938255 FTNTFGTlogdesc=Authentication success src=10.1.100.11 dst=172.16.200.55 FTNTFGTpolicyid=1 deviceInboundInterface=port12 duser=bob FTNTFGTgroup=N/A FTNTFGTauthproto=TELNET(10.1.100.11) act=authentication outcome=success reason=N/A msg=User bob succeeded in authentication",
        "event": {
            "action": "authentication",
            "code": "0102043008",
            "reason": "User bob succeeded in authentication",
            "dataset": "event:user",
            "category": "event"
        },
        "@timestamp": "2018-12-27T19:17:35.000000Z",
        "destination": {
            "address": "172.16.200.55",
            "ip": "172.16.200.55",
            "user": {
                "name": "bob"
            }
        },
        "log": {
            "level": "notice"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "ip": "10.1.100.11",
            "address": "10.1.100.11"
        },
        "action": {
            "name": "authentication",
            "type": "user",
            "outcome": "success",
            "outcome_reason": "User bob succeeded in authentication",
            "target": "network-traffic"
        },
        "related": {
            "user": [
                "bob"
            ],
            "ip": [
                "10.1.100.11",
                "172.16.200.55"
            ]
        }
    }
    	
	```


=== "hostname.STANDARD.json"

    ```json
	
    {
        "message": "time=11:09:50 devname=\"abc\" devid=\"1\" logid=\"1059028704\" type=\"utm\" subtype=\"app-ctrl\" eventtype=\"app-ctrl-all\" level=\"information\" vd=\"root\" eventtime=1579860590 appid=40568 srcip=1.1.1.1 dstip=2.2.2.2 srcport=33345 dstport=443 srcintf=\"test\" srcintfrole=\"undefined\" dstintf=\"port1\" dstintfrole=\"undefined\" proto=6 service=\"HTTPS\" direction=\"outgoing\" policyid=1 sessionid=1508480438 applist=\"default\" appcat=\"Web.Client\" app=\"HTTPS.BROWSER\" action=\"pass\" hostname=\"abcd\" incidentserialno=455926217 url=\"/\" msg=\"Web.Client: HTTPS.BROWSER,\" apprisk=\"medium\"",
        "event": {
            "action": "pass",
            "code": "1059028704",
            "reason": "Web.Client: HTTPS.BROWSER,",
            "dataset": "utm:app-ctrl",
            "category": "utm"
        },
        "@timestamp": "2020-01-24T10:09:50.000000Z",
        "destination": {
            "address": "2.2.2.2",
            "domain": "abcd",
            "port": 443,
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "utm"
                },
                "apprisk": "medium",
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "information",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1",
            "egress": {
                "interface": {
                    "name": "port1"
                }
            },
            "ingress": {
                "interface": {
                    "name": "test"
                }
            }
        },
        "network": {
            "transport": "tcp",
            "application": "HTTPS.BROWSER",
            "protocol": "https"
        },
        "rule": {
            "category": "Web.Client",
            "ruleset": "default",
            "apprisk": "medium"
        },
        "source": {
            "port": 33345,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "url": {
            "original": "/",
            "path": "/"
        },
        "action": {
            "name": "pass",
            "type": "app-ctrl",
            "outcome_reason": "Web.Client: HTTPS.BROWSER,",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc",
                "abcd"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "icmp.json"

    ```json
	
    {
        "message": " time=15:22:43 devname=\"abc\" devid=\"1\" logid=\"0000000011\" type=\"traffic\" subtype=\"forward\" level=\"warning\" vd=\"root\" eventtime=1602591763587868496 tz=\"+0300\" srcip=1.1.1.1 identifier=256 srcintf=\"internal\" srcintfrole=\"lan\" dstip=2.2.2.2 dstintf=\"wan1\" dstintfrole=\"wan\" srcuuid=\"b22e6ef4-2e38-51ea-72c9-53b2da2e20f5\" dstuuid=\"052bdbce-823a-51e9-eb23-7a3e819fea4f\" poluuid=\"1520e1aa-823a-51e9-984f-a55e1f39b3c7\" sessionid=706677975 proto=1 action=\"ip-conn\" policyid=1 policytype=\"policy\" service=\"icmp/0/8\" dstcountry=\"Netherlands\" srccountry=\"Reserved\" appcat=\"unscanned\" crscore=5 craction=262144 crlevel=\"low\"",
        "event": {
            "action": "ip-conn",
            "code": "0000000011",
            "timezone": "+0300",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "@timestamp": "2020-10-13T09:22:43.587868Z",
        "destination": {
            "address": "2.2.2.2",
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "traffic"
                },
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "warning",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1",
            "egress": {
                "interface": {
                    "name": "wan1"
                }
            },
            "ingress": {
                "interface": {
                    "name": "internal"
                }
            }
        },
        "network": {
            "transport": "icmp",
            "protocol": "icmp/0/8"
        },
        "rule": {
            "category": "unscanned",
            "ruleset": "policy"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "ip-conn",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "icmp6.json"

    ```json
	
    {
        "message": " time=13:02:14 devname=\"abc\" devid=\"1\" logid=\"0001000014\" type=\"traffic\" subtype=\"local\" level=\"notice\" vd=\"root\" eventtime=1602586934900309053 tz=\"+0200\" srcip=00::00:00:00:00 identifier=0 srcintf=\"AVR-GUEST-AP\" srcintfrole=\"lan\" dstip=12::16 dstintf=\"unknown0\" dstintfrole=\"undefined\" sessionid=1395131 proto=58 action=\"accept\" policyid=0 policytype=\"local-in-policy6\" service=\"icmp6/143/0\" trandisp=\"noop\" app=\"icmp6/143/0\" duration=60 sentbyte=76 rcvdbyte=0 sentpkt=1 rcvdpkt=0 appcat=\"unscanned\"",
        "event": {
            "action": "accept",
            "code": "0001000014",
            "timezone": "+0200",
            "dataset": "traffic:local",
            "category": "traffic"
        },
        "@timestamp": "2020-10-13T09:02:14.900309Z",
        "destination": {
            "address": "12::16",
            "bytes": 0,
            "packets": 0,
            "ip": "12::16"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "traffic"
                },
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "notice",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1",
            "egress": {
                "interface": {
                    "name": "unknown0"
                }
            },
            "ingress": {
                "interface": {
                    "name": "AVR-GUEST-AP"
                }
            }
        },
        "network": {
            "transport": "ipv6-icmp",
            "bytes": 76,
            "application": "icmp6/143/0",
            "protocol": "icmp6/143/0"
        },
        "rule": {
            "category": "unscanned",
            "ruleset": "local-in-policy6"
        },
        "source": {
            "bytes": 76,
            "packets": 1,
            "ip": "00::00:00:00:00",
            "address": "00::00:00:00:00"
        },
        "action": {
            "name": "accept",
            "type": "local",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "ip": [
                "00::00:00:00:00",
                "12::16"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "icmp_CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.10|00014|traffic:local accept|3|deviceExternalId=FGVM2V0000171868 FortinetFortiGatelogid=0001000014 cat=traffic:local FortinetFortiGatesubtype=local FortinetFortiGatelevel=notice FortinetFortiGatevd=root FortinetFortiGateeventtime=1602663098 src=1.1.1.1 deviceInboundInterface=port1 FortinetFortiGatesrcintfrole=undefined dst=2.2.2.2 deviceOutboundInterface=root FortinetFortiGatedstintfrole=undefined externalId=4887198 proto=1 FortinetFortiGateaction=accept FortinetFortiGatepolicyid=0 FortinetFortiGatepolicytype=local-in-policy app=icmp/8/0 FortinetFortiGatedstcountry=Reserved FortinetFortiGatesrccountry=China FortinetFortiGatetrandisp=noop FortinetFortiGateapp=icmp/8/0 FortinetFortiGateduration=61 out=84 in=84 FortinetFortiGatesentpkt=1 FortinetFortiGatercvdpkt=1 FortinetFortiGateappcat=unscanned",
        "event": {
            "action": "accept",
            "code": "0001000014",
            "dataset": "traffic:local",
            "category": "traffic"
        },
        "@timestamp": "2020-10-14T08:11:38.000000Z",
        "destination": {
            "address": "2.2.2.2",
            "bytes": 84,
            "packets": 1,
            "ip": "2.2.2.2"
        },
        "log": {
            "level": "notice"
        },
        "network": {
            "transport": "icmp",
            "bytes": 168,
            "application": "icmp/8/0",
            "protocol": "icmp/8/0"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "root"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port1"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.10"
        },
        "source": {
            "bytes": 84,
            "packets": 1,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "accept",
            "type": "local",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "ping.json"

    ```json
	
    {
        "message": " time=14:22:37 devname=\"abc\" devid=\"1\" logid=\"0000000013\" type=\"traffic\" subtype=\"forward\" level=\"notice\" vd=\"ROUTER\" eventtime=1602591758311908837 tz=\"+0200\" srcip=1.1.1.1 identifier=29027 srcintf=\"test1\" srcintfrole=\"undefined\" dstip=2.2.2.2 dstintf=\"test\" dstintfrole=\"undefined\" sessionid=3558919660 proto=1 action=\"accept\" policyid=637 policytype=\"policy\" poluuid=\"b23818a6-8f49-51ea-9db7-4e4965a3483c\" service=\"PING\" dstcountry=\"Reserved\" srccountry=\"Reserved\" trandisp=\"noop\" duration=64 sentbyte=420 rcvdbyte=420 sentpkt=5 rcvdpkt=5 appcat=\"unscanned\"",
        "event": {
            "action": "accept",
            "code": "0000000013",
            "timezone": "+0200",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "@timestamp": "2020-10-13T10:22:38.311909Z",
        "destination": {
            "address": "2.2.2.2",
            "bytes": 420,
            "packets": 5,
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "traffic"
                },
                "virtual_domain": "ROUTER"
            }
        },
        "log": {
            "level": "notice",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1",
            "egress": {
                "interface": {
                    "name": "test"
                }
            },
            "ingress": {
                "interface": {
                    "name": "test1"
                }
            }
        },
        "network": {
            "transport": "icmp",
            "bytes": 840,
            "protocol": "ping"
        },
        "rule": {
            "category": "unscanned",
            "ruleset": "policy"
        },
        "source": {
            "bytes": 420,
            "packets": 5,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "accept",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "ssh_access.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.4|32021|event:system login failed|7|deviceExternalId=FGVM2V0000171868 FortinetFortiGatelogid=0100032021 cat=event:system FortinetFortiGatesubtype=system FortinetFortiGatelevel=alert FortinetFortiGatevd=root FortinetFortiGateeventtime=1579172447 FortinetFortiGatelogdesc=Admin login disabled sproc=1.1.1.1 FortinetFortiGateaction=login outcome=failed reason=exceed_limit msg=Login disabled from IP 1.1.1.1 for 60 seconds because of 3 bad attempts",
        "event": {
            "action": "login",
            "code": "0100032021",
            "reason": "exceed_limit",
            "dataset": "event:system",
            "category": "event"
        },
        "@timestamp": "2020-01-16T11:00:47.000000Z",
        "log": {
            "level": "alert"
        },
        "observer": {
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.4"
        },
        "action": {
            "name": "login",
            "type": "system",
            "outcome": "failed",
            "outcome_reason": "Login disabled from IP 1.1.1.1 for 60 seconds because of 3 bad attempts",
            "target": "network-traffic"
        }
    }
    	
	```


=== "ssl_new_con.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.10|39943|event:vpn ssl-new-con|2|deviceExternalId=FGT3HD3916803645 FTNTFGTlogid=0101039943 cat=event:vpn FTNTFGTsubtype=vpn FTNTFGTlevel=information FTNTFGTvd=root FTNTFGTeventtime=1637338258 FTNTFGTlogdesc=SSL VPN new connection act=ssl-new-con FTNTFGTtunneltype=ssl FTNTFGTtunnelid=0 dst=2.2.2.2 duser=N/A FTNTFGTgroup=N/A FTNTFGTdst_host=N/A reason=N/A msg=SSL new connection",
        "event": {
            "action": "ssl-new-con",
            "code": "0101039943",
            "reason": "SSL new connection",
            "dataset": "event:vpn",
            "category": "event"
        },
        "@timestamp": "2021-11-19T16:10:58.000000Z",
        "destination": {
            "address": "2.2.2.2",
            "ip": "2.2.2.2"
        },
        "log": {
            "level": "information"
        },
        "observer": {
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.10"
        },
        "action": {
            "name": "ssl-new-con",
            "type": "vpn",
            "outcome_reason": "SSL new connection",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "traffic_forward-RDP.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|FortiGate-1000C|5.6.14,build1727 (GA)|0000000020|forward traffic accept|5|start=Oct 12 2022 12:50:31 logver=506141727 deviceExternalId=FGT123 dvchost=FW-123 ad.vd=root ad.logid=0000000020 cat=traffic ad.subtype=forward deviceSeverity=notice ad.eventtime=1665571831 src=1.1.1.1 spt=55390 deviceInboundInterface=abc ad.srcintfrole=undefined dst=2.2.2.2 dpt=1522 deviceOutboundInterface=efg ad.dstintfrole=lan foo.poluuid=ec6ff8fe-5e41-51ec-bcbe-9e5484033dc8 externalID=3812440508 proto=6 act=accept ad.policyid=185 ad.policytype=policy app=SQLNET-1522 ad.dstcountry=Reserved ad.srccountry=Reserved ad.trandisp=noop ad.duration=268 out=202 in=52 ad.sentpkt=3 ad.rcvdpkt=1 ad.appcat=unscanned ad.sentdelta=0 ad.rcvddelta=0 tz=\"+0200\"",
        "event": {
            "action": "accept",
            "code": "0000000020",
            "timezone": "+0200",
            "dataset": "traffic",
            "category": "traffic"
        },
        "@timestamp": "2022-10-12T10:50:31.000000Z",
        "destination": {
            "address": "2.2.2.2",
            "bytes": 202,
            "port": 1522,
            "ip": "2.2.2.2"
        },
        "network": {
            "transport": "tcp",
            "bytes": 254,
            "application": "SQLNET-1522",
            "protocol": "sqlnet-1522"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "efg"
                }
            },
            "ingress": {
                "interface": {
                    "name": "abc"
                }
            },
            "type": "FortiGate-1000C",
            "vendor": "Fortinet",
            "version": "5.6.14,build1727 (GA)"
        },
        "source": {
            "bytes": 52,
            "port": 55390,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "accept",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "traffic_forward.CEF-2.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.4|00013|traffic:forward timeout|3|deviceExternalId=FGVM2V0000171868 FortinetFortiGatelogid=0000000013 cat=traffic:forward FortinetFortiGatesubtype=forward FortinetFortiGatelevel=notice FortinetFortiGatevd=root FortinetFortiGateeventtime=1572471876 src=1.1.1.1 spt=49260 deviceInboundInterface=port1 FortinetFortiGatesrcintfrole=undefined dst=3.3.3.3 dpt=80 deviceOutboundInterface=port2 FortinetFortiGatedstintfrole=undefined FortinetFortiGatepoluuid=bafe134e-c0ad-51e8-ed9c-52f798dd69d4 externalId=12812952 proto=6 FortinetFortiGateaction=timeout FortinetFortiGatepolicyid=1 FortinetFortiGatepolicytype=policy app=HTTP FortinetFortiGatedstcountry=Reserved FortinetFortiGatesrccountry=United States FortinetFortiGatetrandisp=dnat destinationTranslatedAddress=2.2.2.2 destinationTranslatedPort=80 FortinetFortiGateduration=20 out=48 in=144 FortinetFortiGatesentpkt=1 FortinetFortiGatercvdpkt=3 FortinetFortiGateappcat=unscanned FortinetFortiGatecrscore=5 FortinetFortiGatecraction=262144 FortinetFortiGatecrlevel=low",
        "event": {
            "action": "timeout",
            "code": "0000000013",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "@timestamp": "2019-10-30T21:44:36.000000Z",
        "destination": {
            "address": "3.3.3.3",
            "bytes": 48,
            "nat": {
                "ip": "2.2.2.2",
                "port": 80
            },
            "packets": 3,
            "port": 80,
            "ip": "3.3.3.3"
        },
        "log": {
            "level": "notice"
        },
        "network": {
            "transport": "tcp",
            "bytes": 192,
            "application": "HTTP",
            "protocol": "http"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port2"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port1"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.4"
        },
        "source": {
            "bytes": 144,
            "packets": 1,
            "port": 49260,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "timeout",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2",
                "3.3.3.3"
            ]
        }
    }
    	
	```


=== "traffic_forward.CEF-3.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|00013|traffic:forward close|3|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0000000013 cat=traffic:forward FTNTFGTsubtype=forward FTNTFGTlevel=notice FTNTFGTvd=vdom1 FTNTFGTeventtime=1545937675 src=10.1.100.11 spt=54190 deviceInboundInterface=port12 FTNTFGTsrcintfrole=undefined dst=52.53.140.235 dpt=443 deviceOutboundInterface=port11 FTNTFGTdstintfrole=undefined FTNTFGTpoluuid=c2d460aa-fe6f-51e8-9505-41b5117dfdd4 externalId=402 proto=6 act=close FTNTFGTpolicyid=1 FTNTFGTpolicytype=policy app=HTTPS FTNTFGTdstcountry=United States FTNTFGTsrccountry=Reserved FTNTFGTtrandisp=snat sourceTranslatedAddress=172.16.200.1 sourceTranslatedPort=54190 FTNTFGTappid=40568 FTNTFGTapp=HTTPS.BROWSER FTNTFGTappcat=Web.Client FTNTFGTapprisk=medium FTNTFGTapplist=g-default FTNTFGTduration=2 out=3652 in=146668 FTNTFGTsentpkt=58 FTNTFGTrcvdpkt=105 FTNTFGTutmaction=allow FTNTFGTcountapp=2",
        "event": {
            "action": "close",
            "code": "0000000013",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "@timestamp": "2018-12-27T19:07:55.000000Z",
        "destination": {
            "address": "52.53.140.235",
            "bytes": 3652,
            "port": 443,
            "ip": "52.53.140.235"
        },
        "log": {
            "level": "notice"
        },
        "network": {
            "transport": "tcp",
            "bytes": 150320,
            "application": "HTTPS",
            "protocol": "https"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "source": {
            "bytes": 146668,
            "nat": {
                "port": 54190,
                "ip": "172.16.200.1"
            },
            "packets": 58,
            "port": 54190,
            "ip": "10.1.100.11",
            "address": "10.1.100.11"
        },
        "action": {
            "name": "close",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "10.1.100.11",
                "172.16.200.1",
                "52.53.140.235"
            ]
        }
    }
    	
	```


=== "traffic_forward.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v5.6.0|00013|traffic:forward close|3|FTNTFGTlogid=0000000013 cat=traffic:forward FTNTFGTsubtype=forward FTNTFGTlevel=notice FTNTFGTvd=vdom1 src=2.2.2.2 shost=2.2.2.2 spt=45719 deviceInboundInterface=port15 dst=3.3.3.3 dhost=3.3.3.3 dpt=80 deviceOutboundInterface=port19 FTNTFGTpoluuid=61c4243a-34ba-51e5-c32a-3859389a5162 externalId=56633 proto=6 act=close cs5=10 cs5Label=Policy Id FTNTFGTdstcountry=Reserved FTNTFGTsrccountry=Reserved FTNTFGTtrandisp=snat sourceTranslatedAddress=1.1.1.1 sourceTranslatedPort=45719 app=HTTP FTNTFGTappid=38783 FTNTFGTapp=Wget.Like FTNTFGTappcat=General.Interest FTNTFGTapprisk=low FTNTFGTapplist=default FTNTFGTappact=detected cn1=7 cn1Label=Duration out=398 in=1605 cn2=5 cn2Label=Packets Sent cn3=5 cn3Label=Packets Received FTNTFGTutmaction=block FTNTFGTcountav=1 FTNTFGTcountapp=1 FTNTFGTcrscore=50 FTNTFGTcraction=2",
        "event": {
            "action": "close",
            "code": "0000000013",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "destination": {
            "address": "3.3.3.3",
            "bytes": 398,
            "domain": "3.3.3.3",
            "packets": 5,
            "port": 80,
            "ip": "3.3.3.3"
        },
        "log": {
            "level": "notice"
        },
        "network": {
            "transport": "tcp",
            "bytes": 2003,
            "application": "HTTP",
            "protocol": "http"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port19"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port15"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v5.6.0"
        },
        "source": {
            "bytes": 1605,
            "domain": "2.2.2.2",
            "nat": {
                "port": 45719,
                "ip": "1.1.1.1"
            },
            "packets": 5,
            "port": 45719,
            "ip": "2.2.2.2",
            "address": "2.2.2.2"
        },
        "action": {
            "name": "close",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "2.2.2.2",
                "3.3.3.3"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2",
                "3.3.3.3"
            ]
        }
    }
    	
	```


=== "traffic_forward.CSV.json"

    ```json
	
    {
        "message": "date=2018-07-26,time=16:51:36,logid=\"0000000013\",type=\"traffic\",subtype=\"forward\",level=\"notice\",vd=\"root\",eventtime=1532616695,srcip=1.1.1.1,srcport=10016,srcintf=\"test\",srcintfrole=\"undefined\",dstip=2.2.2.2,dstport=20,dstintf=\"dmz1\",dstintfrole=\"dmz\",sessionid=10006,proto=6,action=\"accept\",policyid=1,policytype=\"policy\",service=\"tcp/20\",dstcountry=\"France\",srccountry=\"United States\",trandisp=\"noop\",appid=35421,app=\"application\",appcat=\"Storage.Backup\",apprisk=\"medium\",applist=\"default\",duration=10,sentbyte=2000,rcvdbyte=1000,sentpkt=0,rcvdpkt=0,utmaction=\"allow\",countapp=1,devtype=\"iPad\",osname=\"Apple\",osversion=\"ver\",mastersrcmac=\"01:01:01:01:01:01\",srcmac=\"01:01:01:01:01:01\",srcserver=0,dstdevtype=\"Android Phone\",dstosname=\"Android\",dstosversion=\"ver\",masterdstmac=\"00:00:00:00:00:00\",dstmac=\"00:00:00:00:00:00\",dstserver=0,utmref=65491-194",
        "event": {
            "action": "accept",
            "code": "0000000013",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "@timestamp": "2018-07-26T14:51:35.000000Z",
        "destination": {
            "address": "2.2.2.2",
            "bytes": 1000,
            "mac": "00:00:00:00:00:00",
            "packets": 0,
            "port": 20,
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "traffic"
                },
                "apprisk": "medium",
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "notice"
        },
        "network": {
            "transport": "tcp",
            "bytes": 3000,
            "application": "application",
            "protocol": "tcp/20"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "dmz1"
                }
            },
            "ingress": {
                "interface": {
                    "name": "test"
                }
            }
        },
        "rule": {
            "category": "Storage.Backup",
            "ruleset": "default",
            "apprisk": "medium"
        },
        "source": {
            "bytes": 2000,
            "mac": "01:01:01:01:01:01",
            "packets": 0,
            "port": 10016,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "accept",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "traffic_forward.STANDARD.json"

    ```json
	
    {
        "message": "date=2018-07-26 time=16:51:36 logid=\"0000000013\" type=\"traffic\" subtype=\"forward\" level=\"notice\" vd=\"root\" eventtime=1532616695 srcip=1.1.1.1 srcport=10016 srcintf=\"test\" srcintfrole=\"undefined\" dstip=2.2.2.2 dstport=20 dstintf=\"test1\" dstintfrole=\"dmz\" sessionid=10006 proto=6 action=\"accept\" policyid=1 policytype=\"policy\" service=\"tcp/20\" dstcountry=\"France\" srccountry=\"United States\" trandisp=\"noop\" appid=35421 app=\"Dropbox_File.Download\" appcat=\"Storage.Backup\" apprisk=\"medium\" applist=\"default\" duration=10 sentbyte=2000 rcvdbyte=1000 sentpkt=0 rcvdpkt=0 utmaction=\"allow\" countapp=1 devtype=\"iPad\" osname=\"Apple\" osversion=\"ver\" mastersrcmac=\"01:01:01:01:01:01\" srcmac=\"01:01:01:01:01:01\" srcserver=0 dstdevtype=\"Android Phone\" dstosname=\"Android\" dstosversion=\"ver\" masterdstmac=\"00:00:00:00:00:00\" dstmac=\"00:00:00:00:00:00\" dstserver=0 utmref=65491-194",
        "event": {
            "action": "accept",
            "code": "0000000013",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "@timestamp": "2018-07-26T14:51:35.000000Z",
        "destination": {
            "address": "2.2.2.2",
            "bytes": 1000,
            "mac": "00:00:00:00:00:00",
            "packets": 0,
            "port": 20,
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "traffic"
                },
                "apprisk": "medium",
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "notice"
        },
        "network": {
            "transport": "tcp",
            "bytes": 3000,
            "application": "Dropbox_File.Download",
            "protocol": "tcp/20"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "test1"
                }
            },
            "ingress": {
                "interface": {
                    "name": "test"
                }
            }
        },
        "rule": {
            "category": "Storage.Backup",
            "ruleset": "default",
            "apprisk": "medium"
        },
        "source": {
            "bytes": 2000,
            "mac": "01:01:01:01:01:01",
            "packets": 0,
            "port": 10016,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "accept",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "traffic_forward.STANDARD_2.json"

    ```json
	
    {
        "message": "date=2021-06-21 time=09:38:29 devname=\"abc\" devid=\"1\" logid=\"0000000010\" type=\"traffic\" subtype=\"forward\" level=\"notice\" vd=\"PRX1-AA\" eventtime=1624261109 srcip=1.1.1.1 srcport=50592 srcintf=\"port2\" srcintfrole=\"dmz\" dstip=2.2.2.2 dstport=443 dstintf=\"test\" dstintfrole=\"wan\" sessionid=1224900441 poluuid=\"1eb429d4-ff52-51ea-d119-d1db60e409a6\" dstcountry=\"United Kingdom\" srccountry=\"Reserved\" service=\"HTTPS\" wanoptapptype=\"web-proxy\" proto=6 action=\"accept\" duration=37 policyid=1 policytype=\"proxy-policy\" wanin=5851 rcvdbyte=5851 wanout=2523 lanin=2769 sentbyte=2769 lanout=5923 appcat=\"unscanned\" utmaction=\"allow\" countweb=1",
        "event": {
            "action": "accept",
            "code": "0000000010",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "@timestamp": "2021-06-21T07:38:29.000000Z",
        "destination": {
            "address": "2.2.2.2",
            "bytes": 5851,
            "port": 443,
            "ip": "2.2.2.2"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "traffic"
                },
                "virtual_domain": "PRX1-AA"
            }
        },
        "log": {
            "level": "notice",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1",
            "egress": {
                "interface": {
                    "name": "test"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port2"
                }
            }
        },
        "network": {
            "transport": "tcp",
            "bytes": 8620,
            "protocol": "https"
        },
        "rule": {
            "category": "unscanned",
            "ruleset": "proxy-policy"
        },
        "source": {
            "bytes": 2769,
            "port": 50592,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "accept",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "traffic_forward_FTNTFGTtz.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.4.9|00011|traffic:forward dns|4|deviceExternalId=FG5H0ETB19909686 FTNTFGTeventtime=1662381825920035319 FTNTFGTtz=+0200 FTNTFGTlogid=0000000011 cat=traffic:forward FTNTFGTsubtype=forward FTNTFGTlevel=warning FTNTFGTvd=root src=172.16.222.150 spt=49956 deviceInboundInterface=port1 FTNTFGTsrcintfrole=wan dst=172.18.67.10 dpt=53 deviceOutboundInterface=RWC FRANCE 2023 FTNTFGTdstintfrole=lan FTNTFGTsrccountry=Reserved FTNTFGTdstcountry=Reserved externalId=1797928567 proto=17 act=dns FTNTFGTpolicyid=30 FTNTFGTpolicytype=policy FTNTFGTpoluuid=6c8b6672-0b92-51ea-95a0-556c3c0fdb8f FTNTFGTpolicyname=CLT-RWC2023-001 FTNTFGTcentralnatid=6 app=DNS FTNTFGTappcat=unscanned FTNTFGTcrscore=5 FTNTFGTcraction=262144 FTNTFGTcrlevel=low FTNTFGTdsthwvendor=VMware FTNTFGTdstdevtype=Server FTNTFGTdstfamily=Virtual Machine FTNTFGTdstosname=Windows FTNTFGTdsthwversion=Workstation Pro FTNTFGTdstswversion=7 FTNTFGTmasterdstmac=00:50:56:86:7a:ab FTNTFGTdstmac=00:50:56:86:7a:ab FTNTFGTdstserver=0",
        "event": {
            "action": "dns",
            "code": "0000000011",
            "timezone": "+0200",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "@timestamp": "2022-09-05T10:43:45.920035Z",
        "destination": {
            "address": "172.18.67.10",
            "port": 53,
            "ip": "172.18.67.10"
        },
        "log": {
            "level": "warning"
        },
        "network": {
            "transport": "udp",
            "application": "DNS",
            "protocol": "dns"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "RWC FRANCE 2023"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port1"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.4.9"
        },
        "source": {
            "port": 49956,
            "ip": "172.16.222.150",
            "address": "172.16.222.150"
        },
        "action": {
            "name": "dns",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "172.16.222.150",
                "172.18.67.10"
            ]
        }
    }
    	
	```


=== "traffic_nat.STANDARD.json"

    ```json
	
    {
        "message": "date=2018-07-26 time=14:56:21 devname=\"abc\" devid=\"1\" logid=\"0000000013\" type=\"traffic\" subtype=\"forward\" level=\"notice\" vd=\"root\" eventtime=1609941381 srcip=1.1.1.1 srcport=52125 srcintf=\"port9\" srcintfrole=\"undefined\" dstip=3.3.3.3 dstport=3727 dstintf=\"port10\" dstintfrole=\"undefined\" poluuid=\"d77c53b2-a3c6-51e9-49b2-61c9e68c1f7e\" sessionid=578033623 proto=6 action=\"server-rst\" policyid=207 policytype=\"policy\" service=\"tcp/3727\" dstcountry=\"France\" srccountry=\"Netherlands\" trandisp=\"dnat\" tranip=2.2.2.2 tranport=3727 duration=5 sentbyte=80 rcvdbyte=40 sentpkt=2 rcvdpkt=1 appcat=\"unscanned\" dstdevtype=\"Router/NAT Device\" dstdevcategory=\"Windows Device\" masterdstmac=\"00:00:00:00:00:00\" dstmac=\"00:00:00:00:00:00\" dstserver=1",
        "event": {
            "action": "server-rst",
            "code": "0000000013",
            "dataset": "traffic:forward",
            "category": "traffic"
        },
        "@timestamp": "2021-01-06T13:56:21.000000Z",
        "destination": {
            "address": "3.3.3.3",
            "bytes": 40,
            "mac": "00:00:00:00:00:00",
            "nat": {
                "ip": "2.2.2.2"
            },
            "packets": 1,
            "port": 3727,
            "ip": "3.3.3.3"
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "traffic"
                },
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "notice",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1",
            "egress": {
                "interface": {
                    "name": "port10"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port9"
                }
            }
        },
        "network": {
            "transport": "tcp",
            "bytes": 120,
            "protocol": "tcp/3727"
        },
        "rule": {
            "category": "unscanned",
            "ruleset": "policy"
        },
        "source": {
            "bytes": 80,
            "packets": 2,
            "port": 52125,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "action": {
            "name": "server-rst",
            "type": "forward",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2",
                "3.3.3.3"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "tunnel.json"

    ```json
	
    {
        "message": "logver=60 timestamp=1566916060 tz=\"UTC+2\" devname=\"abc\" devid=\"1\" vd=\"IPSEC\" date=2019-08-27 time=16:27:40 logid=\"0101039949\" type=\"event\" subtype=\"vpn\" level=\"information\" eventtime=1566916060 logdesc=\"SSL VPN statistics\" action=\"tunnel-stats\" tunneltype=\"ssl-tunnel\" tunnelid=1995 remip=1.1.1.1 tunnelip=2.2.2.2 user=\"test\" group=\"GRP_Generic_JAIL_VPN\" dst_host=\"N/A\" nextstat=600 duration=8437 sentbyte=71524041 rcvdbyte=6151809 msg=\"SSL tunnel statistics\"\n",
        "event": {
            "action": "tunnel-stats",
            "code": "0101039949",
            "reason": "\"SSL tunnel statistics\"\n",
            "timezone": "UTC+2",
            "dataset": "event:vpn",
            "category": "event"
        },
        "@timestamp": "2019-08-27T12:27:40.000000Z",
        "destination": {
            "bytes": 6151809
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "event"
                },
                "virtual_domain": "IPSEC"
            }
        },
        "log": {
            "level": "information",
            "description": "SSL VPN statistics",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1"
        },
        "source": {
            "bytes": 71524041,
            "ip": "1.1.1.1",
            "nat": {
                "ip": "2.2.2.2"
            },
            "user": {
                "name": "test"
            },
            "address": "1.1.1.1"
        },
        "network": {
            "bytes": 77675850
        },
        "action": {
            "name": "tunnel-stats",
            "type": "vpn",
            "outcome_reason": "SSL tunnel statistics",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "user": [
                "test"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "tunnel_statistics.CSV.json"

    ```json
	
    {
        "message": " time=12:02:57 devname=\"abc\" devid=\"1\" logid=\"0101037141\" type=\"event\" subtype=\"vpn\" level=\"notice\" vd=\"root\" eventtime=1614855777 logdesc=\"IPsec tunnel statistics\" msg=\"IPsec tunnel statistics\" action=\"tunnel-stats\" remip=1.1.1.1 locip=93.187.43.9 remport=500 locport=500 outintf=\"N/A\" cookies=\"9b064274e0648c03/662c2b1264a2295e\" user=\"N/A\" group=\"N/A\" xauthuser=\"N/A\" xauthgroup=\"N/A\" assignip=N/A vpntunnel=\"VPN-HELPLINE\" tunnelip=N/A tunnelid=0 tunneltype=\"ipsec\" duration=102908570 sentbyte=7649 rcvdbyte=0 nextstat=600",
        "event": {
            "action": "tunnel-stats",
            "code": "0101037141",
            "reason": "IPsec tunnel statistics",
            "dataset": "event:vpn",
            "category": "event"
        },
        "@timestamp": "2021-03-04T11:02:57.000000Z",
        "destination": {
            "bytes": 0
        },
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "event"
                },
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "notice",
            "description": "IPsec tunnel statistics",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1"
        },
        "source": {
            "bytes": 7649,
            "ip": "1.1.1.1",
            "user": {
                "name": "N/A"
            },
            "address": "1.1.1.1"
        },
        "network": {
            "bytes": 7649
        },
        "action": {
            "name": "tunnel-stats",
            "type": "vpn",
            "outcome_reason": "IPsec tunnel statistics",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "abc"
            ],
            "user": [
                "N/A"
            ],
            "ip": [
                "1.1.1.1"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "vpn.STANDARD.json"

    ```json
	
    {
        "message": " time=14:38:46 devname=\"abc\" devid=\"1\" logid=\"0101041987\" type=\"event\" subtype=\"vpn\" level=\"information\" vd=\"root\" eventtime=1615469926 logdesc=\"Certificate updated\" action=\"info\" cert-type=\"CRL\" status=\"success\" name=\"CRL_1\" method=\"HTTP\" reason=\"N/A\" msg=\"A certificate is updated\"",
        "event": {
            "action": "CRL_1",
            "code": "0101041987",
            "reason": "A certificate is updated",
            "dataset": "event:vpn",
            "category": "event",
            "provider": "HTTP"
        },
        "@timestamp": "2021-03-11T13:38:46.000000Z",
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "event"
                },
                "virtual_domain": "root"
            }
        },
        "http": {
            "request": {
                "method": "HTTP"
            }
        },
        "log": {
            "level": "information",
            "description": "Certificate updated",
            "hostname": "abc"
        },
        "observer": {
            "hostname": "abc",
            "serial_number": "1"
        },
        "action": {
            "name": "CRL_1",
            "type": "vpn",
            "outcome": "success",
            "outcome_reason": "A certificate is updated",
            "target": "network-traffic"
        },
        "related": {
            "hosts": [
                "abc"
            ]
        },
        "host": {
            "name": "abc"
        }
    }
    	
	```


=== "vpn_login_failed.STANDARD.json"

    ```json
	
    {
        "message": "time=17:43:43 devname=\"FW-FOOBAR\" devid=\"FG123\" eventtime=1665675824075327440 tz=\"+0200\" logid=\"0101039426\" type=\"event\" subtype=\"vpn\" level=\"alert\" vd=\"root\" logdesc=\"SSL VPN login fail\" action=\"ssl-login-fail\" tunneltype=\"ssl-web\" tunnelid=0 remip=1.1.1.1 user=\"CN = foo.bar.baz.com\" group=\"N/A\" dst_host=\"N/A\" reason=\"sslvpn_login_cert_checked_error\" msg=\"SSL user failed to logged in\"",
        "event": {
            "action": "ssl-login-fail",
            "code": "0101039426",
            "reason": "sslvpn_login_cert_checked_error",
            "timezone": "+0200",
            "dataset": "event:vpn",
            "category": "event"
        },
        "@timestamp": "2022-10-13T13:43:44.075328Z",
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "event"
                },
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "alert",
            "description": "SSL VPN login fail",
            "hostname": "FW-FOOBAR"
        },
        "observer": {
            "hostname": "FW-FOOBAR",
            "serial_number": "FG123"
        },
        "source": {
            "ip": "1.1.1.1",
            "user": {
                "name": "CN = foo.bar.baz.com"
            },
            "address": "1.1.1.1"
        },
        "action": {
            "name": "ssl-login-fail",
            "type": "vpn",
            "outcome_reason": "SSL user failed to logged in",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "FW-FOOBAR"
            ],
            "user": [
                "CN = foo.bar.baz.com"
            ],
            "ip": [
                "1.1.1.1"
            ]
        },
        "host": {
            "name": "FW-FOOBAR"
        }
    }
    	
	```


=== "vpn_na_ip.STANDARD.json"

    ```json
	
    {
        "message": "time=17:43:43 devname=\"FW-FOOBAR\" devid=\"FG123\" eventtime=1665675824075327440 tz=\"+0200\" logid=\"0101039426\" type=\"event\" subtype=\"vpn\" level=\"alert\" vd=\"root\" logdesc=\"SSL VPN login fail\" action=\"ssl-login-fail\" tunneltype=\"ssl-web\" tunnelid=0 remip=\"N/A\" user=\"CN = foo.bar.baz.com\" group=\"N/A\" dst_host=\"N/A\" reason=\"sslvpn_login_cert_checked_error\" msg=\"SSL user failed to logged in\"",
        "event": {
            "action": "ssl-login-fail",
            "code": "0101039426",
            "reason": "sslvpn_login_cert_checked_error",
            "timezone": "+0200",
            "dataset": "event:vpn",
            "category": "event"
        },
        "@timestamp": "2022-10-13T13:43:44.075328Z",
        "fortinet": {
            "fortigate": {
                "event": {
                    "type": "event"
                },
                "virtual_domain": "root"
            }
        },
        "log": {
            "level": "alert",
            "description": "SSL VPN login fail",
            "hostname": "FW-FOOBAR"
        },
        "observer": {
            "hostname": "FW-FOOBAR",
            "serial_number": "FG123"
        },
        "source": {
            "user": {
                "name": "CN = foo.bar.baz.com"
            }
        },
        "action": {
            "name": "ssl-login-fail",
            "type": "vpn",
            "outcome_reason": "SSL user failed to logged in",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "hosts": [
                "FW-FOOBAR"
            ],
            "user": [
                "CN = foo.bar.baz.com"
            ]
        },
        "host": {
            "name": "FW-FOOBAR"
        }
    }
    	
	```


=== "webfilter.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.3|13056|utm:webfilter ftgd_blk blocked|4|deviceExternalId=FGT5HD3915800610 FTNTFGTlogid=0316013056 cat=utm:webfilter FTNTFGTsubtype=webfilter FTNTFGTeventtype=ftgd_blk FTNTFGTlevel=warning FTNTFGTvd=vdom1 FTNTFGTeventtime=1545938629 FTNTFGTpolicyid=1 externalId=764 duser=Domain\\\\\\\\bob src=10.1.100.11 spt=59194 deviceInboundInterface=port12 FTNTFGTsrcintfrole=undefined dst=185.230.61.185 dpt=80 deviceOutboundInterface=port11 FTNTFGTdstintfrole=undefined proto=6 app=HTTP dhost=ambrishsriv.wixsite.com FTNTFGTprofile=g-default act=blocked FTNTFGTreqtype=direct request=/bizsquads out=96 in=0 deviceDirection=1 msg=URL belongs to a denied category in policy FTNTFGTmethod=domain FTNTFGTcat=26 requestContext=Malicious Websites FTNTFGTcrscore=60 FTNTFGTcrlevel=high",
        "event": {
            "action": "blocked",
            "code": "0316013056",
            "reason": "URL belongs to a denied category in policy",
            "dataset": "utm:webfilter",
            "category": "utm"
        },
        "@timestamp": "2018-12-27T19:23:49.000000Z",
        "destination": {
            "address": "185.230.61.185",
            "bytes": 96,
            "domain": "ambrishsriv.wixsite.com",
            "port": 80,
            "ip": "185.230.61.185",
            "user": {
                "name": "bob",
                "domain": "Domain"
            }
        },
        "log": {
            "level": "warning"
        },
        "network": {
            "transport": "tcp",
            "bytes": 96,
            "application": "HTTP",
            "protocol": "http",
            "direction": "outbound"
        },
        "observer": {
            "egress": {
                "interface": {
                    "name": "port11"
                }
            },
            "ingress": {
                "interface": {
                    "name": "port12"
                }
            },
            "type": "Fortigate",
            "vendor": "Fortinet",
            "version": "v6.0.3"
        },
        "rule": {
            "category": "Malicious Websites"
        },
        "source": {
            "bytes": 0,
            "port": 59194,
            "ip": "10.1.100.11",
            "address": "10.1.100.11"
        },
        "url": {
            "original": "/bizsquads",
            "path": "/bizsquads"
        },
        "action": {
            "name": "blocked",
            "type": "ftgd_blk - webfilter",
            "outcome_reason": "URL belongs to a denied category in policy",
            "target": "network-traffic",
            "outcome": "success"
        },
        "related": {
            "user": [
                "bob"
            ],
            "hosts": [
                "ambrishsriv.wixsite.com"
            ],
            "ip": [
                "10.1.100.11",
                "185.230.61.185"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`action.properties.icmp_code` | `keyword` | ICMP code (backward compatibility) |
|`action.properties.icmp_type` | `keyword` | ICMP type (backward compatibility) |
|`action.target` | `keyword` | Target of the action (backward compatibility) |
|`destination.address` | `keyword` | Destination network address. |
|`destination.bytes` | `long` | Bytes sent from the destination to the source. |
|`destination.domain` | `keyword` | The domain name of the destination. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.mac` | `keyword` | MAC address of the destination. |
|`destination.nat.ip` | `ip` | Destination NAT ip |
|`destination.nat.port` | `long` | Destination NAT Port |
|`destination.packets` | `long` | Packets sent from the destination to the source. |
|`destination.port` | `long` | Port of the destination. |
|`destination.user.domain` | `keyword` | Name of the directory the user is a member of. |
|`destination.user.name` | `keyword` | Short name or login of the user. |
|`dns.question.class` | `keyword` | The class of records being queried. |
|`dns.question.name` | `keyword` | The name being queried. |
|`dns.question.type` | `keyword` | The type of record being queried. |
|`dns.rrname` | `keyword` | DNS requested name (backward compatibility) |
|`dns.rrtype` | `keyword` | DNS request type (backward compatibility) |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.code` | `keyword` | Identification code for this event. |
|`event.dataset` | `keyword` | Name of the dataset. |
|`event.provider` | `keyword` | Source of the event. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.timezone` | `keyword` | Event time zone. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`file.size` | `long` | File size in bytes. |
|`fortinet.fortigate.apprisk` | `keyword` | Risk level of the application. |
|`fortinet.fortigate.event.desc` | `keyword` | Type of log. |
|`fortinet.fortigate.event.severity` | `keyword` | Anomaly severity as reported by Fortigate |
|`fortinet.fortigate.event.type` | `keyword` | Type of the event. |
|`fortinet.fortigate.icmp.request.code` | `keyword` | The request code. |
|`fortinet.fortigate.icmp.request.type` | `keyword` | The request type. |
|`fortinet.fortigate.virtual_domain` | `keyword` | Name of the virtual domain in which the event was observed |
|`http.request.method` | `keyword` | HTTP request method. |
|`log.level` | `keyword` | Log level of the log event. |
|`network.application` | `keyword` | Application level protocol name. |
|`network.bytes` | `long` | Total bytes transferred in both directions. |
|`network.protocol` | `keyword` | Application protocol name. |
|`network.transport` | `keyword` | Protocol Name corresponding to the field `iana_number`. |
|`observer.egress.interface.name` | `keyword` | Interface name |
|`observer.hostname` | `keyword` | Hostname of the observer. |
|`observer.ingress.interface.name` | `keyword` | Interface name |
|`observer.serial_number` | `keyword` | Observer serial number. |
|`observer.type` | `keyword` | The type of the observer the data is coming from. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`observer.version` | `keyword` | Observer version. |
|`rule.apprisk` | `keyword` | App risk reported by Fortigate (backward compatibility) |
|`rule.category` | `keyword` | Rule category |
|`rule.ruleset` | `keyword` | Rule ruleset |
|`source.bytes` | `long` | Bytes sent from the source to the destination. |
|`source.domain` | `keyword` | The domain name of the source. |
|`source.ip` | `ip` | IP address of the source. |
|`source.mac` | `keyword` | MAC address of the source. |
|`source.nat.ip` | `ip` | Source NAT ip |
|`source.nat.port` | `long` | Source NAT port |
|`source.packets` | `long` | Packets sent from the source to the destination. |
|`source.port` | `long` | Port of the source. |
|`source.user.domain` | `keyword` | Name of the directory the user is a member of. |
|`source.user.name` | `keyword` | Short name or login of the user. |
|`url.full` | `wildcard` | Full unparsed URL. |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

