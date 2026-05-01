# CLB SMS Reader — Android App
## Bank SMS → Wallet Auto-Credit

---

## यह App क्या करता है?

जब कोई customer UPI QR scan करके पैसे भेजता है:
1. Bank SMS आता है आपके phone पर
2. यह App उस SMS को automatically पकड़ता है
3. आपकी WordPress site को SMS भेजता है
4. WordPress plugin virtual account number ढूंढता है
5. सही customer का wallet automatically credit हो जाता है

**कोई external API नहीं — सब कुछ आपके अपने server पर**

---

## Android Studio में Compile कैसे करें?

### Step 1: Android Studio Install करें
- Download: https://developer.android.com/studio
- Install करें (free है)

### Step 2: Project Open करें
1. Android Studio खोलें
2. **File → Open** click करें
3. `clb-android-sms-reader` folder select करें
4. **OK** दबाएं

### Step 3: Sync करें
- "Sync Now" button दबाएं (top bar में आएगा)
- Internet connection चाहिए (dependencies download होंगी)
- 2-3 minutes लगेंगे

### Step 4: APK Build करें
- **Build → Build Bundle(s)/APK(s) → Build APK(s)**
- Path: `app/build/outputs/apk/debug/app-debug.apk`

### Step 5: Phone पर Install करें
- Phone में: Settings → Security → Unknown Sources → ON
- APK file WhatsApp से खुद को भेजें
- Phone पर install करें

---

## App Setup (Phone पर)

### Step 1: Permissions दें
- App खोलें
- SMS, RECEIVE_SMS permission → **Allow** दबाएं

### Step 2: WordPress Settings
WordPress Admin → CLB UPI Settings → Secret Key copy करें

### Step 3: App में भरें
| Field | Value |
|-------|-------|
| WordPress Site URL | https://aapkisite.com |
| Secret Key | WordPress से copy की हुई key |

### Step 4: Switch ON करें
- Switch toggle करें → Green हो जाएगा
- **SAVE** दबाएं

### Step 5: Test करें
- ₹1 का test payment करें अपने QR से
- Log में `✓ Wallet credited` दिखना चाहिए

---

## Files की List

```
clb-android-sms-reader/
├── app/
│   ├── build.gradle                    ← App dependencies
│   └── src/main/
│       ├── AndroidManifest.xml         ← Permissions
│       ├── java/com/clb/smsreader/
│       │   ├── MainActivity.java       ← Main Screen
│       │   ├── SmsReceiver.java        ← SMS Intercept (सबसे जरूरी)
│       │   ├── ApiService.java         ← WordPress API Call
│       │   ├── BootReceiver.java       ← Phone Restart
│       │   └── SharedPref.java         ← Settings Save
│       └── res/
│           ├── layout/activity_main.xml ← Screen Design
│           └── values/                 ← Colors, Strings
├── build.gradle                        ← Project setup
├── settings.gradle
└── README-HINDI.md                     ← यह file
```

---

## Common Problems

| Problem | Solution |
|---------|----------|
| "Permission Denied" | Settings → Apps → CLB SMS Reader → Permissions → SMS Allow |
| Wallet credit नहीं हुआ | Log check करें — URL या Secret Key गलत हो सकती है |
| App band होने पर काम नहीं | Battery Optimization → CLB SMS Reader → "Don't optimize" |
| Reboot के बाद काम नहीं | BootReceiver auto-start enabled है, पर कुछ phones पर manually App Lock में allow करना होता है |

---

## क्या External API चाहिए?

**नहीं।** सिर्फ यह चाहिए:
- आपका Android phone (bank SMS receive करने के लिए)
- आपकी WordPress site (wallet credit करने के लिए)
- Internet connection (phone → WordPress API call)

कोई Razorpay, PayU, Cashfree, Stripe नहीं।
कोई subscription नहीं।
