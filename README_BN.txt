CashTrace Offline PWA - ব্যবহার নির্দেশিকা
==========================================

এই ফোল্ডারে আছে:
- index.html: তোমার CashTrace ওয়েব অ্যাপ
- manifest.json: অ্যাপ ইনস্টল/নাম/আইকন সেটিংস
- sw.js: অফলাইন ক্যাশিং
- icon-192.png এবং icon-512.png: অ্যাপ আইকন

গুরুত্বপূর্ণ:
1) এই ফাইলগুলো HTTPS-এ হোস্ট করতে হবে (যেমন GitHub Pages)। শুধু কম্পিউটারে index.html ডাবল-ক্লিক করলে Service Worker কাজ করবে না।
2) প্রথমবার CashTrace অনলাইনে খুলতে হবে। Service Worker CDN লাইব্রেরি, ফন্ট ও অ্যাপ ফাইল ক্যাশ করার চেষ্টা করবে।
3) প্রথমবার খোলার পর পেজটি একবার Reload করো। তারপর Airplane Mode দিয়ে পরীক্ষা করো।
4) সবকিছু ঠিক থাকলে পরেরবার ইন্টারনেট ছাড়াও অ্যাপ চালু হবে। প্রথমবারের আগে offline launch সম্ভব নয়।
5) APK বানাতে পরে PWABuilder-এ HTTPS ওয়েবসাইটের URL দিতে হবে।

ডেটা:
CashTrace-এর বিদ্যমান localStorage ডেটা একই browser/app origin-এ থাকবে। পুরোনো ওয়েবসাইটের ডেটা নতুন PWA origin-এ স্বয়ংক্রিয়ভাবে আসবে না; আগে CashTrace-এর JSON Backup নিয়ে পরে Restore করতে হবে।

নোট:
অফলাইন ক্যাশিংয়ের জন্য বাইরের লাইব্রেরিগুলো প্রথমবার অনলাইনে লোড/ক্যাশ হওয়া প্রয়োজন। Android-এ APK বানানোর আগে PWABuilder-এর package validation সম্পন্ন করো।
