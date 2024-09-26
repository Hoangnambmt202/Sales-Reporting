# Sales_Reporting

Youtube Tutorial: https://youtu.be/VH2JgqlN2so

Conduct a Report and Analysis on 200,000 sales data points to answer revenue-related questions for the business

## installation instructions
Firstly, you must install the library pandas and matplotlib

Install pandas here: https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html 

- Miniconda: conda create -c conda-forge -n name_of_my_env python pandas
- pip: pip install pandas
  
Install matplotlib here: https://matplotlib.org/stable/install/index.html

- conda: conda install matplotlib
- pip: python -m pip install -U pip
       python -m pip install -U matplotlib
-------------------------------------------------
#  ERROR AND FIX

** Task 2.1 Merge 12-month data? **
* ValueError: shape mismatch: objects cannot be broadcast to a single shape.  Mismatch is between arg 0 with shape (12,) and arg 1 with shape (2,).

> fix: see more in image3.png

** Task 3.5 What product sold the most? Why do you think it sold the most? **
* TypeError: datetime64 type does not support sum operations

line: 

`
all_products = df.groupby('Product').sum()['Quantity Ordered']
all_products
`

 > fix: add parameters 'numeric_only=True'

`
    => all_products = df.groupby('Product').sum(numeric_only=True)['Quantity Ordered']
        all_products 
`

* TypeError: agg function failed [how->mean,dtype->object]

`
    prices = df.groupby('Product').mean()['Price Each']
    prices 
`
> fix: add parameters for pandas.DataFrame.mean() column = '4'

=> read more here: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.mean.html


`
    => prices = df.groupby('Product').mean(4)['Price Each']
        prices
`

