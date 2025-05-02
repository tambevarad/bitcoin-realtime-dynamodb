# Real-Time Bitcoin Price Ingestion and Analysis with AWS DynamoDB

This project implements a real-time data ingestion and analysis pipeline for tracking Bitcoin (BTC) prices using the [CoinGecko API](https://www.coingecko.com/en/api), AWS DynamoDB, and AWS Lambda.

> 🔄 The system fetches BTC price every 60 seconds and logs it to DynamoDB. Lambda is triggered by DynamoDB Streams to log each insert in real-time. The data is analyzed using Python notebooks.

---

## 📦 Components

### `realtime_ingestor.py`
- Fetches Bitcoin price from CoinGecko
- Inserts price + timestamp into DynamoDB table `BitcoinPrices` every 60 seconds

### `template.API.ipynb`
- Demonstrates AWS SDK usage to:
  - List DynamoDB tables
  - Fetch real-time BTC price from the API
  - Insert the price into the table manually

### `template.example.ipynb`
- Loads data from DynamoDB into a Pandas DataFrame
- Converts timestamp into datetime
- Computes and plots:
  - BTC price trend
  - Moving averages

---

## 🧰 Technologies Used

- **Python 3.x**
- **Boto3** – AWS SDK for Python
- **AWS DynamoDB** – NoSQL storage
- **AWS Lambda** – Serverless processing (triggered by DynamoDB Streams)
- **CloudWatch Logs** – For logging Lambda executions
- **CoinGecko API** – Real-time BTC pricing data

---

## 📁 Folder Structure
# Tutorial Template: Two Docker Approaches

- This directory provides two versions of the same tutorial setup to help you
  work with Jupyter notebooks and Python scripts inside Docker environments

- Both versions run the same code but use different Docker approaches, with
  different level of complexity and maintainability

## 1. `data605_style` (Simple Docker Environment)

- This version is modeled after the setup used in DATA605 tutorials
- This template provides a ready-to-run environment, including scripts to build,
  run, and clean the Docker container.

- For your specific project, you should:
  - Modify the Dockerfile to add project-specific dependencies
  - Update bash/scripts accordingly
  - Expose additional ports if your project requires them

## 2. `causify_style` (Causify AI dev-system)

- This setup reflects the approach commonly used in Causify AI dev-system
- **Recommended** for students familiar with Docker or those wishing to explore a
  production-like setup
- Pros
  - Docker layer written in Python to make it easy to extend and test
  - Less redundant since code is factored out
  - Used for real-world development, production workflows
  - Used for all internships, RA / TA, full-time at UMD DATA605 / MSML610 /
    Causify 
- Cons
  - It is more complex to use and configure
  - More dependencies from the 
- For thin environment setup instructions, refer to:  
  [How to Set Up Development on Laptop](https://github.com/causify-ai/helpers/blob/master/docs/onboarding/intern.set_up_development_on_laptop.how_to_guide.md)

## Reference Tutorials

- The `tutorial_github` example has been implemented in both environments for you
  to refer to:
  - `tutorial_github_data605_style` uses the simpler DATA605 approach
  - `tutorial_github_causify_style` uses the more complex Causify approach

- Choose the approach that best fits your comfort level and project needs. Both
  are valid depending on your use case.
