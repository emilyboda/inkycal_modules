# Inkycal Stocks Module
This is third-party module for the [Inkycal project](https://github.com/aceisace/Inky-Calendar)

<p align="center">
<img src="https://github.com/worstface/inkycal_stocks/blob/master/Gallery/inkycal_stocks.jpg" width="800">
</p>

The stocks-module conveniently displays a list of selected stocks, currencies or indices with their current prices and total/procentual daily change.
It depends on [yfinance](https://github.com/ranaroussi/yfinance) which uses the [Yahoo! Finance](https://finance.yahoo.com/) data. You can display any information by using the respective symbols that are used by [Yahoo! Finance](https://finance.yahoo.com/).
It's easily setup with a list of symbols like this e.g.: tickers = ["TSLA", "AMD", "NVDA", "^DJI", "BTC-USD", "EURUSD=X"]

# Installation instructions
How to install the module.

1) Navigate to the modules directory
`cd Inkycal/inkycal/modules`

2) Download the third-party module:
```bash
# The URL is the rawfile url. open inkycal_stocks.py, then click on [raw] to see the rawfile-url
wget https://raw.githubusercontent.com/worstface/inkycal_stocks/master/inkycal_stocks.py
```

3) Install yfinance:
```bash
pip3 install yfinance
```

4) Register this module in Inkycal
Manual steps for Inkycal 2.0.0:

```# 1) Inkycal/modules/__init__.py
# Add this into the modules init file:
# from .filename import Class
# where filename is the name of your module
# where Class is the name of your class e.g. Simple in this case


# 2) Inkycal/__init__.py
# Before the line # Main file, add this:
# import inkycal.modules.filename
# Where the filename is the name of your file inside the modules folder
```

```python3
# In python, type the following commands:
from inkycal import Inkycal
inkycal._add_module('/full/path/to/your/inkycal_stocks.py', 'Stocks')
# If everything went well, you should see a printed message without red lines
```

5) Add the following in your `settings.json` file, inside the `panels` section
```
{
            "position": 3,
            "name": "Stocks",
            "config": {
                "size": [
                    528,
                    326
                ],
                "tickers": ["TSLA", "U", "NVDA", "EURUSD=X"],
                "padding_x": 10,
                "padding_y": 10,
                "fontsize": 18,
                "language": "en"
            }
        },
```

# How to remove this module
```python3
# In python, run the following commands:
from inkycal import Inkycal
Inkycal._remove_module('Stocks')
```
