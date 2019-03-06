> I used to have a bad impression on **MultiTech Gateway MultiConnect Conduit**. However with the new firmware version, I need to consider this gateway at a new level

## Table of contents

* [Bad impression](#bad-impression)
* [What is new ?](#what-is-new-?)
* [Conclusion](#conclusion)
## Bad impression
I've been using a `MultiConnect Conduit MTCDT 210A` for a long time with firmware version 1.4.3. I tried different configurations and finally ended up with package forwarder configuration to TTN network. Here are some disadvantages of this gateway:

1. Instability I would say, it is really slow and glitching. I managed with a support to connect a device with ABP/OTAA modes, the support suggested me should use `confirmed` messages instead of `unconfirmed` messages due to the message loss. It's pretty high like more than 85%.
2. Manual configuration:
    * Everything needs to be configured in mLinux for adding devices, key management..etc
    * LoRa network server integrated in the gateway needs to be configured manually through web interface, no suggestions at all. It's like I needed to do the brute force.
    * To install package forwarder, it's done in linux environment through many complicated steps.
    * When the gateway is shutdown, all connecting devices need to restart to perform join the network. I still don't know why the gateway is not able to restart the LoRa server without configuration loss.
3. To spend for an amount of money (~500 EUR+) to purchase this gateway and ended it up with TTN configuration, I believe it's not worth.

## What is new ?
I had a chance to test with MultiTech new model named `MTCDT-LEU1-247A`. This time I checked on their website to get the latest firmware which was `1.7.0`. I upgraded to this firmware to check what's different. I tested on both old and new gateways
* **To upgrade to new firmware version, it is important to upgrade to the next version from your old firmware version and do it one by one. It takes time indeed and a LAN cable will help for the upgrade stability.**

The new model that I am testing includes WiFi and Cellular connections. It's a great experience because we do not need a LAN cable for internet anymore. Well actually I need it for simple configuration steps at the beginning. 

What is new from this firmware ? 
* New interface
    ![New interface](/img/1.PNG)
* Stability: No more message loss
* If we skip some initial setup step and jump directly to the LoRaWan configuration, it will be much better.
    * Everything is here, I just need to choose what I want. MultiTech integrates 2 options for `Mode` in `LoRa mode`, there are `NETWORK SERVER` and `PACKAGE FORWARDER`. I don't need to install package forwarder from mLinux anymore. 
    * Other settings are available to choose such as `Channel Plan`, `Network Mode`, `RX2 Datarate`, and `Max Datarate` ..etc which is convenient.
        ![Choose everything](/img/2.png)
    * What I want to do is to choose the setting I prefer, save it and restart the LoRa services.
* Device management experience is improved:
    * Key management system: I declare key system here to connect devices quickly (OTAA) or I can manage a device locally by adding it directly in `Local End-Device Credentials` section.
         ![Key management](/img/3.png)
    * Device & Device group management is a plus.
    * I can easily manage packet exchange in `Packets`
         ![package management](/img/4.PNG)
    * Now it is feasible to push the Downlink manually in `Downlink Queue` section
        ![Manual downlink](/img/5.PNG)
    * The most interesting part is MultiTech support FOTA for devices in `Operations`, it is super !
        ![Operations](/img/6.PNG)
* If I choose `PACKAGE FORWARDER`, everything is available to choose. For example, I can choose a default IP address to a server, either TTN or Semtec Demo. `Gateway Info` is always available to register my gateway on TTN network.
    ![Package forwarder](/img/7.png)
## Conclusion
With the new firmware upgrade, I believe MultiTech succdeeded in bringing new experience to users. We don't need to mess up with mLinux environment, friendly and more interactive user interface is available. Especially the stability of the gate way is improved. In addition, MultiTech brings new features such as Class B and C management as well as the FOTA feature; which is brand new. I hope MultiTech can keep this heat and continues it in new firmware verisons.