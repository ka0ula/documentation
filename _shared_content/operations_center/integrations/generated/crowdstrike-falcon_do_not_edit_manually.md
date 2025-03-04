
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Authentication logs` | activities on the CrowdStrike console is traced including authentication |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `alert`, `event` |
| Category | `configuration`, `intrusion_detection` |
| Type | `change`, `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "auth_activity_audit.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"customerIDString\":\"46de5283260647ec8f28def00bffd094\",\"offset\":6755,\"eventType\":\"AuthActivityAuditEvent\",\"eventCreationTime\":1657663146099,\"version\":\"1.0\"},\"event\":{\"UserId\":\"foo.bar@sekoia.fr\",\"UserIp\":\"83.199.26.17\",\"OperationName\":\"twoFactorAuthenticate\",\"ServiceName\":\"CrowdStrike Authentication\",\"Success\":true,\"UTCTimestamp\":1657663146099}}",
        "event": {
            "kind": "event",
            "category": [
                "configuration"
            ],
            "type": [
                "change"
            ]
        },
        "@timestamp": "2022-07-12T21:59:06.099000Z",
        "crowdstrike": {
            "event_type": "AuthActivityAuditEvent",
            "operation_name": "twoFactorAuthenticate"
        },
        "source": {
            "ip": "83.199.26.17",
            "address": "83.199.26.17"
        },
        "service": {
            "name": "CrowdStrike Authentication"
        },
        "user": {
            "id": "foo.bar@sekoia.fr"
        },
        "related": {
            "ip": [
                "83.199.26.17"
            ]
        }
    }
    	
	```


=== "detection_summary_event.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"customerIDString\":\"46de5283260647ec8f28def00bffd094\",\"offset\":189,\"eventType\":\"DetectionSummaryEvent\",\"eventCreationTime\":1657174538000,\"version\":\"1.0\"},\"event\":{\"ProcessStartTime\":1656688889,\"ProcessEndTime\":0,\"ProcessId\":22164474048,\"ParentProcessId\":22163465296,\"ComputerName\":\"nsewmkzevukn-vm\",\"UserName\":\"Administrator\",\"DetectName\":\"Overwatch Detection\",\"DetectDescription\":\"Falcon Overwatch has identified malicious activity carried out by a suspected or known eCrime operator. This activity has been raised for critical action and should be investigated urgently.\",\"Severity\":5,\"SeverityName\":\"Critical\",\"FileName\":\"explorer.exe\",\"FilePath\":\"\\\\Device\\\\HarddiskVolume2\\\\Windows\",\"CommandLine\":\"C:\\\\Windows\\\\Explorer.EXE\",\"SHA256String\":\"249cb3cb46fd875196e7ed4a8736271a64ff2d8132357222a283be53e7232ed3\",\"MD5String\":\"d45bd7c7b7bf977246e9409d63435231\",\"SHA1String\":\"0000000000000000000000000000000000000000\",\"MachineDomain\":\"nsewmkzevukn-vm\"}}",
        "event": {
            "kind": "alert",
            "type": [
                "info"
            ],
            "category": [
                "intrusion_detection"
            ]
        },
        "@timestamp": "2022-07-07T06:15:38.000000Z",
        "crowdstrike": {
            "event_type": "DetectionSummaryEvent",
            "detect_description": "Falcon Overwatch has identified malicious activity carried out by a suspected or known eCrime operator. This activity has been raised for critical action and should be investigated urgently."
        },
        "host": {
            "name": "nsewmkzevukn-vm"
        },
        "log": {
            "hostname": "nsewmkzevukn-vm"
        },
        "process": {
            "pid": 22164474048,
            "parent": {
                "pid": 22163465296
            },
            "command_line": "C:\\Windows\\Explorer.EXE",
            "name": "explorer.exe",
            "working_directory": "\\Device\\HarddiskVolume2\\Windows"
        },
        "file": {
            "hash": {
                "md5": "d45bd7c7b7bf977246e9409d63435231",
                "sha256": "249cb3cb46fd875196e7ed4a8736271a64ff2d8132357222a283be53e7232ed3"
            }
        },
        "related": {
            "hash": [
                "249cb3cb46fd875196e7ed4a8736271a64ff2d8132357222a283be53e7232ed3",
                "d45bd7c7b7bf977246e9409d63435231"
            ]
        }
    }
    	
	```


