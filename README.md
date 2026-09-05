# Clinic Performance Analysis using Power BI

## About the Project

In this project, I analyzed 2,000 dental appointment records using Microsoft Power BI to understand clinic profitability, operating costs, treatment mix, dentist performance, waiting time, and no-show behavior.

The main goal was not just to create a dashboard, but to ask questions about unusual patterns and investigate possible explanations using the data**.

My analysis process was:

**See something unusual → Ask why → Check possible reasons → Compare the numbers → Find the pattern → Make a conclusion**

---

## Dataset

The dataset contains information about:

- Location
- Dentist ID
- Clinic ID
- Appointment Date
- Appointment ID
- Treatment Type
- Staff Cost
- Equipment Cost
- Waiting Time
- Treatment Time
- Appointment Status
- Revenue

 Important Data Observation

I found that **staff cost is added even when an appointment is cancelled.

Therefore, cancelled appointments can still contribute to total cost, which is important when interpreting clinic profitability.

---

## Data Cleaning & Transformation

Before starting the analysis, I prepared the dataset in Power BI.

### Steps Performed

- Removed duplicate Appointment IDs
- Corrected data types
- Checked data consistency
- Created calculated columns
- Created DAX measures
- Built relationships and data models
- Created KPI cards and interactive visuals

Main Calculations 
Total Cost = Staff Cost + Equipment Cost

Total Profit = Revenue − Total Cost
 DAX Measures
 
Total Appointments
- Total Revenue
- Total Cost
- Total Profit
- Profit Margin
- Average Waiting Time
- Average Treatment Time
- No-Show Rate
- Average Total Cost

---

# Dashboard KPIs

| KPI | Value |
|---|---:|
| Total Appointments | **2,000** |
| Total Revenue | **$937,624** |
| Profit Margin | **20.5%** |
| Average Waiting Time | **22.2 minutes** |
| No-Show Rate | **15.5%** |
| Overall Average Cost | **$372.62** |

---

# Analysis & Business Thinking

## 1. Why does Chicago have the lowest profit margin?

While exploring the dashboard, I noticed that **Chicago had the lowest profit margin at 4.11%**.

Instead of stopping at the KPI, I asked:

> **Why is Chicago's profit margin so low?**

I considered several possible factors:

- Staff cost
- Equipment cost
- Treatment time
- Waiting time
- Total operating cost

### Treatment Time

Chicago's average treatment time was **42.89 minutes**, compared with the overall average of **46.67 minutes**.

This showed that Chicago's lower profitability was not explained by having longer treatment times.

I then moved to the cost structure.

### Cost Analysis

| Cost | Chicago | Overall Average |
|---|---:|---:|
| Staff Cost | **$301.48** | **$244.36** |
| Equipment Cost | **$154.54** | **$128.27** |
| Total Cost | **$456.02** | **$372.62** |

Both staff cost and equipment cost were higher in Chicago.

This gave me a clear pattern:

**Higher operating cost → Lower profit margin**

### Waiting Time

Chicago also had the **highest average waiting time at 49.2 minutes**.

This raised another question: could higher waiting time indicate inefficient resource utilization or additional resource usage?

However, this is only a **hypothesis**.

I did not perform a statistical test to prove that waiting time causes higher costs or lower profitability.

### Conclusion

Chicago's low profit margin is strongly associated with its **higher operating costs**, particularly staff and equipment costs.

The high waiting time is another important operational pattern that deserves further investigation.

### Business Insight

Potential areas for further investigation include:

- Staff utilization
- Equipment utilization
- Appointment scheduling
- Waiting-time management
- Reasons behind higher operating costs

---

# 2. Why does New York generate more revenue than Los Angeles?

Another interesting comparison was between **New York and Los Angeles**.

Their appointment volumes were almost identical:

- **New York → 556 appointments**
- **Los Angeles → 560 appointments**

However, their revenue was significantly different:

- **New York → $304,154**
- **Los Angeles → $242,814**

### Revenue Difference

**$304,154 − $242,814 = $61,340**

This led to the question:

> **If both locations have almost the same number of appointments, why does New York generate $61,340 more revenue?**

I checked factors such as cost and treatment duration, but they did not explain the difference sufficiently.

So I investigated the **treatment mix**.

### Treatment Mix

| Treatment | Los Angeles | New York |
|---|---:|---:|
| Cleaning | **205** | **127** |
| Whitening | **94** | **228** |

New York had **134 more whitening appointments** than Los Angeles.

I then checked the profitability of each treatment.

| Treatment | Profit Margin |
|---|---:|
| Whitening | **39.97%** |
| Cleaning | **10.09%** |

### Conclusion

The treatment mix provides an important explanation for the performance difference.

New York had almost the same total appointment volume as Los Angeles, but significantly more appointments for **whitening**, which had a much higher profit margin than cleaning.

### Business Insight

Appointment volume alone is not enough to evaluate performance.

A business should also consider:

**Appointment Volume + Treatment Mix + Treatment Profitability**

---

# 3. Is dentist performance only dependent on the dentist?

I created a **Profit Margin by Dentist ID** visual and found:

- **D2 → 23.71%**
- **D4 → 13.80%**

At first, this made it look like D4 was simply performing worse.

But I asked:

> **Could the location where the dentist works also influence this result?**

So I added location to the analysis.

### D4 by Location

| Location | Profit Margin |
|---|---:|
| Chicago | **4.11%** |
| Houston | **7.59%** |
| Los Angeles | **20.53%** |

D4 did not work in New York.

I then checked D5.

### D5 by Location

