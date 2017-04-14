# Attentation：

		Before you use SDK, please get permission from iHealth team, otherwise you will not be able to use SDK (connect failed)      

		Contact for more information:    
		a. <developer@ihealthlabs.com>(US)  
		b. <louie@ihealthlabs.com>(Europe)  
		c. <huhaiyun@ihealthlabs.com.cn>(Other)  
	
		After received a invitation, you will be able to register your application for iOS and Android platform.  

</br>    
         
# iHealth Device Developer Documentation


This document describes how to use the iHealth Device SDK to accomplish the major operation: Connection Device, Online Measurement, Offline Measurement and iHealth Device Management. 
  
### Latest version

2.3.2

### Support iHealth Device for Android

iHealth Bp3m   
iHealth Bp3l  
iHealth Bp5  
iHealth Bp7  
iHealth Bp7s  
iHealth Bp550BT  
iHealth KD926  
iHealth KD723  
iHealth Abi  
iHealth Hs3  
iHealth Hs4  
iHealth Hs4s  
iHealth Hs5  
iHealth Hs6  
iHealth Am3  
iHealth Am3s  
iHealth Am4
iHealth Po3  
iHealth BG1(AG-680)  
iHealth BG5 



## How to use the iHealth SDK

iHealth Device SDK communicate with iHealth Device by USB, Bluetooth, BluetoothLe, Wifi or Audio.  
**USB:** iHealth Bp3m  
**Bluetooth:** iHealth Bp5, iHealth Bp7, iHealth Bp7s, iHealth Abi, iHealth Hs3, iHealth Hs4, iHealth BG5  
**BluetoothLe:** iHealth Bp3l, iHealth Bp550BT, iHealth KD926, iHealth KD723, iHealth Am3, iHealth Am3s, iHealth Po3, iHealth Hs4s  
**Audio:** iHealth BG1(AG-680)  
**Wifi:** iHealth Hs5, iHealth Hs6


### Configure

Need to introduce the development kit iHealthLibrary.jar.  
Support phone os 4.0+: ABI, BP3, BP5, BP7, BP7S, BG1, BG5, BP, HS3, HS5, HS4S, HS6  
Support phone os 4.4+: AM3, AM3S, AM4, HS4, PO3, BP3L, KD926, KD723, Bp550BT,

Specific configuration as shown below:

> Need to add ACCESS_COARSE_LOCATION permission in Android 6.0。

![box-model](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/public/user_permission.png?raw=true)


![box-model](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/public/ihealth_device_doc.png?raw=true)

### How to apply for SDK permissions

[Click this link](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/doc/Developer_Registration_Application_Instruction.md)   

Contact for more information:  
<enterprise@ihealthlabs.com>    
<developer@ihealthlabs.com>(US)  
<louie@ihealthlabs.com>(Europe)  

### How to use the iHealth SDK

##### 1. Initialization iHealth SDK.

``` 
iHealthDevicesManager.getInstance().init(MainActivity.this);

```

##### 2. Register callback, and get a callback ID.

```
/*
* Register callback to the manager. This method will return a callback Id.
*/
int callbackId = iHealthDevicesManager.getInstance().registerClientCallback(iHealthDevicesCallback);
```

##### 3. Add callback filter.

```
iHealthDevicesManager.getInstance().addCallbackFilterForAddress(clientCallbackId, ...);	iHealthDevicesManager.getInstance().addCallbackFilterForDeviceType(clientCallbackId, ...);
```

##### 4. Verify iHealth device user permission.

```
iHealthDevicesManager.getInstance().sdkUserInAuthor(MainActivity.this, userName, clientId, clientSecret, callbackId);
If verify success, all the api avaliable, else 10 trial days you will get.
```

##### 5. Discovery a iHealth device.

```
int type = iHealthDevicesManager.DISCOVERY_BP5
iHealthDevicesManager.getInstance().startDiscovery(type);
```

```
private iHealthDevicesCallback iHealthDevicesCallback = new iHealthDevicesCallback() {  
	@Override
    public void onScanDevice(String mac, String deviceType) {
    }
};
```

##### 6. Connection a iHealth device.

```
iHealthDevicesManager.getInstance().connectDevice(userName, mac, type);
```

```
private iHealthDevicesCallback iHealthDevicesCallback = new iHealthDevicesCallback() {
	@Override
	    public void onDeviceConnectionStateChange(String mac, String deviceType, int status) {
 	}
};
```

##### 7. Get iHealth device controller.
```

/*
* Get Am3 device controller
*/
Am3Control am3Control = iHealthDevicesManager.getInstance().getAm3Control(mac);

/*
* Get Am3s device controller
*/
Am3sControl am3sControl = iHealthDevicesManager.getInstance().getAm3sControl(mac);

/*
* Get Bg1 device controller
*/
Bg1Control bg1Control = iHealthDevicesManager.getInstance().getBg1Control(mac);

/*
* Get Bg5 device controller
*/
Bg5Control bg5Control = iHealthDevicesManager.getInstance().getBg5Control(mac);

/*
* Get Bp3m device controller
*/
Bp3mControl bp3mControl = iHealthDevicesManager.getInstance().getBp3mControl(mac);

/*
* Get Bp3l device controller
*/
Bp3lControl bp3lControl = iHealthDevicesManager.getInstance().getBp3lControl(mac);

/*
* Get Bp5 device controller
*/
Bp5Control bp5Control = iHealthDevicesManager.getInstance().getBp5Control(mac);

/*
* Get Bp7 device controller
*/
Bp7Control bp7Control = iHealthDevicesManager.getInstance().getBp7Control(mac);

/*
* Get Bp7s device controller
*/
Bp7sControl bp7sControl = iHealthDevicesManager.getInstance().getBp7sControl(mac);

/*
* Get Bp550BT device controller
*/
Bp550BTControl bp550BTControl = iHealthDevicesManager.getInstance().getBp550BTControl(mac);

/*
* Get Bp926 device controller
*/
Bp926Control bp926Control = iHealthDevicesManager.getInstance().getBp926Control(mac);

/*
* Get Bp926 device controller
*/
Bp926Control bp926Control = iHealthDevicesManager.getInstance().getBp926Control(mac);

/*
* Get Hs3 device controller
*/
Hs3Control hs3Control = iHealthDevicesManager.getInstance().getHs3Control(mac);

/*
* Get Hs4 device controller
*/
Hs4Control hs4Control = iHealthDevicesManager.getInstance().getHs4Control(mac);

/*
* Get Hs4s device controller
*/
Hs4sControl hs4sControl = iHealthDevicesManager.getInstance().getHs4sControl(mac);

/*
* Get Hs5 device controller
*/
Hs5Control hs5Control = iHealthDevicesManager.getInstance().getHs5Control(mac);

/*
* Get Hs6 device controller
*/
HS6Control hs6Control = new HS6Control(userName, this, iHealthDevicesManager.TYPE_HS6, mIHealthDeviceHs6Callback);
 
/*
* Get Po3 device controller
*/
Po3Control po3Control = iHealthDevicesManager.getInstance().getPo3Control(mac);

/*
* Get FDTH device controller
*/
BtmControl btmControl = iHealthDevicesManager.getInstance().getBtmControl(mac);   
```



## API Guide

[Click this link](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/tree/master/api-docs)

## Examples

[Click this link](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/tree/master/examples)

## Release Note

[Click this link](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/doc/ReleaseNote.md)

## FAQ

[Click this link](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/doc/FAQ.md)