=== "detection_update.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"customerIDString\":\"46de5283260647ec8f28def00bffd094\",\"offset\":733,\"eventType\":\"UserActivityAuditEvent\",\"eventCreationTime\":1657614940000,\"version\":\"1.0\"},\"event\":{\"UserId\":\"foo.bar@sekoia.fr\",\"UserIp\":\"185.162.177.26\",\"OperationName\":\"detection_update\",\"ServiceName\":\"detections\",\"AuditKeyValues\":[{\"Key\":\"detection_id\",\"ValueString\":\"ldt:5418788591a444d1b45c2b39d3b07b50:21483381998\"},{\"Key\":\"new_state\",\"ValueString\":\"closed\"},{\"Key\":\"assigned_to\",\"ValueString\":\"Erwan Chevalier\"},{\"Key\":\"assigned_to_uid\",\"ValueString\":\"foo.bar@sekoia.fr\"}],\"UTCTimestamp\":1657614940}}",
        "event": {
            "kind": "event",
            "type": [
                "change"
            ],
            "category": [
                "configuration"
            ]
        },
        "@timestamp": "2022-07-12T08:35:40.000000Z",
        "crowdstrike": {
            "event_type": "UserActivityAuditEvent",
            "operation_name": "detection_update"
        },
        "source": {
            "ip": "185.162.177.26",
            "address": "185.162.177.26"
        },
        "service": {
            "name": "detections"
        },
        "user": {
            "id": "foo.bar@sekoia.fr"
        },
        "related": {
            "ip": [
                "185.162.177.26"
            ]
        }
    }
    	
	```


=== "device_event.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"detectionIdString\":\"ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109\",\"eventType\":\"Vertex\",\"edge\":{\"sourceVertexId\":\"pid:9ed90be65f99456c9361141f8cfa39ab:17326818154\",\"type\":\"device\"}},\"event\":{\"id\":\"aid:9ed90be65f99456c9361141f8cfa39ab:9ed90be65f99456c9361141f8cfa39ab\",\"customer_id\":\"5d505aca55a145b3bd234c399201f082\",\"scope\":\"device\",\"object_id\":\"9ed90be65f99456c9361141f8cfa39ab\",\"device_id\":\"9ed90be65f99456c9361141f8cfa39ab\",\"vertex_type\":\"device\",\"timestamp\":\"2022-07-28T15:09:51Z\",\"properties\":{\"AgentLoadFlags\":\"0\",\"AgentLocalTime\":\"2022-07-24T20:09:35.793Z\",\"AgentVersion\":\"6.39.15316.0\",\"BaseTime\":\"663896169\",\"BiosManufacturer\":\"American Megatrends Inc.\",\"BiosReleaseDate\":\"12/07/2018\",\"BiosVersion\":\"090008 \",\"BootArgs\":\" NOEXECUTE=OPTIN  REDIRECT\",\"BootId\":\"7\",\"BootStatusDataAabEnabled\":\"0\",\"BootStatusDataBootAttemptCount\":\"1\",\"BootStatusDataBootGood\":\"1\",\"BootStatusDataBootShutdown\":\"0\",\"BuildNumber\":\"19042\",\"BuildType\":\"3\",\"ChasisManufacturer\":\"Microsoft Corporation\",\"ChassisType\":\"3\",\"CheckedBuild\":\"0\",\"ComputerName\":\"mycomputer\",\"ConfigBuild\":\"1007.3.0015316.10\",\"ConfigIDBase\":\"65994762\",\"ConfigIDBuild\":\"15316\",\"ConfigIDPlatform\":\"3\",\"ConfigStateHash\":\"2445437569\",\"ConfigurationVersion\":\"10\",\"ConnectTime\":\"2022-07-18T09:47:48.602Z\",\"ConnectType\":\"8\",\"ConnectionCipher\":\"26126\",\"ConnectionCipherStrength\":\"128\",\"ConnectionExchange\":\"44550\",\"ConnectionExchangeStrength\":\"255\",\"ConnectionHash\":\"32780\",\"ConnectionHashStrength\":\"0\",\"ConnectionProtocol\":\"2048\",\"ContextTimeStamp\":\"2022-07-24T20:09:35.793Z\",\"CpuFeaturesMask\":\"7037767758369539\",\"CpuSignature\":\"263921\",\"CpuVendor\":\"0\",\"EffectiveTransmissionClass\":\"2\",\"Entitlements\":\"15\",\"FailedConnectCount\":\"0\",\"InstanceMetadataProvider\":\"2\",\"LocalAddressIP4\":\"1.2.3.4\",\"MachineDomain\":\"\",\"MajorVersion\":\"10\",\"MicrocodeSignature\":\"18446744069414584320\",\"MinorVersion\":\"0\",\"MoboManufacturer\":\"Microsoft Corporation\",\"MoboProductName\":\"Virtual Machine\",\"NetworkContainmentState\":\"0\",\"PhysicalAddress\":\"3a-c7-6c-b1-81-38\",\"PlatformId\":\"2\",\"PlatformSecuritySettings\":\"0\",\"PlatformSecurityStatus\":\"4294967296\",\"PointerSize\":\"8\",\"PreviousConnectTime\":\"1601-01-01T00:00:00.000Z\",\"ProductSku\":\"48\",\"ProductType\":\"1\",\"ProvisionState\":\"1\",\"RFMState\":\"0\",\"ServicePackMajor\":\"0\",\"ServicePackMinor\":\"0\",\"SideChannelMitigationFlags\":\"29444\",\"SubBuildNumber\":\"1706\",\"SuiteMask\":\"272\",\"SystemManufacturer\":\"Microsoft Corporation\",\"SystemProductName\":\"Virtual Machine\",\"SystemSerialNumber\":\"0000-0010-2562-7523-7070-7191-32\",\"SystemSku\":\"\",\"TargetFileName\":\"Config.sys\",\"accountId\":\"35f882a7-80ce-4e98-9efb-56f2382b6856\",\"eventPlatformId\":\"0\",\"externalIpAddress\":\"4.3.2.1\",\"instanceId\":\"9ed90be6-5f99-456c-9361-141f8cfa39ab\",\"zone_group\":\"rdp-east-us\"},\"edges\":{\"assigned_ipv4_address\":[{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/ipv4/summary/v1?ids=ip4%3A10.0.4.4%3A10.0.4.4&scope=device\",\"id\":\"ip4:10.0.4.4:10.0.4.4\",\"device_id\":\"10.0.4.4\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"10.0.4.4\",\"direction\":\"out\",\"edge_id\":\"KZZ\\\"V__;Kgi>WZVP5\\\\Ro9MfM']Tc5[VP:C5\\\\od;.hXFhKNnO.RVWpq2h-EaR=a8J)%**N1p(udPF_<1'[/;7\\\\Xnd4%Ia%E3,C4j![?=r-0%.O=l!%&[$5<pJ\\\"98H%rr\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"assigned_ipv4_address\",\"timestamp\":\"2022-07-24T20:09:46Z\",\"properties\":{\"CreationTimeStamp\":\"2022-07-18T09:37:53.716Z\",\"InterfaceAlias\":\"Ethernet\",\"LocalAddressIP4\":\"10.0.4.4\",\"PhysicalAddress\":\"00-0d-3a-9b-ed-fd\"}}],\"established_user_session\":[{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-19%7C997&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-19|997\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-19|997\",\"direction\":\"out\",\"edge_id\":\"KZl^h_E\\\\N!i=cqQ9er-oCNt@b[/gM#_,sbbB,A3Ghtlkkl0)Wh1fb3]fF8DRd^3MM:=W3YFZgac&!(eo3mj`:i;bDl5(.j<\\\\GN`$iU8'T@_A:(<?&2#jt^0:QR.n#`b+cL!!*'!\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T09:50:33Z\",\"properties\":{\"LogonTime\":\"2022-07-18T09:35:04.153Z\",\"LogonType\":\"5\",\"UserIsAdmin\":\"0\",\"UserName\":\"LOCAL SERVICE\",\"UserPrincipal\":\"\"}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-20%7C996&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-20|996\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-20|996\",\"direction\":\"out\",\"edge_id\":\"KZm:#_CuCKi=crh->=-si;lF2!Z\\\"2?31i[c/pMsGcTg;'O\\\"n,%Ot`@k^R;><W!o^hYdq0U\\\\ss8@LW;Dr/QefJ36YQPI)c#MEVF>'_r\\\"+3`-a]]Rj_09,,cO],pXWF.4E@m!!*'!\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T09:50:33Z\",\"properties\":{\"LogonTime\":\"2022-07-18T09:35:03.448Z\",\"LogonType\":\"5\",\"UserIsAdmin\":\"0\",\"UserName\":\"hbmwcsfghmml-vm$\",\"UserPrincipal\":\"\"}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-90-0-1%7C83212&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-90-0-1|83212\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-90-0-1|83212\",\"direction\":\"out\",\"edge_id\":\"KZm:#_CuCKi=crhVJ-[Hi;lF2!Z\\\"2?31i[c/pMsGcTg;'O\\\"n,%'\\\";HWE\\\\hK)TKK<aJ_dHOl?kYR*ZjLg[:%s&:nZa?<3`=@B<7.3GMe]Lr4RbRbh\\\"YUZQb5=5o'0]OHnK;.LZ4W!!*'!\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T09:50:33Z\",\"properties\":{\"LogonTime\":\"2022-07-18T09:35:04.091Z\",\"LogonType\":\"2\",\"UserIsAdmin\":\"0\",\"UserName\":\"DWM-1\",\"UserPrincipal\":\"\"}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-96-0-0%7C52680&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-96-0-0|52680\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-96-0-0|52680\",\"direction\":\"out\",\"edge_id\":\"KZmd1_CuCKnIlY#k\\\"cr\\\"i;lF2!Z\\\"2?31i[c/pMqqcQBnT*b0)S:;UfOm:O@)ct->@Ja0+LFZCI_&!(eo>-LOP/PtAeWZBOJ1Y0U*]5Pk6ra*Gdk3JG6dZI]\\\\K%f-i6<7Z\\\\<a\\\"o.!!*'!\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T09:50:33Z\",\"properties\":{\"LogonTime\":\"2022-07-18T09:35:03.015Z\",\"LogonType\":\"2\",\"UserIsAdmin\":\"0\",\"UserName\":\"UMFD-0\",\"UserPrincipal\":\"\"}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-96-0-1%7C52710&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-96-0-1|52710\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-96-0-1|52710\",\"direction\":\"out\",\"edge_id\":\"KZm:#_CuCKi=crhVF_]0i;lF2!Z\\\"2?31i[c/pMsGcTg;'O\\\"n+:-Z70;oOc[AT_#DA#)\\\\o6l?kYR*ZjLg[:%s&;P;sa<>![>1Y0U*]5Pk6ra*Gdk3JE`gl\\\\rW5um]HO@mLoXRZ`!!<<'\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T09:50:33Z\",\"properties\":{\"LogonTime\":\"2022-07-18T09:35:03.015Z\",\"LogonType\":\"2\",\"UserIsAdmin\":\"0\",\"UserName\":\"UMFD-1\",\"UserPrincipal\":\"\"}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-90-0-3%7C8097548&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-90-0-3|8097548\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-90-0-3|8097548\",\"direction\":\"out\",\"edge_id\":\"KZm:#_CuCKi=crh->=-si;lF2!Z\\\"2?31i[c/pMsGcTg;'O\\\"n,%Ot`@k^R;><W!o^hYdq0U\\\\ss8@LW;Dr/Qeec'I\\\\&O=;TQ\\\\pl+l#j6k[-LVK2FM\\\"u?D2Gp9Q6rY'',p[XXjU-m[!!!$!rr\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T09:50:33Z\",\"properties\":{\"LogonTime\":\"2022-07-18T09:46:32.374Z\",\"LogonType\":\"2\",\"UserIsAdmin\":\"0\",\"UserName\":\"DWM-3\",\"UserPrincipal\":\"\"}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-96-0-3%7C8093909&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-96-0-3|8093909\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-96-0-3|8093909\",\"direction\":\"out\",\"edge_id\":\"KZl^h_E\\\\N!i=cZ2RUhlECNt@b[/gM#_,sbbB,A3Ghtlkkld<ar0iem:jr5GcAD/b0YKbJWeb+%*4Zq#XCT0`1>+rfg&K$2nq\\\"456ipPR,LVK2FM\\\",e'D/,>KA*-AH?W)cMZ8D@\\\\!!*'!\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T09:50:33Z\",\"properties\":{\"LogonTime\":\"2022-07-18T09:46:32.280Z\",\"LogonType\":\"2\",\"UserIsAdmin\":\"0\",\"UserName\":\"UMFD-3\",\"UserPrincipal\":\"\"}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-21-2334176487-1093172873-1803758148-1000%7C27181909&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-21-2334176487-1093172873-1803758148-1000|27181909\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-21-2334176487-1093172873-1803758148-1000|27181909\",\"direction\":\"out\",\"edge_id\":\"KZmXm^d&;ti=ug_cXi9L%2Vj<G//\\\\X)!b+g[0plFkP=WGiZ@:Q&n7l/jDUH$6=D*A#Pu[4qm=CP>rCr9H#76G(l^ruhDMrs;W&NI%7/thctFPrRiR'U>dJn!rc-Nd4LV<QpK\\\"Wcr;'[^(3$N$YgS#Z(39UD.esk\\\\!<<'\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T19:46:20Z\",\"properties\":{\"LogonTime\":\"2022-07-18T19:46:18.696Z\",\"LogonType\":\"3\",\"UserIsAdmin\":\"1\",\"UserName\":\"Administrator\",\"UserPrincipal\":\"\"}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-90-0-4%7C27200188&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-90-0-4|27200188\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-90-0-4|27200188\",\"direction\":\"out\",\"edge_id\":\"KZm:#_CuCKi=crh2JEf-i;lF2!Z\\\"2?31i[c/pMsGcTg;'O\\\"n,%2C:0]\\\\X=$g:``YO@!CqB3hHnmLW;Dr/QfM\\\"'I\\\\'&W;rlc*hT]$B&%f=p@.eh*\\\\h$J`6O7g=DJY+IgKh[[0$g8!WW6#rr\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T19:46:22Z\",\"properties\":{\"LogonTime\":\"2022-07-18T19:46:21.230Z\",\"LogonType\":\"2\",\"UserIsAdmin\":\"0\",\"UserName\":\"DWM-4\",\"UserPrincipal\":\"\"}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/user-sessions/summary/v1?ids=uses%3A835449907c99453085a924a16e967be5%3AS-1-5-90-0-4%7C27199807&scope=device\",\"id\":\"uses:835449907c99453085a924a16e967be5:S-1-5-90-0-4|27199807\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"S-1-5-90-0-4|27199807\",\"direction\":\"out\",\"edge_id\":\"KZm:#_CuCKi=crh->=*ri;lF2!Z\\\"2?31i[d/pMsGcTg;'O$:\\\"1OYFD\\\"hV;6>9Y+<nfYX,\\\\+fE651\\\\.'H(+`?'$5>\\\\(U:Z!%aA6.b,O_lhHcCESa;hDH`$U42@\\\\cE]Do+ncd#)<1$NL2,rr\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"established_user_session\",\"timestamp\":\"2022-07-18T19:46:23Z\",\"properties\":{\"LogonTime\":\"2022-07-18T19:46:21.198Z\",\"LogonType\":\"2\",\"UserIsAdmin\":\"0\",\"UserName\":\"DWM-4\",\"UserPrincipal\":\"\"}}],\"implicated_by_incident\":[{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3Ac46079f88e0643f3a7a1a75897d193f7&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:c46079f88e0643f3a7a1a75897d193f7\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"c46079f88e0643f3a7a1a75897d193f7\",\"direction\":\"out\",\"edge_id\":\"KZr8O__;KaiK^5&s\\\"4s!gB#-mksHj5MJ\\\"SaJXko@pVK^,s)Sh8#d>)\\\\6K\\\"$3EMAIi4,2N#X(JtF)Cnp[mK8^<UpS&snZ\\\\$>Vlb8-s/Y6=qL6*OR]ZFRf0U3B<<3FrppFLH!j[XcIKKQMs8N\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-18T17:48:23Z\",\"properties\":{}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3Adaf413dba4ef43148167ee6d244ad364&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:daf413dba4ef43148167ee6d244ad364\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"daf413dba4ef43148167ee6d244ad364\",\"direction\":\"out\",\"edge_id\":\"KZr8O__;KaiKY\\\\Sa4=NC.$apdgX(^P-kt!6kQ3cjL[Tp=YP9%^b\\\\#5\\\")%47l\\\\&OGsVL;7N*EJa&?3rh5.<al:R#hPfcdZXP*i-I6nbfTT=2q\\\\`[lS.jT%?;odBji86AJnU(,hl6[\\\"3T,!!*'!\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-19T21:58:21Z\",\"properties\":{}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3A40f764711a7c427e8271ae50d0a10678&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:40f764711a7c427e8271ae50d0a10678\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"40f764711a7c427e8271ae50d0a10678\",\"direction\":\"out\",\"edge_id\":\"KZl^h!\\\\k*Qi@?5',_+fbL.kgFTZ+km#h$$e?=;Xdn\\\\+afUYWS]8-GVUL_b$UfHf-r(lkbc_]#jf.meHIJ2pJ<6h_%[?)^[V)17G,lS3.G^$WjQ+1%!YkIK6p$OKK-VgjU?(CQ<Tb:`hqs8N\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-20T08:12:45Z\",\"properties\":{}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3Ac2f2440936c9498ea05010670774138b&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:c2f2440936c9498ea05010670774138b\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"c2f2440936c9498ea05010670774138b\",\"direction\":\"out\",\"edge_id\":\"KZm-t_CuNdi@E/`rk1usV\\\\'+i\\\\0uqO3P42QqUU_rNSe'_bt49I^bULq^njQ]N]KLD+*'BCRX)#G]/O=-dL6U-*<Zr'^l4D'?hJe0.f25dD?\\\"E0Z]6cdKdoi.m`8#iDo\\\"b\\\\A/:*s$NL2,rr\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-20T17:24:41Z\",\"properties\":{}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3Af9eaf689ecd74afc8fb99211b3b4cd55&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:f9eaf689ecd74afc8fb99211b3b4cd55\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"f9eaf689ecd74afc8fb99211b3b4cd55\",\"direction\":\"out\",\"edge_id\":\"KZqW=\\\"#13RiKjD'D#Li26'c'ng^I<oJO\\\"2AJM]&nIJ@.EUG;eE1(fVZ!Q6i%.gg!.Nn0!WmBGWXHY($921aNKUs!9XT]A6#+IgS:*maj?]mLm]IDfhSrOd;k/=\\\\*h9ksO4dh_3'Le@II!!*'!\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-22T15:34:59Z\",\"properties\":{}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3A9b4ef58cd9c6467290ef240b23ce09e8&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:9b4ef58cd9c6467290ef240b23ce09e8\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"9b4ef58cd9c6467290ef240b23ce09e8\",\"direction\":\"out\",\"edge_id\":\"KZm;n\\\"#1'Hd4K&h7c.g4`&JmPL40Pb6HRphh8%h7bB`'EkPS8Yb\\\\#5WN%9J1DM:/ER'[IuG1aA'?Eq=d<qU/Z/?Kc-=VsUO&$XEOO6;\\\"=^LA8EIH9shZ*''a<=jrnLr->)S'V]b;PA\\\"/!!*'!\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-23T21:05:32Z\",\"properties\":{}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3A1c61fb60a33a4fecb65adcf8e96bbca3&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:1c61fb60a33a4fecb65adcf8e96bbca3\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"1c61fb60a33a4fecb65adcf8e96bbca3\",\"direction\":\"out\",\"edge_id\":\"KZm;n_a\\\"Jmd4K&PSagPDW+/);%K-Qd6CG4t\\\\q/Z*bB`'eCAn\\\\%el8>uC1Dk3VHYj@<9^!%401L'?GR18>el/s*>pJG1QISImU<KfnbfSp/*H?h^!<REkI\\\"-2#\\\\\\\"#AmI4o-,397qNK([R!!*'!\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-23T21:28:21Z\",\"properties\":{}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3A4d4ff61114ad45bea5bb87253dbeeb49&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:4d4ff61114ad45bea5bb87253dbeeb49\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"4d4ff61114ad45bea5bb87253dbeeb49\",\"direction\":\"out\",\"edge_id\":\"KZl`^_a\\\"KXi@BmbBCoIVk\\\\*5+%:+WRU!23%kQ17XJ%c_HXQ!$;M,`5sWl3PC9fFikWI9$^mBGlGpBh'E7gB%\\\"+SIX8Qa&9\\\"B0,:Wa7I'C>oC8hpGuqUT%AS>dZG,,V>XS7!T4MeeFj=O!<<'\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-24T04:01:51Z\",\"properties\":{}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3A068b5e72e5624d39b71e03aa0c385c02&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:068b5e72e5624d39b71e03aa0c385c02\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"068b5e72e5624d39b71e03aa0c385c02\",\"direction\":\"out\",\"edge_id\":\"KZq\\\\t\\\"#13LiKbbDqV,Td=k5mC)0-PqJ`,5aBjffnn\\\\+GP[JmP^(hOn!2Q27k>8rTm`\\\\N`qLL\\\"QJ/&41pV'U+#X4n=^kjB!f.A6'S4T?r0b&tr&;.nD$o@h9]bTK0$!l$Y[`Zda*b231!!<<'\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-24T11:05:05Z\",\"properties\":{}},{\"path\":\"http://falconapi.crowdstrike.com/threatgraph/combined/incidents/summary/v1?ids=inc%3A835449907c99453085a924a16e967be5%3A3ba3560a57994112a66c91e4e4e66f13&scope=device\",\"id\":\"inc:835449907c99453085a924a16e967be5:3ba3560a57994112a66c91e4e4e66f13\",\"device_id\":\"835449907c99453085a924a16e967be5\",\"customer_id\":\"46de5283260647ec8f28def00bffd094\",\"object_id\":\"3ba3560a57994112a66c91e4e4e66f13\",\"direction\":\"out\",\"edge_id\":\"KZl^h!\\\\k*Qi@?5AT=\\\",D6`(M?TZ+km#h$&kn,W(2O71>#cf<TW!+s`8)5L.H[fU1Oe$b$:%P-_P<pK*QP['XpR#A!Tj$4_dmp&pX?]Q1U`j+p'/a(2\\\"k.+TjCEk(&d(`#M5WUh<P[=Cj!<<'\",\"source_vertex_id\":\"aid:835449907c99453085a924a16e967be5:835449907c99453085a924a16e967be5\",\"scope\":\"device\",\"edge_type\":\"implicated_by_incident\",\"timestamp\":\"2022-07-24T13:55:04Z\",\"properties\":{}}]}}}\n",
        "event": {
            "kind": "event"
        },
        "@timestamp": "2022-07-28T15:09:51.000000Z",
        "crowdstrike": {
            "event_type": "Vertex",
            "detect_id": "ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109",
            "customer_id": "5d505aca55a145b3bd234c399201f082",
            "host_id": "9ed90be65f99456c9361141f8cfa39ab",
            "vertex_type": "device",
            "scope": "device",
            "object_id": "9ed90be65f99456c9361141f8cfa39ab",
            "edge": {
                "subject_id": "pid:9ed90be65f99456c9361141f8cfa39ab:17326818154",
                "type": "device"
            }
        },
        "file": {
            "name": "Config.sys"
        },
        "source": {
            "ip": "1.2.3.4",
            "nat": {
                "ip": "4.3.2.1"
            },
            "address": "1.2.3.4"
        },
        "host": {
            "name": "mycomputer",
            "ip": [
                "10.0.4.4"
            ],
            "mac": [
                "00-0d-3a-9b-ed-fd"
            ]
        },
        "cloud": {
            "instance": {
                "id": "9ed90be6-5f99-456c-9361-141f8cfa39ab"
            },
            "account": {
                "id": "35f882a7-80ce-4e98-9efb-56f2382b6856"
            },
            "region": "rdp-east-us"
        },
        "related": {
            "ip": [
                "1.2.3.4",
                "10.0.4.4",
                "4.3.2.1"
            ]
        }
    }
    	
	```


=== "module_event.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"detectionIdString\":\"ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109\",\"eventType\":\"Vertex\",\"edge\":{\"sourceVertexId\":\"pid:9ed90be65f99456c9361141f8cfa39ab:17326818154\",\"type\":\"primary_module\"}},\"event\":{\"customer_id\":\"5d505aca55a145b3bd234c399201f082\",\"device_id\":\"9ed90be65f99456c9361141f8cfa39ab\",\"id\":\"mod:9ed90be65f99456c9361141f8cfa39ab:01ba4719c80b6fe911b091a7c05124b64eeece964e09c058ef8f9805daca546b\",\"object_id\":\"01ba4719c80b6fe911b091a7c05124b64eeece964e09c058ef8f9805daca546b\",\"properties\":{\"MD5HashData\":\"68b329da9893e34099c7d8ad5cb9c940\",\"SHA1HashData\":\"0000000000000000000000000000000000000000\",\"SHA256HashData\":\"01ba4719c80b6fe911b091a7c05124b64eeece964e09c058ef8f9805daca546b\",\"TargetProcessId\":\"26229308171\"},\"scope\":\"device\",\"timestamp\":\"2022-07-30T20:32:53Z\",\"vertex_type\":\"module\"}}\n",
        "event": {
            "kind": "event"
        },
        "@timestamp": "2022-07-30T20:32:53.000000Z",
        "crowdstrike": {
            "event_type": "Vertex",
            "detect_id": "ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109",
            "customer_id": "5d505aca55a145b3bd234c399201f082",
            "host_id": "9ed90be65f99456c9361141f8cfa39ab",
            "vertex_type": "module",
            "scope": "device",
            "object_id": "01ba4719c80b6fe911b091a7c05124b64eeece964e09c058ef8f9805daca546b",
            "edge": {
                "subject_id": "pid:9ed90be65f99456c9361141f8cfa39ab:17326818154",
                "type": "primary_module"
            }
        },
        "process": {
            "pid": 26229308171
        },
        "file": {
            "hash": {
                "sha256": "01ba4719c80b6fe911b091a7c05124b64eeece964e09c058ef8f9805daca546b",
                "sha1": "0000000000000000000000000000000000000000",
                "md5": "68b329da9893e34099c7d8ad5cb9c940"
            }
        },
        "related": {
            "hash": [
                "0000000000000000000000000000000000000000",
                "01ba4719c80b6fe911b091a7c05124b64eeece964e09c058ef8f9805daca546b",
                "68b329da9893e34099c7d8ad5cb9c940"
            ]
        }
    }
    	
	```


