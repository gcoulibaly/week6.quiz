week6.quiz
==========
# week6quiz.R
# [For your convenience], here is the provided code from Jared Lander's R for Everyone, 
# 6.7 Extract Data from Web Sites

install.packages("XML")
require(XML)
theURL <- "http://www.jaredlander.com/2012/02/another-kind-of-super-bowl-pool/"
bowlPool <- readHTMLTable(theURL, which = 1, header = FALSE, stringsAsFactors = FALSE)
bowlPool

# 1. What type of data structure is bowlpool? 
class(bowlPool) #data.frame

# 2. Suppose instead you call readHTMLTable() with just the URL argument,
# against the provided URL, as shown below

theURL <- "http://www.w3schools.com/html/html_tables.asp"
hvalues <- readHTMLTable(theURL)
hvalues
class(hvalues) 
# What is the type of variable returned in hvalues?
# The type of variable is "list".

# 3. Write R code that shows how many HTML tables are represented in hvalues
length(hvalues)
#There are 7 HTML tables.

# 4. Modify the readHTMLTable code so that just the table with Number, 
# FirstName, LastName, # and Points is returned into a dataframe
hvalues1 <- readHTMLTable(theURL, which=1)
hvalues1

# 5. Modify the returned data frame so only the Last Name and Points columns are shown.
hvalues1[,c(3,4)]


# 6 Identify another interesting page on the web with HTML table values.
#England Premier League tables 2014
theURL1<-"http://www.espnfc.us/barclays-premier-league/23/table"
soccer <- readHTMLTable(theURL1, which = 1, header = FALSE, stringsAsFactors = FALSE)
length(soccer)
 

# 7 How many HTML tables does that page contain?
#There are 24 tables
length(soccer)


# 8 Identify your web browser, and describe (in one or two sentences) 
# how you view HTML page source in your web browser.
#I use CTRL + U to view HTML page source .
