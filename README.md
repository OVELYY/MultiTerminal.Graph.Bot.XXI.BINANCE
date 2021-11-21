
MULTITERMINAL.GRAPH.BOT.XXI.BINANCE


The program is a graphical version of SIGNAL.PUMP.BOT and is also designed to help a trader in trading on the BINANCE cryptocurrency exchange,
by automatically and continuously monitoring price changes in pairs and signaling to the user about the beginning of the price movement of a coin.

The program window contains a maximum of 272 cells, each of which displays currency data and plots price changes for the last 70 connections.
The fixed size of the program window is due to the comfort of data perception even on a 15" laptop screen with a side-mounted taskbar. 
The schedule is formed completely only after 69 connections, but it becomes quite informative after 30 sessions.

As in the previous version, the bot connects to the BINANCE.API through public requests, so it does not require any registration
data or user keys. The program does not conduct any advanced analysis of the price movement, signaling only a sharp price movement 
in any pairs in the form of coloring the cell and text in green or red. Also, the bot shows the price movement only as a percentage without
repainting the cell, if the price changes within half of the value specified in lines 1 and 3 of the configuration file. 
All minor price changes are ignored so as not to clog up the information background, but the chart is built accurately.

At the urgent requests of novice traders, this release provides for the possibility of manual purchase and sale of currency along with automatic.
In fact, any beginner can test their abilities in cryptocurrency trading in this multi-terminal without the risk of losing money.
And simultaneous observation of almost three hundred currencies in one window will give an understanding of the characters of existing coins and their dynamic rhythms.
Automation of buying and selling is set in the CONFIG.CFG configuration file by specifying the AUTO or NO parameters in lines 2 and 4.

The desired program startup parameters are set line by line in the required file CONFIG.CFG in strict accordance with the template:


1. % UP for BUY
2. AUTO - for automatic buy, NO - for manual buy
3. % DOWN for SELL
4. AUTO - for automatic sell, NO - for manual sell
5. timeout (seconds)
6. amount for BUY $
7. start balance $
8. fee %


Here:

 1. % UP for BUY 	- setting a signal percentage of the price rise (may be a fractional value with a decimal point), the
			  excess of which turns the cell green and leads to the PURCHASE of a coin for the FIRST TIME if available 
			  free funds on the balance and AUTO mode;

 2. AUTO / NO 		- the automatic or manual purchase mode is set;

 3. % DOWN for SELL 	- setting the signal percentage of price reduction (may be a fractional value with a decimal point), the
		      	  negative excess of which turns the cell red, and in AUTO mode leads to a SALE 
                          previously purchased on the rise of the coin, calculating the profit and crediting it to the balance;

 4. AUTO / NO 		- the automatic or manual sale mode is set;

 5. timeout (seconds) 	- specifies the timeout between requests in seconds (INTEGERS ONLY!). BINANCE.The API sets limits on the number of requests
			  and after exceeding the limits, it bans by IP. Therefore, and also, based on the comfort of perception of data on the screen,
			  the recommended timeout is within 5..20 seconds. 

 6. amount for BUY $ 	- the order purchase amount is set to $ (INTEGERS ONLY!). 
			  Each purchase is made for an amount close to this value, but in accordance with the limits of the exchange;

 7. start balance $ 	- start balance (can be a fractional value with a decimal point);

 8. fee %		- transaction fee (may be a fractional value with a decimal point). On BINANCE, the commission is usually 0.1% of the transaction, 
                          but you can install any other one that would simulate other losses when trading.


The correct config file CONFIG.CFG is present in the program folder.

The program takes the list of currency pairs to work from a file CURRENCY.TXT, the presence of which is mandatory in the program folder.
Currency pairs should be written in the file line by line in the BINANCE standard, namely, together and in capital letters:

BTCUSDT
ETHBUSD
1INCHUSDT

The number of pairs can be from 1 to 272. The
program is designed only to work with basic $-stablecoins USDT, BUSD, TUSD, USDC.

On the first click of the LEFT mouse button on the cell, a currency is purchased, while the cell with the purchased currency is marked with a yellow frame.
Repeated LEFT-click on the cell with a yellow frame leads to the sale of this currency.
 
RIGHT-clicking on any cell leads only to hiding text data and full display of the price chart. 

The bot "buys" the currency in accordance with the BINANCE limits, which are requested when the program starts
and stored in the LIMITS file.TXT for all specified pairs.

For clarity, the control of the profitability of trading, the number of currency pairs, the number of BUY-SELL transactions, the total profit, the current total cost 
ALL acquired assets, including free balance funds and the balance itself are displayed in the header with the name of the window.

Of course, the behavior of the bot in automatic mode is not a guide to action, but it is a powerful information advisor
for making decisions in real trading.


GOOD LUCK AND PROFITABLE TRADING TO EVERYONE!


P.S.:
The bot is free to distribute and is free, but as usual among programmers and traders, 
thanks of any size are welcome. 

BTC: 1BTCoinE4qNnLmyRhBQLihwxUD88JdzkAh

Comments, suggestions on this release and prospects are accepted at: signal.pump.bot@gmail.com.
