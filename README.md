# Risk analysis of bladder cancer recurrence according to patient and tumour characteristics among patients receiving Pyridoxine (Vitamin B6), Thiotepa, or placebo

## Abstract
Bladder cancer is characterised by a high risk of recurrence following initial treatment. This project investigated the risk of bladder cancer recurrence among patients receiving Pyridoxine (Vitamin B6), Thiotepa, or placebo, with particular consideration of patient and follow-up characteristics. Data from the *Bladder1* dataset in the R *survival* package were analysed, comprising 118 patients assigned to one of the three treatment groups. Recurrence probability, recurrence rate, relative risk, and odds ratios were calculated to compare recurrence between treatments. Kaplan–Meier survival analysis was used to investigate recurrence-free survival over time, and a Cox proportional hazards model was fitted to assess the association between treatment and hazard of recurrence.

The recurrence probability was 60.4% for placebo, compared with 46.9% for Pyridoxine and 47.4% for Thiotepa. Relative risk and odds ratio estimates similarly indicated lower observed recurrence for both active treatments compared with placebo, while differences between Pyridoxine and Thiotepa were small. Thiotepa had the lowest recurrence rate when follow-up time was taken into account. Kaplan–Meier curves showed broadly similar recurrence-free survival for Pyridoxine and Thiotepa, with the placebo group showing a more rapid decline. The Cox model estimated lower recurrence hazards for Pyridoxine (HR = 0.702, 95% CI: 0.375–1.316) and Thiotepa (HR = 0.682, 95% CI: 0.377–1.234) compared with placebo; however, neither association was statistically significant, and the overall treatment effect was not significant (p = 0.40). The proportional hazards assumption was not found to be violated (p = 0.49).

Overall, the descriptive analyses indicated lower observed recurrence among patients receiving Pyridoxine or Thiotepa compared with placebo, but the survival analysis did not provide sufficient statistical evidence of an association between treatment group and recurrence hazard. The findings demonstrate the importance of accounting for follow-up time and uncertainty when analysing bladder cancer recurrence and suggest that incorporating patient and tumour characteristics and recurrent-event methods could provide further insight into factors associated with recurrence.


## Introduction
Up until the early 1970s, Theotepa was considered an established clinical approach for treatment of superficial bladder cancer. Pyridoxine was introduced later on. Researchers observed abnormalities in trytophan metabolism in patints with bladder cancer, and animal studies suggested that some trytophan metabolites contributed to bladder carcinogenisis. They hypothesized that taking Pyridoxine might correct these metabolic abnormalities. The 1977 randomised trial compared the effectiveness of both treatments with a placebo, and it was fond that theotepa had a higher rate of reduced reccurence, however the published analysis did not make tumor size or patient charecteristics a moor part of its analysis.

## Method
### Data
The data used in this project are from the Bladder1 in the survival package in R. It consists of 118 patients with bladder cancer including information of treatment group and information relating to tumor reccurence and follow up time. Patients recieved one of three treatments: Placebo, Pyridoxine, and Thiotepa. The dataset includes information on number of initial tumors, number of recurrences, follow up times and status after an observed interval. The data was used to investigate and compare risk of bladder cancer recurrence between the three treatment groups using several statistical methods.

For the purpose of this analysis, the data were often modified to account for unique patients who experienced one or more recurrences due to the dataset often containing more than one observation per patient. 
(some sort of license reference to be added later)

### Statistical Analysis
The follwong statistical methods were used to investigate the risk of bladder cancer recurrence.

#### Recurrence Probability and Recurrence Rate
Recurrence probability and recurrence rate were calculated and compared between treatment groups, and he the results were interpreted and presented as a table. The data were modified to account for unique patients that have experienced one or more recurrences.  The formulae that were used are:

$$
\text{Recurrence Probability} =
\frac{\text{Number of patients experiencing a recurrence}}
{\text{Total number of patients}}
$$

$$
\text{Recurrence Rate} =
\frac{\text{Number of recurrence events}}
{\text{Total person-time at risk}}
$$

