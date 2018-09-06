Assignment 2
================
Omar Qasem

The goal of this practice is to improve your understanding of vectors and how to manipulate them. The data we use are the prices of the [2017 Big Mac Index](http://www.economist.com/content/big-mac-index).

For each question, please create a new chunck with your reponse. Use narratives to comment the output whenever the question requires to do so.

1.  Edit the code below to assign country names to the vector `countries` and prices to the vector `prices`. Hide the code below when you knit (check the Rmarkdown cheatsheet to find the appropriate chunk option to hide code).

2.  Use `typeof()` to report the type of both vectors.

``` r
typeof(countries)
```

    ## [1] "character"

``` r
typeof(prices)
```

    ## [1] "double"

1.  Use `names()` to name the `prices` using `countries`. Show the first 5 values of your new vector

``` r
`names<-`(prices[c(1:5)],countries[c(1:5)])
```

    ## Argentina Australia    Brazil   Britain    Canada 
    ##  4.125534  4.527955  5.101568  4.111432  4.655697

1.  Use `round()` to round the prices at the 3rd decimal. Overwrite `prices` with the rounded prices.

``` r
round(prices, digits = 3)
```

    ##  [1] 4.126 4.528 5.102 4.111 4.656 3.844 2.917 3.244 4.000 3.281 4.606
    ## [12] 1.754 4.465 2.458 3.209 2.757 2.403 4.773 3.361 2.003 2.754 4.432
    ## [23] 5.914 3.566 3.229 2.649 2.723 2.278 3.200 4.065 2.261 3.844 3.773
    ## [34] 5.819 6.742 2.264 3.496 3.006 3.812 1.698 5.300 4.529 4.056 2.639
    ## [45] 3.883 4.625 3.597 5.207 4.682 4.454 3.826 4.648 4.796 4.122 3.711
    ## [56] 4.339

1.  Use indexing to report the prices for Canada, United States, Mexico

``` r
`names<-`(prices[c(5,21,41)], countries[c(5,21,41)])
```

    ##        Canada        Mexico United States 
    ##      4.655697      2.754240      5.300000

1.  Use inline code and the function `length()` to display the following sentence:

"The are x observations in the Big-Mac Index" There are 56 observations in the Big-Mac Index

1.  Convert the prices from Dollar to Euro (1 Dollar = .83 Euro). In the narrative, comment about the property which allows you to combine a vector of length 1 (the exchange rate) with a vector of length 56 (the prices).

``` r
#this function is to convert a dollar amount in euros 

euro <- .83    
showValue <- function(dollars) {      
  x <- dollars
  conv_toEuro <- function() paste(x*euro, 'Euros')
  c(conv_toEuro())
}
#We pass the vector "prices" which is a length of 56 through the parameter "x" and it passes each value of prices through
showValue(prices)
```

    ##  [1] "3.42419331074112 Euros" "3.75820265 Euros"      
    ##  [3] "4.23430108524255 Euros" "3.412488145 Euros"     
    ##  [5] "3.86422833970209 Euros" "3.19059930203285 Euros"
    ##  [7] "2.42121546961326 Euros" "2.69219175927868 Euros"
    ##  [9] "3.32002899588642 Euros" "2.72356176250541 Euros"
    ## [11] "3.82338715249787 Euros" "1.4558065417948 Euros" 
    ## [13] "3.705970335 Euros"      "2.04006912884849 Euros"
    ## [15] "2.66342644865181 Euros" "2.28850249777331 Euros"
    ## [17] "1.99443359886308 Euros" "3.9618697924022 Euros" 
    ## [19] "2.78966920219352 Euros" "1.66251310119949 Euros"
    ## [21] "2.28601942020432 Euros" "3.6787758 Euros"       
    ## [23] "4.9087529570801 Euros"  "2.96005706134094 Euros"
    ## [25] "2.68030139935414 Euros" "2.19904501102291 Euros"
    ## [27] "2.26042172248288 Euros" "1.89085237183825 Euros"
    ## [29] "2.65589376424943 Euros" "3.37373884009581 Euros"
    ## [31] "1.87641296156744 Euros" "3.1904949111082 Euros" 
    ## [33] "3.13156610831029 Euros" "4.82970418208933 Euros"
    ## [35] "5.59560234403361 Euros" "1.87909113280288 Euros"
    ## [37] "2.90188474138058 Euros" "2.49507137763734 Euros"
    ## [39] "3.16362646338143 Euros" "1.40922245803589 Euros"
    ## [41] "4.399 Euros"            "3.75892701619926 Euros"
    ## [43] "3.36611111111111 Euros" "2.19069613988783 Euros"
    ## [45] "3.2225829 Euros"        "3.838664925 Euros"     
    ## [47] "2.985628275 Euros"      "4.32205236 Euros"      
    ## [49] "3.88605585 Euros"       "3.69649215 Euros"      
    ## [51] "3.175191975 Euros"      "3.857621295 Euros"     
    ## [53] "3.9808377 Euros"        "3.421624785 Euros"     
    ## [55] "3.080410125 Euros"      "3.6017103 Euros"

-   Could you use the vector `rep(.83, 28)` to do the same?

``` r
# No this just repeats .83 28 times
rep(.83, 28)
```

    ##  [1] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83
    ## [15] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83

-   Could you use the vector `rep(.83, 112)` to do the same?

``` r
# No this just repeats .83 112 times
rep(.83, 112)
```

    ##   [1] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83
    ##  [15] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83
    ##  [29] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83
    ##  [43] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83
    ##  [57] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83
    ##  [71] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83
    ##  [85] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83
    ##  [99] 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83 0.83

-   Would `rep(.83, 45)` also work? Why?

``` r
# No this would just print .83 45 times
```

1.  In your narrative, mention that we are going to drop the 46th element. Use dynamic code to report the country that will drop. We are going to drop the 46th element

``` r
countries[c(46)]
```

    ## [1] "Belgium"

1.  Overwrite the vector of prices with a new vector without observation 46. Use `length()` to make sure you have one observation less.

``` r
prices <- drop(prices[c(1:45,47:56)])
length(prices)
```

    ## [1] 55

1.  Knit, commit and push to your GitHub repo `assignment`. Then submit the link to the *assignment folder* on Moodle.
