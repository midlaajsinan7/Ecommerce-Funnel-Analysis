# E-Commerce Customer Funnel Analysis & Drop-off Optimization

Analysis of a simulated e-commerce customer journey — **Homepage → Search → Product View → Add to Cart → Checkout → Purchase** — to identify where users drop off and recommend improvements.

**Tools:** SQL 
**Dataset:** 50,000 simulated user sessions

---

## Headline Finding

The largest drop-off in the funnel is **Product View → Add to Cart (55.6%)**.

| Device | Product Views | Add to Cart | PV → Cart Rate | Overall Conversion | Avg Order Value |
|---|---:|---:|---:|---:|---:|
| Desktop | 8,611 | 5,576 | **64.8%** | 17.2% | $81.55 |
| Mobile | 14,107 | 4,368 | **31.0%** | 6.7% | $83.17 |
| Tablet | 2,502 | 1,256 | **50.2%** | 11.7% | $82.99 |

Mobile has the highest number of product views but a much lower Product View → Add to Cart rate than desktop. Average order value is similar across devices.

### Problem → Hypothesis → Recommendation → KPI

- **Problem:** High drop-off between Product View and Add to Cart, especially on mobile.
- **Hypothesis:** Mobile product pages may have usability friction or a less visible Add to Cart button.
- **Recommendation:** Investigate the mobile product page and test improvements such as a more visible Add to Cart button.
- **Success KPI:** Mobile Product View → Add to Cart conversion rate.

These are hypotheses and recommendations from simulated data, not verified causes or results from a real A/B test.

---

## Repository Contents

| File | Description |
|---|---|
| `ecommerce_funnel_data.csv` | Session-level dataset containing 50,000 simulated sessions |
| `ecommerce_funnel.sql` | SQL table definition and analysis queries |

---

## Dataset Schema

| Column | Description |
|---|---|
| `User_ID` | Customer identifier |
| `Session_ID` | Unique shopping session identifier |
| `Session_Date` | Date of the session |
| `Device` | Mobile, Desktop, or Tablet |
| `Traffic_Source` | How the customer reached the website |
| `Product_Category` | Category of product browsed |
| `User_Type` | New or Returning customer |
| `Homepage_Visit` | Whether the session reached the homepage |
| `Search` | Whether the customer searched |
| `Product_View` | Whether a product was viewed |
| `Add_to_Cart` | Whether a product was added to the cart |
| `Checkout` | Whether checkout was reached |
| `Purchase` | Whether a purchase was completed |
| `Order_Value` | Order value for completed purchases |

The funnel-stage columns use binary values (0/1).

---

## SQL Analysis

The SQL queries cover:

- Overall funnel stage volumes
- Stage-wise conversion and drop-off rates
- Device-wise conversion performance
- Traffic-source analysis
- Product-category analysis
- New versus returning customer behavior
- Average order value and revenue by device
- Device × product-category deep dive
- Monthly conversion trends

## Methodology Notes

- The dataset is simulated for portfolio and learning purposes; it is not real company data.
- The analysis identifies patterns in this generated dataset. The mobile UX explanation is a hypothesis that would need validation with real data or an experiment.

## Future Improvements

- Build an Excel dashboard to present the findings.
- Create a machine learning model to predict purchase outcomes, with appropriate feature selection and evaluation.
- Validate recommendations using real-world data or an A/B test.

