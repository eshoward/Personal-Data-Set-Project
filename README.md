library(tidyverse)
library(knitr)
library(readxl)
fullstats <- read_excel("full_stats07-21.xlsx")
fb21 <- fullstats %>%
  filter(Season=="2021")
fb20 <- fullstats %>%
  filter(Season=="2020")
fb19 <- fullstats %>%
  filter(Season=="2019")
fb18 <- fullstats %>%
  filter(Season=="2018")
fb17 <- fullstats %>%
  filter(Season=="2017")
fb16 <- fullstats %>%
  filter(Season=="2016")
fb15 <- fullstats %>%
  filter(Season=="2015")
fb14 <- fullstats %>%
  filter(Season=="2014")
fb13 <- fullstats %>%
  filter(Season=="2013")
fb12 <- fullstats %>%
  filter(Season=="2012")
fb11 <- fullstats %>%
  filter(Season=="2011")
fb10 <- fullstats %>%
  filter(Season=="2010")
fb09<- fullstats %>%
  filter(Season=="2009")
fb08 <- fullstats %>%
  filter(Season=="2008")
fb07 <- fullstats %>%
  filter(Season=="2007")
mean <- round(c(mean(fb21$`velo`),mean(fb19$`velo`),mean(fb17$`velo`),
          mean(fb15$`velo`),mean(fb13$`velo`), mean(fb11$`velo`),
          mean(fb09$`velo`),mean(fb07$`velo`)),2)
season <- c("'21","'19","'17","'15","'13","'11","'09","'07")
mean_df <- data.frame(season,mean)
hbp_mean <- round(c(mean(fb21$HBP),mean(fb19$HBP),
                    mean(fb17$HBP),
                    mean(fb15$HBP),mean(fb13$HBP),
                    mean(fb11$HBP),
                    mean(fb09$HBP),mean(fb07$HBP)),2)
season <- c("'21","'19","'17","'15","'13","'11","'09","'07")
hpbmean_df <- data.frame(season, hbp_mean)
ggplot(mean_df, aes(season,mean, group=1))+
  geom_point(colour="orange")+geom_line(size=1.4, colour="orange")+
  xlab("Season")+ylab("Velocity")+
  ggtitle("Avg. Fastball Velocity per Season")+theme_bw()
