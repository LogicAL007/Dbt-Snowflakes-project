# Advanced RFM Analysis with DBT and Snowflake

This project dives into the advanced usage of dbt (data build tool) and Snowflake, a cloud data platform, to perform Recency, Frequency, Monetary (RFM) analysis on e-commerce data. By leveraging Snowpark, Snowflake's powerful library for data operations, we aim to enhance the capabilities of our data transformation processes.

## Features

- **RFM Analysis with DBT**: A comprehensive model in dbt to transform data for RFM analysis.
- **Snowflake and Snowpark Integration**: A deep dive into Snowflake's Snowpark library, integrating its functionality into our dbt models.
- **Data Management with SnowSQL**: Step-by-step data ingestion procedure in Snowflake using SnowSQL commands

## Getting Started

### Prerequisites

- **DBT**: A command-line tool that enables data analysts and engineers to transform data in the warehouse more effectively.
  - Installation: Follow the [official guide](https://docs.getdbt.com/docs/introduction) for installation instructions.
  
- **Snowflake Account**: Ensure you have an active account and the necessary permissions on Snowflake.
  - Sign up: Visit [Snowflake's official website](https://www.snowflake.com/).

- **SnowSQL**: Snowflake's command-line client.
  - Installation: Visit [SnowSQL's official documentation](https://docs.snowflake.com/en/user-guide/snowsql-install-config.html) for installation steps.

### Configuration & Deployment

1. **Repository Setup**:
   ```bash
   git clone [URL_OF_YOUR_GITHUB_REPOSITORY] dbt_snowflake_project
   cd dbt_snowflake_project
   ```

2. **Snowflake Connection**:
   - Set up your Snowflake connection credentials for dbt in `~/.dbt/profiles.yml`.
   - Ensure the necessary permissions for data access.

3. **Data Loading using SnowSQL**:
   - Navigate to the directory containing the Snowflake script:
     ```bash
     snowsql -f snowflake_scripts/data_upload.sql
     ```
   - This script handles various Snowflake operations, such as setting up the working environment, staging CSV data, loading it to tables, and performing clean-up operations.

4. **DBT Model Execution**:
   ```bash
   dbt run --models rfm_analysis
   ```

## Deeper Dive

- **RFM Analysis**:
  - Our dbt model extracts insights from the `invoices` and `items` tables.
  - The aim is to evaluate customers' value using the RFM methodology, which considers how recently a customer has purchased (Recency), how often they purchase (Frequency), and how much the customer spends (Monetary).

- **Snowflake Script Operations**:
  - Login and environment setup within Snowflake.
  - Data staging and ingestion from `upload.csv`.
  - Verification of data population within Snowflake tables.

## Additional Documentation

- **RFM Explanation**: Understand the intricacies of RFM analysis with our detailed document found at `documentation/rfm_explanation.md`.
  
- **Snowpark Guide**: Explore the capabilities of Snowflake's Snowpark and its usage in our models. See `documentation/snowpark_guide.md`.

## Contributing

For those interested in enhancing the capabilities of this project, you're welcome to propose changes! Start by forking this repository, make your proposed modifications, and then open a pull request.

## Feedback and Support

Found a bug or have a suggestion? Open an issue in this repository, and we'll address it promptly.

## Licensing

This project abides by the [MIT License](LICENSE).

---

Remember to adjust placeholders like `[URL_OF_YOUR_GITHUB_REPOSITORY]` and add actual links to documents like `documentation/rfm_explanation.md` if they exist.
