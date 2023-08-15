# A-Comparison-of-the-Relative-Risk-Index-with-Unit-Fragilty
A comparison of the unit fragility index with the new Relative Risk Index (RRI) which measures statistical fragility without dependence upon p-values.

A COMPARATIVE ANALYSIS OF UNIT FRAGILITY AND THE RELATIVE RISK INDEX

Thomas F. Heston MD

Department of Family Medicine, University of Washington, Spokane, Washington.

Department of Medical Education and Clinical Sciences, Washington State
University, Spokane, Washington.

Copyright: CC BY-NC-ND 4.0 and GNU GPL v3.0

ABSTRACT

BACKGROUND: In biostatistics, evaluating the fragility of units is crucial
for understanding their vulnerability to different factors. One proposed
measure of statistical fragility is the unit fragility index (UFI), which
measures the susceptibility of the p-value to flip significance with minor
changes in a 2x2 contingency table. Although the UFI provides valuable
information about statistical fragility, it relies on p-values, which are
arbitrary measures of statistical significance. Alternative measures, such
as the fragility quotient (FQ) and the percent fragility index, have been
proposed to decrease the UFI's reliance on sample size. However, these
approaches still rely on p-values and thus depend on an arbitrary cutoff of
p < 0.05. Instead of quantifying fragility by relying on p-values, this
study evaluated the effect of small changes on relative risk. METHODS:
Random 2x2 contingency tables associated with an initial p-value of 0.001
to 0.05 were evaluated. Each table's UFI and relative risk index (RRI) were
calculated. A derivative of the RRI, the percent RRI, was also calculated
along with the FQ. The UFI, FQ, RRI, pRRI, initial p-value, and sample size
were compared. RESULTS: A total of 15,000 cases were tested. The
correlation between the UFI and the p-value was the strongest (r = -0.809),
and the correlation between the pRRI was the weakest (r = -0.396). The RRI
had the strongest correlation with the sample size (r = 0.822), and the UFI
had the weakest correlation (r = 0.379). The coefficient of variation for
the average RRI was the smallest at 28.1%, and for the FQ, it was the
greatest at 56.8%. The correlation between the UFI, FQ, and p-value is
significantly greater than the correlation between the RRI, pRRI, and
p-value (for all comparisons, p < 0.001). CONCLUSION: The RRI and pRRI are
significantly less correlated with the p-value than the UFI and FQ,
indicating relative independence of the RRI and pRRI from the p-value when
evaluating 2x2 contingency tables.

KEYWORDS: Fragility index, Unit fragility index, Fragility quotient, percent
fragility index, Relative risk index, percent relative risk index, statistical
significance.

FUNDING INFORMATION: Self-funded, no external funding.

CONFLICT OF INTERESTS: No competing interests.

ETHICAL APPROVAL: This study did not involve human or animal research.

INTRODUCTION:

The unit fragility index (UFI) was proposed in 1990 to
quantify the fragility of a test of two proportions (Feinstein 1990). This
test looked at the effect of small outcome changes on the p-value. When
evaluating a standard 2x2 contingency table, the UFI represented the number
of unit changes (integer changes) in the cell counts. Using the standard
labels for a 2x2 table (a, b, c, d), the first step is to look at the
p-value. If it is statistically significant (p < 0.05), one is added to the
cell with the smallest count. For example, if "d" had the fewest cases, the
table would be changed as follows: a+1, b-1, c-1, d+1. The resultant
p-value would then be calculated. If the p-value flipped from significant
to nonsignificant, then the UFI = 1. If the p-value remained significant,
the process would increment by 1 unit again, such that the new table would
be a+2, b-2, c-2, and d+2. The p-value of this new table will be
calculated. If the significance flipped, the process would end, and the UFI
= 2. This is repeated until the p-value flips from < 0.05 to > 0.05, and
the UFI is the number of increments required to do this.

The problem with
the UFI is that it changes with increased sample size. An attempt to fix
this issue was to calculate a Fragility Quotient (FQ), the UFI divided by
the sample size (Ahmed 2016). Another attempt to address this issue was
incrementing by fractions instead of integer units, creating a percent
fragility index (Heston 2023). While these did help address the sample size
issue, the reliance upon p-values remained.

P-values don't necessarily
influence clinicians. What they want to know is significance. Specifically,
should I use this medication or not? Should I do this test or not? The
relative risk (RR) of a new test or medication, as quantified by a 2x2
contingency table, answers this question. If the RR is favorable, then the
evidence favors doing the treatment or test. If not, then there is no
benefit.

The relative risk index (RRI) is a proposed measure to quantify
statistical fragility without relying upon p-values. While the UFI looks at
the effect of incremental changes in outcomes upon the p-value, the RRI
looks at the effect of changing outcomes upon the RR. Instead of a
threshold of flipping the p-value from significant to non-significant, the
RRI quantifies how much of a change in outcomes is required to get the RR
equal to one since when the RR equals one, it indicates that there is no
value whatsoever for the new test or new treatment.

The RRI equals (bc-ad)/(a+b+c+d). Similar to the UFI, the marginal totals
remain fixed.

The percent RRI (pRRI) is a derivative of the RRI that quantifies the percent
change in the 2x2 table rather than the absolute change.

The pRRI equals (RRI/a + RRI/b + RRI/c + RRI/d)/4.

