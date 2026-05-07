# Week 9 Homework: The Case of the Missing Festival Lanterns

## Student Info

Name: Sushant Thapa Chhetri
Student number: 2412092
GitHub username: sushant913

---

## Summary

This program analyzes festival lantern records and checks whether all expected lanterns appeared in the festival log.  

The `analyze_lanterns` function receives three inputs:
- a set of expected lantern names,
- a list of lantern records containing the lantern name and actual section,
- and a dictionary showing the correct section for each lantern.

It processes the records to find:
- missing lanterns,
- unexpected lanterns,
- duplicate lanterns,
- and lanterns placed in the wrong section.

The function also counts how many lantern records appeared in each section.  

Finally, it returns all results inside a report dictionary for easy access and testing.

---

## Approach

- First, I created sets and dictionaries to store seen lanterns, duplicates, section counts, and wrong-section records.
- Then, I looped through every item in `lantern_log` one time.
- During the loop, I added lantern names to the seen set and checked whether they had already appeared.
- If a lantern appeared more than once, I added it to the duplicate set.
- I used a dictionary to count how many lanterns were recorded in each section.
- For expected lanterns only, I compared the actual section with the correct section.
- If the section was wrong, I saved the first wrong section found.
- After the loop, I used set subtraction to calculate missing lanterns and unexpected lanterns.
- Finally, I returned all results inside one dictionary.

---

## How I Used Dictionaries and Sets

### 1. Which parts of your solution used sets?

- `seen_lanterns` stores all lanterns found in the log.
- `seen_once` helps detect duplicates.
- `duplicate_lanterns` stores lanterns that appeared more than once.
- `missing_lanterns` and `unexpected_lanterns` were found using set operations.

### 2. Which parts of your solution used dictionaries?

- `count_by_section` stores how many lanterns appeared in each section.
- `wrong_section_lanterns` stores lanterns placed in the wrong section with expected and actual values.
- `correct_sections` gives the correct location for each expected lantern.

### 3. Why were dictionaries or sets better than using only lists?

Sets are faster for membership checking and automatically avoid duplicates.  

Dictionaries are useful because they connect keys to values, such as section names to counts or lantern names to their correct location.  

Using only lists would require extra loops and slower searching.

```text
Sets were used for unique lantern tracking and duplicate detection.
Dictionaries were used for counting and storing mapped information.
They are faster and cleaner than using only lists.