for recurrence probability and recurrence rate respectively.

#### Relative Risk and Odds Ratio
Relative risks and odds ratios were calculated to compare the risk of recurrence between treatment groups. Comparisons were made between Pyridoxine and Placebo, Thiotepa and Placebo, and Pyridoxine and Thiotepa. The results were presented in a table and interpreted to assess the relative risk and odds of recurrence between treatments. The formulae used are:

$$
\text{Relative Risk} =
\frac{\text{P(Recurrence | Treatment A)}}
{\text{P(Recurrence | Treatment B)}}
$$

$$
\text{Odds Ratio} =
\frac{\text{odds(Recurrence | Treatment A)}}
{\text{odds(Recurrence | Treatment B)}}
$$

for relative risk and odds ratio respectively, and given

$$
\text{odds} = \frac{{p}}{1-p}
$$

Where p is the recurrence probability.

#### Survival Analysis

Survival analysis was conducted to account for the time until recurrence and differences in patient follow-up. Kaplan–Meier analysis was used to investigate the time patients remained recurrence-free according to treatment group. The resulting survival probabilities were visualised using Kaplan–Meier survival curves. A Cox proportional hazards model was then fitted to investigate whether treatment group was associated with the hazard of recurrence. The estimated hazard ratios, confidence intervals and significance levels were examined to assess the relationship between treatment and recurrence hazard. The proportional hazards assumption was also assessed to determine the suitability of the model.

## Results
### Recurrence Probability and Recurrence Rate
The comparison between recurrence probability and recurrence rate according to treatment type is displayed in the table below. The table immediately reveals that the recurrence probability for the placebo is the highest at 60.4% in comparison with Pyridoxine at 46.9% and Thiotepa at 47.4%. We also see that although Pyridoxine has the lowest recurrence probability out of the three, there is very little difference between Thiotepa. This suggests that patients recieving Pyridoxine and Thiotepa had very similar chances of experiencing a recurrence. In contrast the recurrence rate of Thiotepa is the lowest out of the tree at 0.038. This suggests that when the amount of follow up time is taken into account, recurrence occur at a lower rate for patients recieving Thiotepa. We also note that the recurence rate for Pyridoxine is the highest out of the three, including the Placebo, reealing how recurrence probability and recurrence rate are not interchangeable.

<img src="https://github.com/user-attachments/assets/f463992a-7f5c-438a-ae13-c1b2465dbeff" width="500"/>
<p><em>Figure 1: Relationship between recurrence probability and recurrence rate.</em></p>

### Relative Risk vs Odds Ratio
The table below compares the relative risk and odds ratio according to patient treatment type. We see that there is a 21.6% reduced recurrence rate for Thiotepa in comparison with Placebo, 22.4% reduced recurrence rate for Pyridoxine in comparison with Placebo, and 1.052% increased rate or recurrence for Thiotepa in comparison with Pyridoxine to 3sf. It is interestiing to compare the first two relative risks with one another. Both treatments reduce the recurrence rate in comparison with the placebo, but pyridoxine has a slightly higher percentage of reduced recurrence rate, suggesting higher effectiveness than Thiotepa. 
Looking at the odds ratios, we can see that in comparison with the Placebo the odds of recurrence for Thiotepa is approximately 41% lower. Similarly, the odds of recurrence for Pyridoxine in comparison with the placebo is approximately 42% lower. The final odds ratio is easier to analyse through inspection: The ratio between the two odds for thiotepa and pyridoxine is 1.02. This suggest very little difference in the recurrence odds for the two treatments. We conclude that while both pyridoxine and Thiotepa substantially reduce recurrence odds, pyridoxine appears to be slightly more effective.

<img width="500" alt="rr vs or" src="https://github.com/user-attachments/assets/a3e4f9c6-886e-4e42-ae07-1410830fba23" />
<p><em>Figure 1: Relationship between recurrence probability and recurrence rate.</em></p>

