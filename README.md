
Problem Description  
There are three physiological cycles in life, namely physical, emotional and intellectual cycles. Their cycle length is 23 days.
28 days and 33 days. One day in each cycle is the peak. On the peak day, people will perform well in the corresponding aspects. For example, at the peak of the intellectual cycle, people will be quick-thinking and their energy will be highly concentrated. Because the perimeters of the three cycles are different, usually the peaks of the three cycles do not fall on the same day. For everyone, we want to know when the three peaks fall on the same day. For each cycle, we will give the number of days from the first day of the current year to the peak (not necessarily the time of the first peak). Your task is to give a number of days from the first day of the year, output the time from the given time (not including the given time), the next three peaks on the same day (the number of days from a given time). For example, if the given time is 10, the next time there are three peaks on the same day is 12, then output 2 (note that this is not 3).
Input data
Enter four integers: p, e, i, and d. p, e, i represent the time at which physical, emotional, and intellectual peaks occur (time)
Calculated from the first day of the year). d is the given time and may be less than p, e, or i. All given times are non-negative and less than 365, and the time sought is less than or equal to 21252.
Output requirements
The time from the given time, the next three peaks on the same day (the number of days from a given time).  
  
Input sample
0 0 0 0  
0 0 0 100  
5 20 34 325  
4 5 6 7  
283 102 23 320  
203 301 203 40  
-1 -1 -1 -1  
  
Output sample  
Case 1: the next triple peak occurs in 21252 days.  
Case 2: the next triple peak occurs in 21152 days.  
Case 3: the next triple peak occurs in 19575 days.  
Case 4: the next triple peak occurs in 16994 days.  
Case 5: the next triple peak occurs in 8910 days.  
Case 6: the next triple peak occurs in 10789 days.  
  
Problem solving  
  
Assume that starting from the first day of the year, three peaks appear simultaneously on day x. The x that meets the problem requirements must be greater than d, less than or equal to 21252, and meet the following three conditions:
  
1) (x-p) % 23 = 0  
2) (x-e) % 28 = 0  
3) (x-i) % 33 = 0  
In the search space [d+1, 21252], three conditions are judged for each guessed answer, which is expensive and unnecessary. First, find all the time that meets the condition 1) from the search space [d+1, 21252], and then find the time that meets the conditions 2) and 3) from these times, and the number of judgments for the conditions 2) and 3) can be reduced. For the original 1/23. In the same way, it is possible to continue to reduce the number of determinations for condition 3).
For each set of data, the following algorithms are executed separately:  
1) Read p, e, i, d  
2) From d+1 loop to 21252, find the first time that satisfies condition 1) a, and jump out of the loop  
3) From a loop to 21252, find the first time that satisfies condition 2) b, and jump out of the loop  
4) From b to 21252, find the first time x that satisfies condition 3) and jump out of the loop  
5) Output x-d  
