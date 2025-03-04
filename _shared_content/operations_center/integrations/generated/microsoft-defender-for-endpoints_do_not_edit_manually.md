
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Binary file metadata` | Microsoft Defender for Endpoint monitors files |
| `Disk forensics` | Microsoft Defender for Endpoint monitors devices |
| `File monitoring` | Microsoft Defender for Endpoint monitors files |
| `Host network interface` | Microsoft Defender for Endpoint monitors devices |
| `Kernel drivers` | Microsoft Defender for Endpoint monitors processes |
| `Loaded DLLs` | Microsoft Defender for Endpoint monitors processes |
| `Named Pipes` | Microsoft Defender for Endpoint monitors processes |
| `PowerShell logs` | Microsoft Defender for Endpoint monitors processes |
| `Process command-line parameters` | Microsoft Defender for Endpoint monitors processes |
| `Process monitoring` | Microsoft Defender for Endpoint monitors processes |
| `Process use of network` | Microsoft Defender for Endpoint monitors processes |
| `Services` | Microsoft Defender for Endpoint monitors processes |
| `Windows event logs` | Microsoft Defender for Endpoint watch events logs |
| `Windows Registry` | Microsoft Defender for Endpoint monitors the registry |
| `WMI Objects` | Microsoft Defender for Endpoint monitors processes |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `alert`, `enrichment`, `event` |
| Category | `authentication`, `connection`, `email`, `file`, `host`, `iam`, `network`, `process`, `threat` |
| Type | `indicator`, `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "test_detection_source.json"

    ```json
	
    {
        "message": "{\"time\":\"2022-09-02T22:06:00.6652718Z\",\"tenantId\":\"16ed4fbf-027f-47b3-8d1a-a342781dd2d2\",\"operationName\":\"Publish\",\"category\":\"AdvancedHunting-AlertInfo\",\"properties\":{\"AlertId\":\"da637977531594995313_968283104\",\"Timestamp\":\"2022-09-02T22:04:16.134644Z\",\"Title\":\"'Lodi' unwanted software was prevented\",\"ServiceSource\":\"Microsoft Defender for Endpoint\",\"Category\":\"DefenseEvasion\",\"Severity\":\"Informational\",\"DetectionSource\":\"Antivirus\",\"MachineGroup\":\"Windows 10 - remediate threats automatically\",\"AttackTechniques\":\"\"}}",
        "event": {
            "kind": "alert",
            "type": [
                "info"
            ],
            "dataset": "alert_info",
            "category": [
                "threat"
            ]
        },
        "@timestamp": "2022-09-02T22:06:00.665271Z",
        "service": {
            "name": "Microsoft Defender for Endpoint",
            "type": "Antivirus"
        },
        "action": {
            "properties": {
                "ServiceSource": "Microsoft Defender for Endpoint"
            }
        },
        "microsoft": {
            "defender": {
                "alert": {
                    "id": "da637977531594995313_968283104",
                    "title": "'Lodi' unwanted software was prevented"
                },
                "threat": {
                    "category": "DefenseEvasion",
                    "severity": "Informational"
                }
            }
        }
    }
    	
	```


