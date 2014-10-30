# Running **code**<br> on a **phone**

---

## Pushing to a real device

---

### Enable Developer menu

1. `Settings` > `Devices Information` > `More Information`
2. Check `Developer Menu`

---

### Enable USB debugging

1. Go back to `Settings` > `Developer Menu`
2. In `Debugging via USB`
3. Select `ADB and DevTools`

---

### Push Gaia

```bash
$ cd /path/to/gaia
$ make reset-gaia
```

<img src="img/warning.svg" alt="Warning" style="vertical-align: bottom;"> This will erase all the data in your device!

(But you can do a backup)

---

### Useful options

Don't show the first time user experience
```bash
$ NOFTU=1 make reset-gaia
```

Start in debug mode
```bash
$ DEVICE_DEBUG=1 make reset-gaia
```

---

### Pushing a single app

```bash
$ APP=calendar make install-gaia
```

---

### Debug in the WebIDE

1. Launch Firefox Nightly
2. `Tools` > `Web Developer` > `WebIDE`
3. `Select Runtime` > under `USB Devices`
4. Select your device (`Flame`, `GP-Peak`...)

---

### Troubleshooting

[MDN - Installing Firefox OS on a mobile device](https://developer.mozilla.org/en-US/Firefox_OS/Installing_on_a_mobile_device)

---

## Using Firefox Nightly

---

### Build a profile

```bash
$ cd /path/to/gaia
$ DEBUG=1 DESKTOP=0 make
```

---

### Configure the WebIDE

1. Launch Firefox Nightly
1. `Tools` > `Web Developer` > `WebIDE`
2. `Select Runtime` > `Install Simulator`
3. Install the followings:
  * `ADB Helper Add-on`
  * `Firefox OS 2.2 Simulator`

---

### Select your profile

1. Back to Firefox Nightly (close the WebIDE)
2. `Tools` > `Add-ons`
3. Under Simulator 2.2, click on `Preferences`
<img src="img/simulator-preferences.png" alt="Add-ons preferences menu" style="height: 80px;">
4. Click `Select a custom Gaia profile directory`
5. Select your newly created profile

---

### Launch the simulator

1. Back to the WebIDE<br>
<img src="img/WebIDE.png" alt="WebIDE" style="height: 320px;">
2. `Select Runtime` > `Firefox OS 2.2`
