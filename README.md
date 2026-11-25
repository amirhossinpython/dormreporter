<div dir="rtl" align="right">

<p align="center">
  <img src="static/img/college-logo.png" alt="لوگوی دانشکده ملی مهارت نیشابور" width="110">
</p>

<h1 align="center">سامانه مدیریت سرپرست‌های خوابگاه</h1>

<p align="center">
<b>معاونت فرهنگی و دانشجویی</b><br>
دانشکده ملی مهارت و کشاورزی نیشابور<br>
خوابگاه پردیس فناوری (فنی سابق)
</p>

<p align="center">
ثبت گزارش شیفت سرپرستان · بررسی و تأیید · مدیریت کامل توسط معاونت
</p>

<p align="center">
<img alt="Python" src="https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white">
<img alt="Flask" src="https://img.shields.io/badge/Flask-2.3%2B-000000?logo=flask">
<img alt="SQLite" src="https://img.shields.io/badge/SQLite-no%20server-003B57?logo=sqlite&logoColor=white">
<img alt="Windows" src="https://img.shields.io/badge/Windows%20Server-supported-0078D6?logo=windows&logoColor=white">
<img alt="Linux" src="https://img.shields.io/badge/Linux-supported-FCC624?logo=linux&logoColor=black">
<img alt="Offline" src="https://img.shields.io/badge/Offline-ready-success">
<img alt="Tests" src="https://img.shields.io/badge/tests-41%20passing-brightgreen">
</p>

---

## 📑 فهرست

**بخش اول — آموزش استفاده**

