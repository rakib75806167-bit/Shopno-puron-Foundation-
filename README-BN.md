# স্বপ্ন পূরণ ফাউন্ডেশন — Android অ্যাপ

## ফিচার
- ৮ জন সদস্য, প্রত্যেকের মাসিক নির্ধারিত জমা ১,০০০ টাকা
- মাসভিত্তিক জমা হয়েছে/বাকি তালিকা
- মোট জমা, মোট খরচ ও বর্তমান ব্যালেন্স
- Firebase Authentication দিয়ে অ্যাডমিন লগইন
- সাধারণ দর্শকের জন্য লগইন ছাড়াই হিসাব দেখা
- GitHub Actions দিয়ে APK বিল্ড workflow

## Firebase সেটআপ
1. `src/firebase.js`-এ Firebase Console → Project settings → Your apps থেকে পাওয়া Web App config বসান।
2. Firestore Database তৈরি করুন।
3. Firebase Authentication-এ Email/Password চালু করে অ্যাডমিন ইউজার তৈরি করুন।
4. `firestore.rules`-এ `REPLACE_WITH_ADMIN_EMAIL`-এর জায়গায় অ্যাডমিনের ইমেইল বসিয়ে Firestore Rules-এ প্রকাশ করুন।

## APK
সব ফাইল GitHub repository-র root-এ commit/push করার পর Actions → Build Android APK workflow চালান। সফল হলে run-এর Artifacts থেকে `shopno-puron-foundation-apk` ডাউনলোড করুন; ZIP-এর মধ্যে `app-debug.apk` থাকবে।

**গুরুত্বপূর্ণ:** জমা ও খরচের তথ্য সবার কাছে দৃশ্যমান হবে—এতে সদস্যদের সম্মতি নিশ্চিত করুন। Firebase Rules-ই প্রকৃত নিরাপত্তা নিয়ন্ত্রণ করে; শুধু অ্যাপের UI-তে অ্যাডমিন বোতাম লুকানো যথেষ্ট নয়।
