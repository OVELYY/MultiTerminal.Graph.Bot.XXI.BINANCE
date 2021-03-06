
MULTITERMINAL.GRAPH.BOT.XXI.BINANCE


Программа является графической версией SIGNAL.PUMP.BOT и также предназначена для помощи трейдеру в торговле на криптовалютной бирже BINANCE, 
путём автоматического и непрерывного мониторинга изменения цен в парах и подачи сигнала пользователю о начале движения цены какой-либо монеты.

Окно программы содержит максимально 272 ячейки, в каждой из которых выводятся данные о валюте и строится график изменения цены за последние 70 подключений.
Фиксированный размер окна программы обусловлен комфортностью восприятия данных даже на 15" экране ноутбука с боковым расположением панели задач. 
График формируется полностью лишь после 69 подключения, но становится вполне информативным уже через 30 сессий.

Как и в предыдущей версии, бот подключается к BINANCE.API посредством публичных запросов, поэтому ему не требуется никаких регистрационных 
данных или ключей пользователя. Программа не проводит какого-либо продвинутого анализа движения цены, сигнализируя лишь о резком движении цены 
в каких-либо парах в виде окрашивания ячейки и текста в зелёный или красный цвета. Также бот показывает движение цены лишь в процентах без
перекраски ячейки, если цена меняется в пределах от половины значения указанного в 1 и 3 строках файла конфигурации. 
Все незначительные изменения цены игнорируются, чтобы не засорять информационный фон, однако график выстраивается точно.

По настоятельным просьбам начинающих трейдеров, в данном релизе предусмотрена возможность ручной покупки и продажи валюты наряду с автоматической.
Фактически, любой новичок может протестировать свои способности в торговле криптовалютой в этом мультитерминале без риска потерять деньги.
А одновременное наблюдение за почти тремя сотнями валют в одном окне, даст понимание о характерах существующих монет и их динамических ритмах.
Автоматизация покупки и продажи задаётся в файле конфигурации CONFIG.CFG через указания во 2 и 4 строках параметров AUTO или NO.

Желаемые параметры запуска программы задаются построчно в обязательном файле CONFIG.CFG в строгом соответствии с шаблоном:

1. % UP for BUY
2. AUTO - for automatic buy, NO - for manual buy
3. % DOWN for SELL
4. AUTO - for automatic sell, NO - for manual sell
5. timeout (seconds)
6. amount for BUY $
7. start balance $
8. fee %

Здесь:

 1. % UP for BUY 	- установка сигнального процента подъема цены (может быть дробное значение с десятичной ТОЧКОЙ),
			  превышение которого окрашивает ячейку в зелёный цвет и ПЕРВЫЙ РАЗ приводит к ПОКУПКЕ монеты при наличии 
			  свободных средств на балансе и режиме AUTO;
 
 2. AUTO / NO           - задаётся режим автоматической или ручной покупки;

 3. % DOWN for SELL	- установка сигнального процента снижения цены (может быть дробное значение с десятичной ТОЧКОЙ), 
			  отрицательное превышение которого окрашивает ячейку в красный цвет, а в режиме AUTO приводит к ПРОДАЖЕ 
                          ранее купленной на подъёме монеты, вычислению профита и зачислению его на баланс;

 4. AUTO / NO           - задаётся режим автоматической или ручной продажи;

 5. timeout (seconds) 	- указание таймаута между запросами в секундах (ТОЛЬКО ЦЕЛЫЕ ЧИСЛА!). BINANCE.API устанавливает ограничения на количество запросов
			  и после превышения лимитов банит по IP. Поэтому, а также, исходя из комфортности восприятия данных на экране,
			  рекомендуемый таймаут находится в границах 5..20 секунд. 

 6. amount for BUY $	- устанавливается сумма покупки ордера в $ (ТОЛЬКО ЦЕЛЫЕ ЧИСЛА!). 
			  Каждая покупка производится на сумму, близкую к этому значению, но в соотетствии с лимитами биржи;

 7. start balance $	- стартовый баланс (может быть дробное значение с десятичной ТОЧКОЙ);

 8. fee %		- комиссия за сделку (может быть дробное значение с десятичной ТОЧКОЙ). На BINANCE обычно комиссия 0.1% от сделки, 
                          но можно установить любую другую, которая бы имитировала иные потери при торговле.


Корректный конфиг-файл CONFIG.CFG присутствует в папке с программой.

Список валютных пар для работы программа берёт из файла CURRENCY.TXT, наличие которого обязательно в папке с программой.
Валютные пары должны быть записаны в файле построчно в стандарте BINANCE, а именно слитно и заглавными буквами:

BTCUSDT
ETHBUSD
1INCHUSDT

Количество пар может быть от 1 до 272.
Программа предназначена только для работы с базовыми $-стейблкоинами USDT, BUSD, TUSD, USDC.

По первому клику ЛЕВОЙ клавиши мыши на ячейке происходит покупка валюты, при этом ячейка с купленной валютой помечается желтой рамкой и показывается уже процент прибыли
или убытка. Повторный клик ЛЕВОЙ клавишей по ячейке с желтой рамкой приводит к продаже этой валюты.
 
Клик ПРАВОЙ клавиши мыши по любой ячейке приводит лишь к скрытию текстовых данных и полному отображению графика цены. 

Бот "покупает" валюту в соответствии с лимитными ограничениями BINANCE, которые запрашиваются при запуске программы 
и сохраняются в файле LIMITS.TXT для всех указанных пар.

Для наглядности контроля прибыльности торговли, количество валютных пар, количество BUY-SELL сделок, суммарный профит, текущая суммарная стоимость 
ВСЕХ приобретённых активов, включая свободные средства баланса и сам баланс отображаются в шапке с названием окна.

Разумеется, поведение бота в автоматическом режиме не является руководством к действию, но является мощным информационным советником 
для принятия решений в реальной торговле.


УДАЧИ И ПРИБЫЛЬНОЙ ТОРГОВЛИ ВСЕМ И КАЖДОМУ!


P.S.:
Бот свободен к распространению и бесплатен, но, как водится в среде программеров и трейдеров, 
любого размера благодарность приветствуются. 

BTC: 1BTCoinE4qNnLmyRhBQLihwxUD88JdzkAh

Замечания, пожелания по данному релизу и перспективам принимаются на: signal.pump.bot@gmail.com.

