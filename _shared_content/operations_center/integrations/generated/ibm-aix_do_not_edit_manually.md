
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Authentication logs` | From system module, login dataset retrieve User logins, logouts, and system boots |
| `File monitoring` | The file metricset sends events when a file is changed (created, updated, or deleted) on disk. The events contain file metadata and hashes |
| `Process monitoring` | Process dataset retrieve Started and stopped processes |
| `Process use of network` | Scket dataset retrieve Opened and Closed sockets |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `process` |
| Type | `` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "AUD_It.json"

    ```json
	
    {
        "message": "AUD_It audit Pipin root OK 16 sep 2022 15:42:41.885007 No associated roles cmd: 1 arg: 0",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "AUD_It"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "Pipin"
        },
        "process": {
            "args": "0",
            "user": {
                "name": "root"
            },
            "command_line": "1"
        },
        "user": {
            "name": "audit"
        },
        "related": {
            "user": [
                "audit"
            ]
        }
    }
    	
	```


=== "AUD_Proc.json"

    ```json
	
    {
        "message": "AUD_Proc cron root root OK 25 sep 2022 23:10:00.924334 No associated roles pid: 0 cmd: 5",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "AUD_Proc"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "cron",
            "pid": 0,
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "CRON_Finish.json"

    ```json
	
    {
        "message": "CRON_Finish cron root root OK 25 sep 2022 23:00:00.861158 No associated roles user = root pid = 3932756 time = Sun Sep 25 23:00:00 2022",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "CRON_Finish"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "cron",
            "pid": 3932756,
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "CRON_Start.json"

    ```json
	
    {
        "message": "CRON_Start cron root root OK 17 sep 2022 00:00:00.139458 No associated roles event = start cron job cmd = /usr/share/centrifydc/bin/logrotate.sh 2>&1 >> /var/log/centrify_logrotate.log time = Sat Sep 17 00:00:00 2022",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "CRON_Start"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "cron",
            "user": {
                "name": "root"
            },
            "command_line": "cron /usr/share/centrifydc/bin/logrotate.sh 2>&1 >> /var/log/centrify_logrotate.log"
        }
    }
    	
	```


=== "FILE_Link.json"

    ```json
	
    {
        "message": "FILE_Link dad root root OK 31 jul 2022 14:02:33.696402 No associated roles linkname /usr/bin/cdax/bsh filename /usr/bin/cdax/ksh93",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "FILE_Link"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "/usr/bin/cdax/ksh93",
            "target_path": "/usr/bin/cdax/bsh"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "root"
            }
        },
        "user": {
            "name": "dad"
        },
        "related": {
            "user": [
                "dad"
            ]
        }
    }
    	
	```


=== "FILE_Link2.json"

    ```json
	
    {
        "message": "filename /bin/cdax/ksh FILE_Link dad root root OK 31 jul 2022 15:02:33.597401 No associated roles",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "FILE_Link"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "/bin/cdax/ksh"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "root"
            }
        },
        "user": {
            "name": "dad"
        },
        "related": {
            "user": [
                "dad"
            ]
        }
    }
    	
	```


=== "FILE_Pipe.json"

    ```json
	
    {
        "message": "FILE_Pipe Pipin root admin OK 10 Nov 2022 09:21:53.955363 No associated roles read: 7 write: 8",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "FILE_Pipe"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "admin"
            }
        },
        "user": {
            "name": "Pipin"
        },
        "related": {
            "user": [
                "Pipin"
            ]
        }
    }
    	
	```


=== "FILE_Read.json"

    ```json
	
    {
        "message": "FILE_Read tar Pipin root OK 10 Nov 2022 09:30:12.229710 No associated roles file descriptor = 1635083369 filename = t object read event detected /app1/coresec/active/BEKAL-CORE-01S.p12",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "FILE_Read"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "t"
        },
        "group": {
            "name": "Pipin"
        },
        "process": {
            "name": "tar",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "FILE_Rename.json"

    ```json
	
    {
        "message": "FILE_Rename BESClient root root OK 25 sep 2022 22:33:21.081155 No associated roles frompath: /var/opt/BESClient/besclient.config.tmp topath: /var/opt/BESClient/besclient.config",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "FILE_Rename"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": " /var/opt/BESClient/besclient.config",
            "path": "/var/opt/BESClient/besclient.config.tmp"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "root"
            }
        },
        "user": {
            "name": "BESClient"
        },
        "related": {
            "user": [
                "BESClient"
            ]
        }
    }
    	
	```


=== "FILE_Stop.json"

    ```json
	
    {
        "message": "SRC_Start srcmstr root root OK 21 sep 2022 00:00:08.467005 No associated roles syslog_ng",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "SRC_Start"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "syslog_ng"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "srcmstr",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "FILE_Unlink.json"

    ```json
	
    {
        "message": "FILE_Unlink Pipin root root OK 25 sep 2022 23:14:20.756159 No associated roles filename /var/adm/nim/glock",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "FILE_Unlink"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "/var/adm/nim/glock"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "root"
            }
        },
        "user": {
            "name": "Pipin"
        },
        "related": {
            "user": [
                "Pipin"
            ]
        }
    }
    	
	```


=== "FS_Chroot.json"

    ```json
	
    {
        "message": "FS_Chroot sshd root root OK 23 sep 2022 17:14:21.748158 No associated roles change root directory to: /var/empty",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "FS_Chroot"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "/var/empty"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "sshd",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "FS_Mkdir.json"

    ```json
	
    {
        "message": "FS_Mkdir Pipin root root OK 25 sep 2022 23:04:23.825394 No associated roles mode: 755 dir: /var/adm/nim/6292044",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "FS_Mkdir"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "directory": "/var/adm/nim/6292044"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "root"
            }
        },
        "user": {
            "name": "Pipin"
        },
        "related": {
            "user": [
                "Pipin"
            ]
        }
    }
    	
	```


=== "FS_Rmdir.json"

    ```json
	
    {
        "message": "FS_Rmdir rm root root OK 25 sep 2022 23:14:20.859389 No associated roles remove of directory: /var/adm/nim/6292046",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "FS_Rmdir"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "directory": "/var/adm/nim/6292046"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "rm",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "PROC_Adjtime.json"

    ```json
	
    {
        "message": "PROC_Adjtime xntpd root root OK 25 sep 2022 21:57:37.226128 No associated roles old time: 01 jan 1970 01:00:00.1664135, delta: 226172812:0",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "PROC_Adjtime"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "xntpd",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "PROC_Execute.json"

    ```json
	
    {
        "message": "PROC_Execute    sh                              root     Pipin FAIL          22 Nov 2022 10:20:32.056053  No associated roles                      euid: 503 egid: 403 epriv: 0:0 name sh -c /app/DB2/11.1/instance/db2iset -i Pipin DB2AUTOSTART 2>&1 ",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "PROC_Execute"
        },
        "action": {
            "target": "process",
            "status": "FAIL"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "-c"
        },
        "group": {
            "name": "root",
            "id": "403"
        },
        "process": {
            "name": "sh",
            "user": {
                "name": "Pipin"
            },
            "command_line": "sh  /app/DB2/11.1/instance/db2iset -i Pipin DB2AUTOSTART 2>&1 "
        },
        "user": {
            "id": "503"
        }
    }
    	
	```


=== "PROC_Kill.json"

    ```json
	
    {
        "message": "PROC_Kill rsyslogd root root OK 25 sep 2022 23:14:20.816166 No associated roles pid: 3605020, sig: 22",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "PROC_Kill"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "rsyslogd",
            "pid": 3605020,
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "PROC_LoadError.json"

    ```json
	
    {
        "message": "PROC_LoadError perl5.28.1 root root FAIL 25 sep 2022 23:12:21.397204 No associated roles flags: 80, libpath: , file: /usr/lib/nls/loc/C C C C C C",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "PROC_LoadError"
        },
        "action": {
            "target": "process"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "perl5.28.1",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "PROC_RealGID.json"

    ```json
	
    {
        "message": "PROC_RealGID rm_mlcache_file root root OK 25 sep 2022 21:13:31.584159 No associated roles old rgid: 0, new gid: 0, which: egid",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "PROC_RealGID"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "rm_mlcache_file",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "PROC_SetGroups.json"

    ```json
	
    {
        "message": "PROC_SetGroups cron root root OK 25 sep 2022 23:00:00.835203 No associated roles group set: system,bin,sys,security,cron,audit,lp,ivmgr,apache",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "PROC_SetGroups"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "cron",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "PROC_SetUserIDs.json"

    ```json
	
    {
        "message": "PROC_SetUserIDs db2fm                           root     db2inst1 OK          22 Nov 2022 14:19:42.790048  No associated roles                      effect: 503, real: 503, saved: -1, login: -1#012",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "PROC_SetUserIDs"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "db2inst1"
        },
        "process": {
            "name": "db2fm",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "PROC_Sysconfig.json"

    ```json
	
    {
        "message": "PROC_Sysconfig exportfs root root OK 25 sep 2022 23:14:20.836155 No associated roles 3",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "PROC_Sysconfig"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "exportfs",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "S_PASSWD_READ.json"

    ```json
	
    {
        "message": "S_PASSWD_READ cron root root OK 25 sep 2022 23:10:00.924334 No associated roles audit object read event detected /etc/security/passwd",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "S_PASSWD_READ"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "/etc/security/passwd"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "root"
            }
        },
        "user": {
            "name": "cron"
        },
        "related": {
            "user": [
                "cron"
            ]
        }
    }
    	
	```


=== "S_USER_WRITE.json"

    ```json
	
    {
        "message": "S_USER_WRITE vi Pipin root OK 21 sep 2022 10:26:12.893117 No associated roles audit object write event detected /etc/security/user",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "S_USER_WRITE"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "/etc/security/user"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "vi"
        },
        "user": {
            "name": "Pipin"
        },
        "related": {
            "user": [
                "Pipin"
            ]
        }
    }
    	
	```


=== "TCP_kaccept.json"

    ```json
	
    {
        "message": "TCP_kaccept Pipin root root OK 25 sep 2022 23:09:25.544152 No associated roles fd14 Port 10.30.134.100 1022 kx5frsip01-a nimaux",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "TCP_kaccept"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "root"
            }
        },
        "source": {
            "ip": "10.30.134.100",
            "port": 1022,
            "address": "10.30.134.100"
        },
        "user": {
            "name": "Pipin"
        },
        "related": {
            "ip": [
                "10.30.134.100"
            ],
            "user": [
                "Pipin"
            ]
        }
    }
    	
	```


=== "TCP_kbind.json"

    ```json
	
    {
        "message": "TCP_kbind Pipin root root OK 25 sep 2022 23:14:20.826159 No associated roles fd11 /dev/.SRC-unix/SRC0006292046YEya",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "TCP_kbind"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "/dev/.SRC-unix/SRC0006292046YEya"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "root"
            }
        },
        "user": {
            "name": "Pipin"
        },
        "related": {
            "user": [
                "Pipin"
            ]
        }
    }
    	
	```


=== "TCP_klisten.json"

    ```json
	
    {
        "message": "TCP_klisten Pipin root root OK 31 jul 2022 10:21:24.798402 0 fd15 qlimit 1",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "TCP_klisten"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "user": {
                "name": "root"
            }
        },
        "user": {
            "name": "Pipin"
        },
        "related": {
            "user": [
                "Pipin"
            ]
        }
    }
    	
	```


=== "USER_Login.json"

    ```json
	
    {
        "message": "flags: 80, libpath: , file: /usr/lib/security/DCE USER_Login sshd root root OK 29 jul 2022 09:58:03.091427 No associated roles",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "USER_Login"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "file": {
            "name": "/usr/lib/security/DCE"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "sshd",
            "user": {
                "name": "root"
            }
        }
    }
    	
	```


=== "USER_Login2.json"

    ```json
	
    {
        "message": "USER_Login      db2ckpw                         root     Pipin OK          22 Nov 2022 13:41:34.586022  No associated roles                      user: Pipin tty: #012",
        "event": {
            "kind": "event",
            "category": [
                "process"
            ],
            "action": "USER_Login"
        },
        "action": {
            "target": "process",
            "status": "OK"
        },
        "observer": {
            "vendor": "IBM"
        },
        "group": {
            "name": "root"
        },
        "process": {
            "name": "db2ckpw",
            "user": {
                "name": "Pipin"
            }
        },
        "user": {
            "name": "Pipin"
        },
        "related": {
            "user": [
                "Pipin"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`action.status` | `keyword` | The status of the action |
|`action.target` | `keyword` | The target of the action. This field is mandatory for STIX2 compliance |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.code` | `keyword` | Identification code for this event. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`file.directory` | `keyword` | Directory where the file is located. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`file.path` | `keyword` | Full path to the file, including the file name. |
|`file.target_path` | `keyword` | Target path for symlinks. |
|`group.id` | `keyword` | Unique identifier for the group on the system/platform. |
|`group.name` | `keyword` | Name of the group. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`process.args` | `keyword` | Array of process arguments. |
|`process.command_line` | `wildcard` | Full command line that started the process. |
|`process.name` | `keyword` | Process name. |
|`process.pid` | `long` | Process id. |
|`process.tty` | `object` | Information about the controlling TTY device. If set, the process belongs to an interactive session. |
|`process.user.name` | `keyword` | The effective user (euid). |
|`source.ip` | `ip` | IP address of the source. |
|`source.port` | `long` | Port of the source. |
|`user.id` | `keyword` | Unique identifier of the user. |
|`user.name` | `keyword` | Short name or login of the user. |

