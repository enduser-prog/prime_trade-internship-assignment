# Trader Performance vs Market Sentiment

---

## Project Objective

The goal of this project was to understand whether **market sentiment (Fear & Greed)** affects trader performance and trading behavior on **Hyperliquid**.

Instead of just calculating basic stats, I wanted to understand **why** traders performed differently under different market conditions, and whether certain trader groups consistently did better than others.

---

## Methodology

### Step 1 – Data Preparation

I used two datasets:

- **Bitcoin Fear & Greed Index**
- **Hyperliquid Historical Trading Data**

Here's what I did to prepare the data:

- Checked dataset dimensions
- Looked for missing values and duplicates
- Converted timestamps into daily dates
- Merged both datasets using the trading date
- Made sure every trade got the correct market sentiment attached

---

### Step 2 – Feature Engineering

To answer the main questions, I created a few new metrics:

- **Daily trader profit** (Closed PnL)
- **Win rate**
- **Trade frequency**
- **Trade size**
- **Trading direction**
- **Trader segments**

I used these later to compare trader behavior across different market sentiments.

---

## Analytical Thinking Behind the Project

This project wasn't just about calculating averages. A few questions came up along the way that pushed me to dig deeper.

### Why compare Average and Median?

At first, I just calculated average profit and average trade size.

But I noticed some trades were way larger than most others — this told me the data was pretty **skewed**.

A handful of huge trades could pull the average up and give a misleading picture of what a typical trader actually experienced.

So I added **median values** too, since the median doesn't get thrown off by extreme outliers and gives a better sense of a typical case.

Because of this, I reported both average and median wherever it made sense.

---

### Why look at trader segments?

While looking at total profits, another question came up:

**Does earning more total profit actually mean a trader is better?**

Someone who makes thousands of trades naturally has more chances to profit than someone who only makes a few hundred.

So comparing total profit alone wouldn't be a fair way to measure performance.

To fix this, I split traders into different groups:

- **Frequent vs Infrequent Traders**
- **Consistent Winners vs Inconsistent Traders**
- **Large Position vs Small Position Traders**

This made it possible to compare traders more fairly.

---

### Why look at profit per trader?

When comparing frequent vs infrequent traders, frequent traders had much bigger total profits.

But that raised another question:

**Were they actually more skilled, or just trading a lot more?**

Instead of stopping at total profit, I calculated **median profit per trader**.

This let me compare a "typical" trader from each group instead of comparing groups with very different levels of activity.

---

### Why use median trade count?

Trade counts varied a lot between traders.

Some made only a few hundred trades, while others made tens of thousands.

Because of this big gap, I used **median trade count** instead of just the average, so it would better represent what a typical trader actually does.

---

## Key Findings

- Trader profitability changed a lot depending on market sentiment
- **Extreme Greed** had the highest average and median profitability
- Traders were **most active during Fear**
- **Large position traders** outperformed small position traders in most conditions
- Frequent traders made more total profit, but they also traded a lot more
- Different trader groups performed differently depending on market conditions

---

## Business Insights

The analysis shows that success isn't just about trading more.

**Key takeaways:**

- Market sentiment affects both behavior and profitability
- Trading more often doesn't automatically mean better skill
- Traders with larger positions tended to be more selective while still performing well
- Different market conditions suit different trading styles

---

## Strategy Recommendations

1. **During Fear or uncertain markets**, focus on quality trades instead of just trading more often.
2. **Judge trader performance** using median profit and win rate along with total profit, since total profit alone can be misleading.
3. **Factor in market sentiment** before making trading decisions, since behavior and profitability clearly shifted across different conditions.

---

## Limitations

- This is based on historical data from only **32 traders**
- The analysis shows relationships, **not proof of cause and effect**
- Market sentiment is just one factor — things like news events, volatility, and individual strategies weren't included here

---

## Conclusion

This project shows that market sentiment has a real impact on both trader behavior and performance.

More importantly, it shows why it's worth digging deeper before accepting the first result you see. By questioning averages, checking for skew, comparing medians, and breaking traders into segments, I was able to get a more balanced and reliable picture of what was actually going on.
