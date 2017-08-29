---
title: "Missing Data Project"
output:
  word_document: default
  html_document: default
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Here we are reading in each data file naming them data1:total.  See what happens when there is missing data.

The following organizations had two sesstions Youth Services Association, IUSSW Alumni Conference , Janet Decker Law Class, and MCCSC had three sessions.  I data12 is missing there so there are 22 total excel documents with 5 duplicates therefore there are 17 unique sites visited with 22 total programs provided to 1041 people.
```{r}
#setwd("~/Box Sync/Unreviewed Excel Training Data/ Matt'sExcelTraining Data")
library(XLConnect)
data1 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 1, startCol = 4, endCol = 13)
colnames(data1) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data1)
dim(data1)
data1$site = rep(1,length(data1$gender))
data1 = cbind(data1[,1:7], site= data1[,11])

data2 = readWorksheetFromFile("Meadows Hospital Lunch & Learn.xlsx", sheet = 1, startCol = 3, endCol = 12)
colnames(data2) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data2)
data2$site = rep(2,length(data2$gender))
data2 = cbind(data2[,1:7], site = data2[,11])


data3 = readWorksheetFromFile("Merriville Training 7272016.xlsx", sheet = 1, startCol = 4, endCol = 13)
colnames(data3) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data3)
data3$site = rep(3,length(data3$gender))
dim(data3)
data3 = data3[-c(1),]; head(data3)
data3 = cbind(data3[,1:7], site = data3[,11])
head(data3)


data4 = readWorksheetFromFile("Terre Haute 7272016.xlsx", sheet = 1, startCol = 4, endCol = 13)
colnames(data4) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data4)
dim(data4)
data4$site = rep(3,length(data4$gender))
data4 = data4[-c(1),]; head(data4)

data4 = cbind(data4[,1:7], site = data4[,11])
head(data4)


data5 = readWorksheetFromFile("Youth Services Association Administraiont 9012016.xlsx", sheet = 1, startCol = 3, endCol = 12)
colnames(data5) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data5)
dim(data5)
data5$site = rep(5,length(data5$gender))
data5 = data5[-c(1),]; head(data5)

data5 = cbind(data5[,1:7], site = data5[,11])
head(data5)


data6 = readWorksheetFromFile("Youth Services Association Session 2.xlsx", sheet = 1, startCol = 3, endCol = 12)
colnames(data6) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data6)
dim(data6)
data6$site = rep(6,length(data6$gender))
data6 = cbind(data6[,1:7], site = data6[,11])
head(data6)



data7 = readWorksheetFromFile("Youth Services Bureau 7-29-16 (Created by Piper; Edited by Brie).xlsx", sheet = 1, startCol = 3, endCol = 12)
colnames(data7) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data7)
dim(data7)
data7$site = rep(7,length(data7$gender))
data7 = cbind(data7[,1:7], site = data7[,11])
head(data7)


data8 = readWorksheetFromFile("Ivy Tech 2017 Training.xlsx", sheet = 1, startCol = 2, endCol = 11)
colnames(data8) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data8)
dim(data8)
data8$site = rep(8,length(data8$gender))
data8 = cbind(data8[,1:7], site = data8[,11])
head(data8)

data9 = readWorksheetFromFile("IUSSW Alumni Conference.xlsx", sheet = 1, startCol = 3, endCol = 12)
colnames(data9) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data9)
dim(data9)
data9$site = rep(9,length(data9$gender))
data9 = data9[-c(1),]; head(data9)

data9 = cbind(data9[,1:7], site = data9[,11])
head(data9)

data10 = readWorksheetFromFile("IUSSW Alumni Conference.xlsx", sheet = 2, startCol = 3, endCol = 12)
colnames(data10) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data10)
dim(data10)
data10$site = rep(10,length(data10$gender))
data10 = cbind(data10[,1:7], site = data10[,11])
head(data10)

data11 = readWorksheetFromFile("IU Pre School Training 12716.xlsx", sheet = 1, startCol = 4, endCol = 13)
colnames(data11) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data11)
dim(data11)
data11$site = rep(11,length(data11$gender))
data11 = data11[-c(1),]; head(data11)
data11 = cbind(data11[,1:7], site = data11[,11])
head(data11)

data13 = readWorksheetFromFile("Indiana School Health Conference.xlsx", sheet = 1, startCol = 2, endCol = 11)
colnames(data13) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data13)
dim(data13)
data13$site = rep(13,length(data13$gender))
data13 = cbind(data13[,1:7], site = data13[,11])
head(data13)

data14 = readWorksheetFromFile("Boys + Girls Club Camp Training 2016.xlsx", sheet = 1, startCol = 4, endCol = 13)
colnames(data14) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data14)
dim(data14)
data14$site = rep(14,length(data14$gender))
data14 = cbind(data14[,1:7], site = data14[,11])
head(data14)

data15 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 2, startCol = 4, endCol = 13)
colnames(data15) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data15)
dim(data15)
data15$site = rep(15,length(data15$gender))
data15 = cbind(data15[,1:7], site = data15[,11])
head(data15)


data16 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 3, startCol = 5, endCol = 14)
colnames(data16) = c("gender", "sexorien", "age", "eth", "Pre-Competent",	"Pre-Confident",	"Pre-Comfort",	 "Post-Competent",	"Post-Confident",	"Post-Comfort")
head(data16)
dim(data16)
data16$site = rep(16,length(data16$gender))
data16 = cbind(data16[,1:7], site = data16[,11])
head(data16)

data = rbind(data1, data2, data3, data4, data5, data6, data7, data8, data9, data10, data11, data13, data14, data15, data16)
colnames(data) = c("gender", "sexorien", "age", "eth", "PreCompetent",	"PreConfident",	"PreComfort", "site")
dim(data)
head(data)
typeof(data)
```

