# Maximizing subscription value with a Pro-to-Premier switching strategy

*(Originally published as a [Reddit post](https://www.reddit.com/r/SunoAI/comments/1gzdviv/maximizing_subscription_value_with_a_protopremier/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button))*

Like many of you, I often find that the 10,000 credits from the Premier plan just aren't enough to last me through the month. This is a hassle since buying additional credits is prohibitively expensive compared to just subscribing. So, when you run out, your only viable option, apart from waiting until the next billing cycle, is to create and subscribe on a second account, which comes with its own set of inconveniences like limited ability to share songs between accounts.

I wanted to share a method I've been experimenting with to maximize the number of usable credits. During the experiment, I also found out that it actually saves your money (both in monthly and per-credit terms) — although this has never been the goal.

# Rationale

For power users who burn through credits quickly, Suno doesn't offer a straightforward way to get more credits at a reasonable price. If you exhaust your credits before your billing cycle renews, your options are limited:

* **Wait** until your next billing cycle begins.
* **Purchase additional credits**, which are costly.
* **Create a second account and subscribe again**, which is inconvenient.

To tackle this, I've explored a method that involves strategically switching subscriptions via the **App Store** (this is important — see below) to get more credits within a billing period.

# The Experiment

**Objective:** Increase the total number of credits available within a billing period by starting with a Pro subscription and upgrading to Premier via the App Store when you run out of credits.

**Method:**

1. **Start with a Pro Subscription** ($10/month for 2,500 credits).
2. **Determine Your "Pro Usage Factor":** This is how quickly you use up your Pro credits. A Pro usage factor of **6** means you use up your 2,500 Pro credits in **1/6 of a month** (about **5 days**).
3. **Upgrade to Premier via the App Store** once you run out of Pro credits.

**Why App Store?**

With a usual web subscription (made via Stripe), if you upgrade, you just pay a certain (prorated) additional price and are left with the same billing cycle (1 month) and the same total amount of credits (10,000, including the already used 2,500) as if you just subscribed to Premier.

App Store works differently. When you upgrade to a higher tier, it:

1. Refunds the unused portion of your Pro subscription.
2. Charges you for a full month of Premier, starting a new billing cycle immediately.

So in the end you receive 5/4 of the monthly credits amount (12,500 credits) for an extended subscription period. If you've used up your Pro credits sooner than in 1/4 of a month, your billing cycle will be extended *less* than the credit surplus, meaning that you’ll get more credits per amount of time.

To make it less confusing, let's consider an example:

# Example: Pro Usage Factor of 6

Pro Usage Factor 6 means that you use up your 2500 Pro credits in 1/6 of a month, i.e. \~5 days. (This also means that you *would have* used the 10,000 Premier credits in 4/6=2/3 of a month \~= 20 days, which is what I myself typically face.)

**Calculations:**

1. **Total Cost:**
   * **Pro Subscription Used:** $10.00 / 6 = **$1.67** (since you used only 1/6 of the month).
   * **Premier Subscription:** $30.00 (full month charge upon upgrading).
   * **Total Cost:** $1.67 (used Pro) + $30.00 (Premier) = **$31.67**.
2. **Total Period:**
   * **Pro Period Used:** 1/6 month (\~5 days).
   * **Premier Period:** 1 month (new billing cycle starts).
   * **Total Period:** 1/6 + 1 = **1.17 months**.
3. **Total Credits** (regardless of usage factor)**:**
   * **Pro Credits:** 2,500 credits.
   * **Premier Credits:** 10,000 credits.
   * **Total Credits:** 2,500 + 10,000 = **12,500 credits**.
4. **Average Monthly Cost:**
   * **$31.67** total cost / **1.17 months** = **$27.14 per month**
5. **Credits per Month:**
   * **12,500 credits** / **1.17 months** ≈ **10,714 credits per month**.
6. **Cost per 1,000 Credits:**
   * **$31.67** / **12,500 credits** \* 1,000 = **$2.53 per 1,000 credits**.

**Benefits:**

* **More Credits per Month:** Instead of 10,000 credits, you get an *average* of 10,714, i.e. 7% more credits per month. It might not sound like a lot (this converts to an average of 2 additional generations/4 additional songs a day), but it adds up over the year.
* **Lower Cost per Credit:** Cost per 1,000 credits drops from $3.00 (standard Premier rate) to $2.53. This is a 16% saving per credit — quite substantial if you ask me!
* **Lower Monthly Cost:** Compared to the Premier plan, your *average* monthly cost would be $27, which is a \~10% saving per month.

# Comparison for various Pro usage factors

Here's how the benefits stack up depending on your Pro usage factor:

|Pro Usage factor|4|5|6|7|8|
|:-|:-|:-|:-|:-|:-|
|Pro Credits Used In|7.5 days|6 days|5 days|4.3 days|3.75 days|
|Total Cost|$32.50|$32.00|$31.67|$31.43|$31.25|
|Total Credits|12,500|12,500|12,500|12,500|12,500|
|Total Period (Months)|1.25|1.20|1.17|1.14|1.13|
|Avg. Monthly Cost|$26.00|$26.67|$27.14|$27.50|$27.78|
|Credits per Month|10,000|10,417|10,714|10,938|11,111|
|Cost per 1,000 Credits|$2.60|$2.56|$2.53|$2.51|$2.50|
|Price Benefit per Month|13%|11%|10%|8%|7%|
|Price Benefit per Credit|13%|15%|16%|16%|17%|

# Key Takeaways

* **Maximize Credits:** By starting with Pro and upgrading to Premier via the App Store when you run out of credits, you get more average credits per month.
* **Cost Efficiency:** While the primary goal is to get more credits, this method also reduces the cost per credit *and* the average cost per month.

# A Few Notes

* **Cancel After Upgrading:** After upgrading to Premier, consider canceling the subscription immediately. You'll retain Premier benefits until the end of the new billing period, ensuring you're not charged for an additional month you might not need.
* **Limitations:** Even with this method, you might still run out of credits before the new billing period ends, resulting in the same hassle with the second account, but this will happen  less frequently than with the standard Premier plan.
* **Is This Cheating?** I don’t think so. We're utilizing the subscription terms provided by the App Store to better match our usage needs. Moreover, the primary goal is to get enough credits without unnecessary hassle. Actually, if Suno offered higher-tier plans, reasonably priced additional credits, or a way to reset the subscription mid-period, I wouldn’t have even started this experiment at all. Hopefully someone from the Suno team will have a read and think about it.

# Conclusion

If you frequently find yourself running out of Suno credits before the month is up, this method might be worth considering. By strategically starting with Pro and upgrading to Premier via the App Store when you exhaust your credits, you can get more credits in a month, at lower costs.

Here’s the Google Sheet I used for calculation: [**https://docs.google.com/spreadsheets/d/1esThnF60fL-Ofp3M4buxxDVXL9Aui6HX2BTLXpb7aFI**](https://docs.google.com/spreadsheets/d/1esThnF60fL-Ofp3M4buxxDVXL9Aui6HX2BTLXpb7aFI)

You can create a copy of it to calculate for your own usage needs or your own subscription prices, if the App Store prices in your country are different than $10/$30 for Pro/Premier, respectively: