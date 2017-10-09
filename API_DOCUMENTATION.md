#API Documentation

###Schema

######Schema includes 2 tables shown below:
#####events Table
field name|field type
----------|----------
id | integer, auto increasing
trader | varchar(50) NOT NULL
symbol | varchar(50) NOT NULL
event_type | char(50) NOT NULL
price | decimal(10, 4) NOT NULL
volume | Int NOT NULL
date_time | Datetime NOT NULL

#####positions Table
field name | field type
-----------|-----------
id | integer, auto increasing
trader | varchar(50) NOT NULL
symbol | varchar(50) NOT NULL
number_of_shares | int NOT NULL
time_of_last_event | Int NOT NULL
total_cost | decimal NOT NULL
net_gain | Decimal NOT NULL

###/login/google
Allows user to sign in using their google account
GET request to /login/google will allow the user to sign in to their account if they had one.  If not it will make a new account.  The user’s account holds the stock that the user has purchased if the page is refreshed before the game time is up.

###/login/google/return
Returns redirects the user to their home page.
GET request to /login/google/return redirects the user to their homepage.  This homepage will have all the stocks they have bought if they refreshed before the game time was up.

###/stock/send-all
Sends all the current stock info to the client
GET requests to /stock/send-all send all the stock info currently saved in the server side by the worker to the client.


###/portfolio/send-all
GET requests to /portfolio/send-all sends all the purchased stocks that are stored in the database to the client



###/stock/buy
POST requests to /stock/buy saves the stock info at time of purchase into the database.

###/stock/sell
POST requests to /stock/sell saves the stock info at time of sale to the database.  This info will also be compared and calculated to the to the time of purchase info and will adjust the portfolio amount accordingly.