Doing the transformations for the the pre variables.
Need to missing values as something other than NA make them -9  then you need to get rid of them at the end, because they are values that do not make sense.

```{r}
data = apply(data,2, function(x){ifelse(x == "[Crossed out 7] 9 ", 9, ifelse(x == "2 <-> 3", 2.5, ifelse(x == "7 & 10", 8.5, ifelse(x == "7&8", 7.5, ifelse(x == "8-9", 8.5, ifelse(x == "No Pre", NA, ifelse(x == "7_8" , 7.5, ifelse(x == "NR", NA, ifelse(x == "6-7", 6.5, ifelse(x == "7_9", 8, ifelse(x == "8_10", 9, ifelse(x == "9 10", 9.5, ifelse(x =="4-5", 4.5, ifelse(x == "7-9", 8, ifelse(x == "N/A", NA, ifelse(x =="\"N/A\"", NA, ifelse(x == "3 I can't create it.", 3, ifelse(x == "6_7", 6.5, ifelse(x == "8&9", 8.5, ifelse(x == "No Pre", NA, ifelse(x == "[Crossed out 9] 7", 7, ifelse(x == "3_4", 3.5, ifelse(x == "5 6", 5.5, ifelse(x == "7-8", 8.5, ifelse(x == "9-10", 9.5, ifelse(x == "Not sure", NA, ifelse(x == "9 (10 crossed out) ", 9, ifelse(x == "N/A", NA,ifelse(x == "9 10 ", 9.5, ifelse(x == "[Crossed out 7] 9", 9, ifelse(x == "6 7 ", 6.5, ifelse(x == "9&10", 9.5, ifelse(x == "[Crossed out 9] 10", 10, ifelse(x =="5 Resources helpful", 5, ifelse(x == "7 (Crossed out \"4\")", 7, ifelse(x == "8_9", 8.5, ifelse(x == "9_10", 9.5, ifelse(x == "99", NA, ifelse(x == "[Scribbled out 5]", NA, ifelse(x == "4_5" , 4.5, ifelse(x == "8-8", 8,ifelse(x == "10 (\"Crossed out \"7\")", 10,ifelse(x == "10 (Crossed out 9)", 10, ifelse(x == "5 6 ", 5.5, ifelse(x == "6 I mean, for myself.", 6, ifelse(x == "7 (5 crossed out)", 7, ifelse(x == "9_11", 10.5, ifelse(x == "\"Better\"", NA, x ))))))))))))))))))))))))))))))))))))))))))))))))})
data = as.data.frame(data)

data = apply(data,2, function(x){ifelse(x == "[Scribbled out 5 and underlined 8]", 8, ifelse(x == "10 (Crossed out \"7\")", 10, ifelse(x == "2 \"Willing but a lot to learn", 2, ifelse(x == "5 to 7", 6, ifelse(x == "6 (3 crossed out)", 6, ifelse(x == "7 Still need practice!!", 7 , ifelse(x == "9 10 sometimes I mess up.", 9.5, ifelse(x== "As long as I know what they are.", 9, ifelse(x == "9_12", 10.5, ifelse(x == "S", NA, ifelse(x == "Same response as on the PRE-ASSESSMENT.", NA, ifelse(x == "A + Strongly Agree", 7, ifelse(x== "Strongly Agree", 7, ifelse(x == "Strongly Disagree", 1, ifelse(x == "Disagree", 3, ifelse(x == "Neutral", 4, ifelse(x == "Agree", 6, ifelse(x == "Strongly Agree", 7, ifelse(x == "Circled Strongly Agree and Agree", 6, ifelse(x == "Neural", 4, ifelse(x== "Stringly Agree", 7,ifelse(x == "Strongly Agree [Crossed out \"Strongly Disagree\"]", 7, ifelse(x == "Agree *Strongly Agree*", 6, ifelse(x == "D_N", NA, ifelse(x == "N + Agree", 4, ifelse(x == "Neutral ", 3, ifelse(x == "Nuetral", 3,ifelse(x == "Strongly agree", 5, ifelse(x == "Strongly Agree ", 7,ifelse(x == "N_A", NA, ifelse(x == "Agree ", 6, ifelse(x== "Agree Strongly Agree", 7, ifelse(x == "Stongly Agree", 7, ifelse(x == "[circled \"LGBTQ+ youth\"]", NA, ifelse(x == "Agree Don't directly work w/youth in my job.", 6, ifelse(x == "I learned a lot from the research data statements. That was eye popping to me. I plan to share those findings to my students.", NA, ifelse(x == "Strongly Agree (Police Dept. Sherifs Dept.)", 7, ifelse(x =="Strongly Agree!", 7, ifelse(x == " Strongly Agree", 7, x)))))))))))))))))))))))))))))))))))))))})
data = as.data.frame(data)

data = apply(data,2, function(x){ifelse(x == "\"Unsure\"", NA, ifelse(x == "?", NA, ifelse(x == "[Crossed out 8] 10", 10, ifelse(x == "[Crossed out 8] 5 I usually use their name, so I don't make a mistake and offend someone.", 5, ifelse(x == "10 -Had transgender student in class and referred to the student's preferred gender pronouns", 10, ifelse(x == "10 I see no reason why you could object to this as long as you know the preference.", 10, ifelse(x == "2_3", 2.5, ifelse(x ==  "4 My fear is of offending the person by doing something wrong." , 4, ifelse(x=="5_7", 6,ifelse(x == "6 to 10 [wrote \"competent\"]", 8, ifelse(x== "6&7", 6.5, ifelse(x == "8 I'm comfortable using them I'm just horrible @ remembering!!!" , 8, ifelse(x =="N/A 9", 9, ifelse(x == "Using the pronouns to refer to that someone: 9 using the pronouns to refer to myself, or for myself: would depend on what the pronouns were.", NA, ifelse(x == "5_6", 5.5, ifelse(x =="6 I mean, for myself…", 6, ifelse(x == "77", 7, ifelse(x== "6 I mean, for myself…", 6, ifelse(x == "10 [wrote \"& confident\"]", 10, ifelse(x == "9 As long as I know what they are.", 9, ifelse(x =="WOULD NEED TO PRACTICE THIS ONE seemed to go over fast - future maybe give examples more", NA, ifelse(x == "Nuetral ", 4, ifelse(x == "7 9 other issues impede", 8, ifelse(x == "9 other issues impede", 9, ifelse(x == "Pre-Competent", NA, x)))))))))))))))))))))))))})
data = as.data.frame(data)
dataPre = data
dataTest = as.factor(data$PreCompetent)
levels(dataTest)
dim(dataPre)
dataTestGender = data$gender
head(dataTestGender)
```

