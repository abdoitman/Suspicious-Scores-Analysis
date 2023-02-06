![sus](https://user-images.githubusercontent.com/77892920/216881662-2b781cd0-2e79-48a7-a45e-dfe4b7b17ff5.png)<br>
<p align=center>Analyzing suspicious scores including midterm scores and year work scores for a whole class, trying to identify patterns and figuring out how these scores were evaluated.<br>

## Table of Contents:
* __[Context](#context)__
* __[Objective](#objective)__
* __[About The Dataset](#about-the-dataset)__
* __[Analysing Class Data](#analysing-class-data)__
  - __[Midterm Scores](#midterm-scores)__
  - __[Year Work Scores](#year-work-scores)__
  - __[Added Bonus](#added-bonus)__
  - __[Final Year Work Scores](#final-year-work-scores)__
* __[Conclusion](#conclusion)__

## Context
  To better understand where the data came from, the context must be explained. Year work scores have a total of 40 marks, 30 of which are the midterm score and the rest are evaluated based on student's work over the semester. In this case, midterm scores were revealed to the class (out of 30). After that, year work scores were revealed (out of 40) with some nonsensical results. Lastly, bonus marks were added to the class to compensate for the error.
  
## Objective
  The objective of this project is to get an idea of what might have hapened during the evaluation of the total year work score, how it affected the class and figuring out if the added bonus actually made up for the error.
  
## About The Dataset
  The dataset was originally collected from real college students data in text form, later it was cleaned and transformed into **3 excel workbooks** with **231** enteries:
  1. [Students List](../main/Students_list.xlsx) which contains the **ID**, **Name** and **Gender** of each student in the class.
  2. [Midterm Scores](../main/Midterm_scores.xlsx) which contains the following:
      * `ID`: ID of each student in the class.
      * `MID`: Midterm score.
  3. [Year Work Scores](../main/YearWork.xlsx) which contains the following columns:
      * `ID`: ID of each student.
      * `TOT`: Year work score (*before* the added bonus).
      * `NEW_TOT`: Year work score (*after* the added bonus).
  
  Other attributes are generated from the data in the project, which are:<br>
  * `diff`: The difference between __year work__ scores (_before_ adding the bonus) and __midterm__ scores.<br>
  * `bonus`: The added bonus.<br>
  * `yw_diff`: The difference between __total year work__ scores (_after_ adding the bonus) and __midterm__ scores.
  
## Analysing Class Data
  The project with made with Python 3.9 on jupyter notebook. 
  
### Midterm Scores
### Year Work Scores
### Added Bonus
### Final Year Work Scores
  
## Conclusion
