ANT Radio Service 4.7.0
===============

This repository currently only contains the prebuilt (.apk) version of the ANT Radio Service for Android. The ANT Radio Service allows apps to communicate with ANT wireless hardware built in to phones or external adapters such as an ANT USB stick.

For more info on the ANTRadioService view the Google Play Description at https://play.google.com/store/apps/details?id=com.dsi.ant.service.socket

For details on adding this to the Android platform source see https://github.com/ant-wireless/ANT_in_Android


Changelog
==============
<b><u>Android_ANTRadioService_4-7-0 (Changes since 4.6.0) - 8 Aug 2014:</u></b>

* Fix service to be visible on Play Store for phones without bluetooth again
* Fix null pointer crash in ChannelCloseController.onChannelMessage() when adapter changes state
* Fix burst function to return earlier when channel drops to search instead of waiting the full search timeout period
* Fix required and desired capabilities to work again when requesting channels (was broken since 4.4.0)

<b><u>Android_ANTRadioService_4-6-0 (Changes since 4.5.0.RC3) - 5 Aug 2014:</u></b>

* Add advanced burst support
* Fix channel not being made available if a task failed in the cleanup after it was released
* Add bluetooth permissions to mainfest(as per Google's suggestion since some adapters require interaction with bluetooth stack)
* Added handling of an error where the closed channel event is not received after a search timeout on some old firmware, such as in the Xperia Ray
* Added better logging for serial message length failures

<b><u>Android_ANTRadioService_4-5-0_RC3 (Changes since 4.02.00):</u></b>

* Add private network key support
* Allow channels interface to automatically re-enable ANT without rebinding
* Better support for Airplane Mode behaviours:
    * Add a channel not available reason to explicitly indicate Airplane mode is preventing ANT from starting    
    * Support airplane mode disabling by default on platforms that don't specify ANT airplane mode behaviour
    * Prevent hang on some phones when enabling airplane mode and attempting to restart ANT
    * Fixed a crash when toggling airplane mode on some phones
* Fixed some channel behaviour bugs
    * Prevent an error on some Samsung phones where burst messages could lose data when acknowledged messages were being sent on other channels
    * Fixed a bug where channels that were opened and closed quickly would spontaneuously close after opening again
    * Fixed a bug where an acknowledged message result on one channel could be erroneously returned as a burst result on a different channel
* Support for capabilities of AP2 module
* Prevent an error on some old apps using the Wahoo API from failing during startup
* Update application icon to grey version for visibility in dark themes
* Fixed some inconsistencies with channel transmit power
* Fixed some errors with NPE or long delays starting up and shutting down
* Fixed bugs that could cause error recovery to loop indefinitely
* Fixed some errors when running with multiple ANT USB adapters over USB-Host
* Removed some extraneous debug logging
* Various other bug fixes
