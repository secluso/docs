---
sidebar_position: 2
---

# Five Minute Setup

Want to get started fast? This is the quickest way to set up Secluso. In just a few minutes, you’ll have a secure camera system running with end-to-end encryption.


### 1. Install the Secluso App

Download the official Secluso app from your app store:
* Google Play (Android)
* App Store (iOS)

---

### 2. Set up your Raspberry Pi 

If you don't have a Raspberry Pi or any hardware, we recommend you take a look at the [Hardware page](./RECOMMENDED_HARDWARE.md).

On your Raspberry Pi, just run:

```md
curl -sSL https://github.com/secluso/secluso/camera_hub/setup.sh | bash
```

<details>
<summary><strong>What the script does under the hood</strong></summary>
This will:
* Install all dependencies  
* Download the latest verified Secluso camera hub release  
* Configure with our custom rpicam-apps if needed  
* Configure system services to automatically run it on startup  
* Auto-generate your camera secret QR code (for pairing in the app)  
</details>

After the script runs, it will display and save a QR code image  `camera_secret_qrcode.png`. You’ll scan this with the Secluso app later.

---

### 3. Set up your Server

Pick one of our recommended low-cost VPS providers, or use your own:
* [Ionos VPS – $2/mo, 1 vCPU, 1 GB RAM, **unlimited bandwidth**, month-to-month commitment](https://www.ionos.com/servers/vps)

Once you have a server, run this on your **local machien**:

```md
curl -sSL https://github.com/secluso/secluso/server/setup.sh | bash
```

This will prompt you to enter things such as your server IP and password to set it up remotely.

<details>
<summary><strong>What the script does under the hood</strong></summary>
This will:
* Install the Secluso server binary
* Configure system services to automatically run it on startup
* Auto-generate server credentials + QR code for your app and save it locally on your computer.
</details>


Again, a QR code will be shown and saved named `user_credentials.png`. Keep it safe.

---

### 4. Pairing the App
* Open the Secluso app.
* Scan the server QR code (from Step 3).
* Then scan the camera QR code (from Step 2).

That’s it, your app is paired!

---

Done! You now have a fully private, end-to-end encrypted camera system with minimal setup.

