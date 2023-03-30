# Intelligent-EOD-Stock-Financial-News-API
An Intelligent EOD Stock &amp; Financial News, and Social Media Stock Sentiment Analysis API


#### Documentation

    Welcome to our *Stock Market &amp; Financial News API* documentation. 

**Stock Marketing & Financial News API**,

    provides end-of-day stock information for multiple exchanges around the world. 
    With this API, you can retrieve data for a specific stock at a given date, or for a range of dates. and also get access
    to companies fundamental data, financial statements, social media trending stocks by sentiment, and also the ability to create a summary of the Financial 
    News Related to a certain stock or company and its sentiment.



**Endpoints**
#### Obtain EOD Data for all Stocks in One Exchange at a Given Date
    Endpoint:
    /api/v1/eod/{_date}/{exchange_code}
    
    Method: GET 
    Description:
        This endpoint will return end of day (EOD) data for all stocks in an exchange at a given date. 
        The end of day data provides information about the performance of a stock at the close of a trading day.
    
    Path Parameters: 
        _exchange_code (string, required):_ This parameter represents the exchange code of the stock for which you want to retrieve the end of day data. 
        __date (string, required):_ This parameter represents the date for which you want to retrieve the end of day data.
    
    Responses: 
    200 (default): On success, 
        the response will include a JSON object that conforms to the "EODStockResponse" schema.

    Example Request: 
        GET /api/v1/eod/2022-12-31/AAPL

----------------------------------------------------------------------------------------------------------------------------------------

##### Obtain EOD Data for a Specific Stock on a certain Date
    Endpoint:  
        /api/v1/eod/{_date}/{exchange_code}.{stock_code}
    
    Method: GET 
        Description:
            This endpoint will return end of day (EOD) data for a certain stock at a given date. The end of day data provides information about the performance of a stock at the close of a trading day.
    
    Path Parameters: 
        exchange_code (string, required): This parameter represents the exchange code of the stock for which you want to retrieve the end of day data. 
        _date (string, required): This parameter represents the date for which you want to retrieve the end of day data. 
        stock_code (string, required): This parameter represents the code for the specific stock for which you want to retrieve the end of day data.
    
    Responses: 
        200 (default): On success, the response will include a JSON object that conforms to the "EODStockResponse" schema.

    Example Request: 
        GET /api/v1/eod/2022-12-31/AAPL.MSFT

----------------------------------------------------------------------------------------------------------------------------------------
#### Obtain EOD Data for a certain date range from one exchange
    Endpoint:
        /api/v1/eod/{_from}.{_to}/{exchange_code}
    
    _Method: GET_
    
    Description: 
        This endpoint returns a list of end of day (EOD) historical data for a specific stock on a specific exchange code between two dates. The end of day data provides information about the performance of a stock at the close of a trading day.
    
    Path Parameters: 
        exchange_code (string, required): This parameter represents the exchange code of the stock for which you want to retrieve the end of day data. 
        _from (string, required): This parameter represents the start date for which you want to retrieve the end of day data. 
        _to (string, required): This parameter represents the end date for which you want to retrieve the end of day data.
    
    Responses: 
        200 (default): On success, the response will include a JSON object that conforms to the "EODStockListResponse" schema.
    
    Example Request: 
        /api/v1/eod/2022-01-01.2022-12-31/US

----------------------------------------------------------------------------------------------------------------------------------------
#### Obtain EOD Data for a Stock between Two Dates
    Endpoint:
        /api/v1/eod/{_from}.{_to}/{stock_code}
    
    HTTP Method: GET
    
    Description: 
        This endpoint returns end of day data for a certain stock between two dates.
    
    Path Parameters: 
        stock_code: A required string that specifies the code of the stock to retrieve data for. 
        _to: A required string that specifies the end date in the format "YYYY-MM-DD" of the date range to retrieve data for. 
        _from: A required string that specifies the start date in the format "YYYY-MM-DD" of the date range to retrieve data for.
    
    Responses: 
        _Default (200 OK)_ 
        The API returns a JSON object containing the end of day data for the specified stock between the two dates. 
        The data will be returned in the format described by the EODStockResponse definition in the API schema.
    Example Request: 
        /api/v1/eod/2022-01-01.2022-12-31/AAPL

----------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------
#### Given Exchange Code Obtain Exchange Data
    Endpoint
    
        /api/v1/exchange/code/{exchange_code}
    
    HTTP Method: GET
    
    Description:
    
        This endpoint returns exchange data, given an exchange_code.  
        The exchange_code is passed as a path parameter in the URL.
    
    
    Parameters
    
       exchange_code (string, required): The exchange_code parameter is a required string that specifies the exchange code 
        for which you want to retrieve data.
    
    Responses
        This endpoint returns a JSON object containing the details of the exchange 
    
    
    Example Request: 
        /api/v1/exchange/code/us

----------------------------------------------------------------------------------------------------------------------------------------
#### Given an Exchange ID Obtain Exchange Data
    Endpoint
        /api/v1/exchange/id/{exchange_id}
    
    HTTP Method: GET
    
    Description:
    
        This endpoint returns exchange data, given an exchange_code.  
        The exchange_code is passed as a path parameter in the URL.
    
    
    Parameters
    
       exchange_code (string, required): The exchange_code parameter is a required string that specifies the exchange code 
        for which you want to retrieve data.
    
    Responses
        This endpoint returns a JSON object containing the details of the exchange 

    Example Request: 
        /api/v1/exchange/id/RP5zfbmYel63f0Wc

    ExchangeResponse Structure:
        {
               "message": "Exchange successfully fetched",
               "payload": {
                        "code": "BA",
                        "country": "Argentina",
                        "currency_symbol": "ARS",
                        "exchange_id": "RP5zfbmYel63f0Wc",
                        "name": "Buenos Aires Exchange",
                        "operating_mic": "XBUE"
                    },
               "status": true
        }


