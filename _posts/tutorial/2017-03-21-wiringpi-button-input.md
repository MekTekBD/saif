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
- Input
---

# **রাস্পবেরি-পাই বাটন ইনপুট**

---

এ পর্বে আমরা দেখব কিভাবে একটি পুশ বাটন থেকে ইনপুট নিয়ে একটা লেড বাল্ব জ্বালাতে হয়। কাজটি করতে আমাদের যা যা লাগবে,  
**১। অবশ্যই একটা রাস্পবেরি পাই  
২। একটা পুশ বাটন  
৩। একটা লেড বাল্ব  
৪। দুইটা ৩৩০ ওহমস রেজিস্টর  
৫। একটা ব্রেড বোর্ড  
৬। কিছু জাম্পার ওয়্যার**

এ পর্বে আমরা প্রথমে যেটা করব সেটা হল, রাস্পবেরি পাই এর একটা পিন এর সাথে একটা পুশ বাটান লাগাব। পুশ বাটনটির অপর প্রান্ত রাস্পবেরি পাই এর একটা 3.3v পিন এর সাথে লাগাব , ফলে যেটা হবে যখন আমরা পুশ বাটনটি প্রেস করব তখন রাস্পবেরি পাই এর সাথে যে পিনটা থাকবে সেটা হাই হবে , এখন রাস্পবেরিপাই এর বাটন পিনটি হাই হলে আমরা লেড পিনটিও হাই করব, এবং পিনটি লো হলে আমরা লেড পিনটিও লো করব । সুতরাং আমরা যতক্ষণ বাটনটি প্রেস করে রাখব ততক্ষণ লেড বাল্বটি জ্বলে থাকবে এবং যখন রিলিজ করব তখন বাল্বটি নিভে থাকবে।

এখন নিচের ধাপ গুলা অনুসরণ করতে থাকো-

![](/assets/Selection_010.png)  


১। প্রথমে ছবির মত করে তোমার রাস্পবেরি পাই ও ব্রেড বোর্ড কানেকশন দাও।

২। গত পর্বে আমরা home ডিরেক্টরিতে examples নামের একটা ডিরেক্টরি তৈরি করছিলাম। প্রথমে ঐ ডিরেক্টরিতে যাও। এটা করার জন্য তুমি নিচের কমান্ডটি টাইপ করতে পার।  
$cd examples বা,  
$cd /home/examples/

৩। এখন button.c নামের একটা ফাইল ক্রিয়েট কর এবং নিচের কোড টি লিখ -

$sudo nano button.c

```c
1.#include<wiringPi.h>
2.
3.#defineLED 0
4.#define BTN 1
5.
6.int main (void)
7.{
8.wiringPiSetup ();
9.pinMode (LED, OUTPUT);
10.pinMode (BTN, INPUT);
11.digitalWrite (LED, LOW);
12.for(;;)
13.{
14.if(digitalRead (BTN) == HIGH)
15.digitalWrite (LED, HIGH);
16.else if(digitalRead (BTN) == LOW)
17.digitalWrite (LED, LOW);
18.}
19.return 0;
20.}
```

গত পর্বের থেকে যে কোডলাইন গুলো একটু আলাদা , ৪নং লাইন এ আমরা GPIO1 পিনকে বাটন পিন ডিক্লেয়ার করেছি। যেহেতু পিনটি বাটন পিন এবং বাইরে থেকে একটা ইনপুট নিবে সুতরাং ১০নং লাইনে আমরা বাটন পিনকে ইনপুট মোড এ নিয়েছি। ১৪ থেকে ১৭নং লাইন এ আমরা বাটন হাই হলে লেড হাই বাটন লো হলে লেড পিন লো করেছি।

এখন কোডটি কম্পাইল করে রান করাও, এবং বাটন প্রেস করে দেখ কি ঘটছে।  
$ gcc -o button button.c -l wiringPi  
$chmod +x button  
$./button

কোন সমস্যা হলে আমাদের জানাও...![](https://www.facebook.com/images/emoji.php/v8/f4c/1/16/1f642.png):\)![](https://www.facebook.com/images/emoji.php/v8/f4c/1/16/1f642.png):\)

আগামী পর্বে আমরা দেখব বাটন থেকে ইনপুট নিয়ে কিভাবে একটা লেড বাল্ব টোগল করা যায়। মানে একবার প্রেস করলে বাল্বটি জ্বলবে পরের বার প্রেস এ বাল্বটি নিভবে আবার পরের প্রেস এ জ্বলবে এবং এভাবে চলতে থাকবে। আচ্ছা কতক্ষণ এভাবে চলবে ? রাস্পবেরি পাই এ পাওয়ার থাকলে Ctrl+c প্রেস করার আগ পর্যন্ত।