```{r}
data = as.data.frame(apply(data, 2, function(x){ifelse(x == "Professor", -9, ifelse(x == "Straight", -9, ifelse(x == "Nb", -9, x)))}))

data = apply(data, 2, function(x){ifelse(x == "\"?\"", -9, ifelse(x == "\"50+\"", -9,ifelse(x == "\"Old\"", -9, ifelse(x == "40 and fabulous",-9,ifelse(x == "No Pre", -9, ifelse(x == "\"60+\"", -9, ifelse(x == "\"2\"", -9, ifelse(x == "45+", -9, ifelse(x == "over 21", -9, ifelse(x == "\"30+\"", -9,ifelse(x == "\"Guess\"", -9, ifelse(x == "Illegible", -9, ifelse(x == "range 22-68", -9, ifelse(x == "\"4\"", -9, ifelse(x == "\"MYOB\"", -9, ifelse(x == "\"40ish\"", -9, ifelse(x == "\"Ø\"", -9, ifelse(x == "50+", -9, ifelse(x =="\"?\"", -9, ifelse(x == "\"Ø\"", -9, x))))))))))))))))))))})
data = as.data.frame(data)

#levels(ethLevels)
```

Here is where I first recode all possible missing values into a "Missing" code and then delete the -9's which are the missing values I created in the step above.