=== "process_event.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"detectionIdString\":\"ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109\",\"eventType\":\"Vertex\",\"edge\":{\"sourceVertexId\":\"pid:9ed90be65f99456c9361141f8cfa39ab:17326818154\",\"type\":\"child_process\"}},\"event\":{\"id\":\"pid:f0e3fbf905c14b88adb500a495f9292f:123456789\",\"customer_id\":\"5d505aca55a145b3bd234c399201f082\",\"scope\":\"device\",\"object_id\":\"123456789\",\"device_id\":\"9ed90be65f99456c9361141f8cfa39ab\",\"vertex_type\":\"process\",\"timestamp\":\"2022-07-30T20:22:29Z\",\"properties\":{\"AllocateVirtualMemoryCount\":\"0\",\"ArchiveFileWrittenCount\":\"0\",\"AsepWrittenCount\":\"0\",\"AuthenticationId\":\"55555555\",\"BinaryExecutableWrittenCount\":\"0\",\"CLICreationCount\":\"0\",\"CommandLine\":\"taskhostw.exe Install $(Arg0)\",\"ConHostId\":\"856\",\"ConHostProcessId\":\"58913928\",\"ConfigBuild\":\"1007.3.0015316.10\",\"ConfigStateHash\":\"2146686153\",\"ContextProcessId\":\"8322695771\",\"ContextThreadId\":\"409412655947\",\"CycleTime\":\"224272919\",\"DirectoryCreatedCount\":\"0\",\"DirectoryEnumeratedCount\":\"0\",\"DnsRequestCount\":\"0\",\"DocumentFileWrittenCount\":\"0\",\"ExeAndServiceCount\":\"0\",\"ExecutableDeletedCount\":\"0\",\"ExitCode\":\"0\",\"FileDeletedCount\":\"0\",\"GenericFileWrittenCount\":\"0\",\"ImageFileName\":\"\\\\Device\\\\HarddiskVolume2\\\\Windows\\\\System32\\\\taskhostw.exe\",\"ImageSubsystem\":\"2\",\"InjectedDllCount\":\"0\",\"InjectedThreadCount\":\"0\",\"IntegrityLevel\":\"8192\",\"KernelTime\":\"468750\",\"MaxThreadCount\":\"8\",\"ModuleLoadCount\":\"25\",\"NetworkBindCount\":\"0\",\"NetworkCapableAsepWriteCount\":\"0\",\"NetworkCloseCount\":\"0\",\"NetworkConnectCount\":\"0\",\"NetworkConnectCountUdp\":\"0\",\"NetworkListenCount\":\"0\",\"NetworkModuleLoadCount\":\"0\",\"NetworkRecvAcceptCount\":\"0\",\"NewExecutableWrittenCount\":\"0\",\"ParentAuthenticationId\":\"81349050\",\"ParentProcessId\":\"58913928\",\"PrivilegedProcessHandleCount\":\"0\",\"ProcessCreateFlags\":\"525316\",\"ProcessEndTime\":\"133027667380241770\",\"ProcessEndTime_formatted\":\"2022-07-20T04:58:58.024177Z\",\"ProcessParameterFlags\":\"24577\",\"ProcessStartTime\":\"133027667360825182\",\"ProcessStartTime_formatted\":\"2022-07-20T04:58:56.082518Z\",\"ProcessSxsFlags\":\"64\",\"ProtectVirtualMemoryCount\":\"0\",\"QueueApcCount\":\"0\",\"RawProcessId\":\"14264\",\"RegKeySecurityDecreasedCount\":\"0\",\"RemovableDiskFileWrittenCount\":\"0\",\"RunDllInvocationCount\":\"0\",\"SHA256HashData\":\"f1e8525fe2fbff523b2e56472231d4ac9aa102ba614694213e59b5eb2590cc15\",\"ScreenshotsTakenCount\":\"0\",\"ScriptEngineInvocationCount\":\"0\",\"ServiceEventCount\":\"0\",\"SessionId\":\"5\",\"SetThreadContextCount\":\"0\",\"SnapshotFileOpenCount\":\"0\",\"SourceProcessId\":\"58913928\",\"SourceThreadId\":\"409387743461\",\"SuspectStackCount\":\"0\",\"SuspiciousCredentialModuleLoadCount\":\"0\",\"SuspiciousDnsRequestCount\":\"0\",\"SuspiciousFontLoadCount\":\"0\",\"SuspiciousRawDiskReadCount\":\"0\",\"Tags\":\"41, 53, 54, 55, 151, 874, 924, 12094627905582, 12094627906234\",\"TokenType\":\"2\",\"UnsignedModuleLoadCount\":\"0\",\"UserMemoryAllocateExecutableCount\":\"0\",\"UserMemoryAllocateExecutableRemoteCount\":\"0\",\"UserMemoryProtectExecutableCount\":\"0\",\"UserMemoryProtectExecutableRemoteCount\":\"0\",\"UserSid\":\"S-1-0-0\",\"UserSidHex\":\"0000000000000000\",\"UserTime\":\"312500\",\"WindowFlags\":\"128\",\"WindowTitle\":\"C:\\\\Windows\\\\system32\\\\taskhostw.exe\",\"platform\":\"0\",\"processTerminated\":\"true\"}}}\n",
        "event": {
            "kind": "event"
        },
        "@timestamp": "2022-07-30T20:22:29.000000Z",
        "crowdstrike": {
            "event_type": "Vertex",
            "detect_id": "ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109",
            "customer_id": "5d505aca55a145b3bd234c399201f082",
            "host_id": "9ed90be65f99456c9361141f8cfa39ab",
            "vertex_type": "process",
            "scope": "device",
            "object_id": "123456789",
            "edge": {
                "subject_id": "pid:9ed90be65f99456c9361141f8cfa39ab:17326818154",
                "type": "child_process"
            }
        },
        "user": {
            "id": "S-1-0-0"
        },
        "process": {
            "command_line": "taskhostw.exe Install $(Arg0)",
            "executable": "\\Device\\HarddiskVolume2\\Windows\\System32\\taskhostw.exe",
            "name": "taskhostw.exe",
            "title": "C:\\Windows\\system32\\taskhostw.exe",
            "working_directory": "\\Device\\HarddiskVolume2\\Windows\\System32",
            "pid": 14264,
            "parent": {
                "pid": 58913928
            },
            "exit_code": 0
        },
        "file": {
            "hash": {
                "sha256": "f1e8525fe2fbff523b2e56472231d4ac9aa102ba614694213e59b5eb2590cc15"
            }
        },
        "related": {
            "hash": [
                "f1e8525fe2fbff523b2e56472231d4ac9aa102ba614694213e59b5eb2590cc15"
            ]
        }
    }
    	
	```


=== "stream_started.json"

    ```json
	
    {
        "message": "{\"metadata\": {\"customerIDString\": \"46de5283260647ec8f28def00bffd094\", \"offset\": 174, \"eventType\": \"AuthActivityAuditEvent\", \"eventCreationTime\": 1657110865303, \"version\": \"1.0\"}, \"event\": {\"UserId\": \"api-client-id:00000000000000000000000000000000\", \"UserIp\": \"185.162.177.26\", \"OperationName\": \"streamStarted\", \"ServiceName\": \"Crowdstrike Streaming API\", \"Success\": true, \"UTCTimestamp\": 1657110865, \"AuditKeyValues\": [{\"Key\": \"partition\", \"ValueString\": \"0\"}, {\"Key\": \"offset\", \"ValueString\": \"-1\"}, {\"Key\": \"appId\", \"ValueString\": \"sio-00000\"}, {\"Key\": \"eventType\", \"ValueString\": \"All event type(s)\"}, {\"Key\": \"APIClientID\", \"ValueString\": \"00000000000000000000000000000000\"}]}}",
        "event": {
            "kind": "event",
            "category": [
                "session"
            ],
            "type": [
                "start"
            ]
        },
        "@timestamp": "2022-07-06T12:34:25.303000Z",
        "crowdstrike": {
            "event_type": "AuthActivityAuditEvent",
            "operation_name": "streamStarted"
        },
        "source": {
            "ip": "185.162.177.26",
            "address": "185.162.177.26"
        },
        "service": {
            "name": "Crowdstrike Streaming API"
        },
        "user": {
            "id": "api-client-id:00000000000000000000000000000000"
        },
        "related": {
            "ip": [
                "185.162.177.26"
            ]
        }
    }
    	
	```


=== "stream_stopped.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"customerIDString\":\"46de5283260647ec8f28def00bffd094\",\"offset\":200,\"eventType\":\"AuthActivityAuditEvent\",\"eventCreationTime\":1657203917516,\"version\":\"1.0\"},\"event\":{\"UserId\":\"api-client-id:00000000000000000000000000000000\",\"UserIp\":\"185.162.177.26\",\"OperationName\":\"streamStopped\",\"ServiceName\":\"Crowdstrike Streaming API\",\"Success\":true,\"UTCTimestamp\":1657203917,\"AuditKeyValues\":[{\"Key\":\"APIClientID\",\"ValueString\":\"00000000000000000000000000000000\"},{\"Key\":\"partition\",\"ValueString\":\"0\"},{\"Key\":\"offset\",\"ValueString\":\"-1\"},{\"Key\":\"appId\",\"ValueString\":\"sio-00000\"},{\"Key\":\"eventType\",\"ValueString\":\"All event type(s)\"}]}}",
        "event": {
            "kind": "event",
            "category": [
                "session"
            ],
            "type": [
                "stop"
            ]
        },
        "@timestamp": "2022-07-07T14:25:17.516000Z",
        "crowdstrike": {
            "event_type": "AuthActivityAuditEvent",
            "operation_name": "streamStopped"
        },
        "source": {
            "ip": "185.162.177.26",
            "address": "185.162.177.26"
        },
        "service": {
            "name": "Crowdstrike Streaming API"
        },
        "user": {
            "id": "api-client-id:00000000000000000000000000000000"
        },
        "related": {
            "ip": [
                "185.162.177.26"
            ]
        }
    }
    	
	```


