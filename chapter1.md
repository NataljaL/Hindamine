---
title       : Hindamine R-is
description : siia mingi tekst...


--- type:NormalExercise lang:r xp:100 skills:1 key:af3c1cf198
## Üldkogumi parameetrite hindamine R-is

Selles praktikumis keskendume punkthinnangute ja vahemikhinnangute leidmisele. Vahemikhinnangu leidmise algoritmid põhinevad hinnangute jaotustel, millest võib mõelda kui mängu:
kui oleks võimalik võtta juhuslik valim uuesti ja uuesti ning igas valimis arvutada näiteks valimikeskmine, siis saadud valimikeskmiste jaotus ongi nn hinnangu jaotuseks.

Tuleb välja, et paljude hinnangute korral saab nende jaotuse lähendada normaaljaotusega teatud parameetritega. Selle tulemuseks on kuulus tsentraalne piirteoreem.

Et oleks võimalik uurida hinnangute jaotusi, me alustame praktikumi tehniliste vahenditega, mille abil saame korduvaid valimeid simuleerida.

*** =instructions

  *  DataCamp-i keskkonna eripära on see, et kui on tarvis käivitada koodi, mis jätkub mitmel real, siis tuleks esmalt need read ära märkida ja seejärel vajutada `Ctrl+Enter` või nuppu `Run Code`.
  *  Käivita 3 rida, mis vastab tsüklile (algab sõnaga `for`).
  *  Vajuta nuppu `submit`, et suunduda järgmise harjutuse juurde.

*** =hint

   * Kui mingil põhjusel ridu ei õnnestu märgistada, siis lihtsalt vajuta nuppu `submit`.

*** =pre_exercise_code
```{r}
# pre exercise code here
```


*** =sample_code
```{r}
# Käivita mind!
for(i in 1:6) {
  print("I am a loop")
}
```



*** =solution
```{r}
# Käivita mind!
for(i in 1:6) {
  print("I am a loop")
}
```



*** =sct
```{r}
test_error()
success_msg("Hea töö!")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:6664db2256
## Indeksid ja sulud
Olete vektoritega juba varem kokku puutunud. Siin uurime neid veel kord. Vektorite abil saab hoida sama tüüpi väärtuseid ja nendele väärtustele vastavad vektoris indeksid: esimesel vektori elemendil on indeks 1, teisel 2 jne.

Väärtust saab muuta/vaadata, kasutades selleks vektori nime järel nurksulgudes vastavat indeksit, näiteks `linnad[1]`. Kasutades nurksulgudes ühe indeksi asemel indeksite vektorit, saab vektorist välja võtta mitut elementi korraga, näiteks `linnad[1:3]` annab kolme esimest elementi vektoris `linnad`.

Indeksite abil on võimalik elementide asukohta vahetada. Uuri järgmises näiteks, kuidas saab manipuleerida indeksitega.

*** =instructions
* Loome vektori `nimed` (käsk on juba kirjutatud).
* Uuri indeksite tööd käivitades näitekäske.
* Nurksulgude ja vektori `nimed` abil loo uus vektor `tydrukud`, mis sisaldab nimesid "Liisa" ja "Anna" (just sellises järjekorras).
* Nurksulgude ja vektori `nimed` abil loo uus vektor `poisid`, mis sisaldab nimesid "Peeter" and "Heikki" (just sellises järjekorras).

*** =hint
* Pane tähele, et tühikud vektori nime ja nurksulgude vahel võivad tekitada veateateid.
* Indeksite vektorid `c(1,2)` ja `c(2,1)` annavad erinevaid tulemusi. Elementide järjekord on oluline!

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Vektori nimed loomine
nimed <- c("Marek", "Peeter", "Liisa", "Anna")

# Vektori 1. element
nimed[1]

# Muudame 1. elementi
nimed[1] <- "Heikki"

# 1. ja 3. element
nimed[c(1, 3)]

# Kasuta indekseid ja sulge, et moodustada vektorist nimed kaks vektorit; ära unusta elementide järjekorda!
tydrukud <-
poisid <-
```

*** =solution
```{r}
# Vektori nimed loomine
nimed <- c("Marek", "Peeter", "Liisa", "Anna")

# Vektori 1. element
nimed[1]

# Muudame 1. elementi
nimed[1] <- "Heikki"

# 1. ja 3. element
nimed[c(1, 3)]

# Kasuta indekseid ja sulge, et moodustada vektorist nimed kaks vektorit; ära unusta elementide järjekorda!
tydrukud <- nimed[c(3, 4)]
poisid <- nimed[c(2, 1)]
```