=== "test_device_event.json"

    ```json
	
    {
        "message": "{\"time\":\"2022-09-01T07:28:59.5127177Z\",\"tenantId\":\"5ac3ff49-0e19-4600-9ad1-333e64e3b5cc\",\"operationName\":\"Publish\",\"category\":\"AdvancedHunting-DeviceEvents\",\"properties\":{\"AccountSid\":null,\"AccountDomain\":null,\"AccountName\":null,\"LogonId\":null,\"FileName\":null,\"FolderPath\":null,\"MD5\":null,\"SHA1\":null,\"FileSize\":null,\"SHA256\":null,\"ProcessCreationTime\":null,\"ProcessTokenElevation\":null,\"RemoteUrl\":null,\"RegistryKey\":null,\"RegistryValueName\":null,\"RegistryValueData\":null,\"RemoteDeviceName\":null,\"FileOriginIP\":null,\"FileOriginUrl\":null,\"LocalIP\":\"1.2.3.4\",\"LocalPort\":null,\"RemoteIP\":\"5.6.7.8\",\"RemotePort\":null,\"ProcessId\":null,\"ProcessCommandLine\":null,\"AdditionalFields\":\"{\\\"BaseAddress\\\":2098738167808,\\\"RegionSize\\\":262144,\\\"ProtectionMask\\\":64}\",\"ActionType\":\"NtAllocateVirtualMemoryApiCall\",\"InitiatingProcessVersionInfoCompanyName\":\"Google\",\"InitiatingProcessVersionInfoProductName\":\"Software Reporter Tool\",\"InitiatingProcessVersionInfoProductVersion\":\"102.286.200\",\"InitiatingProcessVersionInfoInternalFileName\":\"software_reporter_tool_exe\",\"InitiatingProcessVersionInfoOriginalFileName\":\"software_reporter_tool.exe\",\"InitiatingProcessVersionInfoFileDescription\":\"Software Reporter Tool\",\"InitiatingProcessFolderPath\":\"c:\\\\users\\\\USER\\\\appdata\\\\local\\\\google\\\\chrome\\\\user data\\\\swreporter\\\\102.286.200\\\\software_reporter_tool.exe\",\"InitiatingProcessFileName\":\"software_reporter_tool.exe\",\"InitiatingProcessFileSize\":14687048,\"InitiatingProcessMD5\":\"51a9cac9c4e8da44ffd7502be17604ee\",\"InitiatingProcessSHA256\":\"6fe5e57df8d132eaf06f9134461dd172e36cf01679f13eb0f6e70c1f21b18323\",\"InitiatingProcessSHA1\":\"44543e0c6f30415c670c1322e61ca68602d58708\",\"InitiatingProcessLogonId\":121834210,\"InitiatingProcessAccountSid\":\"S-1-00-1-1111111-2222222222-3333333333-4444444444\",\"InitiatingProcessAccountDomain\":\"intranet\",\"InitiatingProcessAccountName\":\"group1\",\"InitiatingProcessAccountUpn\":\"user@example.org\",\"InitiatingProcessAccountObjectId\":\"9d6c8861-bc27-4c1c-b5d7-aa00401d0fd2\",\"InitiatingProcessCreationTime\":\"2022-09-01T06:56:23.7887846Z\",\"InitiatingProcessId\":1664,\"InitiatingProcessCommandLine\":\"\\\"software_reporter_tool.exe\\\" --use-crash-handler-with-id=\\\"\\\\\\\\.\\\\pipe\\\\crashpad_11111_XXXXXXXXXXXXXXXX\\\" --sandboxed-process-id=2 --init-done-notifier=804 --sandbox-mojo-pipe-token=********** --mojo-platform-channel-handle=780 --engine=2\",\"InitiatingProcessParentCreationTime\":\"2022-09-01T06:56:23.595229Z\",\"InitiatingProcessParentId\":15532,\"InitiatingProcessParentFileName\":\"software_reporter_tool.exe\",\"DeviceId\":\"1111111111111111111111111111111111111111\",\"AppGuardContainerId\":\"\",\"MachineGroup\":\"UnassignedGroup\",\"Timestamp\":\"2022-09-01T07:09:47.4980566Z\",\"DeviceName\":\"test.lab\",\"ReportId\":104061}}",
        "event": {
            "kind": "event",
            "type": [
                "info"
            ],
            "dataset": "device_events",
            "category": [
                "host"
            ]
        },
        "@timestamp": "2022-09-01T07:28:59.512717Z",
        "host": {
            "id": "1111111111111111111111111111111111111111",
            "name": "test.lab"
        },
        "process": {
            "pid": 1664,
            "start": "2022-09-01T06:56:23.7887846Z",
            "executable": "software_reporter_tool.exe",
            "command_line": "\"software_reporter_tool.exe\" --use-crash-handler-with-id=\"\\\\.\\pipe\\crashpad_11111_XXXXXXXXXXXXXXXX\" --sandboxed-process-id=2 --init-done-notifier=804 --sandbox-mojo-pipe-token=********** --mojo-platform-channel-handle=780 --engine=2",
            "working_directory": "c:\\users\\USER\\appdata\\local\\google\\chrome\\user data\\swreporter\\102.286.200",
            "user": {
                "domain": "intranet",
                "name": "group1",
                "id": "S-1-00-1-1111111-2222222222-3333333333-4444444444",
                "email": "user@example.org"
            },
            "parent": {
                "pid": 15532,
                "executable": "software_reporter_tool.exe",
                "start": "2022-09-01T06:56:23.595229Z"
            },
            "args": [
                "--use-crash-handler-with-id=\"\\\\.\\pipe\\crashpad_11111_XXXXXXXXXXXXXXXX\"",
                "--sandboxed-process-id=2",
                "--init-done-notifier=804",
                "--sandbox-mojo-pipe-token=**********",
                "--mojo-platform-channel-handle=780",
                "--engine=2"
            ]
        },
        "action": {
            "type": "NtAllocateVirtualMemoryApiCall",
            "properties": {
                "InitiatingProcessAccountObjectId": "9d6c8861-bc27-4c1c-b5d7-aa00401d0fd2",
                "InitiatingProcessFileSize": 14687048,
                "InitiatingProcessLogonId": "121834210",
                "InitiatingProcessVersionInfoCompanyName": "Google",
                "InitiatingProcessVersionInfoFileDescription": "Software Reporter Tool",
                "InitiatingProcessVersionInfoInternalFileName": "software_reporter_tool_exe",
                "InitiatingProcessVersionInfoOriginalFileName": "software_reporter_tool.exe",
                "InitiatingProcessVersionInfoProductName": "Software Reporter Tool",
                "InitiatingProcessVersionInfoProductVersion": "102.286.200"
            }
        },
        "microsoft": {
            "defender": {
                "report": {
                    "id": "104061"
                }
            }
        },
        "source": {
            "ip": "1.2.3.4",
            "address": "1.2.3.4"
        },
        "destination": {
            "ip": "5.6.7.8",
            "address": "5.6.7.8"
        },
        "related": {
            "ip": [
                "1.2.3.4",
                "5.6.7.8"
            ]
        }
    }
    	
	```


=== "test_device_file_certificate_info.json"

    ```json
	
    {
        "message": "{\"time\":\"2022-09-02T13:12:14.2082552Z\",\"tenantId\":\"16ed4fbf-027f-47b3-8d1a-a342781dd2d2\",\"operationName\":\"Publish\",\"category\":\"AdvancedHunting-DeviceFileCertificateInfo\",\"properties\":{\"SHA1\":\"4334f41d684200d1a52c977417f5ba1eba4969b5\",\"IsSigned\":true,\"IsRootSignerMicrosoft\":true,\"Signer\":\"Microsoft Windows\",\"SignerHash\":\"fe51e838a087bb561bbb2dd9ba20143384a03b3f\",\"Issuer\":\"Microsoft Windows Production PCA 2011\",\"IssuerHash\":\"580a6f4cc4e4b669b9ebdc1b2b3e087b80d0678d\",\"SignatureType\":\"Catalog\",\"IsTrusted\":true,\"CertificateCreationTime\":\"2021-09-02T18:23:41Z\",\"CertificateExpirationTime\":\"2022-09-01T18:23:41Z\",\"CertificateCountersignatureTime\":\"2022-07-06T05:55:26.23Z\",\"CrlDistributionPointUrls\":\"[\\\"http://www.microsoft.com/pkiops/crl/MicWinProPCA2011_2011-10-19.crl\\\"]\",\"CertificateSerialNumber\":\"330000033c89c66a7b45bb1fbd00000000033c\",\"DeviceId\":\"db1b7a6a38796c8d49f7746d3ab2252b53b45c80\",\"MachineGroup\":\"Windows 10 - remediate threats automatically\",\"Timestamp\":\"2022-09-02T13:10:10.7177Z\",\"DeviceName\":\"test.lab\",\"ReportId\":20370}}\n",
        "event": {
            "kind": "event",
            "type": [
                "info"
            ],
            "dataset": "device_file_certificate_info",
            "category": [
                "file"
            ]
        },
        "@timestamp": "2022-09-02T13:12:14.208255Z",
        "file": {
            "hash": {
                "sha1": "4334f41d684200d1a52c977417f5ba1eba4969b5"
            },
            "x509": {
                "serial_number": "330000033c89c66a7b45bb1fbd00000000033c",
                "not_after": "2022-09-01T18:23:41Z"
            }
        },
        "host": {
            "id": "db1b7a6a38796c8d49f7746d3ab2252b53b45c80",
            "name": "test.lab"
        },
        "microsoft": {
            "defender": {
                "report": {
                    "id": "20370"
                },
                "certificate": {
                    "is_signed": true,
                    "is_trusted": true,
                    "is_root_signer_microsort": true,
                    "signature_type": "Catalog",
                    "issuer": "Microsoft Windows Production PCA 2011",
                    "signer": "Microsoft Windows",
                    "crl": {
                        "urls": [
                            "http://www.microsoft.com/pkiops/crl/MicWinProPCA2011_2011-10-19.crl"
                        ]
                    },
                    "created_at": "2021-09-02T18:23:41Z",
                    "counter_signed_at": "2022-07-06T05:55:26.23Z"
                }
            }
        },
        "related": {
            "hash": [
                "4334f41d684200d1a52c977417f5ba1eba4969b5"
            ]
        }
    }
    	
	```