=== "user_activity_audit.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"customerIDString\":\"46de5283260647ec8f28def00bffd094\",\"offset\":747,\"eventType\":\"UserActivityAuditEvent\",\"eventCreationTime\":1657614940000,\"version\":\"1.0\"},\"event\":{\"UserId\":\"foo.bar@sekoia.fr\",\"UserIp\":\"185.162.177.26\",\"OperationName\":\"detection_update\",\"ServiceName\":\"detections\",\"AuditKeyValues\":[{\"Key\":\"detection_id\",\"ValueString\":\"ldt:5418788591a444d1b45c2b39d3b07b50:21482411386\"},{\"Key\":\"new_state\",\"ValueString\":\"closed\"},{\"Key\":\"assigned_to\",\"ValueString\":\"Foo Bar\"},{\"Key\":\"assigned_to_uid\",\"ValueString\":\"foo.bar@sekoia.fr\"}],\"UTCTimestamp\":1657614940}}",
        "event": {
            "kind": "event",
            "type": [
                "change"
            ],
            "category": [
                "configuration"
            ]
        },
        "@timestamp": "2022-07-12T08:35:40.000000Z",
        "crowdstrike": {
            "event_type": "UserActivityAuditEvent",
            "operation_name": "detection_update"
        },
        "source": {
            "ip": "185.162.177.26",
            "address": "185.162.177.26"
        },
        "service": {
            "name": "detections"
        },
        "user": {
            "id": "foo.bar@sekoia.fr"
        },
        "related": {
            "ip": [
                "185.162.177.26"
            ]
        }
    }
    	
	```


=== "user_event.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"detectionIdString\":\"ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109\",\"eventType\":\"Vertex\",\"edge\":{\"sourceVertexId\":\"pid:9ed90be65f99456c9361141f8cfa39ab:17326818154\",\"type\":\"user\"}},\"event\":{\"customer_id\":\"5d505aca55a145b3bd234c399201f082\",\"device_id\":\"9ed90be65f99456c9361141f8cfa39ab\",\"id\":\"uid:9ed90be65f99456c9361141f8cfa39ab:S-1-0-0\",\"object_id\":\"S-1-0-0\",\"properties\":{\"AuthenticationId\":\"999\",\"AuthenticationPackage\":\"NTLM\",\"ConfigBuild\":\"1007.3.0015316.10\",\"ConfigStateHash\":\"755481218\",\"ContextProcessId\":\"8941136\",\"ContextThreadId\":\"53626098020\",\"LogonDomain\":\"DOMAIN\",\"LogonId\":\"999\",\"LogonServer\":\"\",\"LogonTime\":\"2022-07-18T09:35:00.180Z\",\"LogonType\":\"0\",\"PasswordLastSet\":\"1601-01-01T00:00:00.000Z\",\"RemoteAccount\":\"0\",\"SessionId\":\"0\",\"UserCanonical\":\"\",\"UserFlags\":\"0\",\"UserIsAdmin\":\"0\",\"UserLogonFlags\":\"12\",\"UserName\":\"myuser\",\"UserPrincipal\":\"\",\"UserSid\":\"S-1-0-0\",\"UserSidHex\":\"0000000000000000\"},\"scope\":\"device\",\"timestamp\":\"2022-07-30T20:42:28Z\",\"vertex_type\":\"user\"}}\n",
        "event": {
            "kind": "event"
        },
        "@timestamp": "2022-07-30T20:42:28.000000Z",
        "crowdstrike": {
            "event_type": "Vertex",
            "detect_id": "ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109",
            "customer_id": "5d505aca55a145b3bd234c399201f082",
            "host_id": "9ed90be65f99456c9361141f8cfa39ab",
            "vertex_type": "user",
            "scope": "device",
            "object_id": "S-1-0-0",
            "edge": {
                "subject_id": "pid:9ed90be65f99456c9361141f8cfa39ab:17326818154",
                "type": "user"
            }
        },
        "user": {
            "domain": "DOMAIN",
            "name": "myuser",
            "id": "S-1-0-0"
        },
        "action": {
            "properties": {
                "LogonType": "0",
                "LogonId": "999"
            }
        },
        "related": {
            "user": [
                "myuser"
            ]
        }
    }
    	
	```


