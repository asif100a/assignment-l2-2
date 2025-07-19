### What is PostgreSQL?

**Ans:** PostgreSQL হল একটি শক্তিশালী, ওপেন-সোর্স, রিলেশনাল ডাটাবেস ম্যানেজমেন্ট সিস্টেম (RDBMS) যা তার দৃঢ়তা, নির্ভরযোগ্যতা এবং উন্নত বৈশিষ্ট্যের জন্য পরিচিত।

### What is the difference between the VARCHAR and CHAR data types?

**Ans:** PostgreSQL-এ VARCHAR এবং CHAR ডেটা টাইপের মধ্যে কিছু পার্থক্য রয়েছে। এর মধ্যে রয়েছে-

-- **CHAR(N):**

১. Fixed-length স্টোরেজ (সর্বদা N অক্ষর ধারণ করে)।

২. যদি stored স্ট্রিংটি N-এর চেয়ে ছোট হয়, তাহলে এটি N পরিমাণ দৈর্ঘ্যে পৌঁছানোর জন্য স্পেস দিয়ে প্যাড করে।

-- **VARCHAR(N):**

১. Variable-length স্টোরেজ (শুধুমাত্র প্রকৃত অক্ষর + ওভারহেডের জন্য space ব্যবহার করে)।

২. কোনও প্যাডিং নেই; যা insert করানো হয় ঠিক তাই সংরক্ষণ করে (সর্বোচ্চ দৈর্ঘ্য N পর্যন্ত)।

### Explain the purpose of the WHERE clause in a SELECT statement.

**Ans:** SELECT স্টেটমেন্টে WHERE ক্লজের কিছু উদ্দেশ্য এখানে দেওয়া হল-

১. Filter Data: শুধুমাত্র সেই সারিগুলি বের করে যা একটি নির্দিষ্ট শর্ত পূরণ করে।

উদাহরণ:

```bash
SELECT * FROM employees WHERE department = 'Sales';
```

→ "Sales" বিভাগের শুধুমাত্র কর্মীদের ফেরত পাঠায়।

২. Improve Query Performance: প্রক্রিয়াকৃত row সংখ্যা হ্রাস করে, কোয়েরি দ্রুত করে।

উদাহরণ:

```bash
SELECT * FROM orders WHERE order_date >= '2023-01-01';
```

### How can you modify data using UPDATE statements?

**Ans:** UPDATE স্টেটমেন্ট একটি টেবিলের বিদ্যমান ডেটা পরিবর্তন করে। বেসিক syntax:

উদাহরণ:

```bash
UPDATE users SET email = 'new@example.com' WHERE user_id = 5;
```

### Explain the GROUP BY clause and its role in aggregation operations.

**Ans:** SQL-এর GROUP BY clause টি নির্দিষ্ট কলামে অভিন্ন মান সহ row গুলিকে summary row তে group করে, প্রতিটি গ্রুপে aggregation operations (যেমন sums, averages, বা counts) সক্ষম করে।

উদাহরণ:

```bash
SELECT department, COUNT(*)
FROM employees
GROUP BY department;
```