For example, I believe that "Flank" is actually "Blank", which is one of the codes the Prism students to code missing values.  Therefore, I am recoding the "Flank" code to "Missing".  Let me know what you think about these codes.
```{r}

data1 =apply(data, 2, function(x) {ifelse(x == "NA", "Missing", ifelse(x == -9, NA, ifelse(x == "Blank", "Missing", ifelse( x == "N/A", "Missing", ifelse(x == "Flank", "Missing",ifelse(x == "MIssing", "Missing", ifelse(x == "[Crossed something out]", "Missing", ifelse(x == "I'd need to know you better to share that =)", NA, ifelse(x =="[Crossed something out]", NA, x )))))))))})

data1 = as.data.frame(data1)
head(data1)
data1 = na.omit(data1)
sum(is.na(data1))
data1 = as.data.frame(data1)
dim(data1)
head(data1)
```
Here I created a female variable, other gender identity variable (otherGI), and a straight variable.  

For example, I believed that  "\"Female-> like males\"" meant that they were straight and therefore I coded that as a 1 in the straight variable meaning that they would be classified as straight.  Therefore, the reference category is all non-straight sexual orientations.

For the gender variable, I also created a other gender identity variable, which means that male is the reference category for the gender variable.

For sexual orientation, because straight is coded as one, all non-straight sexual orientations are the reference category.

Let me know what you think about these codes.

The data1SexOrien variable is the incorrect variable.  I didn't change the name, because the name is used later on.
```{r}
# Incorrect variable for sexual orientation
data1SexOrien = ifelse(data1$sexorien == "\"Left\"", 1, ifelse(data1$sexorien == "\"F\"", 1, ifelse(data1$sexorien == "\"Woman\"", 1, ifelse( data1$sexorien == "\"I date men only\"", 1, ifelse( data1$sexorien == "\"I date men only\"", 1, ifelse(data1$sexorien == "\"F\"", 1, ifelse(data1$sexorien == "\"Ø\"", 1, ifelse(data1$sexorien == "\"Yes\"", 1, ifelse(data1$sexorien == "\"M\"", 1, ifelse(data1$sexorien == "\"Happily married\"",1, ifelse(data1$sexorien == "\"MYOB\"" , 1, ifelse( data1$sexorien == "(I?)", 1, ifelse( data1$sexorien == "~ ? ~ " , 1, ifelse(data1$sexorien == "\"Male\"", 1, ifelse(data1$sexorien == "\"Married to a man\"", 1, ifelse(data1$sexorien == "F", 1, ifelse(data1$sexorien == "h", 1, ifelse(data1$sexorien == "H", 1, ifelse(data1$sexorien == "Female",1, ifelse(data1$sexorien == "She" , 1, ifelse(data1$sexorien == "Single", 1, ifelse(data1$sexorien == "\"Female\"", 1, ifelse(data1$sexorien == "L", 1, ifelse(data1$sexorien == "M", 1, ifelse(data1$sexorien == "\"Feminine\"", 1, ifelse(data1$sexorien == "Male", 1,0))))))))))))))))))))))))))
data1SexOrien = as.data.frame(data1SexOrien)
sexOrienLevels = as.factor(data1$sexorien)
levels(sexOrienLevels)

female = ifelse(data1$gender == "\"Female-->sex, androgyne/butch, top/bottom\"", 1, ifelse(data1$gender == "Cis woman", 1, ifelse(data1$gender == "f", 1, ifelse(data1$gender == "F.", 1, ifelse(data1$gender =="Femal",1, ifelse(data1$gender == "Female", 1, ifelse(data1$gender == "Female (Cisgender)", 1, ifelse(data1$gender == "Female/she", 1, ifelse(data1$gender == "Femele", 1, ifelse(data1$gender == "Lady" , 1, ifelse(data1$gender == "Woman", 1, ifelse(data1$gender == "\"Female--cisgender\"", 1, ifelse(data1$gender == "\"She\"", 1, ifelse(data1$gender == "[Female symbol]" , 1, ifelse(data1$gender == "Cis woman", 1, ifelse(data1$gender == "F", 1, ifelse(data1$gender == "Famel",1, ifelse(data1$gender == "Female (cis)", 1, ifelse(data1$gender == "Female/Woman", 1, ifelse(data1$gender == "She, her, hers Female", 1, ifelse(data1$gender == "woman", 1, ifelse(data1$gender =="Woman (she/her)", 1, ifelse(data1$gender == "female", 1, ifelse(data1$gender == "f", 1, ifelse(data1$gender == "Missing", "Missing", 0)))))))))))))))))))))))))
dim(female)

levelsGender = as.factor(data1$gender)
levels(levelsGender)
otherGI =  ifelse(data1$gender == "Non-binary", 1, ifelse(data1$gender == "Genderqueer", 1, ifelse(data1$gender == "Trans women", 1, 0)))
sum(otherGI)


```