### Kaplan-Meier Analysis
The Kaplan-Meier analysis indicates that for all three treatments, the probability of remaining recurrence free declines over time. The survival curve below reveals that all treatments appear to have similar probabilities of remaining recurrence free for the first initial months, and out of the three treatments, the Placebo shows a fairly rapid decline in recurrence free survival. Pyridoxine and Thiotepa showed broadly similar chances of recurrence free survival, although estimates become increasingly uncertain at later follow up times due to the small number of patients remaining at risk. 
The table below displays the last observed time interval where there was a recurrence for each treatment type, theyre respective survival probabilities and confidence intervals. This confirms the uncertainty in the estimates from our model, and it seems increases the importance of a cox test.

<img width="500" alt="km curve" src="https://github.com/user-attachments/assets/8afb8007-882b-47cd-83da-56d0f806b678" />
<p><em>Figure 1: Relationship between recurrence probability and recurrence rate.</em></p>

### Cox proportional hazard model
The Cox proportional hazards model estimated a lower hazard of recurrence for both pyridoxine (HR = 0.702, 95% CI: 0.375–1.316) and thiotepa (HR = 0.682, 95% CI: 0.377–1.234) compared with placebo. However, neither association was statistically significant, as the confidence intervals included 1 and the p-values were greater than 0.05. The overall tests of treatment effect also provided insufficient evidence of differences in recurrence hazard between treatment groups (p = 0.40). The proportional hazards assumption was not found to be violated (global p = 0.49). The concordance of 0.533 indicates limited discrimination of the model based on treatment alone.

## Discussion
The aim of this analysis was to investigate whether the risk of bladder cancer recurrence differed between patients receiving Pyridoxine, Thiotepa, and placebo, while also considering the effect of follow-up time. Several statistical approaches were used to investigate recurrence, including recurrence probability, recurrence rate, relative risk, odds ratios, Kaplan–Meier survival analysis, and a Cox proportional hazards model. Although the descriptive analyses suggested differences between the treatment groups, the survival analysis provided limited statistical evidence for a difference in recurrence hazard.

The recurrence probability was highest among patients receiving placebo, with 60.4% experiencing a recurrence, compared with 46.9% for Pyridoxine and 47.4% for Thiotepa. This suggests that a smaller proportion of patients receiving either active treatment experienced recurrence. However, the difference between Pyridoxine and Thiotepa was very small. The relative risk estimates similarly indicated a lower probability of recurrence for both treatments compared with placebo. Pyridoxine had a slightly lower relative risk than Thiotepa, although the difference between the two active treatments was small.

The recurrence rate produced a somewhat different interpretation. Unlike recurrence probability, recurrence rate incorporates the amount of follow-up time available for each patient. Thiotepa had the lowest recurrence rate, despite having a slightly higher recurrence probability than Pyridoxine. This demonstrates the importance of accounting for follow-up time when analysing recurrent events. Patients who are followed for longer periods have more opportunity to experience recurrence, meaning that a simple proportion of patients experiencing recurrence does not completely describe the underlying recurrence process. The difference between recurrence probability and recurrence rate therefore highlights why several complementary statistical measures were used rather than relying on a single measure.

The odds ratio analysis also suggested lower odds of recurrence for both active treatments compared with placebo. The odds of recurrence were approximately 41% lower for Thiotepa and 42% lower for Pyridoxine compared with placebo. However, the odds ratio comparing Thiotepa with Pyridoxine was close to one, indicating little difference between the two active treatments. Therefore, while the descriptive measures suggest that both treatments may have been associated with lower recurrence than placebo, there was little evidence from these measures of a meaningful difference between Pyridoxine and Thiotepa.

The Kaplan–Meier analysis provided an additional perspective by incorporating the timing of recurrence and allowing patients with different lengths of follow-up to contribute appropriately. The curves suggested broadly similar recurrence-free survival for Pyridoxine and Thiotepa, while the placebo group appeared to experience a more rapid decline in recurrence-free survival. However, the confidence intervals became increasingly wide at later follow-up times. This reflects the decreasing number of patients remaining at risk and means that the apparent differences between treatment groups at later times should be interpreted cautiously.

