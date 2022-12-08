SQLDF Case Study
================
Monalisa Roy

### Read the data,load libraries

``` r
customer=read.csv("customer-churn",stringsAsFactors = T)

library(sqldf)
```

    ## Loading required package: gsubfn

    ## Loading required package: proto

    ## Loading required package: RSQLite

#### Select the ‘OnlineBackup’column from the customer_churn dataframe and store the result in’customer_online_backup’

``` r
sqldf("select[OnlineBackup]from customer")->customer_online_backup
View(customer_online_backup)
```

#### Select the ‘StreamingTV’,‘StreamingMovies’and ’Contract’columns and store the result in ’customer_streaming_contract’

``` r
sqldf("select[StreamingTV],[StreamingMovies],[Contract]from customer")->customer_streaming_contract
View(customer_streaming_contract)
```

#### Select all the customers whose payment method is ‘mailed check’ and store the result in ‘customer_mail’

``` r
sqldf("select*from customer where [PaymentMethod]=('Mailed check')")->customer_mail1
View(customer_mail1)
```

#### Select all the Female customers whose tenure is of 1 month and PaymentMethod is’Mailed check’ and store the result in’customer_random_selection’

``` r
sqldf("select*from customer where [gender]=('Female') AND [tenure]=1 AND [PaymentMethod]=('Mailed check')")->customer_random_selection
View(customer_random_selection)
```
