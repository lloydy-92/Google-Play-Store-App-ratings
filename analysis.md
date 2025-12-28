## 1) Do paid apps actually have higher ratings than free apps?
<img width="567" height="455" alt="download" src="https://github.com/user-attachments/assets/6f07b22a-512a-4bdf-9eeb-e242a4abad9e" />

Due to an enormous amount of data points have price values of $0, to stop the results from becoming too zero-inflated skewed, it has been decided to emit all free apps from further analysis for this question.<br/><br/>

<img width="584" height="455" alt="image" src="https://github.com/user-attachments/assets/5c6cd729-47fb-4d3b-b31a-53b36f5a3187" />

Spearman ρ = -0.088, p-value = 0.0348<br/><br/>

<img width="671" height="455" alt="image" src="https://github.com/user-attachments/assets/4d41bfbd-6244-45e3-b099-047fe90b0d1b" />

Spearman ρ = -0.226, p-value = 0.0664<br/>
It is clear that there are also some extreme values of apps with prices of $300+ distorting the results, so it would be wise to redo this analysis without those values to investigate any potential differnce.<br/><br/>

<img width="692" height="455" alt="image" src="https://github.com/user-attachments/assets/1878cfa1-483e-4107-9b08-63bc2254b70c" />

Spearman ρ = -0.052, p-value = 0.221<br/><br/>

<img width="812" height="455" alt="image" src="https://github.com/user-attachments/assets/63de60b0-5629-4477-a311-a36de34c5ffa" />

Spearman ρ = -0.110, p-value = 0.4<br/><br/>

<img width="608" height="455" alt="image" src="https://github.com/user-attachments/assets/a7eda2fb-9358-471f-9e56-b1f16d4b7421" /><br/><br/>

The results here were somewhat inconclusive; Figure 6 shows that the overall distribution of paid apps' ratings is higher than that of free ones. However, whilst Figures 2-5 all appeared to show a negative correlation between price and rating, Spearman rank showed that only Figure 1, price vs rating across the entire non-zero price range, had a significant correlation (p = 0.348); accounting for extreme price values (only including apps price above 0 but below 50 dollars) did not yield a more significant correlation, visually or statistically.

## 2) Do larger apps receive lower ratings due to storage concerns?
<img width="567" height="455" alt="image" src="https://github.com/user-attachments/assets/9a4dc9f5-73a2-47e3-898a-362b2406813a" />

Spearman ρ = 0.069, p-value = 1.03e-09<br/>

Despite being a very weak correlation in magnitude, with a ρ value of only 0.069, and there being almost no discernible pattern between size and rating in Figure 6, the Spearman rank correlation test still computes a significant correlation between the two variables, with a p value of 1.03 x 10^-9.

## 3) How do ratings vary across different content rating groups?
<img width="630" height="455" alt="image" src="https://github.com/user-attachments/assets/5f1cf78d-330e-48b3-8db5-79501f81ba92" />

ANOVA F-statistic: 8.428, p-value: 0.00001<br/>

**Multiple Comparison of Means - Tukey HSD, FWER = 0.05**
| group1 | group2 | meandiff | p-adj | lower | upper | reject |
|--------|--------|----------|-------|-------|-------|--------|
| Everyone | Everyone 10+ | 0.0946 | 0.0134 | 0.0142 | 0.1749 | True |
| Everyone | Mature 17+ | -0.0711 | 0.0707 | -0.1461 | 0.0039 | False |
| Everyone | Teen | 0.0606 | 0.0113 | 0.01 | 0.1113 | True |
| Everyone 10+ | Mature 17+ | -0.1656 | 0.0004 | -0.2726 | -0.0586 | True |
| Everyone 10+ | Teen | -0.0339 | 0.7767 | -0.1255 | 0.0577 | False |
| Mature 17+ | Teen | 0.1317 | 0.0006 | 0.0448 | 0.2186 | True |<br/><br/>

Looking at Figure 7, it does not appear at first glance that there is a significant difference between the ratings for different content rating groups, aside from 'Mature 17+', which appears to rank lower than the other 3 categories. However, by using ANOVA, we can see that is actually a significant difference given by the p-value of 0.00001, and Tukey's test tells us that there is a significant difference between each content rating category (except for between 'Everyone' and 'Mature 17+', and 'Everyone 10+' and 'Teen'), with the most significant differences being that of pairs including 'Mature 17+', which is to be expected as it is the most visually significantly different group when looking at Figure 7. Interestingly, Tukey's test reveals that there is a significant difference for rating between 'Everyone' and 'Teen', despite their distributions looking nearly identical to one another in Figure 7.

## 4) Do recently updated apps have better ratings?
<img width="658" height="455" alt="image" src="https://github.com/user-attachments/assets/1ed19daf-66b3-44e5-9a7c-3f709bffbdfe" />

Spearman ρ = -0.171, p-value = 1.41e-51<br/>

Looking at Figure 8, there does appear to be a downward overall trend between years since last update and an app's rating, suggesting that more frequently updated apps do tend to rate higher than older, more 'forgotten about' ones. The Spearman rank backs up Figure 8's findings, that there is a very significant (p = 1.41x10^-51), albeit weak (ρ = -0.171), negative correlation between the years elapsed since a app received an update and the rating a user gives it.

## 5) Do saturated categories suffer from lower average ratings?
<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/fbef74df-9071-4838-8669-68d6eb0b85f9" />

Spearman ρ = -0.259, p-value = 0.145<br/>

Looking at Figure 10, whilst it shows a negative regression line suggesting that more apps there are in a category the lower that app receives in rating on average, its Spearman Rank test shows that this relationship is not significant.

# Conclusion
These results suggest that while several variables are indeed statistically associated with app rating on the Google Play Store, their practical impact is generally modest, and strong effects don't appear to be common. Monetisation shows the least significant influence: although paid apps show a higher overall rating distribution than free apps, the relationship between price and rating is predominantly statistically insignificant once realistic price boundaries are considered. This suggests that a more expensive app does not necessarily lead to users ranking it higher. Similarly, whilst app storage size shows a statistically significant with its user rating, this effect is very small, indicating that storage concerns play only a negligible role in shaping individual user ratings.

Variables such as content targeting and maintenance behaviour towards and app show more meaningful patterns. Ratings differ significantly across content rating groups, with statistical testing revealing distinctions not immediately obvious from the data visualisations, bring attention to the importance of statistical testing alongside exploratory visual plots. Specifically, apps rated 'Mature 17+' consistently differ from other content rating groups, implying that audience or content expectations may meaningfully influence user evaluations. Update frequency also demonstrates a clear and statistically robust relationship with ratings: apps that have been updated more recently tend to receive higher ratings, supporting the idea that an app that is regularly maintained and stays relevant positively contributes to user satisfaction, even if the magnitude of this effect is small.

Finally, how competitive an app category is does not appear to significantly lower average app quality. Whilst visually speaking it would appear that more saturated categories receive lower average app ratings, these findings are statistically insignificant, indicating that increased competition alone doesn't necessarily lead to worse user experience.

Overall, findings suggest that user ratings are influenced more by qualitative factors such as active maintenance rather than price, size, or market saturation, and that statistically significant effects in large datasets should be interpreted cautiously with respect to their real-world importance.


