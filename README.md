#### NOTE: In order to access economic data, please use my personal API key provided in the second jupyter notebook cell along with import statements.
#### fredAPIKey = 'f9ac6d2c51f5d5aeea0b07652fd8a52f'


## Requirements:

The following Python libraries are used:

- `pandas`
- `yfinance`
- `pandas_ta`
- `matplotlib`
- `scikit-learn`
- `sqlite3` 
- `requests`
- `os` 
- `datetime`

## Setup Instructions:
1. **Clone the repository:** <br>
  ##### `git clone <repository-url>`
2. **Navigate to the project folder:** <br>
  ##### `cd <project-folder-name>`
3. **Run the notebook:** <br>
  ##### `jupyter notebook <project-name>.ipynb`
4. **Follow the notebook and execute each cell sequentially to run the project.**

### Setup Instructions Using `requirements.txt`

1. **Create a Virtual Environment:**


   `python -m venv project-env`
   

3. **Activate the Virtual Environment:**
    ##### On Linux or Mac:

   `source project-env/bin/activate`


   ##### On Windows:

   `project-env\Scripts\activate`

4. **Install Dependencies:**


   `pip install -r requirements.txt`

6. **Run Jupyter Notebook**

7. **Select the Correct Kernel:**
    In the Jupyter interface, select the correct kernel 'Python (project-env)' from the Kernel menu.

## Key Functions and Example Usage
`resetDatabase('stonks.db')` : Wipes the database clean. <br><br>
`createDatabase('stonks.db')` : Creates a new database. <br><br>
`processStockData('PLTR', 'stonks.db')`: Fetch, clean, calculate technical indicators, and store stock data of a specified symbol in the database all in one function. <br><br>
`economicData = fetchEconomicData(fredAPIKey)`: Fetch economic data and create a dataframe with it to be added to the database. <br><br>
`storeEconomicData(economicData, 'stonks.db')`: Stores economic data in the database. <br><br>
`validateStockData('PLTR', 'stonks.db')`: Check if the stock and economic data are stored correctly in the database. <br><br>
`model, mse, mae, r2, future_price = predictStockPrice('PLTR', 31, 'stonks.db')`: Prepares data obtained from SQL queries to train the Random Forest learning model and predicts the stock price for a given symbol and number of days into the future. <br><br>
`plotStockData('PLTR', 'stonks.db', days=365)`: Plot stock price, EMA lines, MACD, Signal Line, and RSI for the stock. Specify a days parameter to limit the graph to recent data, otherwise all historical data will be charted by default. <br>
