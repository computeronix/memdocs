---
# required metadata

title: Use VPN settings for Android devices in Microsoft Intune - Azure | Microsoft Docs
description: See all the settings to create VPN connections on Android devices in Microsoft Intune. Enter the connection name, IP address or FQDN of the VPN server, choose how users authenticate, and choose Citrix, SonicWall, Check Point Capsule, and Pulse Secure connection types.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/19/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology:

# optional metadata

#ROBOTS:
#audience:

ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Android device settings to configure VPN in Intune

This article lists and describes the different VPN connection settings you can control on Android devices. As part of your mobile device management (MDM) solution, use these settings to create a VPN connection, choose how the VPN authenticates, select a VPN server type, and more.

As an Intune administrator, you can create and assign VPN settings to Android devices. 

To learn more about VPN profiles in Intune, see [VPN profiles](vpn-settings-configure.md).

## Before you begin

[Create a device configuration profile](vpn-settings-configure.md), and choose **Android device administrator**.

## Base VPN

- **Connection name**: Enter a name for this connection. End users see this name when they browse their device for the available VPN connections. For example, enter `Contoso VPN`.
- **IP address or FQDN**: Enter the IP address or fully qualified domain name (FQDN) of the VPN server that devices connect. For example, enter **192.168.1.1** or **vpn.contoso.com**.

  - **Authentication method**: Choose how devices authenticate to the VPN server. Your options:

    - **Certificates**: Select an existing SCEP or PKCS certificate profile to authenticate the connection. [Configure certificates](../protect/certificates-configure.md) lists the steps to create a certificate profile.
    - **Username and password**: When signing into the VPN server, end users are prompted to enter their user name and password.

- **Connection type**: Select the VPN connection type. Your options:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Access**
  - **Pulse Secure**
  - **Citrix SSO**

- **Fingerprint** (Check Point Capsule VPN only): Enter a string, such as **Contoso Fingerprint Code**, to verify that the VPN server can be trusted. A fingerprint is sent to the client so the client knows to trust any server that has the same fingerprint. If the device doesn't have the fingerprint, it prompts the user to trust the VPN server while showing the fingerprint. The user manually verifies the fingerprint, and chooses to trust to connect.
- **Enter key and value pairs for the Citrix VPN attributes** (Citrix only): Enter key and value pairs, provided by Citrix. These values configure the properties of the VPN connection. 

  You can also **Import** a comma-separated values file (.csv) with keys and value pairs. Be sure to review the **My data has headers** and **Key** properties.

  After you've added your key and values pairs, use **Export** to back up your data to a .csv file.

## Next steps

[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

You can also create VPN profiles for [Android Enterprise](vpn-settings-android-enterprise.md), [iOS/iPadOS](vpn-settings-ios.md), [macOS](vpn-settings-macos.md), [Windows 10 and later](vpn-settings-windows-10.md), [Windows 8.1](vpn-settings-windows-8-1.md), and [Windows Phone 8.1](vpn-settings-windows-phone-8-1.md) devices.