1. [سامانه چیست؟](#-سامانه-چیست)
2. [شروع سریع (۵ دقیقه)](#-شروع-سریع-۵-دقیقه)
3. [آموزش معاونت (مدیر کل سامانه)](#-آموزش-معاونت-مدیر-کل-سامانه)
4. [آموزش کارشناس](#-آموزش-کارشناس)
5. [آموزش سرپرست](#-آموزش-سرپرست)
6. [مسیر یک گزارش](#-مسیر-یک-گزارش)
7. [فهرست آدرس‌ها](#-فهرست-آدرسها)

**بخش دوم — نصب و راه‌اندازی**

8. [اجرا روی کامپیوتر خودتان](#-اجرا-روی-کامپیوتر-خودتان)
9. [دستورهای مدیریتی (CLI)](#-دستورهای-مدیریتی-cli)
10. [تنظیمات `.env`](#-تنظیمات-env)
11. [استقرار روی ویندوز سرور](#-استقرار-روی-ویندوز-سرور)
12. [استقرار روی لینوکس (Ubuntu)](#-استقرار-روی-لینوکس-ubuntu--nginx--https)
13. [هاست اشتراکی cPanel](#-هاست-اشتراکی-cpanel)
14. [نصب آفلاین و زیرمسیر](#-نصب-آفلاین-و-زیرمسیر)
15. [بکاپ و به‌روزرسانی](#-بکاپ-و-بهروزرسانی)

**بخش سوم — مرجع**

16. [امنیت](#-امنیت)
17. [سفارشی‌سازی](#-سفارشیسازی)
18. [رفع مشکل](#-رفع-مشکل)
19. [مرجع API](#-مرجع-api)
20. [ساختار پروژه](#-ساختار-پروژه)
21. [تست خودکار](#-تست-خودکار)
22. [آنچه تست شده / نشده](#-آنچه-تست-شده--نشده)

---

## 📌 سامانه چیست؟

سامانه‌ای تحت وب برای **ثبت گزارش شیفت سرپرستان خوابگاه** و بررسی آن. هر نقش صفحهٔ ورود و نشست جدا دارد، ولی همه روی **یک بک‌اند و یک دیتابیس** کار می‌کنند.

| نقش | کار |
|---|---|
| 🏛️ **معاونت** | **مدیر کل سامانه (سوپر ادمین).** فقط یک‌بار ثبت‌نام می‌کند. همهٔ گزارش‌ها را می‌بیند، مثل کارشناس **تأیید یا رد** می‌کند، کارشناس و سرپرست می‌سازد، رمز می‌دهد، حساب را فعال/غیرفعال می‌کند و بدون رمز وارد پنل کارشناس/سرپرست می‌شود |
| 🧑‍🔍 **کارشناس** | همهٔ گزارش‌ها و آمار را می‌بیند؛ **تأیید** یا **رد (با دلیل اجباری)** می‌زند |
| 🧑‍💼 **سرپرست** | فرم شیفت را پر می‌کند و وضعیت گزارش (در حال بررسی / تأیید شده / رد شده + دلیل) را می‌بیند |

### ✨ امکانات

- ✅ ثبت‌نام یک‌بارهٔ معاونت؛ بعد از آن هیچ‌کس دیگری نمی‌تواند معاونت ثبت‌نام کند
- ✅ مدیریت کامل کاربران از پنل (ساخت، ویرایش، فعال/غیرفعال، تعیین رمز، ورود بدون رمز با نوار قرمز «بازدید»)
- ✅ تأیید/رد گزارش توسط کارشناس **و** معاونت؛ رد فقط با ذکر دلیل
- ✅ فرم شیفت هوشمند: تاریخ و ساعت شمسی با انتخابگر، پیش‌فرض ساعت تهران، روز هفته خودکار
- ✅ لیست اتاق‌ها به‌صورت چک‌باکس (مرتب/نامرتب) با جستجو و «افزودن اتاق»
- ✅ «افزودن عنوان جدید…» در همهٔ لیست‌های کشویی؛ برای همهٔ کاربران ذخیره می‌شود
- ✅ نام سرپرست خودکار از حساب؛ کد ملی، شماره تماس و اتاق میهمانان اجباری و اعتبارسنجی‌شده
- ✅ خروجی PDF فارسی از هر گزارش
- ✅ آپلود عکس پروفایل (اعتبارسنجی با امضای فایل)
- ✅ **بدون وابستگی به اینترنت**: فونت، آیکون و بوت‌استرپ داخل پروژه‌اند
- ✅ دیتابیس SQLite (بدون نصب سرور دیتابیس) با **ارتقای خودکار** دیتابیس نسخه‌های قبل
- ✅ API داخلی `/api/v1`، محافظت CSRF، محدودیت تلاش ورود، هدرهای امنیتی
- ✅ ۴۱ تست خودکار

---

## 🚀 شروع سریع (۵ دقیقه)

```bash
python3 -m venv venv
venv/bin/python -m pip install -r requirements.txt
venv/bin/python app.py
```

(ویندوز: `venv\Scripts\python` به‌جای `venv/bin/python`)

سپس:

1. مرورگر را روی `http://127.0.0.1:5000/deputy/login` باز کنید. چون هنوز معاونتی وجود ندارد، خودکار به **صفحهٔ ثبت‌نام معاونت** می‌روید.
2. نام کاربری، رمز (حداقل ۸ نویسه)، تکرار رمز و (اختیاری) شماره تماس را بدهید ← **ساخت حساب معاونت**. وارد پنل می‌شوید و ثبت‌نام معاونت برای همیشه بسته می‌شود.
3. از منوی **مدیریت سامانه** یک **کارشناس** و چند **سرپرست** بسازید.
4. سرپرست‌ها از `/login` وارد می‌شوند و گزارش ثبت می‌کنند؛ کارشناس یا معاونت تأیید/رد می‌کنند.

> 🔐 روی سرور عمومی قبل از ثبت‌نام معاونت، در `.env` مقدار `DEPUTY_SETUP_TOKEN=یک-کد-دلخواه` بگذارید تا فقط کسی که کد را دارد بتواند اولین حساب را بسازد.

---

## 🏛️ آموزش معاونت (مدیر کل سامانه)

### ۱) ثبت‌نام اولیه (فقط یک‌بار)

آدرس `ADDRESS/deputy/setup` (یا `ADDRESS/deputy/login`). فرم شامل: نام کاربری · رمز (حداقل ۸ نویسه) · تکرار رمز · شماره تماس (اختیاری؛ اگر وارد شود باید ۱۱ رقم و مثل `09123456789` باشد) · و در صورت فعال بودن `DEPUTY_SETUP_TOKEN`، کد راه‌اندازی.

بعد از ساخته شدن حساب، این صفحه بسته می‌شود و معاونت دیگری از هیچ مسیری قابل ثبت‌نام نیست.

### ۲) ورود

`ADDRESS/deputy/login` ← پنل معاونت. منوی کناری: **گزارشات** · **مدیریت سامانه** · **سرپرستان** · **کارشناسان** · **حساب من**.

### ۳) گزارشات (گزارش‌گیری کامل)

- همهٔ گزارش‌های همهٔ سرپرستان در چهار تب: **همهٔ گزارش‌ها · در حال بررسی · تأیید شده · رد شده**
- جستجو (نام سرپرست یا تاریخ)، فیلتر وضعیت نظافت، صفحه‌بندی
- کارت‌های آمار کلی و نمودار
- مشاهدهٔ جزئیات کامل هر گزارش و **دانلود PDF**
- **تأیید** با یک کلیک؛ **رد** فقط با نوشتن دلیل (دلیل برای سرپرست نمایش داده می‌شود)
- تصمیم نهایی است: گزارشی که تأیید/رد شد، دوباره قابل تغییر نیست (برای جلوگیری از تضاد معاونت و کارشناس)

### ۴) مدیریت کارشناسان و سرپرستان

**مدیریت سامانه ← کارشناس جدید / سرپرست جدید** ← فرم را پر کنید:

| فیلد | توضیح |
|---|---|
| نام کاربری | ۳ تا ۵۰ نویسه؛ فقط حروف انگلیسی، عدد و `_ . -` |
| نام و نام خانوادگی | برای سرپرست، همین نام خودکار در فرم گزارش می‌آید |
| شماره تماس | ۱۱ رقم، مثل `09123456789` |
| رمز عبور | حداقل ۶ نویسه |
| فعال | حساب غیرفعال نمی‌تواند وارد شود |

در فهرست هر کاربر می‌توانید: **ویرایش** · **فعال/غیرفعال** · **تغییر رمز** (بدون دانستن رمز قبلی؛ رمز فقط به‌صورت هش ذخیره می‌شود) · **ورود به پنل**.

### ۵) ورود بدون رمز به پنل کارشناس/سرپرست

دکمهٔ **ورود به پنل** کنار هر کاربر فعال، شما را با دسترسی کامل وارد پنل او می‌کند (برای عیب‌یابی یا ثبت گزارش به‌جای سرپرست). در تمام مدت یک **نوار قرمز «شما معاونت هستید و در حال بازدید…»** بالای صفحه می‌ماند و با لینک «مدیریت سامانه» داخل همان نوار به پنل مدیریت برمی‌گردید. نشست معاونت‌تان دست‌نخورده می‌ماند.

### ۶) حساب من

تغییر نام کاربری و رمز خودتان. (حساب خودتان از فهرست کاربران قابل غیرفعال‌سازی نیست؛ سامانه هیچ‌وقت بدون معاونت نمی‌ماند.)

### ۷) ثبت‌نام عمومی سرپرستان

به‌طور پیش‌فرض **بسته** است (`/register` خطای ۴۰۴ می‌دهد)؛ سرپرست‌ها را معاونت می‌سازد. برای بازکردن: `PUBLIC_REGISTRATION=1` در `.env`.

---

## 🧑‍🔍 آموزش کارشناس

1. ورود: `ADDRESS/expert/login`
2. صفحهٔ اصلی: آمار کلی (کل / در حال بررسی / تأیید شده / رد شده) و فهرست گزارش‌ها. هر ۳۰ ثانیه خودکار به‌روز می‌شود.
3. با تب‌ها و جستجو گزارش مورد نظر را پیدا کنید و **جزئیات** را باز کنید.
4. **تأیید** یا **رد**. رد بدون نوشتن دلیل ثبت نمی‌شود.
5. نتیجه بلافاصله برای سرپرست و معاونت نمایش داده می‌شود.

> کارشناس هیچ دسترسی به مدیریت کاربران ندارد؛ آن فقط با معاونت است.

---

## 🧑‍💼 آموزش سرپرست

### ورود

`ADDRESS/login` با نام کاربری و رمزی که معاونت داده است. بعد از ورود به **داشبورد** می‌روید.

### ثبت گزارش جدید (`/form/new`)

فرم در چند بخش است و با نوار مراحل بالای صفحه می‌توانید بین بخش‌ها بروید:

| بخش | توضیح |
|---|---|
| **اطلاعات شیفت** | روز، تاریخ، زمان تحویل شیفت، ساعت حضور و خروج. تاریخ/ساعت با **انتخابگر شمسی** پر می‌شوند، پیش‌فرض تاریخ و ساعت **تهران**‌اند و **روز هفته خودکار** تنظیم می‌شود. نام شما خودکار از حساب گرفته می‌شود و قابل تغییر نیست |
| **آمار دانشجویان** | تعداد حاضر و غایب (فقط عدد؛ ارقام فارسی هم پذیرفته می‌شود) |
| **نظافت** | مسئول نظافت، وضعیت کل، و وضعیت ۹ بخش: آبدارخانه، سرویس بهداشتی، حمام، راهروها، تخلیه زباله سطل‌ها، راه‌پله‌ها، نمازخانه، محوطه، تخلیه زباله اطراف (عالی / خوب / متوسط / نیازمند بهبود + توضیح) |
| **بازدیدکننده** | نام، سمت، ساعت ورود/خروج، محل، نتیجه و توضیح (اختیاری) |
| **اتاق‌ها** | یک فهرست چک‌باکسی؛ اتاق‌های **مرتب** و **نامرتب** را علامت بزنید |
| **تخلفات** | جدول پویا (نام، اتاق، نوع، زمان) با افزودن/حذف ردیف |
| **میهمانان** | جدول پویا؛ برای هر میهمان **نام، اتاق، کد ملی و شماره تماس همگی اجباری‌اند** |
| **توضیحات** | نکات قابل تقدیر، مسائل انتظامی، فرهنگی‌ورزشی، وضعیت تجهیزات، پیگیری‌ها، نکات شیفت بعد |

#### 🏠 لیست اتاق‌ها
- هر اتاق یک چک‌باکس است: **تیک = مرتب**، بدون تیک = نامرتب.
- دکمه‌های **«همه مرتب»** و **«پاک‌کردن همه»** و **جستجو** برای پیدا کردن سریع اتاق.
- اتاق ندارید؟ **افزودن اتاق** ← شمارهٔ اتاق را بنویسید؛ برای همهٔ سرپرستان ذخیره می‌شود و به ترتیب (عددی) در فهرست می‌نشیند.

#### ➕ عنوان جدید در لیست‌های کشویی
در لیست‌هایی مثل «وضعیت نظافت» و «نتیجهٔ بازدید» گزینهٔ **«➕ افزودن عنوان جدید…»** هست. عنوان را بنویسید؛ برای همهٔ کاربران ذخیره می‌شود.

#### 👥 میهمانان (همه‌چیز اجباری)
| فیلد | قاعده |
|---|---|
| نام | اجباری |
| اتاق | اجباری |
| کد ملی | اجباری؛ دقیقاً **۱۰ رقم** |
| شماره تماس | اجباری؛ **۱۱ رقم** و مثل `09123456789` |

ردیف میهمانِ کاملاً خالی نادیده گرفته می‌شود. اگر هر مورد ناقص یا بد‌فرمت باشد، فرم ثبت نمی‌شود و خطای فارسی همان ردیف نمایش داده می‌شود (هم در مرورگر و هم در سرور).

### پیگیری گزارش‌ها

- **گزارشات ارسال‌شده** (`/submitted`): وضعیت هر گزارش با نشان رنگی؛ برای گزارش رد شده **دلیل رد** را می‌بینید.
- **جزئیات** و **PDF** هر گزارش.
- **گزارش‌گیری کلی** (`/reports`): جدول گزارش‌ها با جستجو بر اساس نام سرپرست و تاریخ.

---

## 🔄 مسیر یک گزارش

```
سرپرست ثبت می‌کند  →  🟡 در حال بررسی
          ↓
کارشناس یا معاونت بررسی می‌کند → ✅ تأیید   یا   ❌ رد (با دلیل الزامی)
          ↓
نتیجه بلافاصله در پنل معاونت/کارشناس و «گزارشات ارسال‌شده» سرپرست دیده می‌شود
```

## 🌐 فهرست آدرس‌ها

`ADDRESS` یعنی آدرس سایت (لوکال: `http://127.0.0.1:5000`).

| بخش | آدرس | چه کسی |
|---|---|---|
| ثبت‌نام معاونت (فقط یک‌بار) | `ADDRESS/deputy/setup` | معاونت |
| ورود / پنل معاونت | `ADDRESS/deputy/login` · `ADDRESS/deputy` | معاونت |
| مدیریت سامانه | `ADDRESS/deputy/manage` | معاونت |
| ورود / پنل کارشناس | `ADDRESS/expert/login` · `ADDRESS/expert` | کارشناس |
| ورود سرپرستان | `ADDRESS/login` | سرپرست |
| ثبت‌نام سرپرست (پیش‌فرض بسته) | `ADDRESS/register` | — |
| ثبت گزارش جدید | `ADDRESS/form/new` | سرپرست |
| گزارشات ارسال‌شده | `ADDRESS/submitted` | سرپرست |
| گزارش‌گیری کلی | `ADDRESS/reports` | سرپرست |
| سلامت سرویس | `ADDRESS/api/v1/health` | عمومی |

> آدرس‌های قدیمی `/admin/...` به پنل معاونت هدایت می‌شوند؛ پنل جداگانهٔ سوپر ادمین دیگر وجود ندارد.

---

## 💻 اجرا روی کامپیوتر خودتان

پیش‌نیاز: **Python 3.9 یا بالاتر** (ویندوز: هنگام نصب حتماً تیک *Add Python to PATH*).

<details open>
<summary><b>🪟 ویندوز (PowerShell)</b></summary>

```powershell
cd C:\dorm
python -m venv venv
venv\Scripts\python -m pip install --upgrade pip
venv\Scripts\python -m pip install -r requirements.txt
venv\Scripts\python app.py
```
</details>

<details>
<summary><b>🐧 لینوکس / 🍎 مک</b></summary>

```bash
cd ~/dorm
python3 -m venv venv
venv/bin/python -m pip install --upgrade pip
venv/bin/python -m pip install -r requirements.txt
venv/bin/python app.py
```
</details>

مرورگر خودکار `http://127.0.0.1:5000` را باز می‌کند. توقف: `Ctrl+C`. سپس طبق [شروع سریع](#-شروع-سریع-۵-دقیقه) معاونت را ثبت‌نام کنید.

### 🧪 داده نمونه (فقط لوکال)

```bash
venv/bin/python manage.py seed-demo
```

| نام کاربری | نقش | رمز |
|---|---|---|
| `demo_sup1` | سرپرست | `demo1234` |
| `demo_expert` | کارشناس | `demo1234` |
| `demo_deputy` | معاونت | `demo1234` |

> ⛔ `seed-demo` را **هرگز روی سرور اصلی** اجرا نکنید (علاوه بر داده‌های نمونه، یک حساب معاونت می‌سازد و ثبت‌نام اولیهٔ معاونت بسته می‌شود).

### انتقال از نسخهٔ قدیمی

فایل `dorm.db` قدیمی را در `instance/` و عکس‌ها را در `static/uploads/` بگذارید. دیتابیس خودکار ارتقا می‌یابد و چیزی پاک نمی‌شود:

- گزارش‌های قدیمی «در حال بررسی» می‌شوند.
- حساب‌های «سوپر ادمین» نسخهٔ قبلی خودکار به **معاونت** تبدیل می‌شوند و با همان نام کاربری و رمز وارد پنل معاونت می‌شوند.

## 🛠️ دستورهای مدیریتی (CLI)

حساب‌ها را می‌توان با پنل معاونت یا با CLI ساخت؛ هر دو **دقیقاً یک حساب یکسان** می‌سازند (همان جدول، همان هش رمز). (ویندوز: `venv\Scripts\python`)

| کار | دستور |
|---|---|
| ساخت کارشناس | `venv/bin/python manage.py create-user --role expert --username NAME --full-name "نام" --phone 09123456789` |
| ساخت سرپرست | `... create-user --role supervisor ...` |
| ساخت معاونت (در صورت نیاز فنی) | `... create-user --role deputy ...` |
| فهرست کاربران | `venv/bin/python manage.py list-users` |
| تغییر نقش | `venv/bin/python manage.py set-role --username NAME --role expert` |
| تغییر/ریست رمز | `venv/bin/python manage.py set-password --username NAME` |
| ارتقای دیتابیس قدیمی | `venv/bin/python manage.py upgrade-db` |
| داده نمونه | `venv/bin/python manage.py seed-demo` |

نقش‌های مجاز: `supervisor` · `expert` · `deputy` (مقدار قدیمی `admin` هم پذیرفته و به `deputy` تبدیل می‌شود).

> 🆘 **رمز معاونت را فراموش کردید؟** `venv/bin/python manage.py set-password --username NAME` (روی خود سرور).

## ⚙️ تنظیمات `.env`

فایل `.env` را کنار `app.py` بسازید (`.env.example` را کپی کنید). روی لوکال لازم نیست.

| متغیر | کاربرد | مقدار پیشنهادی روی سرور |
|---|---|---|
| `OPEN_BROWSER` | باز شدن خودکار مرورگر | `0` |
| `HOST` | آدرس شنود | `0.0.0.0` یا `127.0.0.1` (پشت پروکسی) |
| `PORT` | پورت (پیش‌فرض ۵۰۰۰) | `8000` |
| `BEHIND_PROXY` | پشت nginx/IIS هستید؟ | `1` یا `0` |
| `SESSION_COOKIE_SECURE` | کوکی فقط روی HTTPS | `1` **فقط** اگر سایت https است |
| `SECRET_KEY` | کلید نشست | خالی بگذارید؛ خودکار در `instance/secret.key` ساخته می‌شود |
| `DEPUTY_SETUP_TOKEN` | کد لازم برای ثبت‌نام اولیهٔ معاونت (نام قدیمی `ADMIN_SETUP_TOKEN` هم کار می‌کند) | یک کد دلخواه (پیشنهادی روی سرور عمومی) |
| `PUBLIC_REGISTRATION` | ثبت‌نام عمومی سرپرستان `/register` | `0` (پیش‌فرض: بسته) |
| `URL_PREFIX` | اگر زیر زیرمسیر است (`/dorm`) | معمولاً خالی |
| `DORM_DATA_DIR` | پوشهٔ دیتابیس | اختیاری |
| `DORM_DB_PATH` | مسیر فایل دیتابیس | اختیاری |
| `DORM_UPLOAD_DIR` | پوشهٔ عکس‌ها | اختیاری |

**نمونه ۱ — HTTP روی شبکهٔ داخلی:**

```env
OPEN_BROWSER=0
HOST=0.0.0.0
PORT=8000
BEHIND_PROXY=0
SESSION_COOKIE_SECURE=0
```

**نمونه ۲ — پشت nginx/IIS با HTTPS:**

```env
OPEN_BROWSER=0
HOST=127.0.0.1
PORT=8000
BEHIND_PROXY=1
SESSION_COOKIE_SECURE=1
DEPUTY_SETUP_TOKEN=یک-کد-طولانی-و-دلخواه
```

> ⛔ **رایج‌ترین خطا:** `SESSION_COOKIE_SECURE=1` روی سایتی که با `http://` باز می‌شود. نتیجه: «نشست فرم منقضی شده» و ورود ناموفق. روی HTTP مقدار را `0` کنید.

## 🪟 استقرار روی ویندوز سرور

**پیش‌نیاز از IT:** Remote Desktop با Administrator، ویندوز سرور ۲۰۱۲ R2+، پورت قابل‌باز (مثلاً ۸۰۰۰)، IP یا دامنه.

### روش الف — اجرای مستقیم + سرویس ویندوز (ساده‌ترین)

**۱)** پایتون را نصب کنید (*Install for all users* + *Add to PATH*). پروژه را در `C:\dorm` باز کنید (فایل `C:\dorm\app.py` باید وجود داشته باشد).

**۲)** PowerShell را با *Run as administrator* باز کنید:

```powershell
cd C:\dorm
python -m venv venv
venv\Scripts\python -m pip install --upgrade pip
venv\Scripts\python -m pip install -r requirements.txt
copy .env.example .env
notepad .env
```

محتوای `.env`:

```env
OPEN_BROWSER=0
HOST=0.0.0.0
PORT=8000
BEHIND_PROXY=0
SESSION_COOKIE_SECURE=0
```

**۳)** تست: `venv\Scripts\python serve.py` و روی خود سرور `http://localhost:8000/deputy/login` را باز کنید ← معاونت را ثبت‌نام کنید؛ سپس `Ctrl+C`.

**۴) فایروال:**

```powershell
New-NetFirewallRule -DisplayName "Dorm Report 8000" -Direction Inbound -Protocol TCP -LocalPort 8000 -Action Allow
```

**۵) سرویس ویندوز با NSSM** (فایل را از <https://nssm.cc/download> بگیرید و `win64\nssm.exe` را در `C:\nssm\` بگذارید):

```powershell
mkdir C:\dorm\logs
C:\nssm\nssm.exe install DormReport "C:\dorm\venv\Scripts\python.exe" "serve.py"
C:\nssm\nssm.exe set DormReport AppDirectory "C:\dorm"
C:\nssm\nssm.exe set DormReport Start SERVICE_AUTO_START
C:\nssm\nssm.exe set DormReport AppStdout "C:\dorm\logs\out.log"
C:\nssm\nssm.exe set DormReport AppStderr "C:\dorm\logs\err.log"
C:\nssm\nssm.exe set DormReport AppRotateFiles 1
C:\nssm\nssm.exe set DormReport AppRotateBytes 5000000
C:\nssm\nssm.exe start DormReport
```

**۶)** تست از کامپیوتر دیگر: `http://SERVER-IP:8000/login` (آدرس IP را با `ipconfig` ببینید).

مدیریت سرویس:

```powershell
C:\nssm\nssm.exe status DormReport
C:\nssm\nssm.exe restart DormReport
C:\nssm\nssm.exe stop DormReport
Get-Content C:\dorm\logs\err.log -Tail 50
```

### روش ب — IIS با دامنه و HTTPS (اختیاری)

1. در `.env`: `HOST=127.0.0.1`، `BEHIND_PROXY=1`، `SESSION_COOKIE_SECURE=1` (اگر HTTPS دارید) و سرویس را ریستارت کنید.
2. نصب **IIS** + افزونه‌های **URL Rewrite** و **Application Request Routing (ARR)**.
3. IIS Manager ← نام سرور ← *Application Request Routing Cache* ← *Server Proxy Settings* ← **Enable proxy**.
4. ساخت سایت (پوشهٔ خالی مثلاً `C:\inetpub\dorm` با Binding دامنه/۸۰/۴۴۳).
5. فایل `web.config` در همان پوشه:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <system.webServer>
    <rewrite>
      <rules>
        <rule name="ToDorm" stopProcessing="true">
          <match url="(.*)" />
          <serverVariables>
            <set name="HTTP_X_FORWARDED_PROTO" value="https" />
          </serverVariables>
          <action type="Rewrite" url="http://127.0.0.1:8000/{R:1}" />
        </rule>
      </rules>
    </rewrite>
    <security>
      <requestFiltering>
        <requestLimits maxAllowedContentLength="6291456" />
      </requestFiltering>
    </security>
  </system.webServer>
</configuration>
```

6. در *URL Rewrite ← View Server Variables* مقدار `HTTP_X_FORWARDED_PROTO` را اضافه کنید (روی http مقدار را `http` بگذارید).

> اگر IIS گیر کرد، روش الف به‌تنهایی کامل کار می‌کند.

### به‌روزرسانی روی ویندوز

```powershell
C:\nssm\nssm.exe stop DormReport
# فایل‌های جدید را کپی کنید؛ این‌ها را بازنویسی نکنید: instance  static\uploads  .env
cd C:\dorm
venv\Scripts\python -m pip install -r requirements.txt
venv\Scripts\python manage.py upgrade-db
C:\nssm\nssm.exe start DormReport
```

### بکاپ شبانهٔ ویندوز

`C:\dorm\backup.ps1`:

```powershell
$src = "C:\dorm"
$dst = "D:\dorm_backups"
New-Item -ItemType Directory -Force -Path $dst | Out-Null
$name = "dorm-" + (Get-Date -Format "yyyy-MM-dd_HHmm") + ".zip"
Compress-Archive -Path "$src\instance", "$src\static\uploads" -DestinationPath "$dst\$name" -Force
Get-ChildItem $dst -Filter "dorm-*.zip" | Sort-Object LastWriteTime -Descending | Select-Object -Skip 30 | Remove-Item
```

زمان‌بندی (هر شب ساعت ۲):

```powershell
schtasks /Create /SC DAILY /ST 02:00 /TN "DormBackup" /TR "powershell -ExecutionPolicy Bypass -File C:\dorm\backup.ps1" /RU SYSTEM
```

## 🐧 استقرار روی لینوکس (Ubuntu) — nginx + HTTPS

به‌جای `example.ir` دامنهٔ خودتان را بنویسید.

```bash
# ۱) اتصال و ابزارها
ssh root@SERVER-IP
apt update && apt upgrade -y
apt install -y python3 python3-venv python3-pip nginx unzip ufw

# ۲) کاربر برنامه
adduser --disabled-password --gecos "" dorm
mkdir -p /opt/dorm && chown dorm:dorm /opt/dorm
```

انتقال پروژه (از کامپیوتر خودتان):

```bash
scp dorm_report.zip root@SERVER-IP:/opt/dorm/
```

داخل سرور:

```bash
cd /opt/dorm && unzip -o dorm_report.zip && chown -R dorm:dorm /opt/dorm
sudo -u dorm python3 -m venv venv
sudo -u dorm venv/bin/python -m pip install --upgrade pip
sudo -u dorm venv/bin/python -m pip install -r requirements.txt

cat > /opt/dorm/.env <<EOF
OPEN_BROWSER=0
HOST=127.0.0.1
PORT=8000
BEHIND_PROXY=1
SESSION_COOKIE_SECURE=1
DEPUTY_SETUP_TOKEN=یک-کد-طولانی-و-دلخواه
EOF
chown dorm:dorm /opt/dorm/.env && chmod 600 /opt/dorm/.env
```

سرویس systemd:

```bash
cat > /etc/systemd/system/dorm.service <<EOF
[Unit]
Description=Dorm Report
After=network.target

[Service]
User=dorm
Group=dorm
WorkingDirectory=/opt/dorm
ExecStart=/opt/dorm/venv/bin/gunicorn -w 3 -b 127.0.0.1:8000 wsgi:app
Restart=always
RestartSec=3

[Install]
WantedBy=multi-user.target
EOF
systemctl daemon-reload && systemctl enable --now dorm
systemctl status dorm --no-pager
```

nginx:

```bash
cat > /etc/nginx/sites-available/dorm <<EOF
server {
    listen 80;
    server_name example.ir www.example.ir;
    client_max_body_size 6m;

    location / {
        proxy_pass http://127.0.0.1:8000;
        proxy_set_header Host \$host;
        proxy_set_header X-Real-IP \$remote_addr;
        proxy_set_header X-Forwarded-For \$proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto \$scheme;
    }
}
EOF
ln -sf /etc/nginx/sites-available/dorm /etc/nginx/sites-enabled/dorm
rm -f /etc/nginx/sites-enabled/default
nginx -t && systemctl reload nginx

ufw allow OpenSSH && ufw allow "Nginx Full" && ufw --force enable
```

HTTPS رایگان (نیاز به دامنه‌ای که به IP سرور اشاره کند):

```bash
apt install -y certbot python3-certbot-nginx
certbot --nginx -d example.ir -d www.example.ir --redirect -m you@example.ir --agree-tos -n
```

بعد از بالا آمدن سرویس، `https://example.ir/deputy/login` را باز کنید و **بلافاصله معاونت را ثبت‌نام کنید** (با کد `DEPUTY_SETUP_TOKEN`).

دستورهای روزمره:

```bash
systemctl restart dorm
journalctl -u dorm -n 100 --no-pager
journalctl -u dorm -f
```

## 🌍 هاست اشتراکی cPanel

هاست باید **Setup Python App** داشته باشد (وگرنه VPS بگیرید).

1. cPanel ← **Setup Python App** ← Create Application: نسخهٔ پایتون ۳٫۹+، Application root = `dorm`، Startup file = `passenger_wsgi.py`، Entry point = `application`.
2. پروژه را در پوشهٔ `dorm` (نه `public_html`) آپلود و Extract کنید.
3. در همان صفحه `requirements.txt` را بدهید و **Run Pip Install** (اگر `gunicorn` خطا داد، آن خط را حذف کنید).
4. متغیرهای محیطی: `OPEN_BROWSER=0` ، `BEHIND_PROXY=1` ، `SESSION_COOKIE_SECURE=1` (در صورت https) ، `DEPUTY_SETUP_TOKEN=...` ← Save ← Restart.
5. آدرس `https://YOUR-DOMAIN/deputy/login` را باز کنید و معاونت را ثبت‌نام کنید.
6. **SSL/TLS Status ← Run AutoSSL**.

## 📦 نصب آفلاین و زیرمسیر

### سرور بدون اینترنت

روی کامپیوتر دیگر (با **همان نسخهٔ پایتون و همان سیستم‌عامل**):

```bash
python -m pip download -r requirements.txt -d wheels
```

پوشهٔ `wheels` را با فلش به سرور ببرید:

```powershell
python -m venv venv
venv\Scripts\python -m pip install --no-index --find-links=C:\wheels -r requirements.txt
```

> اگر نسخهٔ پایتون یا ۳۲/۶۴ بیتی بودن دو سیستم فرق کند، خطای `No matching distribution` می‌گیرید.

### زیرمسیر (`https://university.ir/dorm`)

```env
URL_PREFIX=/dorm
BEHIND_PROXY=1
```

و در nginx/IIS مسیر `/dorm/` را بدون حذف پیشوند به برنامه بفرستید.

## 💾 بکاپ و به‌روزرسانی

| مسیر | محتوا |
|---|---|
| `instance/dorm.db` | همهٔ کاربران، گزارش‌ها و عنوان‌های افزوده‌شده |
| `instance/secret.key` | کلید نشست |
| `static/uploads/` | عکس پروفایل‌ها |
| `.env` | تنظیمات |

> ⚠️ **حذف پوشهٔ `instance` یعنی از دست رفتن همهٔ کاربران و گزارش‌ها** (باید دوباره معاونت را ثبت‌نام و کاربران را بسازید و کلید نشست هم تازه ساخته می‌شود). قبل از هر آپدیت بکاپ بگیرید.

بکاپ شبانهٔ لینوکس و به‌روزرسانی:

```bash
mkdir -p /var/backups/dorm
cat > /etc/cron.d/dorm-backup <<EOF
0 2 * * * root tar czf /var/backups/dorm/dorm-\$(date +\%F).tgz -C /opt/dorm instance static/uploads && find /var/backups/dorm -name "dorm-*.tgz" -mtime +30 -delete
EOF

# به‌روزرسانی
systemctl stop dorm && cd /opt/dorm
unzip -o dorm_new.zip -x "instance/*" "static/uploads/*" ".env"
chown -R dorm:dorm /opt/dorm
sudo -u dorm venv/bin/python -m pip install -r requirements.txt
sudo -u dorm venv/bin/python manage.py upgrade-db
systemctl start dorm
```

---

## 🛡️ امنیت

- رمز معاونت قوی (سامانه حداقل ۸ نویسه می‌خواهد؛ ۱۲ یا بیشتر بهتر است) و `DEPUTY_SETUP_TOKEN` روی سرور عمومی
- `seed-demo` فقط روی لوکال
- `.env` و `instance/` بیرون از دسترس وب و **هرگز روی گیت commit نشوند** (`.gitignore` زیر)
- روی اینترنت عمومی حتماً HTTPS و `SESSION_COOKIE_SECURE=1`
- فقط پورت لازم باز باشد؛ سرور و پایتون به‌روز باشند
- ورود بدون رمز معاونت همیشه با نوار قرمز علامت‌گذاری می‌شود و فقط برای کارشناس/سرپرست فعال کار می‌کند
- داخل برنامه: رمزها با هش (werkzeug)، محافظت CSRF، محدودیت تلاش ورود (۸ تلاش ناموفق در ۱۰ دقیقه)، هدرهای امنیتی، جلوگیری از XSS، اعتبارسنجی آپلود با امضای فایل، تصمیم‌گیری اتمیک روی گزارش (تأیید/رد هم‌زمان تداخل نمی‌کند)، قفل نوشتن هنگام ثبت‌نام اولیهٔ معاونت (دو ثبت‌نام هم‌زمان هر دو موفق نمی‌شوند)

پیشنهاد `.gitignore`:

```gitignore
venv/
__pycache__/
*.pyc
.env
instance/*
!instance/.gitkeep
static/uploads/*
!static/uploads/.gitkeep
logs/
*.db
```

## 🎛️ سفارشی‌سازی

### اتاق‌ها

اتاق‌ها را **لازم نیست در کد تغییر دهید**: سرپرست‌ها در فرم گزارش با «افزودن اتاق» اتاق جدید اضافه می‌کنند و برای همه ذخیره می‌شود. اگر خواستید فهرست پایهٔ پیش‌فرض را عوض کنید، فایل `dormapp/forms.py` خط ۸:

```python
# پیش‌فرض: ۱۰۱–۱۲۰ ، ۲۰۱–۲۲۰ ، ۳۰۱–۳۲۰
ROOMS = [str(n) for base in (100, 200, 300) for n in range(base + 1, base + 21)]

# افزودن اتاق‌های ۱ و ۲ و ۳ و چند اتاق دستی
ROOMS = ['1', '2', '3'] + [str(n) for base in (100, 200, 300) for n in range(base + 1, base + 21)] + ['401', '402']

# لیست کاملاً دستی
ROOMS = ['101', '102', '105', '201', '350']
```

بعد از تغییر برنامه را ریستارت کنید.

### لوگو

لوگوی دانشکده فایل `static/img/college-logo.png` است و در صفحه‌های ورود، منوی پنل‌ها و نوار بالای سایت سرپرستان نمایش داده می‌شود. با جایگزین کردن همین فایل (با همین نام) لوگو عوض می‌شود.

### عنوان‌ها

متن سربرگ ورود/ثبت‌نام معاونت در `templates/panel/_deputy_brand.html` و پاورقی «خوابگاه پردیس فناوری (فنی سابق)» در `templates/panel/login.html` و `templates/manage/setup.html` است.

## 🩺 رفع مشکل

| مشکل | راه‌حل |
|---|---|
| `python` شناخته نمی‌شود | نصب‌کننده ← Modify ← تیک PATH؛ یا `py -m venv venv`؛ ترمینال را ببندید و باز کنید |
| `pip install` خطا/timeout | اینترنت قطع یا فیلتر است؛ دسترسی `pypi.org` یا نصب آفلاین |
| «نشست فرم منقضی شده» / ورود نمی‌شود | `SESSION_COOKIE_SECURE=0` روی http و ریستارت |
| صفحه بدون استایل | `BEHIND_PROXY=1` یا پروکسی مسیر `/static/` را رد می‌کند |
| ۵۰۲ / Bad Gateway | برنامه اجرا نیست: `nssm status DormReport` یا `systemctl status dorm` |
| از کامپیوتر دیگر باز نمی‌شود | `HOST=0.0.0.0` + فایروال |
| `Address already in use` | `PORT` دیگر بدهید؛ ویندوز: `netstat -ano \| findstr :8000` |
| PDF فارسی حروف جدا | `pip install arabic-reshaper python-bidi` و ریستارت |
| صفحهٔ ثبت‌نام معاونت باز نمی‌شود («قبلاً انجام شده») | معاونت ساخته شده؛ از `/deputy/login` وارد شوید. رمز را فراموش کرده‌اید؟ `manage.py set-password --username NAME` |
| ثبت‌نام معاونت «کد راه‌اندازی» می‌خواهد | مقدار `DEPUTY_SETUP_TOKEN` در `.env` را وارد کنید |
| `/register` خطای ۴۰۴ می‌دهد | عمدی است؛ معاونت سرپرست می‌سازد (یا `PUBLIC_REGISTRATION=1`) |
| سرپرست «دسترسی ندارید» / وارد نمی‌شود | حساب غیرفعال است؛ معاونت ← سرپرستان ← فعال‌سازی |
| فرم ثبت نمی‌شود و خطای میهمان می‌دهد | نام، اتاق، کد ملی (۱۰ رقم) و تماس (۱۱ رقم، `09…`) هر میهمان اجباری است؛ یا ردیف را حذف کنید |
| بعد از آپدیت گزارش‌ها نیست | `instance` پاک/بازنویسی شده؛ از بکاپ برگردانید |
| خطای PowerShell Execution Policy | از دستورهای بدون Activate استفاده کنید یا `Set-ExecutionPolicy -Scope Process Bypass` |
| خطای Permission | کاربر سرویس باید روی `instance` و `static/uploads` دسترسی نوشتن داشته باشد |

## 🔌 مرجع API

احراز هویت با نشست (کوکی) همان پنل؛ درخواست‌های تغییردهنده هدر `X-CSRFToken` لازم دارند. کارشناس و معاونت هر دو از همین مسیرها استفاده می‌کنند (فقط پیشوند `expert` یا `deputy` فرق دارد).

| متد | مسیر | دسترسی | کار |
|---|---|---|---|
| GET | `/api/v1/health` | عمومی | سلامت |
| GET | `/api/v1/{expert\|deputy}/overview` | کارشناس/معاونت | آمار کلی |
| GET | `/api/v1/{expert\|deputy}/reports` | کارشناس/معاونت | فهرست (`status`, `q`, `date`, `cleaning`, `page`, `per_page`) |
| GET | `/api/v1/{expert\|deputy}/reports/<id>` | کارشناس/معاونت | جزئیات |
| POST | `/api/v1/{expert\|deputy}/reports/<id>/approve` | کارشناس/معاونت | تأیید |
| POST | `/api/v1/{expert\|deputy}/reports/<id>/reject` | کارشناس/معاونت | رد (فیلد `note` اجباری) |

## 🗂️ ساختار پروژه

```
dorm/
├── app.py                 اجرای ساده (لوکال)
├── serve.py               اجرای تولیدی با waitress (ویندوز/لینوکس)
├── wsgi.py                ورودی gunicorn  (wsgi:app)
├── passenger_wsgi.py      ورودی cPanel
├── manage.py              مدیریت کاربران و دیتابیس (CLI)
├── requirements.txt
├── .env.example
├── dormapp/               هستهٔ برنامه
│   ├── __init__.py  config.py  db.py  security.py  jalali.py
│   ├── services.py  forms.py  pdf.py
│   ├── routes_site.py     صفحات سرپرست
│   ├── routes_panels.py   ورود و صفحات پنل کارشناس/معاونت
│   ├── routes_manage.py   ثبت‌نام و مدیریت معاونت (/deputy/setup, /deputy/manage)
│   └── routes_api.py      /api/v1
├── templates/{site,panel,manage}/
├── static/{css,js,panel,img,vendor,fonts}/
├── tests/test_flow.py
└── instance/              دیتابیس و کلید (بکاپ بگیرید، commit نکنید!)
```

## 🧪 تست خودکار

```bash
venv/bin/python -m unittest discover -s tests -v
```

باید در پایان `OK` ببینید (ویندوز: `venv\Scripts\python`). تست‌ها جریان کامل ثبت ← تأیید/رد ← نمایش، ثبت‌نام یک‌بارهٔ معاونت، مدیریت کاربران، ورود بدون رمز، اعتبارسنجی فرم، ارتقای دیتابیس و CSRF را پوشش می‌دهند.

## ✅ آنچه تست شده / نشده

**تست‌شده:** اجرای لوکال، ۴۱ تست خودکار، جریان کامل ثبت‌نام معاونت ← ساخت کاربر ← ثبت گزارش ← تأیید/رد در Chromium واقعی، ظاهر موبایل بدون سرریز، ارتقای دیتابیس قدیمی (سوپر ادمین ← معاونت).

**تست‌نشده (دستورها استاندارد و از دانش عمومی‌اند):** ویندوز سرور واقعی، NSSM، IIS/ARR، cPanel، gunicorn + nginx + certbot روی Ubuntu واقعی، پایتون ۳٫۹، ظاهر عنوان PDF در فایل خروجی. اگر جایی گیر کردید، بخش «رفع مشکل» و لاگ‌ها را ببینید.

---

<p align="center">ساخته‌شده برای معاونت فرهنگی و دانشجویی — دانشکده ملی مهارت و کشاورزی نیشابور<br>خوابگاه پردیس فناوری (فنی سابق)</p>

</div>
