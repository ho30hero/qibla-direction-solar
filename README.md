# 🧭 Qibla Direction & Solar Shadow Alignment Calculator
### محاسبه‌گر فوق‌العاده دقیق جهت قبله و انطباق سایه شاخص با کعبه

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PWA Ready](https://img.shields.io/badge/PWA-Installable-emerald.svg)](https://w3c.github.io/manifest/)
[![Vite](https://img.shields.io/badge/Vite-6.x-646CFF.svg)](https://vitejs.dev/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-v4-38BDF8.svg)](https://tailwindcss.com/)
[![Leaflet](https://img.shields.io/badge/Leaflet-1.9.4-199900.svg)](https://leafletjs.com/)
[![Multi--Language](https://img.shields.io/badge/Languages-9%20Supported-orange.svg)](#supported-languages--زبانهای-پشتیبانیشده)

---

## 📑 Table of Contents / فهرست مطالب

- [English Documentation](#-english-documentation)
  - [About the Project](#about-the-project)
  - [Why the Solar Shadow Method?](#why-the-solar-shadow-method)
  - [Key Features](#key-features)
  - [Supported Languages](#supported-languages)
  - [Scientific & Mathematical Foundations](#scientific--mathematical-foundations)
  - [How to Use (Step-by-Step Guide)](#how-to-use-step-by-step-guide)
  - [Things Good to Know (Practical Tips)](#things-good-to-know-practical-tips)
  - [Islamic Prayer Times](#islamic-prayer-times)
  - [Technology Stack](#technology-stack)
  - [Local Development & Deployment](#local-development--deployment)
- [راهنمای فارسی (Persian Documentation)](#-راهنمای-جامع-فارسی-persian-documentation)
  - [درباره برنامه و هدف آن](#درباره-برنامه-و-هدف-آن)
  - [چرا روش سایه شاخص آفتاب دقیق‌ترین روش است؟](#چرا-روش-سایه-شاخص-آفتاب-دقیقترین-روش-است)
  - [قابلیت‌ها و امکانات کلیدی](#قابلیتها-و-امکانات-کلیدی)
  - [زبان‌های پشتیبانی‌شده](#زبانهای-پشتیبانیشده)
  - [مبانی علمی و محاسبات ریاضی](#مبانی-علمی-و-محاسبات-ریاضی)
  - [راهنمای گام‌به‌گام نحوه استفاده](#راهنمای-گامبهگام-نحوه-استفاده)
  - [نکات طلایی و کاربردی که باید بدانید](#نکات-طلایی-و-کاربردی-که-باید-بدانید)
  - [محاسبه اوقات شرعی](#محاسبه-اوقات-شرعی)
  - [فناوری‌های به‌کار رفته و توسعه محلی](#فناوریهای-بهکار-رفته-و-توسعه-محلی)

---

# 🇬🇧 English Documentation

## About the Project

**Qibla Direction & Solar Shadow Alignment Calculator** is a high-precision, web-based astronomical instrument and interactive dashboard designed to determine the exact direction of the **Holy Kaaba in Mecca** from anywhere on Earth. 

Unlike conventional compass apps that rely solely on erratic magnetic sensors, this application combines **rigorous spherical trigonometry (Great Circle Geodesics)** with **real-time celestial solar positioning algorithms (Meeus Astronomical Algorithms)**. It calculates the exact second of the day when the shadow cast by a vertical rod (gnomon / شاخص) aligns with mathematical precision along the Qibla azimuth.

Whether you are architecting a new mosque, orienting a prayer hall (Mihrab), setting up a home prayer space, or conducting scientific and educational field observations, this tool provides laboratory-grade astronomical precision right in your web browser.

---

## Why the Solar Shadow Method?

Smartphones and standard compasses are notoriously susceptible to errors:
1. **Magnetic Declination**: Magnetic North deviates significantly from True Geographic North depending on your location on Earth (sometimes by 5° to 20°+).
2. **Electromagnetic & Structural Interference**: Reinforced concrete rebar in modern buildings, electrical cables, structural steel beams, smart watches, and phone speaker magnets cause severe magnetic deflection.
3. **Sensor Drift**: Internal digital magnetometers require frequent recalibration and are prone to unannounced sensor tilt errors.

### The Astronomical Solution: The Solar Gnomon (شاخص آفتاب)
The sun's position is dictated by immutable celestial mechanics. When a straight, plumb rod is placed perpendicularly on a flat horizontal plane exposed to direct sunlight:
- Its shadow falls directly opposite the sun's azimuth:
  $$\text{Shadow Azimuth} = (\text{Solar Azimuth} + 180^\circ) \pmod{360^\circ}$$
- At specific times of day, this shadow line either aligns directly with the Qibla bearing or lies precisely on its reverse extension.
- Aligning a prayer rug or wall along this shadow line achieves **an accuracy within 0.1 degrees**, entirely free from magnetic distortion.

---

## Key Features

### 1. 🧭 Exact Mathematical Qibla Calculation
- Calculates the forward Great Circle azimuth from any observer coordinate $(\phi_1, \lambda_1)$ to the Kaaba $(\phi_2 = 21.422500^\circ\text{ N}, \lambda_2 = 39.826200^\circ\text{ E})$.
- Displays bearing down to two decimal places (e.g., `218.42°`), complete with 16-point cardinal compass directions (SW, SSW, etc.).
- Calculates the true geodesic surface distance to Mecca in kilometers.

### 2. ☀️ Real-Time Solar Mechanics Engine
- Computes real-time **Solar Azimuth**, **Solar Altitude (Elevation)**, **Solar Declination**, **Equation of Time**, and **Local Astronomical Solar Noon (Transit)**.
- Computes the instantaneous shadow length multiplier relative to gnomon height:
  $$\text{Shadow Length} = \frac{h}{\tan(\text{Altitude})}$$
- Dynamic day/night status indicator showing elevation degrees above the horizon or degrees below the horizon during twilight and nighttime.

### 3. ⏱️ Automated Daily Shadow Alignment Scanner
- High-resolution iterative scanning engine scans every minute (and refines to the exact second) throughout the chosen day to find the exact moment when the solar shadow aligns with the Qibla direction.
- Accounts for both direct alignment (when the shadow points towards Kaaba) and reverse alignment (when the shadow points away from Kaaba while the sun is in the Qibla direction).
- Highlights the countdown or time difference between the current local time and the exact alignment moment.

### 4. 🕋 Semi-Annual Solar Zenith over Mecca (رصد خورشید در مکه)
- Automatically computes and highlights the two days each year (**May 28 at ~09:18 UTC** and **July 16 at ~09:27 UTC**) when the sun reaches the exact local zenith ($90^\circ$ altitude) directly above the Holy Kaaba.
- At these exact two moments, anyone on Earth who can see the sun in the sky faces the Kaaba simply by looking directly toward the sun.

### 5. 🗺️ Interactive Dual-Layer Leaflet Map
- **High-Resolution Satellite Imagery**: Toggle between detailed Esri World Imagery satellite basemap and clear Street maps.
- **Geodesic Great Circle Line**: Real-time vector line connecting the observer directly to Mecca.
- **Solar Shadow Vector**: Real-time projected golden ray showing the shadow direction on the ground.
- **Draggable Marker**: Drag the observer pin anywhere in the world to instantly recompute all angles, prayer times, and shadow alignment moments.
- **Smart Mobile Gesture Lock**: 2-finger scroll-safe gesture overlay prevents unwanted map capturing while browsing on mobile phones, with a 1-tap quick toggle to 1-finger panning.
- **Fit-to-Bounds**: One-click button to zoom and pan the map to frame both your location and Mecca simultaneously.

### 6. 📅 Synchronized Dual Calendar (Jalali / Solar Hijri & Gregorian)
- Seamless bidirectional conversion between **Persian Solar Hijri (هجری شمسی / جلالی)** and **Gregorian (میلادی)** calendars.
- Quick "Today" jump buttons for both calendar modes.
- Complete time-travel capabilities: simulate solar shadows and Qibla alignments for any past or future date and time.
- Real-time live clock ticking mode with freeze/resume option.

### 7. 🕌 Accurate Islamic Prayer Times (Awqat al-Salah)
- Displays all standard daily prayer moments computed using high-accuracy astronomical formulas:
  - **Fajr** (Dawn, astronomical twilight)
  - **Sunrise** (Tulu' al-Shams)
  - **Dhuhr** (Astronomical Solar Noon)
  - **Asr** (Standard Shadow Ratio)
  - **Maghrib** (Sunset / Dusk)
  - **Isha** (Night twilight)
  - **Midnight** (Islamic Midnight / Nisf al-Layl)
- Next prayer countdown badge with active prayer period highlighting.

### 8. 📍 Global Geocoding & City Search
- Integrated geocoding search powered by OpenStreetMap Nominatim for searching any city, district, or address worldwide.
- Built-in instant preset cities across Iran and international metropolises (Tehran, Mashhad, Isfahan, Tabriz, Shiraz, Mecca, Medina, Jerusalem, Cairo, Istanbul, London, Berlin, Paris, Beijing, Madrid, etc.).
- One-tap hardware GPS button to retrieve device coordinates with high spatial accuracy.

### 9. 📱 Progressive Web App (PWA) & Offline Support
- Fully installable on iOS, Android, macOS, Windows, and ChromeOS.
- Service Worker caching enabling offline calculation of Qibla bearings and solar shadow mechanics without active internet connection.
- Custom iOS Safari install guide modal detailing the "Add to Home Screen" procedure.

---

## Supported Languages / زبان‌های پشتیبانی‌شده

The application features full internationalization (i18n) across **9 languages**, complete with native typographic directionality (**RTL / LTR**) and dynamic numeral formatting:

| Language | Code | Script Direction | Numeral System |
| :--- | :---: | :---: | :---: |
| **Persian (فارسی)** | `fa` | RTL (راست به چپ) | Persian digits (`۰ ۱ ۲ ۳ ۴ ۵ ۶ ۷ ۸ ۹`) |
| **English** | `en` | LTR (Left to Right) | Latin digits (`0 1 2 3 4 5 6 7 8 9`) |
| **Arabic (العربية)** | `ar` | RTL (يمين إلى يسار) | Eastern Arabic digits (`٠ ١ ٢ ٣ ٤ ٥ ٦ ٧ ٨ ٩`) |
| **German (Deutsch)** | `de` | LTR (Left to Right) | Latin digits (`0 1 2 3 4 5 6 7 8 9`) |
| **Chinese (中文)** | `zh` | LTR (Left to Right) | Latin digits (`0 1 2 3 4 5 6 7 8 9`) |
| **French (Français)** | `fr` | LTR (Left to Right) | Latin digits (`0 1 2 3 4 5 6 7 8 9`) |
| **Spanish (Español)** | `es` | LTR (Left to Right) | Latin digits (`0 1 2 3 4 5 6 7 8 9`) |
| **Turkish (Türkçe)** | `tr` | LTR (Soldan Sağa) | Latin digits (`0 1 2 3 4 5 6 7 8 9`) |
| **Urdu (اردو)** | `ur` | RTL (دائیں سے بائیں) | Urdu / Eastern Arabic digits (`۰ ۱ ۲ ۳ ۴ ۵ ۶ ۷ ۸ ۹`) |

---

## Scientific & Mathematical Foundations

### 1. Great Circle Qibla Azimuth
The forward azimuth $Q$ from an observer at latitude $\phi_1$ and longitude $\lambda_1$ to the Kaaba at latitude $\phi_2$ and longitude $\lambda_2$ is governed by spherical trigonometry:

$$\tan(Q) = \frac{\sin(\lambda_2 - \lambda_1)}{\cos(\phi_1)\tan(\phi_2) - \sin(\phi_1)\cos(\lambda_2 - \lambda_1)}$$

Using `atan2` to handle quadrants accurately:
$$Q = \text{atan2}\Big(\sin(\Delta\lambda), \; \cos(\phi_1)\tan(\phi_2) - \sin(\phi_1)\cos(\Delta\lambda)\Big)$$

Where:
- $\phi_1, \lambda_1$: Observer Latitude and Longitude (radians)
- $\phi_2 = 21.4225^\circ \times \frac{\pi}{180} \approx 0.373899\text{ rad}$
- $\lambda_2 = 39.8262^\circ \times \frac{\pi}{180} \approx 0.695099\text{ rad}$
- $\Delta\lambda = \lambda_2 - \lambda_1$
- Result $Q$ is converted to degrees and normalized to $[0^\circ, 360^\circ)$.

### 2. Solar Position (Meeus Astronomical Algorithms)
The solar coordinates are determined using high-precision approximation formulas for:
1. **Julian Century $T$** from J2000.0.
2. **Geometric Mean Longitude $L_0$** and **Mean Anomaly $M$** of the Sun.
3. **Equation of the Center $C$** and Sun's **True Longitude $\odot$**.
4. **Sun's Apparent Declination $\delta$** and **Equation of Time $E_t$**.
5. **Local Hour Angle $H$** based on Local Solar Time and Greenwich Mean Sidereal Time.
6. **Solar Elevation (Altitude) $\alpha$**:
   $$\sin(\alpha) = \sin(\phi)\sin(\delta) + \cos(\phi)\cos(\delta)\cos(H)$$
7. **Solar Azimuth $A$**:
   $$\tan(A) = \frac{\sin(H)}{\cos(H)\sin(\phi) - \tan(\delta)\cos(\phi)}$$

---

## How to Use (Step-by-Step Guide)

### Method 1: Using the Live Map & GPS (Quick Method)
1. Open the application on your smartphone, tablet, or laptop.
2. Tap the **"موقعیت‌یابی GPS" (GPS Location)** button or type your city into the search box.
3. Alternatively, click anywhere on the map or drag the blue user pin to your exact building or roof.
4. Read your **Qibla Azimuth** (e.g., `218.4°`). The green line on the map indicates the direct Great Circle trajectory to Mecca.

### Method 2: The Physical Gnomon Shadow Alignment (Laboratory-Grade Method)
1. In the **"انطباق سایه شاخص با قبله" (Solar Shadow Alignment)** card, view the calculated alignment time for today (e.g., `13:42:15`).
2. A few minutes before the designated time, prepare a clean, flat, level horizontal surface exposed to sunlight.
3. Fix a straight rod, stick, or plumb line (شاقول) strictly perpendicular to the surface.
4. At the designated second, mark the shadow line cast by the rod on the ground.
5. If the system indicates direct alignment, **the shadow line points directly toward the Qibla**. If the sun is in the direction of the Qibla, **looking along the shadow toward the rod points directly to the Kaaba**.

### Method 3: The Semi-Annual Kaaba Zenith Moment (May 28 & July 16)
1. On **May 28 (at ~12:48 Tehran time / 09:18 UTC)** or **July 16 (at ~12:57 Tehran time / 09:27 UTC)**:
2. Ensure you are outdoors with direct visibility to the sun.
3. Face the sun directly (taking care not to stare directly into solar glare without eye protection).
4. **You are looking directly toward the Holy Kaaba** anywhere in the world where the sun is currently above the horizon.

---

## Things Good to Know (Practical Tips)

> 💡 **Tip 1: Verticality is Paramount**  
> Use a weighted string (plumb line / شاقول) rather than a rigid rod if possible. A plumb line is naturally and flawlessly vertical according to Earth's gravitational field, eliminating vertical tilt errors.

> 💡 **Tip 2: Surface Horizontality**  
> Ensure the floor or board on which the shadow is cast is perfectly horizontal using a spirit level (تراز حباب‌دار) or a smartphone level app.

> 💡 **Tip 3: The Shadow Edge (Umbra vs. Penumbra)**  
> The sun is not a point light source; it has an apparent angular diameter of $\approx 0.5^\circ$. This creates an umbra (inner dark shadow) and penumbra (soft outer edge). Always trace along the centerline of the shadow or use a thin pin/wire at the top for maximum sharpness.

> 💡 **Tip 4: Local Time Accuracy**  
> Ensure your phone or watch is synchronized with standard internet time (NTP / Network Time Protocol) to within a second. A timing error of 4 minutes corresponds to an angular error of approximately $1^\circ$ in solar azimuth.

---

## Islamic Prayer Times

The app calculates daily prayer times based on established solar altitude criteria:
- **Fajr**: Sun is $17.7^\circ$ (or standard twilight angles) below the eastern horizon.
- **Sunrise**: Upper limb of the sun touches the eastern horizon.
- **Dhuhr**: Instantaneous moment of Solar Noon when the sun crosses the local meridian (highest daily altitude).
- **Asr**: Shadow length equals object height plus noontime shadow.
- **Maghrib**: Sun drops below the western horizon plus dusk transition.
- **Isha**: End of twilight when the sun is $14.0^\circ$ below the western horizon.
- **Midnight**: Halfway mark between Sunset and the following Dawn.

---

## Technology Stack

- **Core Framework**: Modern HTML5, ES Modules, and Vanilla JavaScript with Vite compilation.
- **Styling**: Tailwind CSS v4 with custom CSS variables for light/dark theme contrast.
- **Mapping**: Leaflet.js v1.9.4 with custom SVG markers, Great Circle geodesic polylines, and Esri World Imagery + OpenStreetMap tile providers.
- **PWA Architecture**: Web App Manifest (`manifest.webmanifest`), custom offline caching Service Worker (`sw.js`), Apple Touch Icon configurations, and responsive viewport scaling.
- **Icons**: Lucide Icons vector set.
- **Zero External Backend Requirement**: 100% of mathematical and astronomical computations occur locally in-browser on the client side with zero latency and full privacy.

---

## Local Development & Deployment

### Prerequisites
- Node.js (version 18 or higher recommended)
- npm or yarn

### Installation
```bash
# Clone the repository
git clone https://github.com/your-username/qibla-direction-calculator.git

# Navigate to project directory
cd qibla-direction-calculator

# Install dependencies
npm install
```

### Running Development Server
```bash
npm run dev
```
Open `http://localhost:3000` in your web browser.

### Production Build
```bash
npm run build
```
The optimized production bundle will be generated in the `dist/` directory.

### Preview Production Build
```bash
npm run preview
```

---
---

# 🇮🇷 راهنمای جامع فارسی (Persian Documentation)

## درباره برنامه و هدف آن

نرم‌افزار **محاسبه‌گر فوق‌العاده دقیق جهت قبله و انطباق سایه شاخص با کعبه** یک ابزار نجومی، مهندسی و کاربردی آنلاین است که با هدف محاسبه دقیق‌ترین جهت ممکن به سمت **کعبه مشرفه در مکه مکرمه** طراحی شده است.

برخلاف قطب‌نماهای معمولی گوشی‌های هوشمند که به دلیل خطاهای مغناطیسی همواره دچار انحراف هستند، این برنامه با ترکیب **محاسبات مثلثات کروی ژئودزیک (روی مدار دایره عظیمه کره زمین)** و **فرمول‌های مکانیک سماوی موقعیت خورشید (الگوریتم‌های نجومی ژان میوس)**، لحظه دقیق ثانیه‌ای از روز را محاسبه می‌کند که در آن، امتداد سایه یک شاخص عمودی (میله یا شاقول) دقیقاً منطبق بر زاویه قبله خواهد بود.

این نرم‌افزار برای معماران، سازندگان مساجد، قبله‌شناسان، ستاره‌شناسان آماتور و تمامی مسلمانانی که می‌خواهند با اطمینان صددرصدی و بدون کوچک‌ترین خطای سنسوری، جهت سجاده، محراب و قبله محل زندگی یا کار خود را تنظیم کنند ایده‌آل است.

---

## چرا روش سایه شاخص آفتاب دقیق‌ترین روش است؟

قطب‌نماهای مغناطیسی و سنسورهای قطب‌نمای موبایل به چند دلیل بزرگ دارای خطای فاحش هستند:
1. **انحراف مغناطیسی (Magnetic Declination)**: قطب شمال مغناطیسی با قطب شمال جغرافیایی (محور چرخش زمین) منطبق نیست. در شهرهای مختلف ایران و جهان، این اختلاف زاویه‌ای بین ۵ تا ۲۰ درجه متغیر است!
2. **تداخل الکترومغناطیسی و سازه‌های بتنی**: میلگردهای درون بتن مسلح ساختمان‌ها، تیرآهن‌ها، سیم‌کشی برق و حتی آهنربای بلندگوی گوشی موبایل قطب‌نما را منحرف می‌کنند.
3. **خطای کالیبراسیون و شیب دست**: سنسور مغناطیسی گوشی‌ها نیاز به کالیبراسیون مداوم (حرکت عدد 8 انگلیسی) دارند و با کوچک‌ترین زاویه گرفتن گوشی در دست، جهت تغییر می‌کند.

### راهکار نجومی: روش شاخص خورشید (سنت کهن دانشمندان اسلامی)
حرکت ظاهری خورشید حاصل قوانین لایتغیر مکانیک مداری کیهان است. وقتی یک شاخص (میله صاف یا نخ شاقول) را بر سطحی تراز و در برابر نور خورشید قرار می‌دهید:
- سایه آن دقیقاً در سمت مخالف زاویه آزیموت خورشید کشیده می‌شود:
  $$\text{زاویه سایه} = (\text{زاویه خورشید} + ۱۸۰^\circ) \pmod{۳۶۰^\circ}$$
- در ساعت و دقیقه‌ای مشخص از روز، این سایه دقیقاً در امتداد خط قبله قرار می‌گیرد.
- دقت این روش **کسری از دهم درجه (زیر ۰٫۱ درجه)** است و هیچ میلگرد، کابل برق یا میدان مغناطیسی نمی‌تواند آن را دستکاری کند.

---

## قابلیت‌ها و امکانات کلیدی

### ۱. 🧭 محاسبه ریاضی و ژئودزیک زاویه قبله
- محاسبه زاویه سمتی بر مبنای دایره عظیمه (Great Circle) از مختصات هر نقطه دلخواه روی زمین به مختصات کعبه معظمه ($21.4225^\circ\text{ N}, 39.8262^\circ\text{ E}$).
- نمایش جهت سمتی با دقت دو رقم اعشار (مانند `۲۱۸٫۴۲ درجه`) و جهت‌های ۱۶ گانه قطب‌نما (جنوب‌غربی، جنوب-جنوب‌غربی و ...).
- محاسبه دقیق فاصله مستقیم جغرافیایی تا مکه مکرمه به کیلومتر.

### ۲. ☀️ موتور موقعیت‌یاب لحظه‌ای خورشید
- محاسبه لحظه‌ای **زاویه سمت خورشید (Azimuth)**، **زاویه ارتفاع از افق (Altitude)**، **میل خورشید (Declination)**، **تعدیل زمان (Equation of Time)** و **لحظه ظهر شرعی نجومی (نصف‌النهار محلی)**.
- محاسبه نسبت طول فیزیکی سایه به بلندی شاخص در هر لحظه.
- نمایش وضعیت روز و شب با ذکر زاویه خورشید در بالای افق یا زاویه منفی آن در زیر افق هنگام تاریکی.

### ۳. ⏱️ اسکنر هوشمند لحظه انطباق سایه با قبله
- پویشگر خودکار در طول روز که دقیق‌ترین لحظه (ساعت، دقیقه و ثانیه) انطباق سایه شاخص با خط قبله را استخراج می‌کند.
- تفکیک حالت انطباق مستقیم (سایه رو به قبله) و انطباق معکوس (خورشید در جهت قبله و سایه پشت به قبله).
- تایمر معکوس برای آگاهی از فاصله زمانی باقی‌مانده تا لحظه طلایی انطباق امروز.

### ۴. 🕋 محاسبه رویداد خورشید بر فراز کعبه (دو بار در سال)
- شناسایی خودکار دو روز مشهور سال (**۷ خرداد / ۲۸ مه** ساعت حدود ۱۲:۴۸ به وقت ایران و **۲۵ تیر / ۱۶ ژوئیه** ساعت حدود ۱۲:۵۷ به وقت ایران) که خورشید درست در سرسو (سمت‌الرأس ۹۰ درجه) بالای کعبه در مکه قرار می‌گیرد.
- در این دو لحظه، هر کس در هر نقطه از نیم‌کره روشن زمین به سمت خورشید بایستد، مستقیماً رو به قبله ایستاده است.

### ۵. 🗺️ نقشه تعاملی و پیشرفته دو لایه
- امکان تغییر آنی بین **نقشه ماهواره‌ای باکیفیت و زنده (تصاویر ماهواره‌ای سنجش از دور Esri)** و **نقشه معابر و خیابان‌ها**.
- خط سبز ژئودزیک پیوسته که موقعیت کاربر را مستقیماً به خانه کعبه وصل می‌کند.
- بردار پرتو زرین سایه که زاویه و جهت سایه را در همین لحظه روی نقشه رسم می‌کند.
- قابلیت کشیدن و رها کردن (Drag & Drop) نشانگر روی نقشه با به‌روزرسانی آنی تمامی محاسبات.
- **حالت لمس امن دو انگشتی برای گوشی‌های موبایل** جهت جلوگیری از گیر کردن صفحه هنگام اسکرول، با قابلیت سوییچ به لمس تک‌انگشتی.
- دکمه کادربندی هوشمند (Fit Bounds) جهت نمایش هم‌زمان ناظر و مکه در یک قاب.

### ۶. 📅 تقویم هم‌گام هجری شمسی (جلالی) و میلادی
- مبدل دوسویه و کاملاً دقیق تاریخ جلالی و میلادی با در نظر گرفتن سال‌های کبیسه.
- دکمه‌های پرش سریع «امروز» برای هر دو تقویم.
- امکان شبیه‌سازی گذشته و آینده: بررسی سایه و اوقات قبله در هر روز دلخواه از سال‌های گذشته یا آینده.
- تایمر زنده ساعت محلی با امکان توقف، تنظیم ثانیه‌ای و بازیابی به لحظه کنونی.

### ۷. 🕌 محاسبه دقیق اوقات شرعی هفت‌گانه
- محاسبه نجومی اوقات بر اساس ضوابط استاندارد و شیعی/بین‌المللی:
  - **اذان صبح** (فجر صادق)
  - **طلوع آفتاب**
  - **اذان ظهر** (ظهر شرعی و نصف‌النهار محلی)
  - **عصر** (بر مبنای افزایش طول سایه)
  - **اذان مغرب** (غروب شرعی خورشید و رفع حمره مشرقیه)
  - **اذان عشاء** (شفق نجومی)
  - **نیمه‌شب شرعی** (منتصف اللیل)
- شمارشگر معکوس تا نوبت اذان بعدی به همراه برجسته‌سازی نوبت جاری.

### ۸. 📍 جستجوی هوشمند شهرها و موقعیت‌یاب GPS
- جستجوی زنده در نام شهرها، روستاها و خیابان‌های سراسر جهان از طریق دیتابیس معتبر Nominatim و OpenStreetMap.
- فهرست پیش‌فرض از کلان‌شهرهای ایران (تهران، مشهد، اصفهان، تبریز، شیراز) و مقاصد بین‌المللی.
- دکمه اتصال مستقیم به سخت‌افزار GPS گوشی و تبلت با بازخوانی مختصات میلی‌متری.

### ۹. 📱 وب‌اپلیکیشن پیش‌رونده (PWA) و کارکرد کاملاً آفلاین
- قابل نصب بر روی گوشی‌های اندروید، آیفون (iOS)، مک و ویندوز به صورت یک اپلیکیشن مستقل.
- دارای سرویس‌ورکر اختصاصی (`sw.js`) و کش محلی که امکان استفاده از محاسبات نجومی و تقویم را **بدون نیاز به اینترنت** در سفرها و بیابان‌ها فراهم می‌آورد.
- پنجره راهنمای تصویری برای کاربران iOS جهت افزودن به صفحه اصلی (Add to Home Screen).

---

## زبان‌های پشتیبانی‌شده

نرم‌افزار دارای موتور بین‌المللی‌سازی بومی و پشتیبانی همه‌جانبه از **۹ زبان زنده دنیا** همراه با تغییر خودکار جهت متن (**راست‌به‌چپ / چپ‌به‌راست**) و فونت‌های استاندارد است:

1. **فارسی (Persian)** - راست به چپ با اعداد فارسی
2. **انگلیسی (English)** - چپ به راست با اعداد لاتین
3. **عربی (العربية)** - راست به چپ با اعداد عربی شرقی
4. **آلمانی (Deutsch)** - چپ به راست
5. **چینی (中文)** - چپ به راست
6. **فرانسوی (Français)** - چپ به راست
7. **اسپانیایی (Español)** - چپ به راست
8. **ترکی استانبولی (Türkçe)** - چپ به راست
9. **اردو (اردو)** - راست به چپ

---

## مبانی علمی و محاسبات ریاضی

### فرمول سمتی دایره عظیمه (Great Circle)
زاویه سمت قبله $Q$ از رابطه مثلثات کروی زیر استخراج می‌شود:

$$\tan(Q) = \frac{\sin(\lambda_2 - \lambda_1)}{\cos(\phi_1)\tan(\phi_2) - \sin(\phi_1)\cos(\lambda_2 - \lambda_1)}$$

در این رابطه:
- $\phi_1$ و $\lambda_1$: عرض و طول جغرافیایی محل سکونت شما
- $\phi_2 = 21.4225^\circ$: عرض جغرافیایی کعبه
- $\lambda_2 = 39.8262^\circ$: طول جغرافیایی کعبه
- نتیجه بر اساس تابع دوم آرک‌تانژانت (`atan2`) در بازه ۰ تا ۳۶۰ درجه به دست می‌آید.

---

## راهنمای گام‌به‌گام نحوه استفاده

### روش اول: تشخیص سریع از روی نقشه ماهواره‌ای
1. دکمه **«موقعیت‌یابی GPS»** را فشار دهید یا نام شهر/محله خود را جستجو کنید.
2. نقشه را به حالت **ماهواره‌ای (Satellite)** تغییر دهید.
3. بزرگ‌نمایی نقشه را زیاد کرده و نشانگر را دقیقاً روی سقف خانه، بالکن یا حیاط خود قرار دهید.
4. امتداد **خط سبز رنگ** به وضوح نشان می‌دهد که جهت قبله نسبت به دیوارهای ساختمان، کوچه یا خیابان شما دقیقاً چگونه است.

### روش دوم: روش آزمایشگاهی شاخص و سایه (دقیق‌ترین شیوه)
1. در بخش «انطباق سایه شاخص با قبله»، به زمان دقیق انطباق امروز نگاه کنید (مثلاً ساعت `۱۳:۲۱:۴۵`).
2. چند دقیقه قبل از ساعت اعلام‌شده، به محلی آفتاب‌گیر بروید.
3. سطحی کاملاً صاف و افقی انتخاب کنید و میله‌ای صاف یا نخ شاقول آویزان کنید.
4. رأس ثانیه مشخص‌شده، خط امتداد سایه را روی زمین علامت‌گذاری کنید.
5. خط ترسیم‌شده با اطمینان ۱۰۰٪ امتداد جهت قبله شماست.

---

## نکات طلایی و کاربردی که باید بدانید

> 🌟 **نکته ۱: عمود بودن شاخص**  
> توصیه می‌شود به جای چوب یا میله، از یک وزنه متصل به نخ باریک (شاقول بنایی) استفاده کنید. کشش گرانش زمین باعث می‌شود شاقول به طور طبیعی و بی‌نقص کاملاً بر سطح زمین عمود باشد.

> 🌟 **نکته ۲: تراز بودن سطح زمین**  
> تخته یا کاغذی که سایه روی آن می‌افتد باید کاملاً افقی باشد. یک تراز بنایی یا برنامه تراز حباب‌دار گوشی به شما در اطمینان از این موضوع کمک می‌کند.

> 🌟 **نکته ۳: لبه سایه (نیم‌سایه)**  
> چون قطر ظاهری قرص خورشید حدود نیم درجه است، سایه شاخص دارای یک حاشیه نیم‌سایه باریک است. همیشه مرکز سایه شاخص را ملاک قرار دهید.

> 🌟 **نکته ۴: تنظیم بودن ساعت**  
> اطمینان حاصل کنید که ساعت گوشی یا مچی شما با ساعت رسمی شبکه هماهنگ است. حتی یک دقیقه اختلاف در ساعت می‌تواند حدود یک چهارم درجه خطا ایجاد کند.

---

## محاسبه اوقات شرعی

تمامی محاسبات اوقات شرعی در این نرم‌افزار به شکل محلی و بر اساس موقعیت جغرافیایی و ارتفاع خورشید انجام می‌گیرد:
- **فجر (اذان صبح)**: زاویه ارتفاع منفی ۱۷٫۷ درجه خورشید زیر افق
- **طلوع آفتاب**: مماس شدن لبه بالایی خورشید با خط افق
- **ظهر شرعی**: رسیدن خورشید به بالاترین نقطه اوج آسمان (نصف‌النهار محلی)
- **عصر**: بر مبنای افزایش طول سایه اجسام
- **غروب و مغرب**: گذشتن قرص خورشید از افق غربی و زوال حمره مشرقیه
- **عشاء**: محو کامل شفق سرخ و قرارگیری خورشید در منفی ۱۴ درجه
- **نیمه‌شب شرعی**: میانگین دقیق زمانی بین غروب تا اذان صبح فردا

---

## فناوری‌های به‌کار رفته و توسعه محلی

این پروژه با بهره‌گیری از بروزترین استانداردهای وب توسعه یافته است:
- **محیط کامپایل و بیلد**: Vite 6.x همراه با تایپ‌اسکریپت
- **رابط کاربری و چیدمان**: Tailwind CSS نسخه ۴، طراحی واکنش‌گرا (Responsive) سازگار با موبایل، تبلت و دسکتاپ
- **موتور نقشه**: Leaflet.js همراه با پرووایدرهای CartoDB و Esri World Imagery
- **معماری PWA**: وب مانیفست اختصاصی، سرویس ورکر کش آفلاین و آیکون‌های وکتور
- **کتابخانه آیکون‌ها**: Lucide Icons
- **اجرای ۱۰۰٪ کلاینت‌ساید**: بدون نیاز به ارسال مختصات به سرور و با بالاترین سطح حریم خصوصی کاربران

### دستورات راه‌اندازی:
```bash
# نصب وابستگی‌ها
npm install

# اجرای سرور توسعه
npm run dev

# ساخت بیلد نهایی جهت استقرار در گیت‌هاب پیجز یا هاست
npm run build
```

---

## 📜 License / مجوز

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.  
این پروژه تحت مجوز متن‌باز MIT منتشر شده است و استفاده از آن برای عموم آزاد می‌باشد.
