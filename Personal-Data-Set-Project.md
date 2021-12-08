Personal-Data-Set-Project
================
Evan Howard
12/7/2021

In today’s world of Major League Baseball we tend to see pitchers with
higher velocities then what we were used to ten years ago. Could this be
from an increase in focus on biomechanics? Could it be from even more
specialized training than before? Or, are our memories deceiving us and
increased velocity isn’t real?

It would seem that MLB’s focus on increased velocities stems from
increased focus on both biomechanics and specialized training. This is
proven with programs such as Driveline Baseball which has a significant
roll in using biomechanics and data analytics to implement their
training programs. However, could this increased focus on velocity be
having a negative effect on control? Could increased velocity lead to
more hit by pitches? More base on balls? More losses than wins?

The data collecting, cleaning, and transforming were all fairly simple.
I downloaded the CSV from <https://www.fangraphs.com/>. From the
homepage of fangraphs I clicked on Team Stats. From there I went down to
the Multiple Seasons and entered 2007 to 2020. I then went down to the
Custom Leaderboards and created my own Leaderboard by selecting the
columns Season, Team, Win, Loss, ERA, Base_on_Balls, HBP, WP, Balls,
Strikes, K/9, BB/9, K/BB, and Velo. After looking at the data I realized
that I wanted to get rid of the 2020 season where there were only 60
games played. I chose to do this because only 60 games played is a
outlier to the regular 162 game season. In doing this I chose to only
use odd numbered years in the data starting with 2009 and ending with
2021.

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.5     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.4     ✓ stringr 1.4.0
    ## ✓ readr   2.0.2     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

![](Personal-Data-Set-Project_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->![](Personal-Data-Set-Project_files/figure-gfm/unnamed-chunk-1-2.png)<!-- -->

    ## 
    ## Call:
    ## lm(formula = mean ~ hbp_mean)
    ## 
    ## Residuals:
    ##        1        2        3        4        5        6        7 
    ## -0.08026  0.43666  0.18612 -0.42388 -0.03715 -0.24722  0.16573 
    ## 
    ## Coefficients:
    ##             Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept) 75.09172    2.62728  28.582 9.82e-07 ***
    ## hbp_mean     0.49819    0.07707   6.464  0.00132 ** 
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 0.3167 on 5 degrees of freedom
    ## Multiple R-squared:  0.8931, Adjusted R-squared:  0.8718 
    ## F-statistic: 41.78 on 1 and 5 DF,  p-value: 0.001319