METHODS:

A Python program generated random 2x2 contingency tables with cell counts
ranging from 15 to 250. Tables selected for analysis were limited to those
associated with a p-value of less than 0.05 as determined by chi-square
testing. The UFI, FQ, RRI, and pRFI were calculated for each table based on the
initial p-value and outcomes changes to flip the p-value to > 0.05 or reach an
RR of one. Fisher's z-transformation determined statistically significant
differences in correlation coefficients.

The python program used is publicly available on github and included below.

RESULTS

Here is the output of the python program.

## START PROGRAM OUTPUT

BASE SETTINGS
Total Cases Tested: 15000
Lowest number in 2x2 table: 15
Highest number in 2x2 table: 251
Lowest p-value: 0.000999
Highest p-value: 0.05

CORRELATIONS
Correlation between UFI and pv: -0.80868 p-value: 0.0
Correlation between FQ and pv: -0.73799 p-value: 0.0
Correlation between RRI (exact RR index) and pv: -0.49156 p-value: 0.0
Correlation between pRRI (percent RR index) and pv: -0.39601 p-value: 0.0
Correlation between UFI and sample size: 0.37923 p-value: 0.0
Correlation between FQ and sample size: -0.43429 p-value: 0.0
Correlation between RRI and sample size: 0.82228 p-value: 0.0
Correlation between pRRI and sample size: -0.78007 p-value: 0.0

AVERAGES, STANDARD DEVIATIONS,COEFFICIENTS OF VARIATION AND RANGE
Average PV, STD, CV (minimum, maximum): 0.01468 , 0.01360 , 92.6 % ( 0.00100 , 0.04999 )
Average Sample Size of Each Case, STD, CV (minimum, maximum): 306.9 , 145.1 , 47.3 % ( 83.0 , 857.0 )
Average UFI, STD, CV (minimum, maximum): 3.101 , 1.714 , 55.3 % ( 1.0 , 9.0 )
Average FQ, STD, CV (minimum, maximum): 0.01144 , 0.00649 , 56.8 % ( 0.00120 , 0.04000 )
Average RRI, STD, CV (minimum, maximum): 10.92 , 3.07 , 28.1 % ( 4.81 , 22.74 )
Average pRRI, STD, CV (minimum, maximum): 0.03998 , 0.01190 , 29.8 % ( 0.01570 , 0.08488 )

# END PROGRAM OUTPUT

The weakest correlation with the p-value was pRRI, and the next weakest was
RRI. The RRI and pRRI had the strongest correlation with the sample size;
however, the RRI had the lowest coefficient of variation (CV), and the pRRI
had the subsequent lowest CV.

DISCUSSION

A weak correlation between RRI, pRRI, and p-values indicates relative
independence of the RRI and pRRI from p-values. While the UFI and FQ strongly
depend on the p-values, the RRI and pRRI do not. Thus, the RRI and pRRI provide
new information that is not well explained by the p-value, making them
statistics that add more information to the p-value than the UFI or FQ do.

The R-squared value for the correlation between the pRRI and
p-value is 0.16, indicating that 16% of the variation in the pRRI is
explained by the p-value. In contrast, the R-squared value of the
correlation between the UFI and the p-value is 0.80868, which equates to
65.3% of the variation in the UFI being explained by the p-value.

While the RRI and pRRI had the strongest correlation with sample size, the fact
that the CV was significantly smaller than the CV for UFI and FQ indicates
that, even though they are correlated with sample size, the RRI and pRRI only
undergo minimal changes with varying sample sizes (i.e., the CVs for both
were small).

The pRRI is clinically useful. If the percent change in
outcomes equals the pRRI, then the research study's object, whether a new
treatment or a new test, has zero benefit. Sometimes, even if a p-value is
non-significant, it can still indicate that, more likely than not, the new
treatment or test is beneficial in most cases (e.g., if the p-value =
0.06). This situation is nebulous. At what point is the test or treatment
of no value? The pRRI answers this question. If there is a pRRI change in
outcomes, then the new test or treatment is useless.

Clinicians can use the pRRI in this manner: if a study shows a pRRI of 0.03, it
means that if 3% of the outcomes were changed, there would be no benefit to the
new test or treatment. For larger pRRI values, clinicians can be increasingly
confident that the new test or treatment will help their specific patient.

CONCLUSION
The RRI and pRRI provide additional information beyond
the p-value. They exhibit improved stability with varying sample sizes
compared to the UFI or the FQ. The RRI and pRRI offer valuable insights
into statistical analysis.

ABBREVIATIONS
cv = coefficient of variation
UFI = Unit Fragility Index
FQ = Fragility Quotient (Ahmed 2016)
pRRI = Percent Relative Risk Index
pv = p-value
RRI = Relative Risk Index
std = standard deviation

REFERENCES

Ahmed W, Fowler RA, McCredie VA (2016). Does sample size matter when interpreting the fragility index? Crit Care Med. 2016 Nov;44(11):e1142–3. DOI: 10.1097/CCM.0000000000001976

Feinstein AR (1990). The unit fragility index: an additional appraisal of “statistical significance” for a contrast of two proportions. J Clin Epidemiol. 1990;43(2):201–9.

Heston TF (2023). The percent fragility index. SSRN Journal 4482643. DOI: 10.2139/ssrn.4482643