*** =sct
```{r}
test_object("tydrukud", incorrect_msg = "Vektor pole õige. Kas kasutasid viitamist elementidele vektorist nimed?")
test_object("poisid", incorrect_msg = "Vektor pole õige. Kas kasutasid viitamist elementidele vektorist nimed? Kontrolli ka elementide järjekorda.")

test_error()

# Final message the student will see upon completing the exercise
success_msg("Sellised siis indeksid... ")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:89ff2d98a8
## Lihtsad vektorid
Võib juhtuda, et vaja läheb pikka indeksite vektorit. Fuktsiooni `c()` kaudu oleks sellise vektori loomine tõlikas. Õnneks, pakub `R` selle jaoks lihtsaid lahendusi.

Täisarvulise vektori jaoks saab kasutada meetodit `algus:lõpp`, mis loob vektorit kõikide täisarvudega alates arvust `algus` kuni arvuni `lõpp`. Kahe järgmise rea tulemused on samad: 

`1:5`  
`c(1,2,3,4,5)`

*** =instructions
*  Loo täisarvuline vektor väärtustega 1 kuni 5 (kaasaarvatud).
  *  Loo täisarvuline vektor väärtustega 2, 4, ..., 10.
  *  Vektor `temperatuur` sisaldab ühe kuu õhutemperatuure (mõõdetud kell 12:00 Otepääl). Võta sellest ühe nädala temperatuure alatest 5-st väärtusest.
  *  Kasuta märki `:`, et luua täisarvuline vektor väärtustega 1, 2, ..., 10.
  *  Võta vektorist `temperatuur` väärtused alatest  2-st kuni 20 sammuga 2. Temperatuuri väärtused peavad vastama vektori `temperatuur` elementidele indeksitega: 2, 4, .. , 20.

*** =hint
*  Kõigepealt läheb vaja vektorit elementidega 2, 4, .. , 20. Uuri näidet, kuidas sellist vektorit luua.
  *  Seejärel kasuta neid väärtuseid koos kandiliste sulgudega `[ ]`.

*** =pre_exercise_code
```{r}
temperatuur <- c(16,14,17,13,11,19,20,18,17,17,17,14,13,16,16,15,14,14,13,10)
```

*** =sample_code
```{r}
# Vektor temperatuur on eelnevalt loodud

# Loo vektor väärtustega 1,2,..,5:
1:5

# Loo vektor väärtustega 2, 4, .. , 10:
(1:5)*2

# Ühe nädala temperatuurid alates 5-st päevast (5, 6, 7, 8, 9, 10, 11):
temperatuur[5:11]

# Loo vektor väärtustega 1,2,..,10:


# Võta vektorist `temperatuur` 2., 4., ..., 20. väärtused:

```

*** =solution
```{r}
# Vektor temperatuur on eelnevalt loodud

# Loo vektor väärtustega 1,2,..,5:
1:5

# Loo vektor väärtustega 2, 4, .. , 10:
(1:5)*2

# Ühe nädala temperatuurid alates 5-st päevast (5, 6, 7, 8, 9, 10, 11):
temperatuur[5:11]

# Loo vektor väärtustega 1,2,..,10:
1:10

# Võta vektorist `temperatuur` 2., 4., ..., 20. väärtused:
temperatuur[(1:10)*2]
```

*** =sct
```{r}
# submission correctness tests

test_student_typed("1:10", not_typed_msg = "Kas kasutasid märki `:` vektori loomisel?")
test_output_contains("temperatuur[(1:10)*2]")
test_output_contains("temperatuur[2*(1:10)]")

# test if the students code produces an error
test_error()

# Final message the student will see upon completing the exercise
success_msg("Tubli töö!")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:865e09760c
## Tsükkel `for`
Programmeerimises ja simuleerimisülesannetes on vaja korrata ühte ja sama tegevust mitu korda (näiteks jaotuse kontrollimiseks). Tsükkel `for` on kõige levinum viis korduste teostamiseks. Selle süntaks näeb välja järgmiselt:

`for (loendur in vektor) {`
  `käsk`
 ` veel käske`
`}`


Tsükkel `for` läbib kõiki väärtuseid täisarvulises vektoris suurendades iga kord loenduri väärtuse ühe võrra. Tsükli alguses võrdub loendur vektori esimese elemendiga, seejärel teisega jne.

Looegiliste sulgude vahel asub tsükli "keha", mis koosneb käskudest. Nendes saab kasutada loenduri jooksvat väärtust. Kõiki käske korratakse kuni loendur saavutab vektori viimase väärtuste.