The Cox proportional hazards model provided a more formal assessment of the association between treatment and the hazard of recurrence. Both Pyridoxine and Thiotepa had estimated hazard ratios below one compared with placebo, with hazard ratios of 0.702 and 0.682 respectively. This corresponds to estimated hazards of recurrence approximately 30% lower for Pyridoxine and 32% lower for Thiotepa relative to placebo. However, the confidence intervals for both estimates included one, and neither treatment effect was statistically significant. The overall treatment test also provided insufficient evidence of a difference in recurrence hazard between the three groups (p = 0.40).

These findings are important because they demonstrate the difference between an observed effect and statistical evidence for an effect. The descriptive results and estimated hazard ratios suggest that recurrence may have been lower among patients receiving active treatment, but the uncertainty surrounding the estimates means that the observed differences cannot be distinguished reliably from random variation using this dataset. The similar hazard ratios for Pyridoxine and Thiotepa also support the conclusion that there was little evidence of a difference between the two active treatments.

The proportional hazards assumption was not found to be violated, with a global test p-value of 0.49. Therefore, there was no statistical evidence that the assumption required by the Cox model was inappropriate for these data. However, the model's concordance of 0.533 indicates that treatment group alone provided limited ability to distinguish between patients who experienced earlier recurrence and those who remained recurrence-free for longer. This suggests that factors other than treatment are likely to be important in explaining differences in recurrence timing.

An important limitation of this analysis is the relatively small sample size of 118 patients. The small number of patients, particularly at longer follow-up times, results in considerable uncertainty in the survival estimates and limits the precision of the estimated treatment effects. In addition, the analysis primarily considered treatment group when modelling recurrence hazard. Patient and tumour characteristics available in the dataset, such as the number of initial tumours, could potentially provide additional information about recurrence risk. Including these variables in a multivariable survival model could determine whether differences in recurrence were associated with treatment after accounting for differences in patient or tumour characteristics.

Another limitation is that the dataset contains multiple observations for some patients because patients could experience more than one recurrence. For the recurrence probability and related calculations, the data were therefore modified to distinguish patients who experienced at least one recurrence from those who did not. This was appropriate for estimating the probability of experiencing a recurrence, but it does not fully capture the repeated nature of recurrence events. A recurrent-event survival analysis could therefore provide a more complete analysis of the data by accounting for multiple recurrences experienced by the same patient.

Overall, the different analyses provide a consistent indication that the two active treatment groups had lower observed recurrence than placebo in several measures, while showing very little difference between Pyridoxine and Thiotepa. However, the Cox proportional hazards model did not provide statistically significant evidence that treatment was associated with recurrence hazard. The results therefore illustrate the importance of considering follow-up time, uncertainty, and repeated events rather than interpreting differences in simple recurrence proportions alone.

## Conclusion
This project investigated the risk of bladder cancer recurrence among patients receiving Pyridoxine, Thiotepa, or placebo using several complementary statistical methods. The descriptive analyses showed a lower recurrence probability for both Pyridoxine and Thiotepa compared with placebo, while the difference between the two active treatments was small. Recurrence rates also differed between the groups, demonstrating the importance of accounting for differences in follow-up time when assessing recurrence.

Kaplan–Meier analysis similarly suggested broadly comparable recurrence-free survival for Pyridoxine and Thiotepa, with the placebo group showing a more rapid decline in recurrence-free survival. However, uncertainty increased at longer follow-up times as fewer patients remained at risk.

The Cox proportional hazards model estimated lower recurrence hazards for both Pyridoxine and Thiotepa compared with placebo. However, neither treatment effect was statistically significant, and the overall treatment effect was also not statistically significant. Therefore, although the observed data showed differences in recurrence between treatment groups, this analysis did not provide sufficient statistical evidence to conclude that treatment group was associated with recurrence hazard.

The analysis also demonstrates the value of considering follow-up time and repeated recurrence events when investigating bladder cancer recurrence. Further analysis incorporating patient and tumour characteristics, as well as methods specifically designed for recurrent events and competing risks, could provide a more comprehensive assessment of factors associated with recurrence.
