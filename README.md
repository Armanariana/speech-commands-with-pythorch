
# 🗣️ دسته‌بندی فرمان‌های صوتی با استفاده از معماری M5 (PyTorch)

این پروژه یک پیاده‌سازی ساده از شبکه‌ی عصبی کانولوشنی یک‌بعدی (1D CNN) با معماری **M5** است که برای تشخیص فرمان‌های صوتی از روی شکل موج خام (Raw Waveform) طراحی شده.  
هدف اصلی پروژه، تمرین پیاده‌سازی مدل از پایه با استفاده از **PyTorch** و **torchaudio** است.

---

## 📂 ساختار پروژه

- `speech_commands.ipynb` – نوت‌بوک اصلی آموزش و تست مدل  
- `model.pt` – فایل ذخیره‌شدهٔ مدل 
  
---
## 🧠 معماری مدل

مدل بر اساس معماری **M5** طراحی شده که در مقاله‌ی زیر معرفی شده است:  
[Very Deep Convolutional Neural Networks for Raw Waveforms](https://arxiv.org/pdf/1610.00087.pdf)

ویژگی‌های مدل:
- شامل ۴ لایه‌ی کانولوشن به همراه BatchNorm و ReLU
- ۴ لایه‌ی max pooling  
- یک لایه fully connected برای خروجی  
این مدل به‌جای استفاده از ویژگی‌های استخراج‌شده (مثل MFCC یا spectrogram)، مستقیماً شکل موج خام را دریافت می‌کند.

---
## 🗃️ دیتاست

داده‌ها از مجموعه‌ی [`SpeechCommands`](https://pytorch.org/audio/stable/datasets.html#speechcommands) مربوط به `torchaudio` گرفته شده است.  
فرکانس نمونه‌برداری (sample rate) به **۸kHz** کاهش داده شده و تمام فایل‌های صوتی تا ۱ ثانیه (۸۰۰۰ نمونه) با صفر پر شده‌اند (padding).

---

## اطلاعات مدل:
![image](https://github.com/user-attachments/assets/c1f0d550-8705-4051-87ca-0d37f48252ca)

