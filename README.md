# Workforce Allocation and Utilization Analysis

This project focuses on analyzing workforce allocation and utilization using the concept of Full-Time Equivalents (FTEs). It integrates data from multiple sources, optimizes bench utilization, monitors workloads, and provides actionable insights through Power BI dashboards and visualizations.

## Features

### 1. Custom Dataset Creation
- Designed and curated a tailored dataset for analyzing workforce allocation.
- Integrated data from various sources to ensure comprehensive insights into employee workload and availability.

### 2. Bench Utilization Optimization
- Identified employees not assigned to any projects ("on the bench").
- Developed Power BI dashboards to provide real-time visibility of bench resources to the sales team.
- Enabled the sales team to secure new projects and improve resource utilization.

### 3. Workload Monitoring and Balancing
- Analyzed employee allocation across multiple projects to detect potential overwork scenarios.
- Highlighted employees with excessive workloads to HR for timely recruitment.
- Ensured balanced workload distribution.

### 4. Data Visualization and Reporting
- Utilized Power BI to create interactive dashboards and visualizations.
- Designed intuitive reports for HR, sales, and management teams.

## Impact and Outcomes
- Improved resource utilization by reducing bench time.
- Optimized workload distribution.
- Empowered HR and sales teams with data-driven insights.
- Maintained employee productivity and satisfaction by addressing workload stress proactively.

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/workforce-allocation-analysis.git
   ```
2. Navigate to the project directory:
   ```bash
   cd workforce-allocation-analysis
   ```
3. Install the required Python libraries:
   ```bash
   pip install pandas openpyxl matplotlib
   ```

---

## Usage

### 1. Data Preparation
Ensure your dataset includes the following columns:
- Employee ID
- Project Name
- FTE Allocation
- Availability Status

### 2. Python Script for Analysis
Here's a sample Python script for analyzing workforce allocation:

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
data = pd.read_excel('workforce_data.xlsx')

# Identify bench employees
bench_employees = data[data['FTE Allocation'] == 0]
print("Bench Employees:")
print(bench_employees[['Employee ID', 'Availability Status']])

# Analyze workload distribution
workload_summary = data.groupby('Employee ID')['FTE Allocation'].sum().reset_index()
workload_summary.columns = ['Employee ID', 'Total FTE']

# Highlight overworked employees
overworked_employees = workload_summary[workload_summary['Total FTE'] > 1]
print("Overworked Employees:")
print(overworked_employees)

# Visualize workload distribution
plt.figure(figsize=(10, 6))
plt.bar(workload_summary['Employee ID'], workload_summary['Total FTE'], color='skyblue')
plt.axhline(y=1, color='r', linestyle='--', label='FTE Threshold')
plt.xlabel('Employee ID')
plt.ylabel('Total FTE Allocation')
plt.title('Workload Distribution')
plt.legend()
plt.show()
```

### 3. Power BI Dashboard
Use the prepared dataset (`workforce_data.xlsx`) to create:
- A bench utilization dashboard.
- Workload distribution charts.
- Interactive filters for HR and sales insights.

---

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a new branch for your feature/bug fix.
3. Commit your changes and push them to your branch.
4. Submit a pull request.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contact
For questions or feedback, please reach out to [Your Name](https://github.com/your-username).
