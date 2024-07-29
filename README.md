# Comprehensive Bank Loan Dashboard
## Overview
The Comprehensive Bank Loan Dashboard project leverages Power BI to analyze and visualize data from over 38,000 loan applications. It tracks key metrics like 5,000+ Month-to-Date Loan Applications, $120M+ Total Funded Amount, and $90M+ Total Amount Received with detailed Month-over-Month analysis.

Features include risk assessment with KPIs for loan quality, advanced visualizations (line charts, bar charts, etc.), and analysis of employment length on 10,000+ applications. Utilizing over 15 DAX calculations and 10 date functions, the dashboard supports dynamic, interactive exploration to aid decision-making and operational efficiency.

## First Dashboard
![](/Dashboard/dashboard.png/dashboard_1.png)
## Second Dashboard
![](/Dashboard/dashboard.png/dashboard_2.png)
## Third Dashboard
![](/Dashboard/dashboard.png/dashboard_3.png)


## Project Scope

The project aims to offer an in-depth analysis of loan data, focusing on key metrics such as application volumes, funding amounts, repayment statistics, and risk assessment. The dashboard is intended to enhance understanding of loan performance, financial health, and risk factors, supporting informed decision-making.

## Features

1. **Comprehensive Loan Analytics:**  Analyzed **38,000+ loan applications** to provide a broad overview of the loan landscape.

2. **Financial Metrics Monitoring:** Tracked significant financial metrics, including **5,000+ Month-to-Date (MTD) Loan Applications**, **$120M+ Total Funded Amount**, and **$90M+ Total Amount Received**, with detailed **Month-over-Month (MoM) analysis**.

3. **Risk Assessment:** Implemented KPIs to evaluate loan quality, distinguishing between Good and Bad Loans. Key indicators include **Good Loan Application Percentage (70%)** and **Bad Loan Funded Amount ($30M)**.

4. **Advanced Visualizations:** Created **7 types of visualizations** such as line charts, donut charts, bar charts, tree maps, shape maps, cards, and tables to highlight trends and insights across various dimensions of loan data, including **regional disparities across 50 states** and **loan purpose breakdowns into 10 categories**.

5. **Advanced Power BI Functionalities:** Utilized over **15 DAX calculations**, **10 date functions**, and **5 KPI indicators**. Added **navigation buttons** to facilitate seamless transitions across **3 dashboard sheets**.

## DAX Code Examples
### Total Funded Amount

```dax
Total Funded Amount = 
SUM(LoanApplications[FundedAmount])
```

###  Good Loan Application Percentage

```dax
Good Loan Application Percentage = 
DIVIDE(
    COUNTROWS(FILTER(LoanApplications, LoanApplications[Status] = "Good")),
    COUNTROWS(LoanApplications),
    0
)
```

###  Month-to-Date Loan Applications

```dax
MTD Loan Applications = 
CALCULATE(
    COUNTROWS(LoanApplications),
    DATESMTD(LoanApplications[ApplicationDate])
)
```

###  Month-over-Month Change in Funded Amount

```dax
MoM Funded Amount Change = 
VAR CurrentMonth = 
    CALCULATE(
        SUM(LoanApplications[FundedAmount]),
        DATESMTD(LoanApplications[ApplicationDate])
    )
VAR PreviousMonth = 
    CALCULATE(
        SUM(LoanApplications[FundedAmount]),
        DATEADD(DATESMTD(LoanApplications[ApplicationDate]), -1, MONTH)
    )
RETURN 
    DIVIDE(CurrentMonth - PreviousMonth, PreviousMonth, 0)
```

## File Contents

1. **`dashboard.pbix`**
   - **Description:** Power BI project file containing all data, visuals, and configurations.
   - **Usage:** Open this file in Microsoft Power BI Desktop to interactively explore and customize the data and visualizations.

2. **`dashboard.pdf`**
   - **Description:** A static report summarizing key findings and metrics from the dashboard.
   - **Usage:** Provides a quick overview for sharing or reference purposes.

3. **`dashboard.pptx`**
   - **Description:** PowerPoint presentation of the main insights and findings from the dashboard.
   - **Usage:** Useful for meetings and stakeholder presentations.

4. **`dashboard.png`**
   - **Description:** A high-resolution screenshots of the dashboard.
   - **Usage:** Ideal for including in reports, presentations, or sharing as a visual reference of the dashboard's layout and key features.


## Future Enhancements

- **Data Updates:** Regular updates to incorporate the latest data and metrics.
- **Additional Metrics:** Potential inclusion of more detailed metrics such as customer segmentation and predictive analysis for loan defaults.
- **User Contributions:** Users are encouraged to suggest improvements or contribute to the project.

## License

This project is licensed under the [MIT License](https://github.com/ThisIsTPM/Comprehensive-Bank-Loan-Dashboard?tab=MIT-1-ov-file). See the LICENSE file for details.

## Contact

For any questions or feedback, please contact [tanmayprasadmallick@gmail.com ](mailto:tanmayprasadmallick@gmail.com).
