# Grading Report

**Final Grade: 7.30/10.00**

## Rubric

| Criterion | Points |
|-----------|--------|
| `extract_data` correctly slices, title-cases names, int conversion, extracts grades, and leaves input untouched | **2.5** |
| `curve_grades` applies the curve (while loop) and caps values at 100 | **1.5** |
| `print_top_performers` prints only qualifying `Name: Score` lines (>= 95) | **2.5** |
| Code quality (required loop choices, clear logic) | **0.7** |

## General Comments

Primary bug: extract_data appends name and grade outside the loop so only the last record is captured—move s_names.append(name) and s_grades.append(grade) inside the for loop and ensure grade is converted to int. Also fix curve_grades to use a proper while i < len(grades) loop with i increment and clamping, and have print_top_performers print names[i] and grades[i] for qualifying students.

## Functionality

- tests/test_grader.py::RosterHelperTests::test_curve_grades_values_and_clamping: Failed (0.0 points)
   Error:     AssertionError: None != [100, 100, 53]

- tests/test_grader.py::RosterHelperTests::test_extract_data_parses_names_and_grades_title_case: Failed (0.0 points)
   Error:     AssertionError: Lists differ: ['Priya Singh'] != ['Ana Lopez', 'Priya Singh']

- tests/test_grader.py::RosterHelperTests::test_extract_data_returns_new_lists: Passed (10.0 points)

- tests/test_grader.py::RosterHelperTests::test_print_top_performers_prints_name_and_score_for_ge_95: Failed (0.0 points)
   Error:     AssertionError: Lists differ: ["['Anna', 'Ben', 'Cara', 'Doug', 'Elle']:[85 chars]92]"] != ['Ben: 95', 'Doug: 100']



