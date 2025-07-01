# CREDIT_CARD_FINANCIAL_REPORT
CREDIT_CARD_FINANCIAL_POWER_BI_DASHBOARD



# 🚀 Credit Card Weekly Dashboard Project: Unveiling Financial Insights! 📊✨

Welcome to the Credit Card Weekly Dashboard project! This repository hosts a powerful dashboard designed to deliver real-time insights into key performance metrics and trends within credit card operations. Get ready to dive deep into your data and make informed decisions! 💡

---

## 👨‍💻 Project Lead:
**Aditya Sharma** 🌟

---

## 🎯 Project's North Star:
Our core objective is to forge a comprehensive credit card weekly dashboard that provides dynamic, real-time insights into critical performance indicators and emerging trends. This empowers stakeholders to meticulously monitor and effectively analyze credit card operations, fostering smarter financial strategies. 🧠💰

---

## 🛠️ The Journey: Project Steps Unveiled! 🗺️

Our project unfolded through a structured series of steps to ensure data integrity and impactful visualization:

1.  **🧼 Data Cleaning using SQL**: We started by meticulously cleaning and refining the raw data using robust SQL queries. [cite_start]Think of it as polishing raw diamonds! 
2.  📤 Data Export with Power BI**: Once sparkling, the cleaned data was seamlessly exported to Power BI, our canvas for dynamic visualizations. 
3.  **🧠 Data Processing & DAX**: This phase involved sophisticated data processing and crafting essential measures and calculated columns using DAX (Data Analysis Expressions). This is where the magic of insights begins! 
4.  **🎨 Dashboard Creation**: The heart of our project! We designed and developed intuitive and interactive dashboards for both credit card transactions and customer reports. Visual storytelling at its best! 
5.  **🌟 Insight Generation**: The grand finale! We extracted compelling and actionable insights from our dashboards to empower data-driven decision-making. Knowledge is power! 

---

## 📥 Importing Data to SQL Database: A Behind-the-Scenes Look! ⚙️

The foundation of our analysis lay in the efficient import of data into our SQL database. Here's how we did it:

1.  **📄 Prepare CSV File**: Our data journey began with preparing the raw CSV files. 
2.  **➕ Create Tables in SQL**: Next, we sculpted the necessary tables within our SQL database to house the incoming data. 
3.  **⬆️ Import CSV File into SQL**: Finally, the cleaned CSV data was imported directly into SQL. 
    * **Success Story**: For instance, a query successfully copied 10108 rows in just 82 milliseconds! That's speed! [cite_start]⚡ 

---


## 💡 Decoding Data: Our DAX Query Arsenal! 🏹

DAX (Data Analysis Expressions) was our secret weapon for transforming raw data into meaningful insights. Here are some key DAX formulas we employed:

