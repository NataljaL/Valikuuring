---
title       : Sissejuhatus R-i
description : Siin saab tutvuda tarkvaraga R ja teha esimesi samme programmeerimises :) Alustame!



--- type:NormalExercise lang:r xp:100 skills:1 key:ca824b1118
## R kui kalkulaator

R-i võib kasutada kui kalkulaatorit. Toome ära mõned tehtemärgid:

- Liitmine: `+`
- Lahutamine: `-`
- Korrutamine: `*`
- Jagamine: `/`
- Astendamine: `^` või `**`
- Jääk jagamisel: `%%`

ja paar funktsiooni:

- Siinus: `sin()`
- Naturaallogaritm: `log()`
- Arvu jääk jagamisel: `%%`


<!--The ^ operator raises the number to its left to the power of the number to its right: for example 3^2 is 9.
The modulo returns the remainder of the division of the number to the left by the number on its right, for example 5 modulo 3 or 5 %% 3 is 2.
With this knowledge, follow the instructions below to complete the exercise.-->

*** =instructions

- Tee läbi Näited 1 kuni 4, ühe rea täitmiseks R script-is vajuta `Ctrl + Enter`.
- Pane tähele, et sümbol  `#` on kasutatud kommenteeritud ridade eristamiseks.
- Kirjuta Ülesandesse tehe, mis leiaks $$(0.5 \cdot 6) ^3 - 4 $$ ja vajuta 'Submit Answer'.

<br>

Kui tekib küsimus mõne R funktsiooni või märgi kohta, näiteks jäägi kohta, siis kirjuta R konsooli: `?"%%"`.



*** =hint

* Kui sul tekkisid probleemid märgi `^` leidmisega, siis kasuta selle asemel `**`.  
* Kümnendemurru sisestamiseks kasuta punkti: `0.5`. 
 





*** =pre_exercise_code
```{r}
#polegi
```

*** =sample_code
```{r}
# Näide 1. Liitmine. 
3 + 4

# Näide 2. Jagamine.
8 / 2

# Näide 3. Mis on jääk, kui jagada 9 arvuga 2?
9 %% 2

# Näide 4. Pikem avaldis.
7 * (8 + 9) - 10 / 5

#Ülesanne


```

*** =solution
```{r}
# Näide 1. Liitmine. 
3 + 4

# Näide 2. Jagamine.
8 / 2

# Näide 3. Funktsiooni kasutamine.
9 %% 2

# Näide 4. Pikem avaldis.
7 * (8 + 9) - 10 / 5

#Ülesanne
(0.5 * 6)^3 - 4

```

*** =sct
```{r}
test_output_contains("(0.5 * 6)^3 - 4", incorrect_msg = "Vale vastus. Proovi uuesti!")
success_msg("Tubli! Suundu järgmise ülesande juurde.")
```

<--! Järmine harjutus-->
