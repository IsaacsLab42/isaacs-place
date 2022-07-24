---
title: "Give Salaried Employees a Raise Without Spending More"
date: 2022-07-16T17:07:36-04:00
draft: true
categories:
  - business
tags:
  - business
  - economy
---
{{< katex >}}
# The Problem
With more and more people living paycheck to paycheck because of the economy,
wouldn't it be nice to give salaried employees a raise? What if you didn't
have to spend any more money to do that? What is this magic? Math.

It comes down to a very simple change -- switch to paying twice per month
rather than every two weeks. The problem is that when being paid biweekly 
then 10 months out of every year would have two paychecks, while the remaining
two months would have three paychecks. This effectively reduces the monthly
take-home pay for those 10 months. Personally, I've NEVER had a bill on
a weekly cycle. All my bills are monthly.

As an engineer I like to see the numbers, so let's take a look.

# The Math
## Getting on the same page
First, ensure we have our terms down:

Biweekly
: Every two weeks -- or once per fortnight if you prefer

Bimonthly
: Twice per month

For these calculations we're going to use these variables:

- \\(S\\) -- annual salary
- \\(P_{bw}\\) -- per-paycheck amount for biweekly pay
- \\(P_{bm}\\) -- per-paycheck amount for bimonthly pay
- \\(M_{bw}\\) -- per-month income for biweekly pay[^mbw]
- \\(M_{bm}\\) -- per-month income for bimonthly pay

[^mbw]: 10 months out of the year will have 2 paychecks, which is
the amount we're assuming for \\(M_{bw}\\).

## Calculations
$$
\begin{align*}
P_{bw} &= \frac{S}{26} \cr
P_{bm} &= \frac{S}{24} \cr
M_{bw} &= 2 \cdot P_{bw} = \frac{S}{13} \cr
M_{bm} &= 2 \cdot P_{bm} = \frac{S}{12}
\end{align*}
$$

Now, before anyone gets grumpy about the calculation for \\(M_{bw}\\) remember
that the above holds true for 10 months per year, which is the whole basis of
this post.

So, if a salaried employee goes from being paid biweekly to bimonthly the monthly
increase percentage (\\(I_{bw2bm}\\)), for 10 months out of the year, is:

$$
\begin{align*}
I_{bw2bm} &= 100 \cdot \frac{M_{bm} - M_{bw}}{M_{bw}} \cr
          &= 100 \cdot \frac{\frac{S}{12} - \frac{S}{13}}{\frac{S}{13}} \cr
          &= 100 \cdot \frac{\frac{1}{12} - \frac{1}{13}}{\frac{1}{13}} \cr
          &= 100 \cdot \frac{\frac{13}{12 \cdot 13} - \frac{12}{12 \cdot 13}}{\frac{1}{13}} \cr
          &= 100 \cdot \frac{\frac{1}{156}}{\frac{1}{13}} \cr
          &= 100 \cdot \frac{13}{156} \cr
          &= 100 \cdot \frac{1}{12} \cr
          &= 8.33
\end{align*}
$$

OK, so that was a lot of numbers just to get the result that for 10 months out of
each year the employee would end up with an 8.33% raise.

# Concrete Example
For ease of calculation, let's assume an annual salary of $100,000. Let's call
\\(P_{bw}\\) the amount per paycheck when paid biweekly. In this case there are
26 pay periods per year.

$$
P_{bw} = \frac{100000}{26} = 3846.15
$$

Call \\(P_{bm}\\) the amount per paycheck when paid bimonthly. Being paid
twice a month (bimonthly) means there are 24 pay periods per years.

$$
P_{bm} = \frac{100000}{24} = 4166.67
$$

When being paid biweekly then 10 months out of every year have two paychecks,
so during those 10 months the monthly take home \\(M_{bw})\\) is:

$$
M_{bw} = \frac{100000}{26} \cdot 2 = 7692.31
$$

When being paid bimonthly the monthly take home \\(M_{bm}\\) is:

$$
M_{bm} = \frac{100000}{24} \cdot 2 = 8333.33
$$

In this particular case