=== "test_device_file_event.json"

    ```json
	
    {
        "message": "{\"time\":\"2022-09-01T07:49:40.4279379Z\",\"tenantId\":\"5ac3ff49-0e19-4600-9ad1-333e64e3b5cc\",\"operationName\":\"Publish\",\"category\":\"AdvancedHunting-DeviceFileEvents\",\"properties\":{\"PreviousFileName\":null,\"FileName\":\"OneDriveFileLauncher.exe\",\"FolderPath\":\"C:\\\\Users\\\\USER\\\\AppData\\\\Local\\\\Microsoft\\\\OneDrive\\\\22.161.0731.0002\",\"PreviousFolderPath\":null,\"SHA1\":null,\"SHA256\":null,\"MD5\":null,\"FileSize\":null,\"FileOriginReferrerUrl\":null,\"FileOriginUrl\":null,\"FileOriginIP\":null,\"SensitivityLabel\":null,\"SensitivitySubLabel\":null,\"IsAzureInfoProtectionApplied\":null,\"ShareName\":null,\"RequestSourceIP\":null,\"RequestSourcePort\":null,\"RequestProtocol\":null,\"RequestAccountName\":null,\"RequestAccountDomain\":null,\"RequestAccountSid\":null,\"AdditionalFields\":null,\"ActionType\":\"FileDeleted\",\"InitiatingProcessVersionInfoCompanyName\":\"Microsoft Corporation\",\"InitiatingProcessVersionInfoProductName\":\"Microsoft OneDrive\",\"InitiatingProcessVersionInfoProductVersion\":\"22.166.0807.0002\",\"InitiatingProcessVersionInfoInternalFileName\":\"OneDriveSetup.exe\",\"InitiatingProcessVersionInfoOriginalFileName\":\"OneDriveSetup.exe\",\"InitiatingProcessVersionInfoFileDescription\":\"Microsoft OneDrive (64 bit) Setup\",\"InitiatingProcessFolderPath\":\"c:\\\\users\\\\USER\\\\appdata\\\\local\\\\microsoft\\\\onedrive\\\\update\\\\onedrivesetup.exe\",\"InitiatingProcessFileSize\":56824728,\"InitiatingProcessMD5\":\"9a3af3a9ce0217bccce1d161e0b6bfde\",\"InitiatingProcessSHA256\":\"30204bef93d692fbcbf7475b154e3f65d3aace6f8f030af9e412f3d9e8d9a595\",\"InitiatingProcessSHA1\":\"8f6ebe4a51ce4b5f76f4d896a6e289e69f91a264\",\"InitiatingProcessAccountSid\":\"S-1-00-1-1111111-2222222222-3333333333-4444444444\",\"InitiatingProcessAccountDomain\":\"intranet\",\"InitiatingProcessAccountName\":\"group1\",\"InitiatingProcessAccountUpn\":\"user@example.org\",\"InitiatingProcessAccountObjectId\":\"9d6c8861-bc27-4c1c-b5d7-aa00401d0fd2\",\"InitiatingProcessCreationTime\":\"2022-09-01T07:46:34.0214941Z\",\"InitiatingProcessId\":27512,\"InitiatingProcessFileName\":\"OneDriveSetup.exe\",\"InitiatingProcessCommandLine\":\"OneDriveSetup.exe /update /restart /updateSource:ODU /peruser /childprocess /extractFilesWithLessThreadCount /renameReplaceOneDriveExe /renameReplaceODSUExe /removeNonCurrentVersions /enableODSUReportingMode \",\"InitiatingProcessParentCreationTime\":\"2022-09-01T07:46:33.5858992Z\",\"InitiatingProcessParentId\":588,\"InitiatingProcessParentFileName\":\"OneDriveSetup.exe\",\"InitiatingProcessIntegrityLevel\":\"Medium\",\"InitiatingProcessTokenElevation\":\"TokenElevationTypeDefault\",\"DeviceId\":\"1111111111111111111111111111111111111111\",\"AppGuardContainerId\":\"\",\"MachineGroup\":\"UnassignedGroup\",\"Timestamp\":\"2022-09-01T07:46:42.4684081Z\",\"DeviceName\":\"test.lab\",\"ReportId\":152059}}",
        "event": {
            "kind": "event",
            "type": [
                "info"
            ],
            "dataset": "device_file_events",
            "category": [
                "file"
            ]
        },
        "@timestamp": "2022-09-01T07:49:40.427937Z",
        "file": {
            "directory": "C:\\Users\\USER\\AppData\\Local\\Microsoft\\OneDrive\\22.161.0731.0002",
            "name": "OneDriveFileLauncher.exe"
        },
        "host": {
            "id": "1111111111111111111111111111111111111111",
            "name": "test.lab"
        },
        "process": {
            "pid": 27512,
            "start": "2022-09-01T07:46:34.0214941Z",
            "executable": "OneDriveSetup.exe",
            "command_line": "OneDriveSetup.exe /update /restart /updateSource:ODU /peruser /childprocess /extractFilesWithLessThreadCount /renameReplaceOneDriveExe /renameReplaceODSUExe /removeNonCurrentVersions /enableODSUReportingMode ",
            "working_directory": "c:\\users\\USER\\appdata\\local\\microsoft\\onedrive\\update",
            "user": {
                "domain": "intranet",
                "name": "group1",
                "id": "S-1-00-1-1111111-2222222222-3333333333-4444444444",
                "email": "user@example.org"
            },
            "parent": {
                "pid": 588,
                "executable": "OneDriveSetup.exe",
                "start": "2022-09-01T07:46:33.5858992Z"
            },
            "args": [
                "/update",
                "/restart",
                "/updateSource:ODU",
                "/peruser",
                "/childprocess",
                "/extractFilesWithLessThreadCount",
                "/renameReplaceOneDriveExe",
                "/renameReplaceODSUExe",
                "/removeNonCurrentVersions",
                "/enableODSUReportingMode",
                ""
            ]
        },
        "action": {
            "type": "FileDeleted",
            "properties": {
                "InitiatingProcessAccountObjectId": "9d6c8861-bc27-4c1c-b5d7-aa00401d0fd2",
                "InitiatingProcessFileSize": 56824728,
                "InitiatingProcessIntegrityLevel": "Medium",
                "InitiatingProcessTokenElevation": "TokenElevationTypeDefault",
                "InitiatingProcessVersionInfoCompanyName": "Microsoft Corporation",
                "InitiatingProcessVersionInfoFileDescription": "Microsoft OneDrive (64 bit) Setup",
                "InitiatingProcessVersionInfoInternalFileName": "OneDriveSetup.exe",
                "InitiatingProcessVersionInfoOriginalFileName": "OneDriveSetup.exe",
                "InitiatingProcessVersionInfoProductName": "Microsoft OneDrive",
                "InitiatingProcessVersionInfoProductVersion": "22.166.0807.0002"
            }
        },
        "microsoft": {
            "defender": {
                "report": {
                    "id": "152059"
                }
            }
        }
    }
    	
	```