Here I created the “progressive” gender identity variable.  My main criteria was when people used multiple “correct” (i.e. did not describe their sexualilty) ways to describe themselves (e.g. Cis Woman). 
```{r}
genderCount = data1$gender
levels(genderCount)
# My criteria is if they use more than one way to describe themselves
Prog = ifelse(genderCount == "\"Female-->sex, androgyne/butch, top/bottom\"", 1, ifelse(genderCount == "\"Hetero-Male\"", 1, ifelse(genderCount == "Cis Female", 1, ifelse(genderCount == "Cis Woman" , 1, ifelse(genderCount == "Cis-man", 1, ifelse(genderCount == "Female (cis)", 1, ifelse(genderCount == "Female, Cis-gender", 1, ifelse(genderCount == "Female/she", 1, ifelse(genderCount == "She, her, hers Female", 1, ifelse(genderCount == "Woman (she/her)" , 1, ifelse(genderCount == "Man/Male", 1, ifelse(genderCount == "\"Female--cisgender\"", 1, ifelse(genderCount == "Cis woman", 1, ifelse(genderCount == "Cis-Male" , 1, ifelse(genderCount == "Cismale", 1, ifelse(genderCount == "Female (Cisgender)" , 1, ifelse(genderCount == "Female Cis", 1, ifelse(genderCount == "Female/masculine" , 1, ifelse(genderCount == "He/him", 1, ifelse(genderCount == "Man/goes by he/him", 1, 0))))))))))))))))))))
head(Prog)
sum(Prog)

```

Now I am doing the same for the ethnicity variable and creating the following categories: black, hispanic, multi (i.e. multiracial), and other ethnicity (otherEth).  Therefore, white is the reference category.
```{r}
ethLevels = as.factor(data1$eth)
levels(ethLevels)

black = ifelse(data1$eth == "Af. Am.", 1, ifelse(data1$eth == "African American", 1, ifelse(data$eth == "African-American", 1, ifelse(data1$eth == "Africian American", 1, ifelse(data1$eth == "black", 1, ifelse(data1$eth == "Black - African American", 1, ifelse(data1$eth == "Black/African American", 1, ifelse(data1$eth == "AA", 1, ifelse(data1$eth ==  "African American Black" , 1, ifelse(data1$eth == "Blacc", 1, ifelse(data1$eth == "Black", 1, ifelse(data1$eth == "Missing", "Missing",0))))))))))))


hispanic =  ifelse(data1$eth ==   "hispanic", 1, ifelse(data1$eth == "H", 1, ifelse(data1$eth == "Hispanic" , 1, ifelse(data1$eth == "Hispanic/Latina", 1, ifelse(data1$eth == "Latina", 1, ifelse(data1$eth == "Latino/Hispanic", 1, ifelse(data1$eth == "Latino", 1, 0)))))))  

multi = ifelse(data1$eth == "hispanic/white", 1, ifelse(data1$eth == "many", 1, ifelse(data1$eth == "Mixed", 1, ifelse(data1$eth == "White & Latinx", 1, ifelse(data1$eth == "\"M\"" , 1, ifelse(data1$eth ==  "African, Irish, American", 1, ifelse(data1$eth == "black + other", 1, ifelse(data1$eth == "Caucasian/Hispanic", 1, ifelse(data1$eth == "m", 1, ifelse(data1$eth == "Many",1, ifelse(data1$eth == "Mix", 1, ifelse(data1$eth == "Mixed white/South Asian", 1, ifelse(data1$eth == "Multiethnic Afrolatina + white", 1, ifelse(data1$eth == "Multiracial" , 1, ifelse(data1$eth ==  "White/mixed", 1,0))))))))))))))) 

otherEth = ifelse(data1$eth == "\"Indian\"", 1, ifelse(data1$eth == "Asian", 1, ifelse(data1$eth == "\"Greek\"", 1, ifelse(data1$eth == "ai", 1, ifelse(data1$eth == "Native American", 1, ifelse(data1$eth == "None", 1, ifelse(data1$eth == "Asian Pacific Islander", 1, ifelse(data1$eth == "Filipino", 1, ifelse(data1$eth == "Other",1, 0)))))))))
```
Here I am creating a missing data identifier for the sexual orientation variable "sexorien".  I have to create a unique missing variable for each variable separately, because missing data must be deleted from the model.  

