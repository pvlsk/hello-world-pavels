<h1>Day 1: January 5, 2018</h1>

**Today's Progress**: 
1. Solved <a href='https://www.hackerrank.com/challenges/interviews/problem'>Hackerrank's challenge "Interviews" (hard)</a>
2. Continue practising "SQL Cookbook" in Postgres. pages 109-112 (Working with strings)

**Thoughts:** Slightly struggled with joining nested queries

Here is MySQL solution to Hackerranks' "Interviews"

```sql
select c.contest_id, c.hacker_id, c.name, SUM(coalesce(total_submissions,0)), SUM(coalesce(total_accepted_submissions,0)), sum(coalesce(total_views,0)), sum(coalesce(total_unique_views,0)) 
from Contests c
join colleges col on c.contest_id = col.contest_id
join challenges ch on col.college_id = ch.college_id

left join (SELECT challenge_id, sum(total_submissions) as total_submissions, sum(total_accepted_submissions) as total_accepted_submissions from submission_stats group by 1) s on ch.challenge_id = s.challenge_id
left join (SELECT challenge_id, sum(total_views) as total_views, sum(total_unique_views) as total_unique_views from view_stats group by 1) v on ch.challenge_id = v.challenge_id

group by 1,2,3
having (sum(coalesce(total_views,0)) + sum(coalesce(total_unique_views,0)) + SUM(coalesce(total_submissions,0)) + SUM(coalesce(total_accepted_submissions,0))) <> 0
order by 1

```
<h1>Day 2: January 6, 2018</h1>
**Today's Progress**: 
Wrestled with  <a href='https://www.hackerrank.com/challenges/15-days-of-learning-sql'>15 Days of Learning SQL" (hard)</a>
**Thoughts:** Found it too challenging

<h1>Day 3: January 7, 2018</h1>
**Today's Progress**: 
1. Continued to wrestle with  <a href='https://www.hackerrank.com/challenges/15-days-of-learning-sql'>15 Days of Learning SQL" (hard)</a>
2. Completed SQL Cookbooks 6.8: Ordering by parts of a string

**Thoughts:** 
Found it challenging to create multi layer of derived tables in Hackerrank. 
I need more practice with Replace and Translate functions. Very cool when you do it one step at the time starting with deepest inner functions.




