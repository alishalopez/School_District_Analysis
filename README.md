# School District Analysis
## Overview of Project
The analysis was done to break down data and get full insight to test scores, look into their size and funding as a whole across the school district. We are able to see each school’s performance by categorizing them by their spending per student.
The requested deliverables of this analysis by the school board are listed below:
* A high-level snapshot of the district’s key metrics
* An overview of the key metrics for each school
* Tables presenting each of the following metrics
  * Top 5 and bottom 5 performing schools, based on the overall passing rate
  * The average math score received by students in each grade level at each school
  * The average reading score received by students in each grade level at each school
  * School performance based on the budget per student
  * School performance based on the school size 
  * School performance based on the type of school


## Results
This analysis was done twice due to academic dishonesty by ninth grade students at Thomas High School. For a more accurate set of data, we decided to omit their test scores as it could obscur the results. We replaced their scores with NaN. 

```Python
student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th"), "reading_score"] = np.nan
```
```Python
student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th"), "math_score"] = np.nan
```
**District Summary**
* The number of students' data included in this analysis went from 39,170 to 38,709. With that drop, each test score accounted for has a greater effect than before as there is less to review. Luckily there was only a marginal effect.
* Students passing math only reduced from 75% to 74.8% and students passing reading reduced from 85.8% to 85.7%.
* The overall passing % for the school district fell to 64.9%.

**School Summary**
* The removal of the 9th graders test scores from Thomas High School did not change school rankings as they are still the 2nd best performing school.
* Passing percentages decreased in all categories for Thomas High School.

**Math and Reading Scores by Grade**
* Thomas High School still scored well in their other grade level compared to the other schools, but their 9th grade scores show NaN. Other schools were unaffected with this 

![Math Scores](https://github.com/alishalopez/School_District_Analysis/blob/664458e6b7fd6d9fd7a0026c66f9a5a18ddf01e9/resources/THS_math_scores.png)

![Reading Scores](https://github.com/alishalopez/School_District_Analysis/blob/664458e6b7fd6d9fd7a0026c66f9a5a18ddf01e9/resources/THS_reading_scores.png)

Looking at the budgets,sizes, and types of schools, we were able to conclude relations between them and test scores.

**School Budgets & Spending**

* Test scores and average passing percentages were not higher in schools that received more funding per student. In fact, Cabera High School received less money per student and scored better than the lowest performing school.
* The data proves true even with omittion of students from the %630-$644 range.

![Spending](https://github.com/alishalopez/School_District_Analysis/blob/b0827a0594eedcebcb3ab2a7c2132777bd586024/resources/Spending_Ranges.png)

**School Size**

* “Large” schools in this school district did noticeably worse than “Small” and “Medium” schools. This may imply that students do better in a smaller setting as they are able to get more attention and focus on their work. 
* There was not a noticeable difference after removing the 9th graders from Thomas High School when it came to looking at the size of schools and their scores and percentages

**Types of Schools**

* As for types of schools, we have Charter or District schools. We recognized that Charter schools did significantly better as they had a 36% higher passing rate compared to District Schools. Charter schools are typically smaller in comparison and may play a role in test scores. 
* This data would have stayed true without the removal of the data

![Types](https://github.com/alishalopez/School_District_Analysis/blob/19c864359df8ae0aa1affa5a8975bf05a03e0b7f/resources/Types.png)

## Summary

To the normal eye there may not have been a huge difference if we would have left the data untouched, but for others where this pertains to their job and affects them personal, it was important to reanalyze. We noticed that the district saw a lower average math and reading score after this reanalysis, as well as their overall passing percentage. Thomas High School had their averages decrease and overall passing percentage fall also. Other schools' individual data was unchanged as their count and scores were not affected. Size, type and the budget of school performance were decreased during this analysis, but only slightly.

In any analysis, we would like a complete set of data in order to obtain the most accurate results. Due to the academic dishonesty, it is impossible to know exactly where the test results were obscured leading us to throw out all of the 9th graders at Thomas High School as a result. When analysing data, decisions must be made to keep accuracy and make the most sense on a case by case basis.