For example, if I wanted to assess whether missing data across all variables is related to any of the included variables, I would create a missing variable that is a 1 anytime any variable has a missing value and zero otherwise.  However, because I need to delete all missing values before I run the analysis, I would end up deleting all the 1's in the missing data variable so there would be no variation.

Therefore, if I create a missing variable indicator for one variable (in the example below I create a missing data variable for sex orientation = sexorien), then delete the missing values for the other variables (female, otherGI, black, hispanic, multi, otherEth, age) I can delete the missing values for all other variables and keep missing values for sex orientation that are not also missing for other variables.

For example, if one person had a missing value for both sexual orientation and gender, then using this process they would be deleted from the dataset.

```{r}
missingSexOrien = data1$sexorien
missingSexOrien = as.data.frame(ifelse(data1$sexorien == "Missing", 1, 0))
colnames(missingSexOrien) = c("missingSexOrien")
dim(missingSexOrien)


dataAnalysis = cbind(missingSexOrien, data1SexOrien, Prog, female, otherGI, black, hispanic, multi, otherEth, age = data1$age, site = data1$site, PreCompetent = data1$PreCompetent,PreConfident = 	data1$PreConfident,	PreComfort = data1$PreComfort)

dataAnalysis = as.data.frame(dataAnalysis)
head(dataAnalysis)
dataAnalysis = apply(dataAnalysis, 2, function(x){ifelse(x == "Missing", NA, x)})
dataAnalysis = as.data.frame(dataAnalysis)
head(dataAnalysis)
dataAnalysis = na.omit(dataAnalysis)
dataAnalysis = as.data.frame(dataAnalysis)
dim(dataAnalysis)
head(dataAnalysis)
write.csv(dataAnalysis, "dataAnalysis.csv", row.names = FALSE)
```
Here I have an example of the model with missing values found in the sexual orientation variable indicated as a 1 for missing and 0 for non-missing.  Then I include the other covariates in the model and allow the model to have different intercepts for different sites, which are the locations that each program took place at.

Overall, none of the included covariates are statistically significantly related to missing values in sexual orientation.

There were no other gender identity because there are no cases
Needed to change the numeric values to numeric, because they were seen as factors
```{r}
library(Zelig)
ageNum = as.numeric(dataAnalysis$age)
PreCompetentNum = as.numeric(dataAnalysis$PreCompetent)
PreConfidentNum =as.numeric(dataAnalysis$PreConfident)
PreComfortNum = as.numeric(dataAnalysis$PreComfort)
head(dataAnalysis)
dataAnalysis = cbind(dataAnalysis, ageNum, PreCompetentNum, PreConfidentNum, PreComfortNum)
z.out1 <- zelig(missingSexOrien ~ female +data1SexOrien + ageNum +Prog + black + hispanic + multi + otherEth + site + PreCompetentNum + PreConfidentNum +PreComfortNum, model = "logit", data = dataAnalysis, cite = FALSE)
summary(z.out1)

.05/27
```
