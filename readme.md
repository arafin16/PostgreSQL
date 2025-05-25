**1.What is PostgreSQL?**
PostgreSQL হলো একটি শক্তিশালী, ওপেন-সোর্স রিলেশনাল ডেটাবেইস ম্যানেজমেন্ট সিস্টেম (RDBMS) যা SQL (Structured Query Language) এবং অনেক উন্নত বৈশিষ্ট্য সমর্থন করে, যেমন: ট্রানজ্যাকশন, কাস্টম ফাংশন, এবং NoSQL ধরনের ডেটা (JSON, XML)। এটি ACID (Atomicity, Consistency, Isolation, Durability) নীতিমালাকে মেনে চলে এবং স্কেলেবল ও একাধিক ইউজার সাপোর্ট করে।

🔸 উদাহরণস্বরূপ, PostgreSQL ব্যবহার করে আপনি একটি `students` টেবিলে সকল ছাত্রের তথ্য সংরক্ষণ, খোঁজ, পরিবর্তন এবং মুছে ফেলার কাজ করতে পারবেন।


**2.What is the purpose of a database schema in PostgreSQL?**
Schema হলো একটি ধরনের logical container যেখানে টেবিল, ভিউ, ফাংশন, ইনডেক্স ইত্যাদি থাকে। এটি এক ডেটাবেইসে একাধিক ব্যবহারকারী বা মডিউলকে আলাদা করতে সাহায্য করে।

🔸 যেমন, ধরুন আপনার university_db ডেটাবেইসে দুইটি স্কিমা আছে: academic ও admin। একটিতে থাকবে ছাত্র-শিক্ষকের তথ্য, আর অন্যটিতে অফিসিয়াল ডেটা। এতে ডেটা অর্গানাইজ করা সহজ হয় এবং কনফ্লিক্ট কমে।


**3.Explain the Primary Key and Foreign Key concepts in PostgreSQL.**
🔹 Primary Key: এটি এমন একটি কলাম বা কলামের সমষ্টি যা প্রতিটি রেকর্ডকে ইউনিকভাবে চিনতে সাহায্য করে। এতে ডুপ্লিকেট বা NULL ভ্যালু থাকা যাবে না।

🔸 উদাহরণ: students(id SERIAL PRIMARY KEY) — এখানে id প্রতিটি ছাত্রের জন্য আলাদা হবে।

🔹 Foreign Key: এটি এমন একটি কলাম যা অন্য টেবিলের Primary Key-এর রেফারেন্স করে। এটি দুইটি টেবিলের মধ্যে সম্পর্ক তৈরি করে।

🔸 উদাহরণ: enrollments(student_id INT REFERENCES students(id)) — এখানে student_id হলো ফরেন কি, যা students টেবিলের id কে রেফার করে।


**4.What is the difference between the VARCHAR and CHAR data types?**
🔹 VARCHAR(n): একটি পরিবর্তনশীল দৈর্ঘ্যের স্ট্রিং ফিল্ড, যেখানে সর্বোচ্চ n ক্যারেক্টার রাখা যায়। অপ্রয়োজনীয় জায়গা নেয় না।

🔹 CHAR(n): একটি নির্দিষ্ট দৈর্ঘ্যের ফিল্ড। যদি আপনি কম ক্যারেক্টার রাখেন, তবে বাকি জায়গা ফাঁকা (padding) দিয়ে পূরণ হবে।


**5.Explain the purpose of the WHERE clause in a SELECT statement.**
WHERE ক্লজ ব্যবহার করে আমরা ডেটাবেইস থেকে নির্দিষ্ট শর্ত অনুযায়ী রেকর্ড বের করতে পারি। এটি ফিল্টার হিসেবে কাজ করে।