=== "test_device_image_load_event.json"

    ```json
	
    {
        "message": "{\"time\":\"2022-09-01T07:49:37.5372014Z\",\"tenantId\":\"5ac3ff49-0e19-4600-9ad1-333e64e3b5cc\",\"operationName\":\"Publish\",\"category\":\"AdvancedHunting-DeviceImageLoadEvents\",\"properties\":{\"FolderPath\":\"C:\\\\Program Files (x86)\\\\Adobe\\\\8.1\\\\Client\\\\BIN\\\\sscfom.dll\",\"FileSize\":1048576,\"FileName\":\"sscfom.dll\",\"MD5\":\"83fd76962ba443b3d6e317ad73126843\",\"SHA256\":\"14c0592339b02885a8e4cf9724c607afe2a0187348c1aa084db3875ce93be0fe\",\"SHA1\":\"742ef984a8f759090f44838f737d575e283942be\",\"InitiatingProcessVersionInfoCompanyName\":null,\"InitiatingProcessVersionInfoProductName\":null,\"InitiatingProcessVersionInfoProductVersion\":null,\"InitiatingProcessVersionInfoInternalFileName\":null,\"InitiatingProcessVersionInfoOriginalFileName\":null,\"InitiatingProcessVersionInfoFileDescription\":null,\"InitiatingProcessFolderPath\":\"c:\\\\program files (x86)\\\\adobe\\\\8.1\\\\client\\\\bin\\\\autosync.exe\",\"InitiatingProcessFileName\":\"autosync.exe\",\"InitiatingProcessFileSize\":66560,\"InitiatingProcessMD5\":\"4617605c67d2a4f8ff7f86042d40011d\",\"InitiatingProcessSHA256\":\"9ff12db8e1aa2bc6781d1e399ec7a0fd38278dee8f2b5ece7403f2bab009dbe7\",\"InitiatingProcessSHA1\":\"1181891a21a785f05de6f40a3c635534ade13262\",\"InitiatingProcessAccountSid\":\"S-1-00-1-1111111-2222222222-3333333333-4444444444\",\"InitiatingProcessAccountDomain\":\"intranet\",\"InitiatingProcessAccountName\":\"group1\",\"InitiatingProcessAccountUpn\":\"user@example.org\",\"InitiatingProcessAccountObjectId\":null,\"InitiatingProcessCreationTime\":\"2022-09-01T07:47:58.182445Z\",\"InitiatingProcessId\":15584,\"InitiatingProcessCommandLine\":\"\\\"autosync.exe\\\" /c C:\\\\PROGRA~2\\\\adobe\\\\8.1\\\\Client\\\\bin\\\\fra\\\\adobe.cfg /c \\\" usa\\\"\",\"InitiatingProcessParentCreationTime\":\"2022-09-01T07:47:17.01345Z\",\"InitiatingProcessParentId\":2548,\"InitiatingProcessParentFileName\":\"explorer.exe\",\"InitiatingProcessIntegrityLevel\":\"Medium\",\"InitiatingProcessTokenElevation\":\"TokenElevationTypeDefault\",\"DeviceId\":\"4b35a092f1578f0a6f1b7dbf9e90465563781043\",\"AppGuardContainerId\":\"\",\"MachineGroup\":\"Windows 10 - remediate threats automatically\",\"Timestamp\":\"2022-09-01T07:47:58.6161271Z\",\"DeviceName\":\"test.lab\",\"ReportId\":3758,\"ActionType\":\"ImageLoaded\"}}",
        "event": {
            "kind": "event",
            "type": [
                "info"
            ],
            "dataset": "device_image_load_events",
            "category": [
                "process"
            ]
        },
        "@timestamp": "2022-09-01T07:49:37.537201Z",
        "file": {
            "directory": "C:\\Program Files (x86)\\Adobe\\8.1\\Client\\BIN\\sscfom.dll",
            "hash": {
                "md5": "83fd76962ba443b3d6e317ad73126843",
                "sha1": "742ef984a8f759090f44838f737d575e283942be",
                "sha256": "14c0592339b02885a8e4cf9724c607afe2a0187348c1aa084db3875ce93be0fe"
            },
            "name": "sscfom.dll",
            "size": 1048576
        },
        "host": {
            "id": "4b35a092f1578f0a6f1b7dbf9e90465563781043",
            "name": "test.lab"
        },
        "process": {
            "pid": 15584,
            "start": "2022-09-01T07:47:58.182445Z",
            "executable": "autosync.exe",
            "command_line": "\"autosync.exe\" /c C:\\PROGRA~2\\adobe\\8.1\\Client\\bin\\fra\\adobe.cfg /c \" usa\"",
            "working_directory": "c:\\program files (x86)\\adobe\\8.1\\client\\bin",
            "user": {
                "domain": "intranet",
                "name": "group1",
                "id": "S-1-00-1-1111111-2222222222-3333333333-4444444444",
                "email": "user@example.org"
            },
            "parent": {
                "pid": 2548,
                "executable": "explorer.exe",
                "start": "2022-09-01T07:47:17.01345Z"
            },
            "args": [
                "/c",
                "C:\\PROGRA~2\\adobe\\8.1\\Client\\bin\\fra\\adobe.cfg",
                "/c",
                "\"",
                "usa\""
            ]
        },
        "action": {
            "type": "ImageLoaded",
            "properties": {
                "InitiatingProcessFileSize": 66560,
                "InitiatingProcessIntegrityLevel": "Medium",
                "InitiatingProcessTokenElevation": "TokenElevationTypeDefault"
            }
        },
        "microsoft": {
            "defender": {
                "report": {
                    "id": "3758"
                }
            }
        },
        "related": {
            "hash": [
                "14c0592339b02885a8e4cf9724c607afe2a0187348c1aa084db3875ce93be0fe",
                "742ef984a8f759090f44838f737d575e283942be",
                "83fd76962ba443b3d6e317ad73126843"
            ]
        }
    }
    	
	```