### 👶👵 AgeGroup Calculation: Categorizing Our Valued Customers!
This DAX formula intelligently groups customers into distinct age brackets based on their `customer_age`:
```dax
AgeGroup = SWITCH(
    TRUE(),
    'public cust_detail'[customer_age] < 30, "20-30",  // Young Explorers! 🧑‍🎤
    'public cust_detail'[customer_age] >= 30 && 'public cust_detail'[customer_age] < 40, "30-40", // Rising Stars! 🌟
    'public cust_detail'[customer_age] >= 40 && 'public cust_detail'[customer_age] < 50, "40-50", // Established Achievers! 🏆
    'public cust_detail'[customer_age] >= 50 && 'public cust_detail'[customer_age] < 60, "50-60", // Experienced Pros! 🦉
    'public cust_detail'[customer_age] >= 60, "60+", // Wise & Wonderful! 👵👴
    "unknown" // The Mysterious Ones! 👻
)


💸 IncomeGroup Calculation: Understanding Financial Power!
This DAX formula elegantly classifies customer income into "Low," "Med," and "High" tiers, providing a clear financial overview:
IncomeGroup = SWITCH(
    TRUE(),
    'public cust_detail'[income] < 35000, "Low", // Budget-Conscious! 🛍️
    'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] < 70000, "Med", // Comfortable Living! 🏡
    'public cust_detail'[income] >= 70000, "High", // High Rollers! 💎
    "unknown" // Income Unspecified! 🤷
)


🗓️ Week Number Calculation: Tracking Time with Precision!
week_num2 = WEEKNUM('public cc_detail'[week_start_date])


💰 Total Revenue Calculation: The Ultimate Financial Pulse!
Revenue = 'public cc_detail'[annual_fees] + 'public cc_detail'[total_trans_amt] + 'public cc_detail'[interest_earned]


💹 Current Week Revenue Calculation: What's Happening NOW!
Current_week_Reveneue = CALCULATE(
    SUM('public cc_detail'[Revenue]),
    FILTER(
        ALL('public cc_detail'),
        'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])
    )
)


⏪ Previous Week Revenue Calculation: A Glimpse into the Past!
Previous_week_Reveneue = CALCULATE(
    SUM('public cc_detail'[Revenue]),
    FILTER(
        ALL('public cc_detail'),
        'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2]) - 1
    )
)

🌟 Project Insights: Week 53 (31st Dec) Highlights! 🚀
Our analysis for Week 53 (ending 31st Dec) brought forth some fascinating insights:

📈 Week-over-Week (WoW) Change: Dynamic Shifts!
Revenue soared by 28.8% – a fantastic weekly jump! 🚀 

Both Total Transaction Amount and Count saw significant increases! More activity, more engagement! 📊 

Customer count also rose, indicating growing user base! 🎉 

🌍 Year-to-Date (YTD) Overview: The Big Picture!
Our overall revenue stands strong at an impressive 

57 Million! 💰 


-->Total interest earned reached a substantial 

8 Million! 🤑 



-->The total transaction amount for the year is 

46 Million! 💳 

-->Male customers are leading the revenue charge with 31 Million, while female customers contributed 26 Million! 💪👩‍🦰 



-->Blue & Silver credit cards are the powerhouses, contributing to a whopping 93% of overall transactions! 💙🥈 


-->TX, NY & CA are our top-performing states, collectively contributing to 68% of the total revenue! 🇺🇸 

The overall activation rate for our credit cards is a healthy 

57.5%! ✅ 

Our overall delinquent rate remains low at just 6.06%! Keep up the good work! 👍 

📊 Credit Card Transaction Report: Every Swipe, Every Detail!
(Refer to CREDIT_CARD_TRANSECTION_REPORT.jpg for a visual representation of this dynamic dashboard.)

Key Metrics at a Glance:

Total Revenue: 

= 57M 

Total Transactions:
= 46M

Total Interest: 

= 8M 

Count of Transactions: 667K

Revenue by Expenditure Type: Discover trends in Swipe, Chip, and Online transactions! 📲

Revenue by Education Level: Insights from Graduate, High School, Unknown, Uneducated, Post-Graduate, and Doctorate holders! 🎓

Revenue by Customer Job: See contributions from Businessmen, White-collars, Self-employed, Govt, Blue-collars, and Retirees! 👔

Revenue by Card Category: A breakdown by Blue, Gold, Platinum, and Silver cards! 🔵🟡⚪

🧑‍🤝‍🧑 Credit Card Customer Report: Understanding Our Community!
(Refer to CREDIT_CARD_CUSTOMER_REPORT.pdf for a visual representation of this comprehensive dashboard.)

Key Metrics at a Glance:

Total Revenue: 

57M 

Total Income: 

588M 

Total Interest: 

8M 

Average CSS: 

3.19 

Revenue by Week: Track weekly performance fluctuations! 📈

-Revenue by Gender: A clear view of contributions from Male (31M) and Female (26M) customers! 🧍‍♂️🧍‍♀️ 

-Customer Job Breakdown: Detailed insights into Revenue, Income, and Interest Earned across various professions:

Businessman: Revenue - 

17,697,472, Income - 190,350,431, Interest Earned - 2,584,604.01 

White-collar: Revenue - 

10,283,124, Income - 105,618,475, Interest Earned - 1,464,690.92 

Self-employed: Revenue - 

8,542,826, Income - 77,659,931, Interest Earned - 1,141,510.40 

Govt: Revenue - 

8,335,534, Income - 90,834,727, Interest Earned - 1,182,230.84 

Blue-collar: Revenue - 

7,040,606, Income - 73,516,911, Interest Earned - 967,751.42 

Retirees: Revenue - 

4,617,448, Income - 49,619,308, Interest Earned - 641,692.22 


--Grand Total: Revenue - 56,517,011, Income - 587,599,783, Interest Earned - 7,982,479.81 

--> Car Owner (Yes/No) and House Owner (Yes/No) distribution: Understanding customer demographics! 🚗🏠

-->Expenditure Type Revenue: Dive into spending habits! 💸

-->Revenue by Income Group: Analyze performance across High, Med, and Low-income segments! 📊

-->Top 5 States by Revenue: Our strongest markets: TX, NY, CA, FL, NJ! 📍

-->Revenue by Age Group: Tailor strategies based on 20-30, 30-40, 40-50, 50-60, and 60+ age brackets! 📈

-->Revenue by Job Type: Further segmentation by job type for targeted insights! 🧑‍💼


