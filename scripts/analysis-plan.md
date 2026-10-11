1. (Modeling) Do students’ domains correlate with students’ preferences in the area of interest?
* Variables, Files, and Respondents:
* Data Preparation:
* Summaries or Plots:
* Key Choices to Check:
* Limitations:

&#x20;



2\. (Modeling) Does programming language correlate with students’ interest in statistical inference?

* Variables, Files, and Respondents:
* Data Preparation:
* Summaries or Plots:
* Key Choices to Check:
* Limitations:



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

