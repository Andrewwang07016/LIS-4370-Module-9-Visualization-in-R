# LIS-4370-Module-9-Visualization-in-R

library(ggplot2)

setwd("/Users/Steven Wang/Downloads")
df <- read.csv("Affairs.csv")
head(df)

df$AgeGroup <- cut(df$age, breaks = c(10, 20, 30, 40, 50, 60), labels = c("10-20", "21-30", "31-40", "41-50", "51-60")) 
boxplot(affairs ~ AgeGroup, data = df, main = "Affairs by Age", xlab = "Age Group", ylab = "Affairs", col = "black")

ggplot(df, aes(x = factor(age), y = affairs, fill = factor(age))) + geom_boxplot() + labs(title = "Affairs by Age") + theme(plot.title = element_text(hjust = 0.5)) + xlab("Age") + ylab("Affairs")

library(lattice)
bwplot(age ~ affairs, df, main = "Affairs by Age", xlab = "Affairs", ylab = "Age Groups")
