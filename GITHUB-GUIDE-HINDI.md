# APK Kaise Banayein — Step by Step (Hindi)
## GitHub se FREE mein APK build karein (koi Android Studio nahi chahiye)

---

## Ek baar karna hai — Phir automatically APK banta rahega

---

## Step 1: GitHub Account Banao (Free)
1. https://github.com/signup kholo
2. Email + Password se account banao
3. Free plan select karo

---

## Step 2: New Repository Banao
1. GitHub.com mein login karo
2. Top-right mein **"+"** icon → **"New repository"** click karo
3. Repository name: `clb-sms-reader`
4. **Public** ya **Private** — dono theek hain
5. **"Create repository"** click karo

---

## Step 3: Files Upload Karo
1. Nayi repository mein **"uploading an existing file"** link click karo
   (ya "Add file" → "Upload files")
2. `clb-android-sms-reader.zip` ko unzip karo apne computer pe
3. Unzip ke andar ki **saari files** drag karke GitHub pe dalo
   ```
   clb-android-sms-reader/
   ├── .github/           ← yeh bhi upload karo (hidden folder)
   ├── app/
   ├── gradle/
   ├── build.gradle
   ├── settings.gradle
   └── ...
   ```
4. Neeche **"Commit changes"** click karo
5. **"Commit directly to the main branch"** select karo
6. **"Commit changes"** button click karo

---

## Step 4: APK Build Hoga Automatically!
1. Repository mein **"Actions"** tab click karo
2. **"Build Android APK"** workflow dikhega
3. Status: 🟡 Yellow = Build chal raha hai (3-5 minute lagenge)
4. Status: ✅ Green = APK ready hai!

---

## Step 5: APK Download Karo
1. Actions tab → Latest successful run click karo
2. Neeche **"Artifacts"** section mein jaao
3. **"CLB-SMS-Reader-APK"** download karo
4. Zip nikalo → `app-debug.apk` milega

---

## Step 6: Phone pe Install Karo
1. `app-debug.apk` apne phone pe transfer karo (WhatsApp ya email se)
2. Phone mein: **Settings → Security → Unknown Sources → ON**
3. APK file tap karo → **Install** click karo
4. App open karo → Permissions Allow karo

---

## App Setup (Install ke Baad)

### WordPress se Secret Key Copy Karo:
WordPress Admin → **CLB UPI Settings** → Secret Key → Copy

### App mein Settings Bharo:
| Field | Example |
|-------|---------|
| WordPress Site URL | https://trustedsattamatka.com |
| Secret Key | (WordPress se copy karo) |

### Switch ON karo → SAVE dabao → Done! ✓

---

## ❓ Kya Phone Restart Karna Padega?

**NAHI.** App ek baar setup karo — phir:
- ✅ Phone ko **restart nahi karna** padega
- ✅ App **background mein hamesha** kaam karega
- ✅ Agar phone restart bhi ho to app **khud se start** ho jaata hai
- ✅ Switch OFF → ON karo — bas itna

---

## ❓ Kya Bar-Bar APK Build Karna Padega?

**NAHI.** Sirf ek baar:
- GitHub pe upload karo → ek baar APK download karo → phone pe install karo
- Agar future mein app update chahiye — toh file change karo GitHub pe → naya APK automatic bnega

---

## ❓ Secret Key Kahan Se Milegi?

WordPress Admin Panel:
1. **CLB UPI Payment → Settings**
2. **"SMS API Secret Key"** field mein ek random key generate hogi
3. Copy karo → Android app mein paste karo

---

## Koi Pareshani? WhatsApp pe Photo/Screenshot bhejo.