=== "user_session_event.json"

    ```json
	
    {
        "message": "{\"metadata\":{\"detectionIdString\":\"ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109\",\"eventType\":\"Vertex\",\"edge\":{\"sourceVertexId\":\"pid:9ed90be65f99456c9361141f8cfa39ab:17326818154\",\"type\":\"user_session\"}},\"event\":{\"customer_id\":\"5d505aca55a145b3bd234c399201f082\",\"device_id\":\"9ed90be65f99456c9361141f8cfa39ab\",\"id\":\"uses:9ed90be65f99456c9361141f8cfa39ab:S-1-0-0|999\",\"object_id\":\"S-1-0-0|999\",\"properties\":{\"AuthenticationId\":\"999\",\"AuthenticationPackage\":\"NTLM\",\"ConfigStateHash\":\"755481218\",\"ContextThreadId\":\"53626098020\",\"LogonDomain\":\"DOMAIN\",\"LogonId\":\"999\",\"LogonServer\":\"\",\"LogonTime\":\"2022-07-18T09:35:00.180Z\",\"LogonType\":\"0\",\"PasswordLastSet\":\"1601-01-01T00:00:00.000Z\",\"RemoteAccount\":\"0\",\"SessionId\":\"0\",\"UserCanonical\":\"\",\"UserFlags\":\"0\",\"UserIsAdmin\":\"0\",\"UserLogonFlags\":\"12\",\"UserName\":\"mysuer\",\"UserPrincipal\":\"\",\"UserSid\":\"S-1-0-0\"},\"scope\":\"device\",\"timestamp\":\"2022-07-30T20:27:27Z\",\"vertex_type\":\"user-session\"}}\n",
        "event": {
            "kind": "event"
        },
        "@timestamp": "2022-07-30T20:27:27.000000Z",
        "crowdstrike": {
            "event_type": "Vertex",
            "detect_id": "ldt:9ed90be65f99456c9361141f8cfa39ab:17212155109",
            "customer_id": "5d505aca55a145b3bd234c399201f082",
            "host_id": "9ed90be65f99456c9361141f8cfa39ab",
            "vertex_type": "user-session",
            "scope": "device",
            "object_id": "S-1-0-0|999",
            "edge": {
                "subject_id": "pid:9ed90be65f99456c9361141f8cfa39ab:17326818154",
                "type": "user_session"
            }
        },
        "user": {
            "domain": "DOMAIN",
            "name": "mysuer",
            "id": "S-1-0-0"
        },
        "action": {
            "properties": {
                "LogonType": "0",
                "LogonId": "999"
            }
        },
        "related": {
            "user": [
                "mysuer"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`action.properties.LogonId` | `keyword` | The id of the Logon |
|`action.properties.LogonType` | `keyword` | The type of the Logon |
|`agent.id` | `keyword` | Unique identifier of this agent. |
|`cloud.account.id` | `keyword` | The cloud account or organization id. |
|`cloud.instance.id` | `keyword` | Instance ID of the host machine. |
|`cloud.region` | `keyword` | Region in which this host, resource, or service is located. |
|`crowdstrike.customer_id` | `keyword` | Customer ID (cid) |
|`crowdstrike.detect_description` | `keyword` | A description of what an adversary was trying to do in the environment and guidance on how to begin an investigation. |
|`crowdstrike.detect_id` | `keyword` | The Detection ID for the detection. Can be used in other APIs, such as Detection Resolution and ThreatGraph. |
|`crowdstrike.edge.subject_id` | `keyword` | The identifier of a parent vertex in the graph exploration |
|`crowdstrike.edge.type` | `keyword` | The type of relationship with the subject |
|`crowdstrike.event_type` | `keyword` | Type of the event |
|`crowdstrike.host_id` | `keyword` | The crowdstrike identifier of the host |
|`crowdstrike.incident_end` | `date` | Time of the latest activity in the incident |
|`crowdstrike.incident_id` | `keyword` | The incident ID of the incident |
|`crowdstrike.incident_start` | `date` | Time of the first activity in the incident |
|`crowdstrike.object_id` | `keyword` | The identifier of a vertex |
|`crowdstrike.operation_name` | `keyword` | Operation name |
|`crowdstrike.scope` | `keyword` | The scope of a vertex |
|`crowdstrike.state` | `keyword` | Shows if the incident is still active. open = the incident is still active, closed = the incident is not active |
|`crowdstrike.vertex_type` | `keyword` | The type of the vertex |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.port` | `long` | Port of the destination. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.hash.md5` | `keyword` | MD5 hash. |
|`file.hash.sha1` | `keyword` | SHA1 hash. |
|`file.hash.sha256` | `keyword` | SHA256 hash. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`host.ip` | `ip` | Host ip addresses. |
|`host.mac` | `keyword` | Host MAC addresses. |
|`host.name` | `keyword` | Name of the host. |
|`process.command_line` | `wildcard` | Full command line that started the process. |
|`process.end` | `date` | The time the process ended. |
|`process.executable` | `keyword` | Absolute path to the process executable. |
|`process.exit_code` | `long` | The exit code of the process. |
|`process.name` | `keyword` | Process name. |
|`process.parent.command_line` | `wildcard` | Full command line that started the process. |
|`process.parent.executable` | `keyword` | Absolute path to the process executable. |
|`process.parent.name` | `keyword` | Process name. |
|`process.parent.pid` | `long` | Process id. |
|`process.parent.working_directory` | `keyword` | The working directory of the process. |
|`process.pid` | `long` | Process id. |
|`process.start` | `date` | The time the process started. |
|`process.title` | `keyword` | Process title. |
|`process.working_directory` | `keyword` | The working directory of the process. |
|`service.name` | `keyword` | Name of the service. |
|`source.ip` | `ip` | IP address of the source. |
|`source.nat.ip` | `ip` | Source NAT ip |
|`source.port` | `long` | Port of the source. |
|`threat.tactic.name` | `keyword` | Threat tactic. |
|`threat.technique.name` | `keyword` | Threat technique name. |
|`user.domain` | `keyword` | Name of the directory the user is a member of. |
|`user.id` | `keyword` | Unique identifier of the user. |
|`user.name` | `keyword` | Short name or login of the user. |
|`user.roles` | `keyword` | Array of user roles at the time of the event. |

