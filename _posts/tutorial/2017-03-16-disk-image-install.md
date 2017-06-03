---
layout: post
title:  Disk Image Install on RaspberryPi
categories: [tutorial]
tags:
- RaspberryPi
- Tags
- Blog
- Post
---

##Disk Image Install on RaspberryPi


# **ডিস্ক ইমেজ ইন্সটল**

---

এ পর্বে দেখানো হবে , কি ভাবে রাস্পবেরি পাই এ ডিস্ক ইমেজ ইন্সটল করা হয় । ডিস্ক ইমেজ হল , আমরা যেমন বিভিন্ন অপারেটিং সিস্টেম ইউজ করি , ঠিক তেমন একটি অপারেটিং সিস্টেম ইমেজ । যেহেতু রাস্পবেরি পাই একটা সিঙ্গেল বোর্ড কম্পিউটার , সুতরাং এটার জন্যও একটা অপারেটিং সিস্টেম প্রয়োজন । তো , রাস্পবেরি পাই এর জন্য অনেক ধরনের অপারেটিং সিস্টেম আছে , কিছু আছে লিনাক্স বেজ , উইন্ডোজ ১০ এর IOT কোর আছে , তুমি চাইলে Android ও ইউজ করতে পার । কিন্তু আমরা এ পর্বে দেখব কি ভাবে রাস্পবিয়ান ইন্সটল করা হয় । কারণ , রাস্পবেরি পাই এর অফিসিয়াল ডিস্ক ইমেজ এটি ।

![](/assets/2.jpg)

**যা যা লাগবে -**

1. অবশ্যই একটা রাস্পবেরি পাই ।
2. একটা ৮ জিবি অথবা ৮ জিবি এর বেশী ধারণ ক্ষমতা সম্পন্ন মেমোরি কার্ড ।
3. একটা কার্ড রিডার , মেমোরি কার্ড এ ইমেজ বার্ন করার জন্য।
4. একটা সচল কম্পিউটার , যেটা দিয়ে ডিস্ক ইমেজ বার্ন করবা ।
5. একটা ৫ ভোল্ট এবং ২ এম্পিয়ার এর পাওয়ার সাপ্লায় ।

আপাতত এগুলা থাকলেই চলবে ।

**এখন নিচের ধাপ গুলা সতর্কতার সাথে সম্পন্ন করতে থাক -**

১। প্রথমে রাস্পবেরি পাই এর সাইট \([http://www.raspberrypi.org/downloads/](https://l.facebook.com/l.php?u=http%3A%2F%2Fwww.raspberrypi.org%2Fdownloads%2F&h=ATNEPgQVlsWdy9EW7WABxGDITE5QynpifwnCUB99Oj23MvHoq4LIubSfFQRLSBm1hpPRy1bvg2Zl2zlMyHLTV98dcb-IXh-sXKBeuBnhXTZe983r9KnCtMRgjhZ3fKY&enc=AZNdyjjjaf7Q7EHibNtq0tvMdjq9Q3G2smcqb25crAl60dF2kIlsGRiGZnQD8U3lKSD3JrNOhconm1jVa7NiYVJCwCVChOQ4F6JJ0fuRqvssNVc9UVceN-_RxhCSf1Zr_fIhAx7_DqX2E65Xvj-EqAs4yhgk9mun1ndgcyY1JYe-fjipElIMpcOueuOd_ptTZ5WPzFzYe1J-8qsbZjB9AwMR&s=1)\)থেকে রাস্পবিয়ান এর ডিস্ক ইমেজ টি নামাতে হবে ।

২ । zip ফাইল থেকে unzip করে একটা ফোল্ডার এ .img ফাইল টি রাখতে হবে ।

৩। SD কার্ড টি কম্পিউটার এ প্রবেশ করাও

৪। ডিস্ক ইমেজ টি মেমোরি কার্ড এ বার্ন করার জন্য Win32DiskImager টি এখান \([http://sourceforge.net/projects/win32diskimager/](https://l.facebook.com/l.php?u=http%3A%2F%2Fsourceforge.net%2Fprojects%2Fwin32diskimager%2F&h=ATMnAEdqxYmRUSOSX0WnFlEWFKdJm7uC3nmrTlVyERgVw0pgcL1brRWG6R8QX8IOcRpAjee_-im8C917Zc6JkSeS0O15ZmVxPNt7ez7XucKeWkzG8_VF_JcfSPXOoAk&enc=AZM2DjGojLf7aBAlcV0lJkvqFkcdRdXhl-rk6RBhS9TsILWu_okvsj1leFLrrirI536oj675adKkFVPY4ZeJ1JYsSq1c9VNOgGEvhoPuOZ4CQNfFnRjgHIBXFadfq9H8_JMFowA44_vdkhK9V9VoOxfYaJxTlwc64F8ad0r0_s-o-7evG-8L8X5aER0ArGRQXHoOqI8qm1XAoXPes_sl2aaN&s=1)\) থেকে নামিয়ে নাও ।

৫। Win32DiskImager টি রান করাও , এবং এটিকে তোমার মেমোরি কার্ড ও ইমেজ ফাইল টিকে দেখিয়ে দাও ।

৬। Write' লেখা বাটন এ ক্লিক কর এবং কমপ্লিট হওয়া পর্যন্ত অপেক্ষা কর ।

৭। কমপ্লিট হয়ে গেলে , মেমোরি কার্ড টি খুলে , রাস্পবেরি পাই এ প্রবেশ করাও , এবং রাস্পবেরি পাই পাওয়ার অন করে তোমার প্রথম রাস্পবেরি পাই টি চালু কর

রাস্পবেরি পাই এর ক্ষেত্রে অবশ্যই মনে রাখবা , এর বাই ডিফল্ট **ইউজার আইডি pi **এবং **পাসওয়ার্ড raspberry**।

![](/assets/3.jpg)

