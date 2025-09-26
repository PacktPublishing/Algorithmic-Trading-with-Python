# Algorithmic Trading with Python

Materials for the Algorithmic Trading with Python workshop hosted by Jason Strimpel on September 27, 2025. Jason is the founder of [PyQuant News](https://www.pyquantnews.com/) Jason and has 20+ years in trading, risk, and quantitative finance across hedge funds, banks, and trading firms. He publishes practical Python workflows for quants and traders at PyQuant News.

##  Installation

The fastest way to get Python, Jupyter, and the scientific stack is the [Anaconda Distribution](https://www.anaconda.com/download). Download the installer for your OS and complete the setup. Open Anaconda Prompt (Windows) or Terminal (macOS/Linux) and verify your install with:

```
conda list
```

You should see a list of installed packages. See the included guide: Install [Python with the Anaconda Distribution (PDF)](https://github.com/PacktPublishing/Algorithmic-Trading-with-Python/blob/main/01.%20Installation%20Instructions/01.%20Install_Python_with_the_Anaconda_Distribution.pdf).

## Install the Python libraries (recommended workflow)

Create an isolated environment and install the workshop dependencies.

```
# update conda itself
conda update -n base -c defaults conda -y

# create and activate a clean environment (Python 3.11 recommended)
conda create -n my_quant_lab python=3.11 -y
conda activate my_quant_lab

# notebooks + tooling
pip install jupyterlab

# backtesting stack
pip install vectorbt
```

See the included guide: [Installing the Python Quant Stack (PDF)](https://github.com/PacktPublishing/Algorithmic-Trading-with-Python/blob/main/01.%20Installation%20Instructions/02.%20Installing_the_Python_Quant_Stack.pdf).

### Optional — Interactive Brokers API (for live trading workflows):

Install the [IB Python API](https://interactivebrokers.github.io/) from Interactive Brokers’ distribution (Windows MSI or Mac/Linux ZIP), then from the extracted pythonclient folder run:

```
pip install .
```

Notes: IBKR Pro is required for market data; the free demo allows order submission only. In TWS: enable ActiveX and Socket Clients, optionally Read-Only API, allow localhost only, and note the default paper-trading socket port 7497. See the included guide: Installing the Python Quant Stack (PDF).

## Start Jupyter

From your activated environment:

```
jupyter lab
```

This opens a browser-based interface where you can run the notebooks.

### Notebooks Overview

`01_prototyping_crack_refiner_spread_trade.ipynb`

Prototype the crack vs. refiner spread trade: define the spread, explain the economic rationale, explore data, engineer features (e.g., rolling z-scores), and sketch a simple rule to test the idea before formal backtesting.

`02_backtest_crack_refiner_spread_trade.ipynb`

Implement a VectorBT backtest: generate signals from the spread (e.g., z-score thresholds), run parameter sweeps, and evaluate returns, drawdowns, and Sharpe/Calmar to pressure-test the concept.

`03_trade_crack_refiner_spread_trade.ipynb`

Move from backtest to execution with Interactive Brokers: connect to TWS/Gateway, retrieve historical data, compute the spread, and place example orders with basic safety checks and runbook notes.