| Location | Profit Margin |
|---|---:|
| New York | **27.44%** |
| Miami | **24.32%** |
| Chicago | **4.11%** |

The same dentist, D5, had:

**27.44% profit margin in New York**

but:

**4.11% in Chicago**

### Conclusion

This showed me that dentist performance should not be evaluated only at the dentist level.

The same dentist can have significantly different profitability across locations.

I cannot say that location directly causes the difference because I did not perform a statistical test.

### Business Insight

A more useful dentist-performance analysis would consider:

**Dentist + Location + Treatment Mix + Operating Cost**

rather than looking only at the dentist's overall profit margin.

---

# 4. Is waiting time related to no-show rate?

Another pattern I noticed was the difference between **waiting time and no-show rate**.

### Location Comparison

| Location | Average Waiting Time | No-Show Rate |
|---|---:|---:|
| Chicago | **49.2 min** | **21.9%** |
| New York | **10.1 min** | **11.3%** |
| Houston | **32.5 min** | **31.0%** |

Initially, the Chicago and New York numbers made me ask:

> **Could higher waiting time be related to more no-shows?**

However, Houston challenged this assumption.

Houston had a lower waiting time than Chicago:

**32.5 minutes vs 49.2 minutes**

but had a higher no-show rate:

**31.0% vs 21.9%**

### Conclusion

Waiting time may be associated with no-show behavior in some parts of the data, but it is clearly **not the only possible factor**.

This means I would not conclude:

> "Higher waiting time causes higher no-shows."

Instead, the data suggests that other factors may also be involved.

Possible factors include:

- Clinic operations
- Scheduling
- Treatment type
- Location-specific factors
- Cost structure
- Other variables not available in the dataset

A future analysis using **correlation or regression** could test this relationship statistically.

---

# Key Business Insights

## 1. Chicago needs a cost investigation

Chicago has only **4.11% profit margin** compared with the overall **20.5%**.

Its average total cost is:

**$456.02 vs $372.62 overall**

Both staff and equipment costs are higher than the overall average.

---

## 2. Treatment mix matters

New York generated:

**$304,154 revenue**

while Los Angeles generated:

**$242,814 revenue**

The difference was:

**$61,340**

Despite having **4 fewer appointments**, New York had significantly more whitening appointments:

**New York → 228**

**Los Angeles → 94**

Whitening also had a much higher profit margin:

**39.97% vs 10.09% for cleaning**

This demonstrates why appointment volume alone should not be used to evaluate clinic performance.

---

## 3. Dentist performance should be analyzed with context

D5 had:

**27.44% profit margin in New York**

but:

**4.11% in Chicago**

This shows why dentist performance should be evaluated together with factors such as location, treatment mix, and operating costs.

---

## 4. Waiting time is an important operational KPI

Chicago had the highest average waiting time:

**49.2 minutes**

This makes waiting time an important metric for further investigation.

However, the data does not prove that waiting time directly causes higher costs or lower profitability.

---

## 5. No-shows have multiple possible factors

Houston had the highest no-show rate:

**31.0%**

despite having a lower average waiting time than Chicago.

This challenged my initial assumption and showed why conclusions should be based on the complete data rather than a single pattern.

---

# What I Learned

The biggest learning from this project was that **dashboard creation is only one part of data analysis**.

The more important part is asking questions about the numbers.

For example:

### I saw:

**Chicago → 4.11% profit margin**

I asked:

**Why?**

Then I checked:

**Treatment Time → Cost → Staff Cost → Equipment Cost → Waiting Time**

---

 I saw:

New York → $304,154 revenue

Los Angeles → $242,814 revenue

I asked:

Why, when appointment numbers are almost the same?

Then I checked:

Treatment Mix → Whitening → Cleaning → Profit Margin

---

 I saw:

**D4 → 13.80% profit margin**

I asked:

Is this really because of the dentist?

Then I checked:

Dentist → Location

This showed that the same dentist can have different profitability across locations.

---

 I saw:

Waiting time and no-show rate appeared related in some locations

I asked:

Does waiting time cause no-shows?

Then I checked another location and found that the pattern was not consistent.

This helped me avoid making a conclusion that the data could not support.

---

 Limitations

This analysis is based on observational data.

Therefore, the conclusions are mainly based on:

- Comparisons
- Patterns
- Associations
- Descriptive analysis

I did **not** perform statistical causation tests.

Therefore, I avoid making claims such as:

- Waiting time causes low profit.
- Waiting time causes no-shows.
- Location causes low dentist performance.

Instead, these are treated as **observations or possible explanations** that require further investigation.

Future analysis could include:

- Correlation analysis
- Regression analysis
- Statistical significance testing
- More detailed treatment-level analysis
- Resource utilization analysis

---

# Tools & Skills Used

- Microsoft Power BI
- Power Query
- DAX
- Data Cleaning
- Data Transformation
- Data Modeling
- Data Visualization
- Exploratory Data Analysis
- KPI Development
- Business Analysis

---

 Project Takeaway

This project helped me understand that good data analysis is not just about finding the highest and lowest numbers.

It is about asking:

What is happening

Then:

Why could this be happening?

Then checking whether the data actually supports that explanation.

Sometimes the data supported my initial thinking, such as the relationship between **higher operating costs and Chicago's low profit margin.

Sometimes the data challenged my assumption, such as the **Houston no-show example**.

The key lesson for me was:

Ask questions → Check the numbers → Challenge assumptions → Find patterns → Make conclusions supported by data.

Power BI helped me visualize the data, but the main value of the project was using those visuals to think through business problems and turn data into actionable insights.
