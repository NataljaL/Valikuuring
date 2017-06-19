---
title       : Tõenäosus
description : Insert the chapter description here

--- type:NormalExercise lang:r xp:100 skills:1 key:4186379252
## Tõenäosusruum

`R`-i jaoks on tõenäosusruumiks objekt tüüpi `data.frame`, mis sisaldab lõpliku elementaarsündmuste hulga $\Omega$ kõikvõimalike väärtuseid ning tõenäosusi, millega need sündmused võivad realiseeruda. 

Paketis `prob` on olemas eraldi funktsioon tõenäosusruumi loomiseks: 

`probspace(x, probs)`, 

kus `x` on elementaarsündmuste ruum ja `probs` tõenäosuste vektor, mille pikkus on võrdne elementaarsündmuste ruumi elementida arvuga ja mille väärtuste summa on 1.

*** =instructions

* Tee läbi näide 1. Pane tähele, kuidas luuakse tõenäosusruum 6-tahulise täringu visketulemuste jaoks.
* Tee läbi näide 2. Selles on ära toodud alternatiivne käsk tõenäosusruumi loomiseks täringu viske korral.
* Ülesanne. Loo tõenäosusruum nimega `mynt.ruum` analoogiliselt näitega 1, mis vastab ebaausa mündi viske tulemustele. Vapi tõenäosus on 0.3. Kasuta funktsiooni `tosscoin()`. 
* Katseta aknas `R Console`, kas käsuga `tosscoin()` on võimalik luua tõenäosusruumi ebaausa mündi visketulemuste kirjeldamiseks?

*** =hint

*** =pre_exercise_code
```{r}
source_github <- function(user = "cran", package = "prob") {
  
  library(httr)
  package_source <- paste0(user, "/",package, "/")
  url <- paste0("https://api.github.com/repos","/", package_source, "git/trees/master?recursive=1")
  req <- GET(url)
  stop_for_status(req)
  filelist <- unlist(lapply(content(req)$tree, "[", "path"), use.names = F)
  R_files <- filelist[grep("R/",filelist)]
  
  for(file in R_files) {
    url <- paste0("https://raw.githubusercontent.com/", package_source, "master/", file)
    source(url)
  }
}
save(file = "source_github.Rda", source_github)

source_github()

source_github <- function(user = "cran", package = "combinat") {
  
  library(httr)
  package_source <- paste0(user, "/",package, "/")
  url <- paste0("https://api.github.com/repos","/", package_source, "git/trees/master?recursive=1")
  req <- GET(url)
  stop_for_status(req)
  filelist <- unlist(lapply(content(req)$tree, "[", "path"), use.names = F)
  R_files <- filelist[grep("R/",filelist)]
  
  for(file in R_files) {
    url <- paste0("https://raw.githubusercontent.com/", package_source, "master/", file)
    source(url)
  }
}
save(file = "source_github.Rda", source_github)

source_github()
```

*** =sample_code
```{r}
# Näide 1. 6-tahulise täringu veeretamise tulemused ja vastav tõenäosusruum.
taring <- rolldie(1)                # elementaarsündmuste ruum 
p <- rep(1/6, times=6)              # tõenäosuste vektor
taring.ruum1 <- probspace(taring, p) # vastav tõenäosusruum

# Näide 2. Alternatiivne viis tõenäosusruumi defineerimiseks
taring.ruum2 <- rolldie(1, makespace = TRUE)

# Ülesanne. Ühe müdni viskamisele vastav tõenäosusruum
mynt <- _________________
p <- _________________
mynt.ruum <- ____________

```

*** =solution
# Näide 1. 6-tahulise täringu veeretamise tulemused ja vastav tõenäosusruum.
taring <- rolldie(1)                # elementaarsündmuste ruum 
p <- rep(1/6, times=6)              # tõenäosuste vektor
taring.ruum1 <- probspace(taring, p) # vastav tõenäosusruum

# Näide 2. Alternatiivne viis tõenäosusruumi defineerimiseks
taring.ruum2 <- rolldie(1, makespace = TRUE)

# Ülesanne. Ebaausa müdni viskamisele vastav tõenäosusruum
mynt <- tosscoin(1)
p <- c(0.3, 0.7)
mynt.ruum <- probspace(mynt, p)

```{r}

```

*** =sct
```{r}

```
