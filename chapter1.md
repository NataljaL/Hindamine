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
attitude[5:11]

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
attitude[5:11]

# Loo vektor väärtustega 1,2,..,10:
1:10

# Võta vektorist `temperatuur` 2., 4., ..., 20. väärtused:
temperatuur[(1:10)*2]
```

*** =sct
```{r}

```
