# 📊 Product Sales Analysis

## 🎯 Problem Description

We have two tables: **Sales** and **Product**. Let’s understand what they store!

### 📋 Sales Table

| Column Name | Type | Description |
|-------------|------|-------------|
| sale_id     | int  | Unique sale number (e.g., 1, 2, 7) |
| product_id  | int  | Product number, connects to the Product table |
| year        | int  | The year the sale happened (e.g., 2008, 2009) |
| quantity    | int  | How many items were sold (e.g., 10, 12) |
| price       | int  | Price per item (e.g., 5000, 9000) |

✅ **Primary key:** `sale_id` and `year` (together, they make each sale unique)
✅ **Foreign key:** `product_id` (connects to the Product table)

---

### 📋 Product Table

| Column Name  | Type    | Description |
|--------------|---------|-------------|
| product_id   | int     | Unique product number (e.g., 100, 200) |
| product_name | varchar | Name of the product (e.g., Nokia, Apple) |

✅ **Primary key:** `product_id`

---

## 🔍 Task: What do we need to do?

We want to show:
- **Product name** 🏷️ (from Product table)
- **Year** 📅 (from Sales table)
- **Price** 💲 (from Sales table)

### 🛠️ How do we do this?
We combine the **Sales** table and **Product** table using `product_id` (like matching puzzle pieces). This helps us get the product name alongside sales details.

### ✨ Output Example

Let’s see what the output looks like!

#### 📥 Input:

**Sales Table:**

| sale_id | product_id | year | quantity | price |
|---------|------------|------|----------|-------|
| 1       | 100        | 2008 | 10       | 5000  |
| 2       | 100        | 2009 | 12       | 5000  |
| 7       | 200        | 2011 | 15       | 9000  |

**Product Table:**

| product_id | product_name |
|------------|--------------|
| 100        | Nokia        |
| 200        | Apple        |
| 300        | Samsung      |

#### 📤 Output:

| product_name | year | price |
|--------------|------|-------|
| Nokia        | 2008 | 5000  |
| Nokia        | 2009 | 5000  |
| Apple        | 2011 | 9000  |

✅ **Explanation:**
- **sale_id 1:** Nokia was sold for 5000 in 2008.
- **sale_id 2:** Nokia was sold for 5000 in 2009.
- **sale_id 7:** Apple was sold for 9000 in 2011.

---

## 🧠 SQL Query (Optional)
Here’s a SQL query that solves this problem:

```sql
Select p.product_name, s.year, s.price from product p
Join sales s
on p.product_id=s.product_id
```

👉 **JOIN** connects both tables using `product_id`.
👉 We select only `product_name`, `year`, and `price`.

---

🚀 **Congratulations!** Now you can analyze sales data like a pro! 🎉

