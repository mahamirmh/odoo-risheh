<div align="center">

# 🌱 Risheh ERP

### زیرساخت یکپارچه مدیریت عملیات «ریشه» بر پایه Odoo 19

[![Odoo](https://img.shields.io/badge/Odoo-19.0-714B67?style=for-the-badge&logo=odoo&logoColor=white)](https://www.odoo.com/)
[![Python](https://img.shields.io/badge/Python-3.10--3.14-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-13%2B-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![License](https://img.shields.io/badge/License-LGPL--3.0-2EA44F?style=for-the-badge)](LICENSE)

**یک هسته ERP ماژولار برای مدیریت متمرکز فروش، CRM، پروژه‌ها، منابع انسانی، مالی، وب‌سایت، عملیات و فرایندهای داخلی ریشه**

</div>

---

## درباره پروژه

**Risheh ERP** مخزن پایه‌ی سیستم مدیریت سازمانی شرکت **فناوران دیجیتال ریشه** است که بر مبنای نسخه‌ی **Odoo 19.0 Community** توسعه و نگهداری می‌شود.

هدف این مخزن، فراهم‌کردن یک هسته‌ی پایدار و توسعه‌پذیر برای یکپارچه‌سازی فرایندهای داخلی کسب‌وکار در یک سیستم مرکزی است؛ به‌گونه‌ای که داده‌های مشتریان، فروش، پروژه‌ها، تیم، اسناد، فعالیت‌ها، مالی و سایر جریان‌های عملیاتی بتوانند در یک معماری ماژولار و قابل گسترش مدیریت شوند.

> وضعیت فعلی مخزن: هسته‌ی کامل Odoo 19 و مجموعه‌ی Add-onهای استاندارد در مخزن قرار دارد. سفارشی‌سازی‌های اختصاصی ریشه باید به‌صورت ماژول‌های جدا از Core نگهداری شوند تا امکان به‌روزرسانی امن Odoo حفظ شود.

---

## اهداف محصول

این پروژه قرار است به‌عنوان هسته‌ی عملیاتی داخلی ریشه عمل کند و زمینه‌ی لازم را برای موارد زیر فراهم کند:

- مدیریت متمرکز مشتریان و ارتباطات در CRM
- مدیریت Lead، Opportunity، Pipeline و فرایند فروش
- مدیریت قراردادها، سفارش‌ها، پیش‌فاکتورها و صورتحساب‌ها
- مدیریت پروژه، Task، Deadline، Assignment و Timesheet
- مدیریت تیم، کارمندان، مرخصی‌ها، هزینه‌ها و فرایندهای منابع انسانی
- مدیریت ارتباطات و فعالیت‌های داخلی
- مدیریت وب‌سایت، فرم‌ها، محتوای آنلاین و پورتال
- مدیریت خرید، انبار، محصول و عملیات مرتبط در صورت نیاز
- ایجاد داشبوردهای مدیریتی و گزارش‌های عملیاتی
- ایجاد Automation و Integration با سرویس‌های بیرونی
- ایجاد پایه‌ی مناسب برای اتصال Agentهای هوش مصنوعی و سرویس‌های داخلی ریشه

---

## وضعیت قابلیت‌ها

Odoo به‌صورت ماژولار طراحی شده است. وجود یک ماژول در کدبیس به معنی فعال‌بودن آن در دیتابیس عملیاتی نیست و هر قابلیت باید متناسب با نیاز سازمان نصب و پیکربندی شود.

| حوزه | ماژول‌های مرتبط در Odoo | کاربرد در ریشه |
|---|---|---|
| CRM | `crm`, `mail` | لیدها، فرصت‌ها، پیگیری مشتری |
| فروش | `sale`, `sale_management` | پیشنهاد قیمت، سفارش فروش، فرایند تجاری |
| پروژه | `project`, `hr_timesheet` | پروژه‌ها، تسک‌ها، زمان صرف‌شده |
| مالی | `account`, `payment` | فاکتور، پرداخت، گزارش‌های مالی |
| منابع انسانی | `hr`, `hr_holidays`, `hr_expense` | پرسنل، مرخصی، هزینه |
| خرید | `purchase` | تأمین‌کنندگان و خرید |
| انبار | `stock` | موجودی و عملیات انبار |
| وب‌سایت | `website` | وب‌سایت و صفحات آنلاین |
| فروش آنلاین | `website_sale` | فروشگاه و Commerce |
| مارکتینگ | مجموعه Add-onهای Marketing | کمپین و ارتباطات بازاریابی |
| پورتال | `portal` | دسترسی کنترل‌شده کاربران بیرونی |
| پیام و فعالیت | `mail` | Chatter، Activity و Notification |

---

## معماری سطح بالا

```text
┌───────────────────────────────────────────────────────────────┐
│                         Users / Teams                         │
│   CEO · Sales · PM · Finance · HR · Operations · Support     │
└──────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
┌───────────────────────────────────────────────────────────────┐
│                        Odoo Web Client                        │
│                 Views · Actions · Dashboards                 │
└──────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
┌───────────────────────────────────────────────────────────────┐
│                     Odoo Application Layer                    │
│                                                               │
│ CRM │ Sales │ Project │ HR │ Accounting │ Website │ Inventory│
│                                                               │
├───────────────────────────────────────────────────────────────┤
│ ORM · Business Logic · Security · Automation · Messaging     │
└──────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
┌───────────────────────────────────────────────────────────────┐
│                         PostgreSQL                            │
│                 Business & Configuration Data                │
└──────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
┌───────────────────────────────────────────────────────────────┐
│                    Integrations / Services                   │
│ API · Webhooks · n8n · AI Agents · Internal Services         │
└───────────────────────────────────────────────────────────────┘
```

---

## ساختار مخزن

```text
odoo-risheh/
├── .github/             # تنظیمات GitHub
├── addons/              # ماژول‌های استاندارد Odoo
├── debian/              # فایل‌های Packaging برای Debian
├── doc/                 # مستندات فنی Odoo
├── odoo/                # هسته اصلی Framework و Server
├── setup/               # فایل‌های نصب و Packaging
├── odoo-bin             # Entry Point اجرای Odoo
├── requirements.txt     # وابستگی‌های Python
├── ruff.toml            # تنظیمات Lint
├── setup.py             # Python Package Setup
├── SECURITY.md          # راهنمای امنیت
├── CONTRIBUTING.md      # راهنمای مشارکت
├── LICENSE              # LGPL-3
└── README.md
```

### محل پیشنهادی توسعه‌های اختصاصی ریشه

برای جلوگیری از تغییر مستقیم هسته‌ی Odoo، توسعه‌های اختصاصی بهتر است در مسیر جداگانه نگهداری شوند:

```text
custom_addons/
├── risheh_core/
├── risheh_crm/
├── risheh_projects/
├── risheh_contracts/
├── risheh_automation/
└── risheh_ai/
```

> مسیر `custom_addons/` در وضعیت فعلی مخزن وجود ندارد و این بخش، الگوی پیشنهادی برای توسعه‌ی بعدی است.

---

## پیش‌نیازها

طبق تنظیمات همین نسخه از کدبیس:

| وابستگی | نسخه |
|---|---|
| Odoo | 19.0 |
| Python | 3.10 تا 3.14 |
| PostgreSQL | 13 یا بالاتر |
| Git | نسخه پایدار |
| سیستم‌عامل پیشنهادی | Ubuntu 24.04 / Debian 12 |

برای محیط Production استفاده از Linux پیشنهاد می‌شود.

---

## نصب برای محیط توسعه

### 1. دریافت مخزن

```bash
git clone -b 19.0 https://github.com/mahamirmh/odoo-risheh.git
cd odoo-risheh
```

### 2. ساخت Virtual Environment

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

### 3. نصب Dependencyها

```bash
pip install -r requirements.txt
```

> برخی Dependencyهای Odoo نیازمند Packageهای سیستمی هستند. روی Ubuntu/Debian باید کتابخانه‌های Development مربوط به PostgreSQL، LDAP، XML، Pillow و سایر Dependencyهای Native نیز نصب باشند.

### 4. آماده‌سازی PostgreSQL

یک Role اختصاصی برای Odoo ایجاد کنید و دسترسی ساخت Database را به آن بدهید.

نمونه:

```bash
sudo -u postgres createuser --createdb --no-createrole --no-superuser odoo
sudo -u postgres psql -c "ALTER USER odoo WITH PASSWORD 'CHANGE_ME';"
```

در محیط Production رمز عبور را در Shell History یا فایل‌های Version Control نگهداری نکنید.

### 5. اجرای Odoo

```bash
./odoo-bin \
  --db_host=localhost \
  --db_port=5432 \
  --db_user=odoo \
  --db_password=CHANGE_ME \
  --addons-path=addons
```

سپس:

```text
http://localhost:8069
```

را باز کنید.

---

## اجرای پروژه با فایل تنظیمات

برای محیط‌های دائمی بهتر است از یک فایل Configuration خارج از Version Control استفاده شود.

نمونه:

```ini
[options]
admin_passwd = CHANGE_MASTER_PASSWORD

db_host = localhost
db_port = 5432
db_user = odoo
db_password = CHANGE_DATABASE_PASSWORD

addons_path = addons
proxy_mode = False

http_port = 8069
```

اجرا:

```bash
./odoo-bin -c /etc/odoo/odoo.conf
```

> هیچ Secret، Password، API Key یا Credential واقعی نباید Commit شود.

---

## توسعه ماژول اختصاصی

برای ساخت ماژول جدید:

```bash
./odoo-bin scaffold risheh_example custom_addons
```

سپس هنگام اجرا مسیر Add-on اختصاصی را نیز اضافه کنید:

```bash
./odoo-bin \
  --addons-path=addons,custom_addons \
  -d risheh_dev
```

هر ماژول اختصاصی باید حداقل دارای ساختاری مشابه زیر باشد:

```text
risheh_example/
├── __init__.py
├── __manifest__.py
├── models/
├── security/
├── views/
├── data/
├── static/
└── tests/
```

### اصول توسعه در این مخزن

1. از تغییر مستقیم فایل‌های Core تا حد ممکن خودداری شود.
2. توسعه‌ی Business Logic ریشه در ماژول‌های `risheh_*` انجام شود.
3. دسترسی‌ها با ACL و Record Rule تعریف شوند.
4. Migration و Upgrade ماژول‌ها قابل تکرار باشد.
5. Integrationها Idempotent و قابل Retry طراحی شوند.
6. Secretها از Environment یا Secret Manager خوانده شوند.
7. تغییرات مهم همراه Test و Documentation باشند.

---

## تست

نمونه اجرای Test یک ماژول:

```bash
./odoo-bin \
  -d risheh_test \
  --test-enable \
  --stop-after-init \
  -i MODULE_NAME
```

برای Upgrade و تست ماژول موجود:

```bash
./odoo-bin \
  -d risheh_test \
  --test-enable \
  --stop-after-init \
  -u MODULE_NAME
```

---

## کیفیت کد

این مخزن دارای تنظیمات `Ruff` است.

```bash
ruff check .
```

پیش از Merge بهتر است حداقل موارد زیر بررسی شوند:

- Syntax و Lint
- نصب و Upgrade صحیح ماژول
- تست Business Logic
- ACL و Record Rules
- Migration Safety
- عدم Commit شدن Secret
- سازگاری با Branch `19.0`

---

## امنیت

برای Production:

- `admin_passwd` قوی و منحصربه‌فرد تنظیم شود.
- Database Manager در صورت عدم نیاز محدود یا غیرفعال شود.
- HTTPS اجباری باشد.
- Odoo پشت Reverse Proxy مانند Nginx اجرا شود.
- `proxy_mode = True` فقط پشت Proxy معتبر فعال شود.
- دیتابیس به اینترنت عمومی Exposure مستقیم نداشته باشد.
- Backup منظم از Database و Filestore گرفته شود.
- Restore Backup به‌صورت دوره‌ای آزمایش شود.
- دسترسی کاربران بر پایه Least Privilege تنظیم شود.
- Credentialها از Git خارج نگه داشته شوند.
- Patchهای امنیتی Odoo به‌صورت کنترل‌شده Sync شوند.

جزئیات بیشتر در [SECURITY.md](SECURITY.md) قرار دارد.

---

## معماری پیشنهادی Production

```text
Internet
   │
   ▼
Reverse Proxy / TLS
   │
   ▼
Odoo 19 Application
   │
   ├──────────────► PostgreSQL
   │
   ├──────────────► Filestore
   │
   ├──────────────► Backup Storage
   │
   └──────────────► Integrations
                    ├─ n8n
                    ├─ Webhooks
                    ├─ AI Agents
                    └─ Internal APIs
```

برای Production باید Workerها، Memory Limit، Timeoutها، Log Rotation، Backup، Monitoring و Database Connectionها متناسب با منابع سرور تنظیم شوند.

---

## استراتژی Branch

Branch اصلی فعلی:

```text
19.0
```

پیشنهاد برای توسعه‌ی داخلی:

```text
19.0
│
├── develop
│   ├── feature/risheh-crm
│   ├── feature/risheh-projects
│   ├── feature/risheh-contracts
│   └── fix/...
│
└── release/...
```

برای Sync کردن تغییرات Odoo Upstream، تغییرات Core باید از توسعه‌های اختصاصی ریشه جدا نگه داشته شوند تا Conflict و ریسک Upgrade کاهش پیدا کند.

---

## مسیر توسعه محصول

معماری پیشنهادی برای تبدیل این مخزن به ERP اختصاصی ریشه:

```text
Odoo 19 Core
      │
      ▼
Risheh Core Module
      │
      ├── CRM & Sales
      ├── Projects & Delivery
      ├── Contracts
      ├── Finance Operations
      ├── Team & HR
      ├── Internal Requests
      ├── Dashboards
      └── Notifications
      │
      ▼
Automation Layer
      │
      ├── n8n
      ├── Webhooks
      └── Scheduled Jobs
      │
      ▼
AI & Intelligence Layer
      ├── Internal Copilot
      ├── Knowledge Retrieval
      ├── CRM Intelligence
      └── Operational Agents
```

---

## مشارکت در توسعه

پیش از ایجاد Pull Request:

```bash
git checkout -b feature/your-feature
```

تغییرات باید کوچک، قابل Review و دارای Commit Message مشخص باشند.

نمونه:

```text
[ADD] risheh_crm: add lead qualification fields
[IMP] risheh_project: improve project workflow
[FIX] risheh_contracts: fix contract access rule
```

در تغییراتی که مستقیماً به Core Odoo مربوط می‌شوند، ابتدا بررسی شود که Fix در Upstream وجود نداشته باشد.

---

## مجوز

هسته‌ی Odoo موجود در این مخزن تحت مجوز **GNU Lesser General Public License v3 (LGPL-3)** منتشر شده است.

برای جزئیات کامل:

- [LICENSE](LICENSE)
- [COPYRIGHT](COPYRIGHT)

برخی Libraryها یا Contributionهای جانبی ممکن است مجوز سازگار دیگری داشته باشند؛ فایل License همان بخش ملاک نهایی است.

---

## منابع

- [مستندات Odoo 19](https://www.odoo.com/documentation/19.0/)
- [مخزن رسمی Odoo](https://github.com/odoo/odoo)
- [راهنمای Developer](https://www.odoo.com/documentation/19.0/developer.html)
- [راهنمای Installation](https://www.odoo.com/documentation/19.0/administration/on_premise/source.html)

---

<div align="center">

### 🌱 Risheh ERP

**زیرساخت عملیاتی یکپارچه برای رشد قابل‌اندازه‌گیری، فرایندهای شفاف و توسعه‌پذیری بلندمدت**

Maintained for **Risheh Digital**

</div>
