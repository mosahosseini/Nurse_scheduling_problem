### Project Title: Nurse Scheduling Problem

This project solves the Nurse Scheduling Problem using **Google OR-Tools** (a constraint programming solver). The aim is to assign nurses to shifts over a 30-day period, ensuring that constraints are met, such as shift coverage, maximum and minimum shifts per nurse, and balancing shifts across nurses.

### Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Input Parameters](#input-parameters)
- [Output](#output)
- [License](#license)

---

### Installation

To run the project, you need to have Python installed along with the required libraries. The main library used for solving the scheduling problem is `ortools`.

use google colab to run the code , jupyter kernel chashed when jupyter notebook is used.


You can install the required libraries by running:

```bash
!pip install ortools pandas
```

### Usage

The main scheduling function is provided in the `main()` function. To execute the scheduling process, simply run the notebook or script. Here's an overview of what happens:

1. The model is built using Google OR-Tools.
2. Nurses are assigned shifts across a 30-day period, considering constraints.
3. The results (nurse schedule) are displayed and saved to a CSV file.

```python
if __name__ == "__main__":
    main()
```

### Features

- **Shift Assignment**: Assigns nurses to two shifts (Morning & Evening) per day over 30 days.
- **Constraints**:
  - Shift requirements for weekdays and weekends.
  - Each nurse works only one shift per day.
  - If a nurse works an evening shift , he/she can not work a day shift the day after 
  - Each nurse should work every other weekend.
  - Minimum and maximum number of shifts per nurse per month.
  - 1 nurse works only day shifts and 2 nurse works only evening shifts. 
- **Optimization**: Balances nurse workloads and ensures that the required number of nurses are assigned to each shift.

### Input Parameters

- **Number of nurses**: `num_nurses = 16`
- **Number of days**: `num_days = 30`
- **Number of shifts per day**: `num_shifts = 2` (Morning, Evening)
- **Weekends**: Saturdays and Sundays are specified as weekends.

#### Shift Requirements:
- Weekdays:
  - Morning shift: 6 nurses
  - Evening shift: 4 nurses
- Weekends:
  - Morning shift: 4 nurses
  - Evening shift: 4 nurses

#### Constraints:
- **Maximum shifts per nurse per month**: 20
- **Minimum shifts per nurse per month**: 17

### Output

The schedule is generated and saved as a CSV file named `nurse_schedule.csv`. This CSV contains the daily assignment of each nurse to either a morning, evening shift, or a day off.

- `M` stands for Morning shift.
- `E` stands for Evening shift.
- `-` stands for a day off.

Additionally, the solving process provides:
- Total time taken to solve the problem.
- Number of branches explored and conflicts encountered during optimization.

### Example Output

An example output for the schedule might look like:

| Nurse     | Day 1 | Day 2 | ... | Day 30 |
|-----------|-------|-------|-----|--------|
| Nurse 1   | M     | M     | ... | E      |
| Nurse 2   | -     | E     | ... | -      |
| ...       | ...   | ...   | ... | ...    |

### License

This project uses Google OR-Tools and is available for non-commercial use. 
