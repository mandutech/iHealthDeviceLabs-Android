# iHealth SDK FAQ

### 1. Android permission explaination

```
    <!-- Internet communication and detect / manage Wi-Fi state -->
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
    <uses-permission android:name="android.permission.CHANGE_WIFI_STATE" />
    <uses-permission android:name="android.permission.CHANGE_WIFI_MULTICAST_STATE" />

    <!-- Bluetooth permission for communicating with iHealth devices -->
    <uses-permission android:name="android.permission.BLUETOOTH" />
    <uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />

    <!-- Permission for writing on device memory -->
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />

    <!-- Permission for locating user device in order to search beacons -->
    <!-- https://developer.android.com/reference/android/bluetooth/le/BluetoothLeScanner.html#startScan(android.bluetooth.le.ScanCallback) -->
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />

    <!-- Permission for iHealth BG1 device (which connect with phone by headphone jack) -->
    <uses-permission android:name="android.permission.RECORD_AUDIO"
    <uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS" />

   ```


### 2. User status    

```
1.New-user registration succeeded.
2.User login succeeded.
3.The user is iHealth user as well, measurement via SDK has been activated, and the data from the measurement belongs to the user.
4.Verification failed, try out for 10 days.


–PS: The measurement via SDK will be operated in the case of 1-3, and there is 10-day tryout if SDK Verification failed in case of SDK cannot connect Internet or Userid/clientID/clientSecret verification failed or SDK has not been authorized or User has not been authorized. SDK is fully functional during tryout period, but will be terminated without verification through Internet after 10 days.The interface needs to be re-called after analyzing the return parameters. SDK application requires Internet connection. If you encounter user status 4 with full internet access, please send Userid/clientID/clientSecret to this email <zhaoyongguang@ihealthlabs.com.cn> to get help.

```

### 3. Android 6.0 location permission

```
	If targetSdkVersion >= 23, need location permission as follows:

	<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>


	Turn location function for the phone.

```

[Location Permission](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/public/Location_Permission.png?raw=true)  
[Location Function](https://github.com/iHealthDeviceLabs/iHealthDeviceLabs-Android/blob/master/public/LocationFunction.jpg?raw=true)


### 4. Android 7.0 connect problem   

```
Connect will fail on Android 7.0 with devices as follows:
1. HS4  Firmware Version < 1.0.5
2. PO3  (Firmware Version < 1.0.5   ||  (Firmware Version = 1.0.5  && Display Version != 11.0.5))
3. PO3M Firmware Version < 2.1.4
4. BP3L  （Firmware Version =1.0.0 && BT Version < 1.2.4）
5. KN-550BT  (Firmware Version =1.0.0 && BT Version < 1.2.4）
6. AM3   All the version
7. AM3S   Firmware Version < 1.1.8
8. AM4   Firmware Version < 1.4.4

```
