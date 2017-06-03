---
layout: post
title:  RaspberryPi GPIO wiringPi
tags:
- RaspberryPi
- Tags
- Blog
- Post
- wiringPi
- GPIO
---
# [রাস্পবেরি পাই wiringPi](/wiringpi.md)**রাস্পবেরি পাই wiringPi**

---

### রাস্পবেরি পাই GPIO

GPIO মানে হল general purpose input output । রাস্পবেরি পাই এ ৪০ টা পিন আছে । এর ভিতর কিছু পিন তুমি ইনপুট অথবা আউটপুট হিসেবে ইউজ করতে পারবা । এখন কথা হল কোথায় ইনপুট এবং কোথায় আউটপুট ব্যাবহার করবা ?? যদি একটা লেড বাল্ব জালাতে চাও তাহলে আউটপুট হিসেবে , যদি একটা মোটর ঘুরাতে চাও তাহলেও আউটপুট হিসেবে যদি একটা বাটন পিন ইউজ করতে চাও তাহলে ইনপুট হিসেবে ইউজ করতে হবে । আর যেহেতু রাস্পবেরি পাই এর gpio পিন বাই ডিরেকশনাল সেহেতু পিন গুলাকে তুমি ইনপুট অথবা আউটপুট হিসেবে ইউজ করতে পারবা । তো কোন পিন ইনপুট অথবা আউটপুট কিভাবে ডিক্লেয়ার করবা ?? এটার জন্য তোমাকে রাস্পবেরি পাই কে প্রোগ্রামিং করতে হবে ।

![](/assets/4.jpg)

#### **যা যা লাগবে ??**

অবশ্যই তোমাকে প্রোগ্রামিং জানা লাগবে । C/C++, Python, Java, JavaScript যে কোন একটা হলেই চলবে । যে ল্যাঙ্গুয়েজ এ প্রোগ্রামিং করবা , তার জন্য এনভায়রনমেন্ট সেটআপ করা লাগবে । তুমি যদি আগে থেকে আরডুইনো জান তাহলে নেক্সট স্টেপ গুলা খুবই সহজ তোমার জন্য । আর যদি না জেনে থাক কোন সমস্যা নাই , আমরা ধাপে ধাপে শিখব ।

**এনভায়রনমেন্ট সেটআপ ফর সি / সি ++ ল্যাঙ্গুয়েজ -**  
১ ।প্রথমে রাস্পবেরি পাই এর টার্মিনাল ওপেন কর ।  
২। এরপর এই গিটটি থেকে ক্লোন কর । এর জন্য কমান্ড লাইনে নিচের কমান্ড টি কপি পেস্ট করলেই হবে  
৩। এরপর wiringPi ডিরেক্টরি তে যেয়ে প্রোগ্রাম টি বিল্ড করলেই এনভায়রনমেন্ট সেটআপ কমপ্লিট ।  
$ git clone git://git.drogon.net/wiringPi  
$ cd wiringPi  
$ git pull origin  
$ ./build

**এনভায়রনমেন্ট সেটআপ টেস্ট -**  
তোমার এনভায়রনমেন্ট ঠিক ভাবে সেটআপ হয়েছে কিনা দেখার জন্য টার্মিনাল এ প্রথমে gpio readall লিখ । তাহলে প্রত্যেক টা gpio এর বর্তমান অবস্থা দেখা যাবে

এখন ধরা যাক ১৮ নং পিন টাকে আউটপুট হিসেবে ব্যাবহার করতে চাও তাহলে নিচের কমান্ড টি লিখ  
gpio -g mode 18 output

প্রত্যেক সময় gpio এর বর্তমান অবস্থা দেখার জন্য প্রত্যেক কমান্ড এর পর gpio readall লিখে gpio এর বর্তমান অবস্থা দেখে নাও । তাহলে চেঞ্জ গুলা খুব ভাল করে বুঝতে পারবা ।

১৮ নং পিন টাকে অন করার জন্য  
gpio -g write 18 1

১৮ নং পিন টাকে অফ করার জন্য  
gpio -g write 18 0
