---
title : "Android wifi"
#excerpt : ""

categories:
   - Blog
tags:
   - Blog
---


- "hardware/interfaces/wifi/1.0/IWifi.hal"
	1. isStarted(),start(),stop(),getChips() 등 함수 선언됨
	2. 위 함수는 "packages/modules/Wifi/service/java/com/android/server/wifi/WifiVendorHal.java" 에서 사용


```
      /**
       * Hal Device Manager callbacks.
       */
      public class HalDeviceManagerStatusListener implements HalDeviceManager.ManagerStatusListener {
          @Override
          public void onStatusChanged() {
              boolean isReady = mHalDeviceManager.isReady();
              boolean isStarted = mHalDeviceManager.isStarted();

              mVerboseLog.i("Device Manager onStatusChanged. isReady(): " + isReady
                      + ", isStarted(): " + isStarted);
              if (!isReady) {
                  // Probably something unpleasant, e.g. the server died
                  WifiNative.VendorHalDeathEventHandler handler;
                  synchronized (sLock) {
                      clearState();
                      handler = mDeathEventHandler;
                  }
                  if (handler != null) {
                      handler.onDeath();
                  }
              }
          }
      }
```    

	3. mHalDeviceManager 는 어디서 만드나?
		--> "packages/modules/Wifi/service/java/com/android/server/wifi/WifiInjector.java"  

```
// Modules interacting with Native.
mHalDeviceManager = new HalDeviceManager(mClock, this, wifiHandler);
```
	4. HalDeviceManager 는 wifi 만 사용하는건가? 