*** =instructions
*   Pane tähele, et siin keskkonnas DataCamp tuleks tsükli käivitamiseks kõik selle käsud ära m'rgistada ja seejärel vajutada `Ctrl+Enter` või nuppu `Submit` (terve harjutuse koodi käivitamiseks).
 *   Näites 1 läbib tsükkel kõiki tähti etteantud vektoris.
 *   Näites 2 läbib tsükkel numbreid 1 kuni 5 ja liidab igale arvule juurde 5.
 *   Koosta tsükkel, mis väljastab teksti `One more time!` 27 korda (ütleme, et Daft Punk'i samanimelise laulu auks).
  *  Vihjed: (1) Pea meeles, et käsk `1:n` loob täisarvulise vektori pikkusega `n`. (2) Tsükli sees tuleks kasutada funktsiooni `print()` teksti väljastamiseks.


*** =hint
 * Pole vahet, kuidas sa oma loendurit nimetad. Näites 2 on kasutatud muutuja nime  `i` loenduri jaoks.
    * Oma ülesandes pole vaja kasutada loenduri jooksvat väärtust.
    * Ära unusta panna prinditavat teksti jutumärkide vahele!

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Näide 1
for(letter in c("a","b","c","d")) {
  print(letter)
}

# Näide 2
for(i in 1:5) {
  print(i + 5)
}

# Kirjuta oma tsükke, mis väljastab  "One more time!" 27 korda:

```

*** =solution
```{r}
# Näide 1
for(letter in c("a","b","c","d")) {
  print(letter)
}

# Näide 2
for(i in 1:5) {
  print(i + 5)
}

# Kirjuta oma tsükke, mis väljastab  "One more time!" 27 korda:
for(i in 1:27) {
  print("One more time!")
}
```

*** =sct
```{r}
test_output_contains("'One more time!'", times = 27, incorrect_msg = "Kas prindid tsüklis teksti 'One more time!' koos hüumärgiga 27 korda?")

# test if the students code produces an error
test_error()

# Final message the student will see upon completing the exercise
success_msg("Suurepärane töö! Kordused on tarkuse ema :)")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:6ff62531f7
## Punkthinnang
Tuleme tagasi statistika juurde ja uurime siin parameetrite hindamist: meil on olemas juhuslik valim ühest üldkogumist ning kasutades valimiandmeid püüame teha järeldusi üldkogumi parameetrite kohta.

Lihtsamatel juhtudel huvitume ühe tunnuse keskväärtuse hindamisest. Kuna andmed on kogutud vaid ühe üldkogu osa pealt, siis saame leida vaid hinnangu sellele. Kõige levinumad parameetrid mida hannatakse on üldkogumi keskväärtus $\mu$ ja üldkogumi dispersioon $\sigma^2$. Nende hinnangud valimis on vastavalt valimikeskmine $\bar x$ ja valimidispersioon $s^2$. 

Statistikas tähistatakse tavaliselt hinnanguid katusemärgi $^$ abil. Näiteks, võite edaspidi näha hinnangu üldkogumi keskväärtusele $\hat{\mu} = \bar{x}$.
*** =instructions

 *   Create object points
  *  Estimate the expected value of points. If you cant remember the name of the R function you need, use your favourite search engine or take a hint.
  *  Estimate the population standard deviation of points.
  *  Combine the estimates to the estimates vector (replace NA). Notice how c() can be used to give names to the values.
  *  Print out the estimates vector, with the values rounded to 2 digits.
*** =hint

   * The table above shows the relationships between the sample statistics and the population parameters.
*    Use the table to figure out which operation you could use to produce the estimate.
 *   Mean can be computed with mean()


*** =pre_exercise_code
```{r}
temperatuur <- c(16,14,17,13,11,19,20,18,17,17,17,14,13,16,16,15,14,14,13,10)
```

*** =sample_code
```{r}
# learning2014 is available

# create object points using the learning2014 data.frame
points <- learning2014$points

# estimate the expected value of points
mu_hat <- 
  
# estimate the population standard deviation of points
sigma_hat <- sd(points)

# Combine the estimates to a named vector and print out the rounded values
estimates <- c("mu_hat" = NA, "sigma_hat" = NA)
round(estimates, digits = 2)

```

*** =solution
```{r}
# learning2014 is available

# create object points using the learning2014 data.frame
points <- learning2014$points

# estimate the expected value of points
mu_hat <- mean(points)

# estimate the population standard deviation of points
sigma_hat <- sd(points)

# Print out the estimated values
estimates <- c("mu_hat" = mu_hat, "sigma_hat" = sigma_hat)
round(estimates, digits = 2)

```

*** =sct
```{r}
# submission correctness tests

test_function("mean", args=c("x"))
test_object("mu_hat", incorrect_msg = "Please create the object mu_hat. Use the correct function on the points vector.")

test_output_contains("round(estimates, 2)", incorrect_msg = "Please insert your hat objects to the estimates vector and do not remove the row with `round()`")

# test if the students code produces an error
test_error()

# Final message the student will see upon completing the exercise
success_msg("Very nice! You get full points for point estimation.")
```
