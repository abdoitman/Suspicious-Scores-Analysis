![sus](https://user-images.githubusercontent.com/77892920/216881662-2b781cd0-2e79-48a7-a45e-dfe4b7b17ff5.png)<br>
<p align=center>Analyzing suspicious scores including midterm scores and year work scores for a whole class, trying to identify patterns and figuring out how these scores were evaluated.<br>

## Table of Contents:
* __[Context](#context)__
* __[Objective](#objective)__
* __[About The Dataset](#about-the-dataset)__
* __[Analysing Class Data](#analysing-class-data)__
  - __[Midterm Scores](#midterm-scores)__
  - __[Year Work Scores](#year-work-scores)__
    + __[Midterm scores vs Year work scores](#midterm-scores-vs-year-work-scores)__
  - __[Difference Between Year Work Scores and Midterm Scores](#difference-between-year-work-scores-and-midterm-scores)__
    + __[Difference Between Year Work Scores and Midterm Scores vs Midterm Scores](#difference-between-year-work-scores-and-midterm-scores-vs-midterm-scores)__
  - __[Added Bonus](#added-bonus)__
    + __[Total Added Marks](#total-added-marks)__
  - __[Final Year Work Scores](#final-year-work-scores)__
* __[Conclusion](#conclusion)__

## Context
  To better understand where the data came from, the context must be explained. Year work scores have a total of 40 marks, 30 of which are the midterm score and the rest are evaluated based on student's work over the semester. In this case, midterm scores were revealed to the class (out of 30). After that, year work scores were revealed (out of 40) with some nonsensical results. Lastly, bonus marks were added to the class to compensate for the error.
  
## Objective
  The objective of this project is to get an idea of what might have hapened during the evaluation of the total year work score, how it affected the class and figuring out if the added bonus actually made up for the error.
  
## About The Dataset
  The dataset was originally collected from real college students data in text form, later it was cleaned and transformed into **3 excel workbooks** ,with **231** enteries, which are:
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
  The project with made with Python 3.9 on jupyter notebook. All the graphs were made using **matplotlib** and **seaborn** modules.
  
### Midterm Scores
  ![image](https://user-images.githubusercontent.com/77892920/217038430-f4bc32ab-9add-4a3d-af82-24d8c5114fef.png)
  
  * Minimum: **1**
  * Average score: **20.3**
  * Maximum: **27**
  * Most students got between **20** and **26**
### Year Work Scores
  ![image](https://user-images.githubusercontent.com/77892920/217044224-6d3f6a6a-8ae4-4a17-b3af-c023544d8581.png)
  <p align=center>We notice that the distribution of the year work scores does not follow or resemble the distribution of the midterm scores, a scaling of some sort must've been applied to the scores.
    
  * Minimum: **9**
  * Average score: **25.58**
  * Maximum: **40**
  * Most students got **20**
  #### Males vs Females
  ![image](https://user-images.githubusercontent.com/77892920/217054900-6aba4a4f-fc21-4a9c-b2f8-4bb38a215719.png)<br>
  <p align=center>Female students have a slightly higher average score than male students 
    
  #### Midterm scores vs Year work scores
  ![image](https://user-images.githubusercontent.com/77892920/217061966-7e960790-0912-41f6-b71d-0ecde724b078.png)
  Plotting the midterm score of each student with their year work score shows a **high density cluster** of students around **(20-25 MID, 20-30 Yearwork)**. It also shows that the data is quite *random* with a correlation coefficient of **0.177** which raises a red flag since high midterm scores should lead to high year work scores.
    
  ### Difference Between Year Work Scores and Midterm Scores
  ![image](https://user-images.githubusercontent.com/77892920/217064426-5cbaf8b1-ccbd-4a9d-bd0b-4b05b9ad2feb.png)
  <p align=center> Around 35% of the students got their midterm scores or less as their year work score.
    
  * Minimum: **-7**
  * Average score: **5.25**
  * Maximum: **25**
    
  #### Males vs Females
  ![image](https://user-images.githubusercontent.com/77892920/217066728-d8d522b3-dd84-4eb8-b755-58d9caa367df.png)
    
  #### Difference Between Year Work Scores and Midterm Scores vs Midterm Scores
  ![image](https://user-images.githubusercontent.com/77892920/217067470-211af4bb-f5c1-4b59-8389-bc519edb7043.png)
  We notice a higher inverse correlation (**-0.468**) between midterm scores & difference between year work scores and midterm scores. Which means people who got higher marks in midterms, are those who got less year work score than their midterm score.<br> A noticeable observation would be the student who got the highest midterm score (**27**) and has the lowest difference (**-7**) meaning he has a year work score of just **20** out of 40.


### Added Bonus
  Bonus marks were added differently for each student with the following frequency:
  ![image](https://user-images.githubusercontent.com/77892920/217127880-b939c81e-6cd3-4b22-86fe-7060fd627650.png)
  **One** bonus mark is the most frequently added bonus to the class. Only one student didn't have any bonus marks, also only 3 student got more than **10 bonus marks**.<br>
  * Minimum: **0**
  * Average added bonus: **5**
  * Maximum: **10**  
  
  #### Males vs Females
  ![image](https://user-images.githubusercontent.com/77892920/217128555-9b533ef6-b838-44c5-ac64-e3d8c90ca77c.png)
  
  #### Total Added Marks
  The difference between the final year work scores (after adding bonus) and the midterm scores has the following frequency:
  ![image](https://user-images.githubusercontent.com/77892920/217130215-ae0ba38e-c845-4994-bd51-63a1a138d377.png)
  * Minimum: **1**
  * Average added marks: **10.26**
  * Maximum: **26** 
    
  #### Males vs Females
  ![image](https://user-images.githubusercontent.com/77892920/217130577-90bfff9a-ded3-41bb-84d9-ebaf691d8301.png)
  <p align=center>Female students got a higher average added marks than the male students.
    
### Final Year Work Scores
  After we took a deeper dive into midterm scores and the added bonus, now we're interested in answering the following questions:
  * Did the addd bonus fix the distribution of year work scores? if so, how? [here.](#final-year-work)
  * Compared to the ideal situation **(each student having their year work score = their midterm score + 10)**, how did the bonus marks benifit students? [here.](#comparing-to-the-ideal-situation)
  * Given that they varied from one student to another, what criteria were the bonus marks based on?
    
  #### Final Year Work
  After adding bonus marks, the year work scores distribution becomes as follows:
  ![image](https://user-images.githubusercontent.com/77892920/217133404-9ff4f01b-a23e-4664-87a4-d0db8a5aab4b.png)
  <p align=center> Adding bonus marks obviously increased the mean score of the class. Also the distribution now resembles the distribution of the midterms scores more.<p>
  
  * Minimum: **14**
  * Average score: **30.58**
  * Maximum: **40**
  #### Males vs Females
  ![image](https://user-images.githubusercontent.com/77892920/217137012-3c8defa8-d092-4335-af46-972a160dedbc.png)
    
  #### Effect of adding bonus to the class
  To better understand how did the bonus affect the class, let's divide them into 4 sections based on their scores:
  ![Screenshot_20230206_043109](https://user-images.githubusercontent.com/77892920/217137766-9b28e4db-8a14-4143-870f-4e9ee27f7539.png)<br>
  <p align=center>Although the lowest 2 sections and the highest section changed drastically, most students still got between 20 and 30 before and after adding the bonus.
  
  #### Comparing To The Ideal Situation
  
## Conclusion
