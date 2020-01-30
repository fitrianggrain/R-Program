# R-Program
#Setting Working directory
getwd()
setwd("E:/fitri/semester 5/SDS 2019/QUIZ") 

#import data secara import dataset 
library(readxl)
DATA_UNTUK_QUIZ <- read_excel("E:/fitri/semester 5/SDS 2019/QUIZ/DATA UNTUK QUIZ.xlsx")
View(DATA_UNTUK_QUIZ)

summary(DATA_UNTUK_QUIZ) #mengetahui banyaknya NA

#Handling Missing value
is.na(DATA_UNTUK_QUIZ) #returns TRUE of x is missing
sum(is.na(DATA_UNTUK_QUIZ)) #count the missing value

#numerik missing diisikan rata2 
DATA_UNTUK_QUIZ$Pendudukmiskin2017[is.na(DATA_UNTUK_QUIZ$Pendudukmiskin2017)]=mean(DATA_UNTUK_QUIZ$Pendudukmiskin2017, na.rm = TRUE)
DATA_UNTUK_QUIZ$Jumlahpenduduk[is.na(DATA_UNTUK_QUIZ$Jumlahpenduduk)]=mean(DATA_UNTUK_QUIZ$Jumlahpenduduk, na.rm = TRUE)
DATA_UNTUK_QUIZ$LuasWilayahKM2[is.na(DATA_UNTUK_QUIZ$LuasWilayahKM2)]=mean(DATA_UNTUK_QUIZ$LuasWilayahKM2, na.rm = TRUE)
DATA_UNTUK_QUIZ$UMP[is.na(DATA_UNTUK_QUIZ$UMP)]=mean(DATA_UNTUK_QUIZ$UMP, na.rm = TRUE)


sum(is.na(DATA_UNTUK_QUIZ)) 
# untuk mengecek bahwa data yang missing telah diperbaiki
#nilai mean dan median
summary(DATA_UNTUK_QUIZ)


#NILAI UMP < 2 juta
library(dplyr)
UMP_kurang_dari_2jt=filter(DATA_UNTUK_QUIZ, UMP<2000000)
View(UMP_kurang_dari_2jt)

#provinsi yang tercemar berat
library(dplyr)
provinsi_tercemar=filter(DATA_UNTUK_QUIZ, Pencemaranairsungai == "cemar berat")
View(provinsi_tercemar)







