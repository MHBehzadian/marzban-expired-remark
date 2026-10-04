# marzban-expired-remark

پچ مرزبان: وقتی حجم یا زمان اشتراک کاربر تموم بشه، بعد از آپدیت ساب، اسم همه‌ی کانفیگ‌ها به‌جز کانفیگ اول عوض می‌شه. اسم‌ها یکی در میون فارسی و انگلیسی هستن:

| وضعیت کاربر | فارسی | English |
|---|---|---|
| حجم تموم شده (`limited`) | کاربر گرامی حجم اشتراک شما به پایان رسیده است | Dear user, your subscription data has run out |
| زمان تموم شده (`expired`) | کاربر گرامی زمان اشتراک شما به پایان رسیده است | Dear user, your subscription has expired |

اسم‌ها با هر درخواست ساب از روی وضعیت فعلی کاربر ساخته می‌شن. پس بعد از تمدید، با اولین آپدیت ساب اسم‌های اصلی برمی‌گردن.

## نصب

روی سرور پنل اصلی مرزبان (نه نودها) با کاربر root:

```bash
bash <(curl -sSL https://raw.githubusercontent.com/MHBehzadian/marzban-expired-remark/main/expired-remark.sh)
```

**بعد از هر `marzban update` دستور بالا رو دوباره اجرا کنید.**

## حذف

```bash
bash <(curl -sSL https://raw.githubusercontent.com/MHBehzadian/marzban-expired-remark/main/expired-remark.sh) uninstall
```

## کار اسکریپت

- فایل `app/subscription/share.py` رو از ایمیج مرزبانِ در حال اجرا برمی‌داره، پچ می‌کنه و در `/opt/marzban/custom/share.py` می‌ذاره.
- همین یک فایل رو در `docker-compose.yml` mount می‌کنه (قبلش از compose بکاپ می‌گیره).
- اگه ساختار فایل در نسخه‌ی مرزبان شما فرق داشته باشه، هیچ تغییری نمی‌ده.
- اگه مرزبان بعد از ری‌استارت درست بالا نیاد، خودکار به حالت قبل برمی‌گرده.
- اگه مرزبان جای دیگه‌ای نصب شده: `APP_DIR=/path/to/marzban bash ...`
