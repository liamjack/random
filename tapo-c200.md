# Tapo C200

## Methods

### Login

#### Request

* Method: `login`
* Params:
	* `hashed`: boolean - optional - Indicates if the provided password is MD5 hashed or not
	* `username`: string - optional
	* `password`: string - optional

```json
{
	"method": "login",
	"params": {
		"hashed": true,
		"username": "admin",
		"password": "EB0A5D3C61C849E7A51874C2A0C81EB2"
	}
}
```

#### Response

* `error_code`
* `result`:
	* `stok`: string - Session token
	* `user_group`: string

```json
{
  "error_code": 0,
  "result": {
    "stok": "079f38dceacede221ea3c035a1c02837",
    "user_group": "root"
  }
}
```

#### Notes

It is possible to authenticate providing a empty params dict, the camera assumes that the username and password are both `admin`

### Manual alarm

#### Request

* Method: `do`
* `msg_alarm`:
	* `manual_msg_alarm`:
		* `action`: string: `start` / `stop`

```json
{
	"method": "do",
	"msg_alarm": {
		"manual_msg_alarm": {
			"action": "start"
		}
	}
}
```

#### Response

```json
{
  "error_code": 0
}
```

### Get P2P Share Password

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "getP2PSharePassword",
				"params": {
					"user_management": {
						"get_p2p_sharepwd": "null"
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "getP2PSharePassword",
        "result": {
          "username": "admin",
          "sharepwd": "51c2a8d8942f80e3568f37136360288d"
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Get app component list

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "getAppComponentList",
				"params": {
					"app_component": {
						"name": ["app_component_list"]
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "getAppComponentList",
        "result": {
          "app_component": {
            "app_component_list": [
              {
                "name": "sdCard",
                "version": 1
              },
              {
                "name": "timezone",
                "version": 1
              },
              {
                "name": "system",
                "version": 3
              },
              {
                "name": "led",
                "version": 1
              },
              {
                "name": "playback",
                "version": 3
              },
              {
                "name": "detection",
                "version": 1
              },
              {
                "name": "alert",
                "version": 1
              },
              {
                "name": "firmware",
                "version": 2
              },
              {
                "name": "account",
                "version": 1
              },
              {
                "name": "quickSetup",
                "version": 1
              },
              {
                "name": "ptz",
                "version": 1
              },
              {
                "name": "video",
                "version": 2
              },
              {
                "name": "lensMask",
                "version": 2
              },
              {
                "name": "lightFrequency",
                "version": 1
              },
              {
                "name": "dayNightMode",
                "version": 1
              },
              {
                "name": "osd",
                "version": 2
              },
              {
                "name": "record",
                "version": 1
              },
              {
                "name": "videoRotation",
                "version": 1
              },
              {
                "name": "audio",
                "version": 2
              },
              {
                "name": "diagnose",
                "version": 1
              },
              {
                "name": "msgPush",
                "version": 2
              },
              {
                "name": "deviceShare",
                "version": 1
              },
              {
                "name": "tapoCare",
                "version": 1
              },
              {
                "name": "blockZone",
                "version": 1
              },
              {
                "name": "personDetection",
                "version": 1
              },
              {
                "name": "targetTrack",
                "version": 1
              },
              {
                "name": "babyCryDetection",
                "version": 1
              }
            ]
          }
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Get connection type

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "getConnectionType",
				"params": {
					"network": {
						"get_connection_type": null
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "getConnectionType",
        "result": {
          "link_type": "wifi",
          "ssid": "IOT-ROUTEUR-4589",
          "rssi": "4",
          "rssiValue": -49
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Check diagnose status

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "checkDiagnoseStatus",
				"params": {
					"system": {
						"check_diagnose_status": "null"
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "checkDiagnoseStatus",
        "result": {
          "status": "off"
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Set diagnose mode

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "setDiagnoseMode",
				"params": {
					"system": {
						"sys": {
							"diagnose_mode": "off"
						}
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "setDiagnoseMode",
        "result": {
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Reset

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "reset",
				"params": {
					"system": {
						"reset": null
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "reset",
        "result": {
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Reset config only

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "resetConfigOnly",
				"params": {
					"system": {
						"resetConfigOnly": null
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "resetConfigOnly",
        "result": {
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Reboot device

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "rebootDevice",
				"params": {
					"system": {
						"reboot": null
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "rebootDevice",
        "result": {
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Get User ID

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "getUserID",
				"params": {
					"system": {
						"get_user_id": null
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "getUserID",
        "result": {
          "user_id": 27
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Bind to cloud

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "bindToCloud",
				"params": {
					"cloud_config": {
						"bind": {
							"username": "email@example.com",
							"password": "MyPassword"
						}
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "bindToCloud",
        "result": {
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Check reset WiFi

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "checkResetWiFi",
				"params": {
					"system": {
						"reset_wifi_supported": null
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "checkResetWiFi",
        "result": {
          "reset_wifi_supported": "0"
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Get rotation status

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "getRotationStatus",
				"params": {
					"image": {
						"name": ["switch"]
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "getRotationStatus",
        "result": {
          "image": {
            "switch": {
              ".name": "switch",
              ".type": "switch_type",
              "switch_mode": "common",
              "schedule_start_time": "21600",
              "schedule_end_time": "64800",
              "flip_type": "off",
              "rotate_type": "off",
              "ldc": "off",
              "night_vision_mode": "inf_night_vision",
              "wtl_intensity_level": "5"
            }
          }
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Get video qualities

#### Request

```json
{
	"method": "multipleRequest",
	"params": {
		"requests": [
			{
				"method": "getVideoQualities",
				"params": {
					"video": {
						"name": ["main"]
					}
				}
			}
		]
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
      {
        "method": "getVideoQualities",
        "result": {
          "video": {
            "main": {
              ".name": "main",
              ".type": "stream",
              "stream_type": "general",
              "resolution": "1280*720",
              "bitrate_type": "vbr",
              "frame_rate": "65551",
              "quality": "3",
              "bitrate": "1024",
              "encode_type": "H264",
              "name": "VideoEncoder_1"
            }
          }
        },
        "error_code": 0
      }
    ]
  },
  "error_code": 0
}
```

### Get third account

#### Request

```json
{
	"method": "get",
	"user_management": {
		"name": ["third_account"]
	}
}
```

#### Response

```json
{
  "user_management": {
    "third_account": {
      ".name": "third_account",
      ".type": "third_account",
      "username": "---",
      "ciphertext": "dl5GoIRk+FMC\/JgP5yLjA+r8PynYYSai8DSmdv1Xw7iALNEKxkE5UusQw6BMC4+FlcWv0bCPuw8DSlSk\/vkmcTZ\/BF\/ZY1ENNJqo+uJtiGi2f1zJFjleYhPlDx4YXa3qp7oSNF8EU1BU4mOY9nEtUakFl4oVPsvlLGM3qE\/zI2k="
    }
  },
  "error_code": 0
}
```

### Get media encrypt

#### Request

```json
{
	"method": "get",
	"cet": {
		"name": ["media_encrypt"]
	}
}
```

#### Response

```json
{
  "cet": {
    "media_encrypt": {
      ".name": "media_encrypt",
      ".type": "on_off",
      "enabled": "off"
    }
  },
  "error_code": 0
}
```

### Set media encrypt

#### Request

```json
{
	"method": "set",
	"cet": {
		"media_encrypt": {
			"enabled": "off"
		}
	}
}
```

#### Response

```json
{
  "result": {
    "responses": [
    ]
  },
  "error_code": 0
}
```

### Get basic device info

#### Request

```json
{
	"method": "get",
	"device_info": {
		"name": ["basic_info"]
	}
}
```

#### Response

```json
{
  "device_info": {
    "basic_info": {
      "ffs": false,
      "device_type": "SMART.IPCAMERA",
      "device_model": "C200",
      "device_name": "C200 3.0",
      "device_info": "C200 3.0 IPC",
      "hw_version": "3.0",
      "sw_version": "1.1.20 Build 220426 Rel.56142n(4555)",
      "device_alias": "HomeCam",
      "features": "3",
      "barcode": "",
      "mac": "1C-61-B4-E5-87-D2",
      "dev_id": "8021B6AC1C73CDC2C65FC030EE37A3DD203AA3CB",
      "oem_id": "5CFA4B8CF3F7D826581082F1C0CFAAE5",
      "hw_desc": "00000000000000000000000000000000"
    }
  },
  "error_code": 0
}
```

### Get full device info

#### Request

```json
{
	"method": "get",
	"device_info": {
		"name": ["info"]
	}
}
```

#### Response

```json
{
  "device_info": {
    "info": {
      ".name": "info",
      ".type": "info",
      "device_model": "C200",
      "hw_version": "3.0",
      "fw_description": "C200 3.0",
      "product_id": "00c20000",
      "device_name": "C200 3.0",
      "device_info": "C200 3.0 IPC",
      "dev_id": "8021B6AC1C73CDC2C65FC030EE37A3DD203AA3CB",
      "hw_id": "A66C7B9DA2F10B7E7CF20AF04814C2D5",
      "fw_cur_id": "5E027E30D8431273EFF57734DA74B77B",
      "mac": "1C-61-B4-E5-87-D2",
      "cur_isp_version": "2",
      "sw_version": "1.1.20 Build 220426 Rel.56142n(4555)",
      "sys_software_revision": "0x500a0101",
      "sys_software_revision_minor": "0x0014",
      "isp_version": "2",
      "device_type": "SMART.IPCAMERA",
      "features": "3",
      "domain_name": "tplogin.cn",
      "language": "EN",
      "enable_dns": "1",
      "manufacturer_name": "TP-LINK",
      "friendly_name": "IPC",
      "model_description": "IPC",
      "manufacturer_url": "http:\/\/www.tp-link.com",
      "vendor_id": "0x00000001",
      "zone_code": "0x0",
      "roi_reg_num": "1",
      "cover_reg_num": "4",
      "md_reg_num": "32",
      "td_reg_num": "1",
      "id_reg_num": "4",
      "cd_reg_num": "4",
      "ac_reg_num": "1",
      "plugin_obtain_way": "web",
      "product_type": "ipc",
      "fw_shared_prefix": "Tapo_C200v3",
      "ext_fw_upgrade": "1"
    }
  },
  "error_code": 0
}
```

### Get basic system info

#### Request

```json
{
	"method": "get",
	"system": {
		"name": ["basic"]
	}
}
```

#### Response

```json
{
  "system": {
    "basic": {
      ".name": "basic",
      ".type": "setting",
      "timezone": "UTC-00:00",
      "timing_mode": "ntp",
      "zone_id": "Europe\/London"
    }
  },
  "error_code": 0
}
```

### Get system info

#### Request

```json
{
	"method": "get",
	"system": {
		"name": ["sys"]
	}
}
```

#### Response

```json
{
  "system": {
    "sys": {
      ".name": "sys",
      ".type": "system",
      "is_factory": "1",
      "makeroom_status": "0",
      "append_dns": "0.0.0.0",
      "alias": "C200 3.0",
      "dev_alias": "HomeCam",
      "diagnose_mode": "off",
      "network_type": "WiFi",
      "hostname": "C200"
    }
  },
  "error_code": 0
}
```

### Get motion detection config

#### Request

```json
{
	"method": "get",
	"motion_detection": {
		"name": ["motion_det"]
	}
}
```

#### Response

```json
{
  "motion_detection": {
    "motion_det": {
      ".name": "motion_det",
      ".type": "on_off",
      "sensitivity": "medium",
      "digital_sensitivity": "50",
      "enabled": "off"
    }
  },
  "error_code": 0
}
```

### Get lens mask config

#### Request

```json
{
	"method": "get",
	"lens_mask": {
		"name": ["lens_mask_info"]
	}
}
```

#### Response

```json
{
  "lens_mask": {
    "lens_mask_info": {
      ".name": "lens_mask_info",
      ".type": "lens_mask_info",
      "enabled": "off"
    }
  },
  "error_code": 0
}
```

### Get target track config

#### Request

```json
{
	"method": "get",
	"target_track": {
		"name": ["target_track_info"]
	}
}
```

#### Response

```json
{
  "target_track": {
    "target_track_info": {
      ".name": "target_track_info",
      ".type": "target_track_info",
      "enabled": "off"
    }
  },
  "error_code": 0
}
```

### Get WAN config

#### Request

```json
{
	"method": "get",
	"network": {
		"name": ["wan"]
	}
}
```

#### Response

```json
{
  "network": {
    "wan": {
      ".name": "wan",
      ".type": "interface",
      "ifname": "br-wan",
      "type": "bridge",
      "wan_type": "dhcp",
      "speed_duplex": "auto",
      "proto": "dhcp",
      "mtu": "1480",
      "auto": "1",
      "netmask": "255.255.255.0",
      "ipaddr": "192.168.0.10",
      "gateway": "192.168.0.1",
      "macaddr": "1C:61:B4:E5:87:D2",
      "fac_macaddr": "1C:61:B4:E5:87:D2",
      "dns": "114.114.114.114 8.8.8.8"
    }
  },
  "error_code": 0
}
```

## Credits

* https://github.com/JurajNyiri/pytapo
* https://md.depau.eu/s/r1Ys_oWoP
* https://drmnsamoliu.github.io/

## Onboarding

In this mode, the camera's LED will alternate between green and red.

The camera creates an unsecured WiFi network such as `Tapo_Cam_87D1` (`87D1` being the last 4 characters of the camera's MAC address)

Once connected to this WiFi network, the camera provides a dynamic IP in the `192.168.191.0/24` subnet and the camera is accessible via `192.168.191.1`

Note: It is possible to log in without any parameters or using `admin:admin`, but it doesn't really matter since authentication is *not* required for the onboarding requests.

### Scan WiFi networks

#### Request

`POST https://192.168.191.1/`

```json
{
	"method": "scanApList",
	"params": {
		"onboarding": {
			"scan": "null"
		}
	}
}
```

#### Response

```json
{
  "error_code": 0,
  "result": {
    "onboarding": {
      "scan": {
        "wpa3_supported": "false",
        "ap_list": [
          {
            "ssid": "IOT-ROUTEUR-5246",
            "bssid": "A5-6E-51-61-54-53",
            "auth": 3,
            "encryption": 2,
            "rssi": 2
          },
          {
            "ssid": "SFR WiFi Mobile",
            "bssid": "72-CE-7D-D9-D8-8D",
            "auth": 5,
            "encryption": 2,
            "rssi": 0
          },
          {
            "ssid": "SFR WiFi FON",
            "bssid": "72-CE-7D-D9-D8-8F",
            "auth": 0,
            "encryption": 0,
            "rssi": 0
          },
          {
            "ssid": "FreeWifi_secure",
            "bssid": "00-24-D4-58-CB-45",
            "auth": 5,
            "encryption": 3,
            "rssi": 0
          }
        ]
      }
    }
  }
}
```

* `auth`: 
	* `0`: None
	* `1`: WEP
	* `2`: WPA2
	* `3`: ?
	* `4`: ?
	* `5`: WPA3

### Connect to a WiFi network

#### Request

`POST https://192.168.191.1/`

```json
{
	"method": "connectAp",
	"params": {
		"onboarding": {
			"connect": {
				"ssid": "IOT-ROUTEUR-5246",
				"bssid": "A5-6E-51-61-54-53",
				"auth": 3,
				"encryption": 2,
				"rssi": 2,
				"password": "JfHLxfTdB+evKq5Pvlcuth2MgVlpw2Z++yEG/O0mk/Otcydno5ujFump0NNa+/dxOiN6D9m6JvpkRhqVY9VafrTkTIOFLesVwRbnzgczl90yS9gjjlyevkCrhIdM+x8OHERMB/NSeZUB6hLLY3IGwcAjVi3Ort13fxV/LovZ1qs="
			}
		}
	}
}
```

You may be wondering where that password comes from, it's encrypted with a 1024 bit RSA public key found in the decompiled Tapo APK (represented as [Java RSAPublicKeySpec](https://docs.oracle.com/javase/7/docs/api/java/security/spec/RSAPublicKeySpec.html)):

```
MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQC4D6i0oD/Ga5qb//RfSe8MrPVI
rMIGecCxkcGWGj9kxxk74qQNq8XUuXoy2PczQ30BpiRHrlkbtBEPeWLpq85tfubT
UjhBz1NPNvWrC88uaYVGvzNpgzZOqDC35961uPTuvdUa8vztcUQjEZy16WbmetRj
URFIiWJgFCmemyYVbQIDAQAB
```

So using a free online tool (such as https://www.devglan.com/online-tools/rsa-encryption-decryption) you should be able to encrypt for example `MyPassword` and obtain `JcRz1lFfpeaa2FPo+tcCVZ6jtpEiLiXCdrb6vk85UXUEfUuVS7Zbh6PzDiWUtvCEMGZm7UCfIpYptnPT5y5jRsKr+C3v8t+jDfGwzW3+1DcnP+Jd/eo1Omfk+tkV0MlLKV+ur16/rzbWfAwDqGnEpwWQJ/u4T8VSJjyZGM+xt3o=`

#### Response

```json
{
  "error_code": 0,
  "result": {
    "onboarding": {
      "connect": {
        "connect_time": 60000,
        "mac": "1c-61-b4-d5-87-d2",
        "support_ap": "true"
      }
    }
  }
}
```

### Get connect status

#### Request

`POST https://192.168.191.1/`

```json
{
	"method": "getConnectStatus",
	"params": {
		"onboarding": {
			"get_connect_status": "null"
		}
	}
}
```

#### Response

```json
{
  "error_code": 0,
  "result": {
    "onboarding": {
      "get_connect_status": {
        "status": 0
      }
    }
  }
}
```

### Note

Once onboarding is performed and the camera is connected to the desired WiFi network, the onboarding endpoints will be unavailable and return the error code `-40101`

The only way to change WiFi network appears to require [a hard reset](https://www.tp-link.com/us/support/faq/2705/), returning the camera to factory settings and back into onboarding mode.

## Diagnostics

`/stok={token}/admin/system/diagnose_logs`

## Upload / Download conf
`/admin/system/download_conf`
`/admin/system/upload_conf`

DES encryption key: `jklsd*%&%HDFG767`

Source: https://github.com/JurajNyiri/pytapo/issues/26

## Error codes

* `-90000`: FFS None Password
* `-71108`: Unknown ?
* `-71101`: No more User IDs available
* `-71102`: User ID already used
* `-71103`: User ID invalid
* `-71112`: Unknown ?
* `-66802`
* `-64303`: Motor busy
* `-64304`: Motor locked rotor
* `-64305`: Preset add moving
* `-64306`: Preset saturated
* `-63103`: Device name excessive
* `-60305`: Unknown ?
* `-52405`: Too many requests
* `-52407`: Too many clients
* `-52419`: Too many HTTPS clients
* `-52409`: No SD Card
* `-40209`: Unknown ?
* `-40401`: Session expired
* `-40404`: Device blocked
* `-40405`: Device factory
* `-40406`: Out of limit
* `-40407`: Other error
* `-40408`: System blocked
* `-40210`: Method doesn't exist
* `-40209`: Unknown username / password ?
* `-40101`: Unknown ?
* `-40102`: Unknown ?
* `-40105`: Unknown ?
* `-40106`: Unsupported method
* `-40108`: Timeout error
* `-51219`: Unknown ?

## TapoCare

* Dev: https://tapo-alpha.tplinkcloud.com
* Beta: https://tapo-care-beta.tplinknbu.com
* Beta2: https://tapo-beta2.tplinkcloud.com
* Beta3: https://tapo-beta3.tplinkcloud.com
* Staging: https://tapo-staging.tplinkcloud.com
* Prod: https://tapo.tplinkcloud.com
