# Firedetectionsensor




این کد به زبان پایتون برای استفاده از Raspberry Pi و کتابخانه RPi.GPIO برای کنترل پایه‌های GPIO نوشته شده است. در زیر به توضیح هر بخش از کد می‌پردازم:وارد کردن کتابخانه‌ها:import RPi.GPIO as GPIO
import timeاین بخش به شما این امکان را می‌دهد که از کتابخانه‌های RPi.GPIO و time استفاده کنید.تنظیمات اولیه:sensor_pin = 17  # پایه GPIO برای خواندن اطلاعات از سنسور
led_pin = 27     # پایه GPIO برای کنترل LED

GPIO.setmode(GPIO.BCM)
GPIO.setup(led_pin, GPIO.OUT)در این بخش، شما پایه‌های GPIO را تعیین کرده و حالت آنها را تنظیم کرده‌اید. GPIO.setmode(GPIO.BCM) به شما این امکان را می‌دهد که از شماره GPIO به عنوان شماره پایه‌ها استفاده کنید.حلقه اصلی:try:
    while True:
        sensor_value = # خواندن مقدار آنالوگ از سنسور

        print(sensor_value)  # چاپ مقدار آنالوگ در کنسول

        if sensor_value > 100:
            GPIO.output(led_pin, GPIO.HIGH)  # روشن کردن LED اگر مقدار گاز بیشتر از 100 باشد
        else:
            GPIO.output(led_pin, GPIO.LOW)   # خاموش کردن LED در غیر اینصورت

        time.sleep(1)  # تاخیر یک ثانیه قبل از خواندن مقدار بعدی
except KeyboardInterrupt:
    GPIO.cleanup()در این بخش، یک حلقه بی‌نهایت اجرا می‌شود که مقدار آنالوگ از سنسور خوانده شده و سپس در کنسول چاپ می‌شود. اگر مقدار گاز بیشتر از 100 باشد، LED روشن می‌شود و در غیر این صورت خاموش می‌شود.پایان حلقه و تمیز کردن GPIO:except KeyboardInterrupt:
    GPIO.cleanup()در صورت فشار Ctrl+C (یا متوقف شدن حلقه به هر دلیل دیگر)، با این بخش اطمینان حاصل می‌شود که GPIO پاکسازی شده و منابع اشغال شده آزاد شوند

لینک ویدیو ها شامل یک ویدیوی نرم افزار و یک ویدیوی سخت افزار : 
https://drive.google.com/drive/folders/1IIO6Jz4lwITJ0vL1D1AQx3cwydVXZyfd?usp=sharing




محمد دشتی 
ایلیا جهان دار
سپنتا مرتضوی
