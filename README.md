# Banking Risk Analytics Dashboard

## Project Overview

This project focuses on developing a Power BI dashboard for banking risk analytics. The objective is to help banks make informed decisions regarding loan approvals by assessing an applicant's likelihood of repaying the loan based on their profile.

The dashboard includes key performance indicators (KPIs) that evaluate customer behavior, banking relationship, loan performance, and more, ultimately helping to minimize the risk of financial loss while lending to customers.

## Data Cleaning and Transformation

Several new columns and calculated fields have been added to enhance the analysis:

1. **Engagement Timeframe**: A column indicating the timeline of a client's engagement with the bank.
2. **Engagement Days**: A column showing the number of days a client has spent at the bank since joining.
3. **Income Band**: A categorization of income into "Low" (<100,000) and "Mid" (<300,000) bands.
4. **Processing Fees**: A new column that calculates the processing fee based on the fee structure.

## Calculated Functions

Here are some key calculated fields used in the project:

- **SUM**: Adds all the numbers in a column.
    ```DAX
    Bank Deposit = SUM('Clients - Banking'[Bank Deposits])
    ```
- **DISTINCTCOUNT**: Counts the number of distinct values in a column.
    ```DAX
    Total Clients = DISTINCTCOUNT('Clients - Banking'[Client ID])
    ```
- **SUMX**: Returns the sum of an expression evaluated for each row in a table.
    ```DAX
    Total Fees = SUMX('Clients - Banking', [Total Loan] * 'Clients - Banking'[Processing Fees])
    ```
- **SWITCH**: Evaluates an expression against a list of values and returns the corresponding result.
  
- **DATEDIFF**: Returns the number of interval boundaries between two dates.
    ```DAX
    Engagement Days = DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)
    ```

## Key Performance Indicators (KPIs)

The following KPIs are calculated and displayed on the dashboard:

- **Total Clients**: Displays the total number of clients.
- **Total Loan**: Represents the sum of all loans, including bank loans, business lending, and credit card balances.
- **Bank Loan**: Shows the loan amount that needs to be repaid by clients to the bank.
- **Business Lending**: Displays the loan amounts given to small businesses.
- **Total Deposit**: Shows the total deposits made by clients.
- **Total Fees**: Displays the total fees charged by the bank.
- **Credit Cards Balance**: Represents the balance owed on credit cards.

## Conclusion

With the use of advanced data visualization techniques in Power BI, this dashboard helps the banking sector assess risk and make informed decisions. It provides a comprehensive analysis of customer profiles, loan amounts, deposit behavior, and client demographics.
