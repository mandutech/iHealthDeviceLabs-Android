# iHealth SDK Release Note

### V2.3.5
Release Date: 2017-10-11
```
Description:
	1. Added TS28B support
	2. Fix the BP3L interrupt measurement failure problem
	3. Fix the callback crash problem
	4. Various other bug fixes

```

### V2.3.4
Release Date: 2017-9-3
```
Description:
	1. Support for new iHealth device: HS2
	2. Optimize the Bluetooth scan, connection efficiency
	3. Optimize BG1 connectivity
	4. Optimize BPM1 connectivity
	5. Fix bugs

```

### V2.3.3
Release Date: 2017-4-14
```
Description:
	1. Update the version format for firmware and hardware (eg. 1.0.3)
	2. Permission verification trial period is modified to 10 days, 10 days any validation error is available, the original only allows no network available
	3. GDH Code updated to V1.1
	4. Support for new iHealth devices: BP5S BG5L
	5. Optimize the Bluetooth scan, connection efficiency; optimize BG1 connectivity
	6. Increase the download progress function for product firmware upgrade
	7. Support upgrade product firmware offline
	8. Fix bugs

```

### V2.3.2
Release Date: 2017-1-21
```
Description:
	1. Support cache function for Api, you can call Api one by one without waiting the callback.
	2. Optimize the connection for BG1
	3. Support GDH strip (OneCode) for BG1 BG5
	4. Support HS5 for Android 7.0
	5. Fix bugs
	6. New api to replace the old one

		/* iHealthDevicesManager */
		Deprecated:
			public boolean connectDevice(String userName, final String mac)
		New:
			public boolean connectDevice(String userName, final String mac, final String type)

		Deprecated:
			public IDPS getIdps(String mac)
		New:
			public String getDevicesIDPS(String mac)

		/* Bg5Control */
		Deprecated:
			public void setBottleMessage(final String QRCode)
			public void setBottleMessage(final String QRCode, final int stripNum, final String overDate)
		New:
			public void setBottleMessageWithInfo(final int stripType, final int measureType, final String QRCode, final int stripNum, final String overDate)


		/* Bg1Control */
		Deprecated:
			public void sendCode(final String QRCode)
		New:
			public void sendCode(final String QRCode, int stripType, int measureType)

		/* Bp7Control */
		Deprecated:
			public void getAngle()
		New:
			public void conformAngle()


```

### V2.3.1
Release Date: 2016-10-21

```
Description:
	1. Support update the firmware of device (AM3 AM3S AM4 HS4 HS4S)
	2. Support FDTH
	3. Optimize the api documents
	4. Optimize the connection for BG1
	5. Optimize the connection for BLE device
	6. Check the paraments for all the api
	7. Support connect without discovery(BT BLE device)
	8. Add log version for debug
	9. Fix bugs

```

### V2.3.0
Release Date: 2016-6-28

```
Description:
	1.Support OneCode
	2.Support Continua BP
	3.Support BTM

```
### V2.2.9
Release Date: 2016-6-20

```
Description:
	1.Fix register bug

```

### V2.2.8
Release Date: 2016-6-8

```
Description:
	1.Fix PO3 HS4 connection bug
	2.Add RSSI for Device with low energy
	Before:
	public void onScanDevice(String mac, String deviceType) {}
	After:
	public void onScanDevice(String mac, String deviceType, int rssi) {}
	3.Other modify

```

### V2.2.7
Release Date: 2016-5-16

```
Description:
	1.solve up cloud bug

```

### V2.2.6
Release Date: 2016-5-13

```
Description:
	1. Fix BP3L measure bug

```

### V2.2.5
Release Date: 2016-5-12

```
Description:
	1.Optimize BG1 Api

```

### V2.2.4
Release Date: 2016-5-05

```
Description:
	1.add dataid to callback data
	2.callback data up cloud
	3.modify real data to calories and total calories of 	AM device
		e.g.{
				"TotalCalories":1062,
				"step":0,
				"Calories":0
			}
	4.modify key
	5.modify some bugs

```


### V2.2.3
Release Date: 2016-3-02

```
Description:
	1.modify po offline data
	2.modify time、step and calories error of AM device
	3.modify user target data of AM device
	4.modify repeat data of BP7S 550BT KD926

```


### V2.2.2
Release Date: 2016-2-19

```
Description:
	1.add weight to HS6
	2.solve no stage data of AM device

```

### V2.2.1
Release Date: 2016-2-05

```
Description: Support AG680

```

### V2.2.0
Release Date: 2016-1-20

```
Description: Support KD926

```

### V2.1.1
Release Date: 2016-1-11

```
Description: Fix bug

```

### V2.1.0
Release Date: 2016-1-11

```
Description: Support BP7S KD550

```

### V2.0
```
Description: New architecture compared V1.0
Release Date: 2015-12-14
```
More info:   
*[ReleaseNotes_DeviceManager.md](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/doc/ReleaseNotes_DeviceManager.md)*       
*[ReleaseNotes_AMDeviceManager.md](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/doc/ReleaseNotes_AMDeviceManager.md)*  
*[ReleaseNotes_BPDeviceManager.md](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/doc/ReleaseNotes_BPDeviceManager.md)*