=== "test_local_ip.json"

    ```json
	
    {
        "message": "{\"time\":\"2022-09-01T07:28:59.5127177Z\",\"tenantId\":\"5ac3ff49-0e19-4600-9ad1-333e64e3b5cc\",\"operationName\":\"Publish\",\"category\":\"AdvancedHunting-DeviceEvents\",\"properties\":{\"AccountSid\":null,\"AccountDomain\":null,\"AccountName\":null,\"LogonId\":null,\"FileName\":null,\"FolderPath\":null,\"MD5\":null,\"SHA1\":null,\"FileSize\":null,\"SHA256\":null,\"ProcessCreationTime\":null,\"ProcessTokenElevation\":null,\"RemoteUrl\":null,\"RegistryKey\":null,\"RegistryValueName\":null,\"RegistryValueData\":null,\"RemoteDeviceName\":null,\"FileOriginIP\":null,\"FileOriginUrl\":null,\"LocalIP\":\"-\",\"LocalPort\":null,\"RemoteIP\":\"-\",\"RemotePort\":null,\"ProcessId\":null,\"ProcessCommandLine\":null,\"AdditionalFields\":\"{\\\"BaseAddress\\\":2098738167808,\\\"RegionSize\\\":262144,\\\"ProtectionMask\\\":64}\",\"ActionType\":\"NtAllocateVirtualMemoryApiCall\",\"InitiatingProcessVersionInfoCompanyName\":\"Google\",\"InitiatingProcessVersionInfoProductName\":\"Software Reporter Tool\",\"InitiatingProcessVersionInfoProductVersion\":\"102.286.200\",\"InitiatingProcessVersionInfoInternalFileName\":\"software_reporter_tool_exe\",\"InitiatingProcessVersionInfoOriginalFileName\":\"software_reporter_tool.exe\",\"InitiatingProcessVersionInfoFileDescription\":\"Software Reporter Tool\",\"InitiatingProcessFolderPath\":\"c:\\\\users\\\\USER\\\\appdata\\\\local\\\\google\\\\chrome\\\\user data\\\\swreporter\\\\102.286.200\\\\software_reporter_tool.exe\",\"InitiatingProcessFileName\":\"software_reporter_tool.exe\",\"InitiatingProcessFileSize\":14687048,\"InitiatingProcessMD5\":\"51a9cac9c4e8da44ffd7502be17604ee\",\"InitiatingProcessSHA256\":\"6fe5e57df8d132eaf06f9134461dd172e36cf01679f13eb0f6e70c1f21b18323\",\"InitiatingProcessSHA1\":\"44543e0c6f30415c670c1322e61ca68602d58708\",\"InitiatingProcessLogonId\":121834210,\"InitiatingProcessAccountSid\":\"S-1-00-1-1111111-2222222222-3333333333-4444444444\",\"InitiatingProcessAccountDomain\":\"intranet\",\"InitiatingProcessAccountName\":\"group1\",\"InitiatingProcessAccountUpn\":\"user@example.org\",\"InitiatingProcessAccountObjectId\":\"9d6c8861-bc27-4c1c-b5d7-aa00401d0fd2\",\"InitiatingProcessCreationTime\":\"2022-09-01T06:56:23.7887846Z\",\"InitiatingProcessId\":1664,\"InitiatingProcessCommandLine\":\"\\\"software_reporter_tool.exe\\\" --use-crash-handler-with-id=\\\"\\\\\\\\.\\\\pipe\\\\crashpad_11111_XXXXXXXXXXXXXXXX\\\" --sandboxed-process-id=2 --init-done-notifier=804 --sandbox-mojo-pipe-token=********** --mojo-platform-channel-handle=780 --engine=2\",\"InitiatingProcessParentCreationTime\":\"2022-09-01T06:56:23.595229Z\",\"InitiatingProcessParentId\":15532,\"InitiatingProcessParentFileName\":\"software_reporter_tool.exe\",\"DeviceId\":\"1111111111111111111111111111111111111111\",\"AppGuardContainerId\":\"\",\"MachineGroup\":\"UnassignedGroup\",\"Timestamp\":\"2022-09-01T07:09:47.4980566Z\",\"DeviceName\":\"test.lab\",\"ReportId\":104061}}",
        "event": {
            "kind": "event",
            "type": [
                "info"
            ],
            "dataset": "device_events",
            "category": [
                "host"
            ]
        },
        "@timestamp": "2022-09-01T07:28:59.512717Z",
        "host": {
            "id": "1111111111111111111111111111111111111111",
            "name": "test.lab"
        },
        "process": {
            "pid": 1664,
            "start": "2022-09-01T06:56:23.7887846Z",
            "executable": "software_reporter_tool.exe",
            "command_line": "\"software_reporter_tool.exe\" --use-crash-handler-with-id=\"\\\\.\\pipe\\crashpad_11111_XXXXXXXXXXXXXXXX\" --sandboxed-process-id=2 --init-done-notifier=804 --sandbox-mojo-pipe-token=********** --mojo-platform-channel-handle=780 --engine=2",
            "working_directory": "c:\\users\\USER\\appdata\\local\\google\\chrome\\user data\\swreporter\\102.286.200",
            "user": {
                "domain": "intranet",
                "name": "group1",
                "id": "S-1-00-1-1111111-2222222222-3333333333-4444444444",
                "email": "user@example.org"
            },
            "parent": {
                "pid": 15532,
                "executable": "software_reporter_tool.exe",
                "start": "2022-09-01T06:56:23.595229Z"
            },
            "args": [
                "--use-crash-handler-with-id=\"\\\\.\\pipe\\crashpad_11111_XXXXXXXXXXXXXXXX\"",
                "--sandboxed-process-id=2",
                "--init-done-notifier=804",
                "--sandbox-mojo-pipe-token=**********",
                "--mojo-platform-channel-handle=780",
                "--engine=2"
            ]
        },
        "action": {
            "type": "NtAllocateVirtualMemoryApiCall",
            "properties": {
                "InitiatingProcessAccountObjectId": "9d6c8861-bc27-4c1c-b5d7-aa00401d0fd2",
                "InitiatingProcessFileSize": 14687048,
                "InitiatingProcessLogonId": "121834210",
                "InitiatingProcessVersionInfoCompanyName": "Google",
                "InitiatingProcessVersionInfoFileDescription": "Software Reporter Tool",
                "InitiatingProcessVersionInfoInternalFileName": "software_reporter_tool_exe",
                "InitiatingProcessVersionInfoOriginalFileName": "software_reporter_tool.exe",
                "InitiatingProcessVersionInfoProductName": "Software Reporter Tool",
                "InitiatingProcessVersionInfoProductVersion": "102.286.200"
            }
        },
        "microsoft": {
            "defender": {
                "report": {
                    "id": "104061"
                }
            }
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`action.properties.AadDeviceId` | `keyword` | Unique identifier for the device in Azure AD |
|`action.properties.AccountSid` | `keyword` | Security Identifier (SID) of the account |
|`action.properties.AccountUPN` | `keyword` | User principal name (UPN) of the account |
|`action.properties.ActionResult` | `keyword` | Result of the action |
|`action.properties.ActionTrigger` | `keyword` | Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery |
|`action.properties.Application` | `keyword` | Application that performed the recorded action |
|`action.properties.ApplicationId` | `keyword` | Unique identifier for the application |
|`action.properties.AttachmentCount` | `number` | Number of attachments in the email |
|`action.properties.AuthenticationDetails` | `keyword` | List of pass or fail verdicts by email authentication protocols like DMARC, DKIM, SPF or a combination of multiple authentication types (CompAuth) |
|`action.properties.ConfidenceLevel` | `keyword` | List of confidence levels of any spam or phishing verdicts. For spam, this column shows the spam confidence level (SCL), indicating if the email was skipped (-1), found to be not spam (0,1), found to be spam with moderate confidence (5,6), or found to be spam with high confidence (9). For phishing, this column displays whether the confidence level is "High" or "Low". |
|`action.properties.Connectors` | `keyword` | Custom instructions that define organizational mail flow and how the email was routed |
|`action.properties.DeliveryAction` | `keyword` | Delivery action of the email: Delivered, Junked, Blocked, or Replaced |
|`action.properties.DeliveryLocation` | `keyword` | Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items |
|`action.properties.DestinationDeviceName` | `keyword` | Name of the device running the server application that processed the recorded action |
|`action.properties.EmailAction` | `keyword` | Final action taken on the email based on filter verdict, policies, and user actions: Move message to junk mail folder, Add X-header, Modify subject, Redirect message, Delete message, send to quarantine, No action taken, Bcc message |
|`action.properties.EmailClusterId` | `keyword` | Identifier for the group of similar emails clustered based on heuristic analysis of their contents |
|`action.properties.EmailDirection` | `keyword` | Direction of the email relative to your network: Inbound, Outbound, Intra-org |
|`action.properties.EmailLanguage` | `keyword` | Detected language of the email content |
|`action.properties.FileOriginIP` | `keyword` | IP address where the file was downloaded from |
|`action.properties.FileOriginReferrerUrl` | `keyword` | URL of the web page that links to the downloaded file |
|`action.properties.FileOriginUrl` | `keyword` | URL where the file was downloaded from |
|`action.properties.IPCategory` | `keyword` | Additional information about the IP address |
|`action.properties.IPTags` | `list` | Customer-defined information applied to specific IP addresses and IP address ranges |
|`action.properties.ISP` | `keyword` | Internet service provider associated with the IP address |
|`action.properties.InitiatingProcessAccountObjectId` | `keyword` | Azure AD object ID of the user account that ran the process responsible for the event |
|`action.properties.InitiatingProcessFileSize` | `long` | Size of the process (image file) that initiated the event |
|`action.properties.InitiatingProcessIntegrityLevel` | `keyword` | Integrity level of the process that initiated the event. Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download. These integrity levels influence permissions to resources |
|`action.properties.InitiatingProcessLogonId` | `keyword` | Identifier for a logon session of the process that initiated the event. This identifier is unique on the same machine only between restarts. |
|`action.properties.InitiatingProcessTokenElevation` | `keyword` | Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event |
|`action.properties.InitiatingProcessVersionInfoCompanyName` | `keyword` | Company name from the version information of the process (image file) responsible for the event |
|`action.properties.InitiatingProcessVersionInfoFileDescription` | `keyword` | Description from the version information of the process (image file) responsible for the event |
|`action.properties.InitiatingProcessVersionInfoInternalFileName` | `keyword` | Internal file name from the version information of the process (image file) responsible for the event |
|`action.properties.InitiatingProcessVersionInfoOriginalFileName` | `keyword` | Original file name from the version information of the process (image file) responsible for the event |
|`action.properties.InitiatingProcessVersionInfoProductName` | `keyword` | Product name from the version information of the process (image file) responsible for the event |
|`action.properties.InitiatingProcessVersionInfoProductVersion` | `keyword` | Product version from the version information of the process (image file) responsible for the event |
|`action.properties.IsAdminOperation` | `keyword` | Indicates whether the activity was performed by an administrator |
|`action.properties.IsAnonymousProxy` | `keyword` | Indicates whether the IP address belongs to a known anonymous proxy |
|`action.properties.IsAzureADJoined` | `boolean` | Boolean indicator of whether machine is joined to the Azure Active Directory |
|`action.properties.IsAzureInfoProtectionApplied` | `boolean` | Indicates whether the file is encrypted by Azure Information Protection |
|`action.properties.IsExternalUser` | `boolean` | Indicates whether a user inside the network doesn't belong to the organization's domain |
|`action.properties.IsImpersonated` | `boolean` | Indicates whether the activity was performed by one user for another (impersonated) user |
|`action.properties.IsLocalAdmin` | `boolean` | Boolean indicator of whether the user is a local administrator on the machine |
|`action.properties.LocalIPType` | `keyword` | Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast |
|`action.properties.Location` | `keyword` | City, country, or other geographic location associated with the event |
|`action.properties.LoggedOnUsers` | `keyword` | List of all users that are logged on the machine at the time of the event in JSON array format |
|`action.properties.LogonId` | `keyword` | Identifier for a logon session. This identifier is unique on the same machine only between restarts |
|`action.properties.LogonType` | `keyword` | Type of logon session, specifically: |
|`action.properties.MachineGroup` | `keyword` | Machine group of the machine. This group is used by role-based access control to determine access to the machine |
|`action.properties.MergedDeviceIds` | `keyword` | Previous device IDs that have been assigned to the same device |
|`action.properties.MergedToDeviceId` | `keyword` | The most recent device ID assigned to a device |
|`action.properties.ObjectId` | `keyword` | Unique identifier of the object that the recorded action was applied to |
|`action.properties.ObjectName` | `keyword` | Name of the object that the recorded action was applied to |
|`action.properties.ObjectType` | `keyword` | Type of object, such as a file or a folder, that the recorded action was applied to |
|`action.properties.OnboardingStatus` | `keyword` | Indicates whether the device is currently onboarded or not to Microsoft Defender for Endpoint or if the device is not supported |
|`action.properties.OrgLevelAction` | `keyword` | Action taken on the email in response to matches to a policy defined at the organizational level |
|`action.properties.OrgLevelPolicy` | `keyword` | Organizational policy that triggered the action taken on the email |
|`action.properties.PreviousFileName` | `keyword` | Original name of the file that was renamed as a result of the action |
|`action.properties.PreviousFolderPath` | `keyword` | Original folder containing the file before the recorded action was applied |
|`action.properties.PreviousRegistryKey` | `keyword` | Original registry key of the registry value before it was modified |
|`action.properties.PreviousRegistryValueData` | `keyword` | Original data of the registry value before it was modified |
|`action.properties.PreviousRegistryValueName` | `keyword` | Original name of the registry value before it was modified |
|`action.properties.ProcessIntegrityLevel` | `keyword` | Integrity level of the newly created process. Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet downloaded. These integrity levels influence permissions to resources |
|`action.properties.ProcessTokenElevation` | `keyword` | Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the newly created process |
|`action.properties.ProcessVersionInfoCompanyName` | `keyword` | Company name from the version information of the newly created process |
|`action.properties.ProcessVersionInfoFileDescription` | `keyword` | Description from the version information of the newly created process |
|`action.properties.ProcessVersionInfoInternalFileName` | `keyword` | Internal file name from the version information of the newly created process |
|`action.properties.ProcessVersionInfoOriginalFileName` | `keyword` | Original file name from the version information of the newly created process |
|`action.properties.ProcessVersionInfoProductName` | `keyword` | Product name from the version information of the newly created process |
|`action.properties.ProcessVersionInfoProductVersion` | `keyword` | Product version from the version information of the newly created process |
|`action.properties.Query` | `keyword` | String used to run the query |
|`action.properties.QueryTarget` | `keyword` | Name of user, group, device, domain, or any other entity type being queried |
|`action.properties.QueryType` | `keyword` | Type of query, such as QueryGroup, QueryUser, or EnumerateUsers |
|`action.properties.RawEventData` | `keyword` | Raw event information from the source application or service in JSON format |
|`action.properties.RecipientObjectId` | `keyword` | Unique identifier for the email recipient in Azure AD |
|`action.properties.RegistryDeviceTag` | `keyword` | Machine tag added through the registry |
|`action.properties.RemoteDeviceName` | `keyword` | Name of the machine that performed a remote operation on the affected machine. Depending on the event being reported, this name could be a fully-qualified domain name (FQDN), a NetBIOS name, or a host name without domain information |
|`action.properties.RemoteIPType` | `keyword` | Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast |
|`action.properties.RequestAccountSid` | `keyword` | Security Identifier (SID) of the account used to remotely initiate the activity |
|`action.properties.SenderDisplayName` | `keyword` | Name of the sender displayed in the address book, typically a combination of a given or first name, a middle initial, and a last name or surname |
|`action.properties.SenderFromDomain` | `keyword` | Sender domain in the FROM header, which is visible to email recipients on their email clients |
|`action.properties.SenderObjectId` | `keyword` | Unique identifier for the sender's account in Azure AD |
|`action.properties.SensitivityLabel` | `keyword` | Label applied to an email, file, or other content to classify it for information protection |
|`action.properties.SensitivitySubLabel` | `keyword` | Sublabel applied to an email, file, or other content to classify it for information protection; sensitivity sublabels are grouped under sensitivity labels but are treated independently |
|`action.properties.ServiceSource` | `keyword` | Product or service that provided the alert information |
|`action.properties.ShareName` | `keyword` | Name of shared folder containing the file |
|`action.properties.TargetAccountDisplayName` | `keyword` | Display name of the account that the recorded action was applied to |
|`action.properties.TargetAccountUpn` | `keyword` | User principal name (UPN) of the account that the recorded action was applied to |
|`action.properties.TargetDeviceName` | `keyword` | Fully qualified domain name (FQDN) of the device that the recorded action was applied to |
|`action.properties.UrlCount` | `number` | Number of embedded URLs in the email |
|`action.properties.UserAgentTags` | `list` | More information provided by Microsoft Defender for Cloud Apps in a tag in the user agent field. Can have any of the following values: Native client, Outdated browser, Outdated operating system, Robot |
|`action.properties.UserLevelAction` | `keyword` | Action taken on the email in response to matches to a mailbox policy defined by the recipient |
|`action.properties.UserLevelPolicy` | `keyword` | End-user mailbox policy that triggered the action taken on the email |
|`agent.version` | `keyword` | Version of the agent. |
|`container.id` | `keyword` | Unique container id. |
|`container.runtime` | `keyword` | Runtime managing this container. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.port` | `long` | Port of the destination. |
|`email.from.address` | `keyword` | The email address of the sender, typically from the RFC 5322 From: header field |
|`email.local_id` | `keyword` | Unique identifier given to the email by the source that created the event |
|`email.message_id` | `keyword` | Identifier from the RFC 5322 Message-ID: email header that refers to a particular email message |
|`email.subject` | `keyword` | A brief summary of the topic of the message |
|`email.to.address` | `keyword` | The email address of recipient |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.dataset` | `keyword` | Name of the dataset. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.directory` | `keyword` | Directory where the file is located. |
|`file.hash.md5` | `keyword` | MD5 hash. |
|`file.hash.sha1` | `keyword` | SHA1 hash. |
|`file.hash.sha256` | `keyword` | SHA256 hash. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`file.size` | `long` | File size in bytes. |
|`file.x509.not_after` | `date` | Time at which the certificate is no longer considered valid. |
|`file.x509.serial_number` | `keyword` | Unique serial number issued by the certificate authority. |
|`host.architecture` | `keyword` | Operating system architecture. |
|`host.id` | `keyword` | Unique host id. |
|`host.mac` | `keyword` | Host MAC addresses. |
|`host.name` | `keyword` | Name of the host. |
|`host.os.family` | `keyword` | OS family (such as redhat, debian, freebsd, windows). |
|`host.os.full` | `keyword` | Operating system name, including the version or code name. |
|`host.os.version` | `keyword` | Operating system version as a raw string. |
|`host.type` | `keyword` | Type of host. |
|`microsoft.defender.activity.objects` | `list` | List of objects, such as files or folders, that were involved in the recorded activity |
|`microsoft.defender.activity.type` | `keyword` | Type of activity that triggered the event |
|`microsoft.defender.alert.id` | `keyword` | Unique identifier for the alert |
|`microsoft.defender.alert.title` | `keyword` | The title of the alert |
|`microsoft.defender.certificate.counter_signed_at` | `keyword` | Date and time the certificate was countersigned |
|`microsoft.defender.certificate.created_at` | `keyword` | Date and time the certificate was created |
|`microsoft.defender.certificate.crl.urls` | `keyword` | JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs) |
|`microsoft.defender.certificate.is_root_signer_microsort` | `boolean` | Indicates whether the signer of the root certificate is Microsoft and if the file is included in Windows operating system |
|`microsoft.defender.certificate.is_signed` | `boolean` | Indicates whether the file is signed |
|`microsoft.defender.certificate.is_trusted` | `boolean` | Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes |
|`microsoft.defender.certificate.issuer` | `keyword` | Information about the issuing certificate authority (CA) |
|`microsoft.defender.certificate.issuer.hash` | `keyword` | Unique hash value identifying issuing certificate authority (CA) |
|`microsoft.defender.certificate.signature_type` | `keyword` | Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file |
|`microsoft.defender.certificate.signer` | `keyword` | Information about the signer of the file |
|`microsoft.defender.certificate.signer.hash` | `keyword` | Unique hash value identifying the signer |
|`microsoft.defender.entity.type` | `keyword` | Type of object, such as a file, a process, a device, or a user |
|`microsoft.defender.evidence.direction` | `keyword` | Indicates whether the entity is the source or the destination of a network connection |
|`microsoft.defender.evidence.role` | `keyword` | How the entity is involved in an alert, indicating whether it is impacted or is merely related |
|`microsoft.defender.host.category` | `keyword` | Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown |
|`microsoft.defender.host.model` | `keyword` | Model name or number of the product from the vendor or manufacturer, only available if device discovery finds enough information about this attribute |
|`microsoft.defender.host.os.build` | `keyword` | Build version of the operating system running on the machine |
|`microsoft.defender.host.os.version` | `keyword` | Additional information about the OS version, such as the popular name, code name, or version number |
|`microsoft.defender.host.subtype` | `keyword` | Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone; only available if device discovery finds enough information about this attribute |
|`microsoft.defender.host.vendor` | `keyword` | Name of the product vendor or manufacturer, only available if device discovery finds enough information about this attribute |
|`microsoft.defender.network.tunnel.protocol` | `keyword` | Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH |
|`microsoft.defender.observer.interface.dhcp.ipv4` | `keyword` | IPv4 address of DHCP server |
|`microsoft.defender.observer.interface.dhcp.ipv6` | `keyword` | IPv6 address of DHCP server |
|`microsoft.defender.observer.interface.dns` | `keyword` | DNS server addresses in JSON array format |
|`microsoft.defender.observer.interface.gateways` | `keyword` | Default gateway addresses in JSON array format |
|`microsoft.defender.observer.interface.ips` | `keyword` | JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local |
|`microsoft.defender.observer.interface.name` | `keyword` | Name of the network adapter |
|`microsoft.defender.observer.interface.networks` | `keyword` | Networks that the adapter is connected to. Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet |
|`microsoft.defender.observer.interface.status` | `keyword` | Operational status of the network adapter. For the possible values, refer to this enumeration |
|`microsoft.defender.observer.interface.type` | `keyword` | Network adapter type. For the possible values, refer to this enumeration |
|`microsoft.defender.report.id` | `keyword` | Unique identifier for the event |
|`microsoft.defender.threat.category` | `keyword` | Type of threat indicator or breach activity identified by the alert |
|`microsoft.defender.threat.detection` | `keyword` | Methods used to detect malware, phishing, or other threats found in the email |
|`microsoft.defender.threat.family` | `keyword` | Malware family that the suspicious or malicious file or process has been classified under |
|`microsoft.defender.threat.names` | `keyword` | Detection name for malware or other threats found |
|`microsoft.defender.threat.severity` | `keyword` | Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert |
|`microsoft.defender.threat.types` | `keyword` | Verdict from the email filtering stack on whether the email contains malware, phishing, or other threats |
|`network.protocol` | `keyword` | Application protocol name. |
|`process.args` | `keyword` | Array of process arguments. |
|`process.code_signature.status` | `keyword` | Additional information about the certificate status. |
|`process.code_signature.subject_name` | `keyword` | Subject name of the code signer |
|`process.command_line` | `wildcard` | Full command line that started the process. |
|`process.executable` | `keyword` | Absolute path to the process executable. |
|`process.hash.md5` | `keyword` | MD5 hash. |
|`process.hash.sha1` | `keyword` | SHA1 hash. |
|`process.hash.sha256` | `keyword` | SHA256 hash. |
|`process.parent.executable` | `keyword` | Absolute path to the process executable. |
|`process.parent.pid` | `long` | Process id. |
|`process.parent.start` | `date` | The time the process started. |
|`process.pid` | `long` | Process id. |
|`process.start` | `date` | The time the process started. |
|`process.user.domain` | `keyword` | Domain of the account that ran the process responsible for the event |
|`process.user.email` | `keyword` | User principal name (UPN) of the account that ran the process responsible for the event |
|`process.user.id` | `keyword` | Security Identifier (SID) of the account that ran the process responsible for the event |
|`process.user.name` | `keyword` | User name of the account that ran the process responsible for the event |
|`process.working_directory` | `keyword` | The working directory of the process. |
|`registry.data.strings` | `wildcard` | List of strings representing what was written to the registry. |
|`registry.data.type` | `keyword` | Standard registry type for encoding contents |
|`registry.key` | `keyword` | Hive-relative path of keys. |
|`registry.value` | `keyword` | Name of the value written. |
|`rule.id` | `keyword` | Rule ID |
|`rule.name` | `keyword` | Rule name |
|`service.name` | `keyword` | Name of the service. |
|`service.type` | `keyword` | The type of the service. |
|`source.geo.city_name` | `keyword` | City name. |
|`source.geo.country_iso_code` | `keyword` | Country ISO code. |
|`source.ip` | `ip` | IP address of the source. |
|`source.port` | `long` | Port of the source. |
|`threat.technique.name` | `keyword` | Threat technique name. |
|`url.domain` | `keyword` | Domain of the url. |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |
|`user.domain` | `keyword` | Name of the directory the user is a member of. |
|`user.full_name` | `keyword` | User's full name, if available. |
|`user.id` | `keyword` | Unique identifier of the user. |
|`user.name` | `keyword` | Short name or login of the user. |
|`user.roles` | `keyword` | Array of user roles at the time of the event. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

