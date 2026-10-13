1. (Modeling) Do students’ domains correlate with students’ preferences in the area of interest?
* Variables, Files, and Respondents:
* Data Preparation:
* Summaries or Plots:
* Key Choices to Check:
* Limitations:

&#x20;



2\. (Modeling) Does programming language correlate with students’ interest in statistical inference?

* Variables, Files, and Respondents:

  * Variables used:

    * `language` (R / Python / No preference), `areas` (multi-select; we use the single option "Statistical models and inference, generally")
  * Files used:

    * `interest-clean.csv` only -- both variables live in this one file, no join needed
  * Respondents:

    * n = 49 (full file). Checked directly: `language`, `type`, and `areas` have zero missing values in the current data, so no respondents were dropped. (An earlier note referencing 2 NA respondents, ids 1038/1046, was based on an older version of the data and does not apply to the current file.)
* Data Preparation:

  * Built a binary outcome: did the respondent select "Statistical models and inference" in `areas`? (`str_detect`, no comma-splitting needed since we only check one label)
  * Set `language` as a factor with reference level `"Python"` (largest group, n = 22) so model output reads as "relative to Python"
* Summaries or Plots:

  * Bar chart: proportion of each language group interested in statistical inference. Python = 50.0%, R = 81.8%, No preference = 68.8%. See `scripts/team 10 scripts/idea1.Rmd` and `results/figures/language-vs-statinference.png`.
* Modeling:

  * Logistic regression: `glm(interested_stat_inference ~ language, family = "binomial")`, reference = Python
  * R vs. Python: odds ratio = 4.50, 95% CI [0.90, 34.2], p = 0.091
  * No preference vs. Python: odds ratio = 2.20, 95% CI [0.59, 9.01], p = 0.251
  * Both point in the expected direction (R leans toward stats interest); the R comparison is close to the conventional significance threshold but does not formally cross it
* Key Choices to Check:

  * Reference level set to Python (largest group) rather than R or No preference -- affects which comparisons are shown directly, but all pairwise relationships can still be derived
  * Scoped to one area (statistical inference) per team decision; a broader 3-area version (also covering Deep learning, NLP) was explored earlier and showed a consistent stats-vs-ML split across all three, available if useful for discussion
* Limitations:

  * Small sample, especially the R group (n = 11) -- wide confidence intervals, neither result reaches p < 0.05
  * Correlation, not causation -- can't claim language preference causes interest in statistical inference; more likely both stem from the same underlying stats-vs-ML leaning
  * No multiple-testing correction applied (not needed for the single scoped area, would matter if the 3-area version is also reported)



3\. (Investigative) Are students that have done supervised research (not related to class or personal project) more interested in research labs than industry or not?

* Variables, Files, and Respondents:

  * Variables to consider:

    * `type`, `research`
  * Files used:

    * background-clean.csv, interest-clean.csv
  * Respondents to consider:

    * Respondent id 1038 and 1046 were dropped for having NA under `type`
* Data Preparation:

  * Join background-clean.csv and interest-clean.csv
  * Drop respondents 1038 and 1046 from the data set
* Summaries or Plots:

  * Create bar plots and summaries to see if there is a valid correlation or not

    * If there is, move on to modeling
    * If not, report conclusion.
* Key Choices to Check:

  * Determine whether or not "both" under project `type` should be classified as "lab" or "industry" or dropped entirely
  * Determine whether or not "unsure" under `research` background should be classified as "yes" or "no" or dropped entirely
* Limitations:

  * The decisions to drop "unsure" under `research` will bias results slightly. There are only a few students who selected these options, so bias will not be extreme. 
  * There may not be a correlation given how majority of students overall will select industry. But this is a conclusion to report on and may have some interesting analysis; students may be preferring industry due to dislike of research lab or can be explained by outside factors like state of economy.

