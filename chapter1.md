---
title       : Hindamine R-is
description : Punkt- ja vahemikhinnangute leidmine R-i abil. Tsükli kirjutamine `for` abil.


--- type:NormalExercise lang:r xp:100 skills:1 key:af3c1cf198
## Üldkogumi parameetrite hindamine R-is

Selles praktikumis keskendume punkthinnangute ja vahemikhinnangute leidmisele. Vahemikhinnangu leidmise algoritmid põhinevad hinnangute jaotustel, millest võib mõelda kui mängu:
kui oleks võimalik võtta juhuslikku valimit uuesti ja uuesti ning igas valimis arvutada näiteks valimikeskmine, siis saadud valimikeskmiste jaotus ongi nn hinnangu jaotuseks.

Tuleb välja, et paljude hinnangute korral saab nende jaotust lähendada normaaljaotusega teatud parameetritega. See tuleneb kuulsast tsentraalsest piirteoreemist.

Et oleks võimalik uurida hinnangute jaotusi, me alustame praktikumi tehniliste vahenditega, mille abil saame simuleerida korduvaid valimeid.

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
  print("Tere!")
}
```



*** =solution
```{r}
# Käivita mind!
for(i in 1:6) {
  print("Tere!")
}
```



*** =sct
```{r}
test_error()
success_msg("Hea töö!")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:6664db2256
## Indeksid ja sulud
Olete vektoritega juba varem kokku puutunud. Siin uurime neid veel kord. Vektorite abil saab hoida sama tüüpi väärtuseid. Nendele väärtustele vastavad vektori indeksid: esimesel vektori elemendil on indeks 1, teisel 2 jne.

Väärtust saab muuta/vaadata, kasutades selleks vektori nime järel nurksulgudes vastavat indeksit, näiteks `linnad[1]`. Kasutades nurksulgudes ühe indeksi asemel indeksite vektorit, saab vektorist välja võtta mitut elementi korraga, näiteks `linnad[1:3]` annab kolme esimest elementi vektorist `linnad`.

Indeksite abil on võimalik elementide asukohta vahetada. Uuri järgmises näites, kuidas saab manipuleerida indeksitega.

*** =instructions
* Loo vektor `nimed` (käsk on juba kirjutatud).
* Uuri indeksite tööd käivitades näitekäske.
* **Ülesanne 1.** Nurksulgude ja vektori `nimed` abil loo uus vektor `tydrukud`, mis sisaldab nimesid "Liisa" ja "Anna" (samas järjekorras).
* **Ülesanne 2.** Nurksulgude ja vektori `nimed` abil loo uus vektor `poisid`, mis sisaldab nimesid "Peeter" and "Heikki" (samas järjekorras).

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

# Ülesanne 1
tydrukud <-

# Ülesanne 2
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

# Ülesanne 1
tydrukud <- nimed[c(3, 4)]

# Ülesanne 2
poisid <- nimed[c(2, 1)]
```

*** =sct
```{r}
test_object("tydrukud", incorrect_msg = "Vektor pole õige. Kas kasutasid viitamist elementidele vektorist `nimed`?")
test_object("poisid", incorrect_msg = "Vektor pole õige. Kas kasutasid viitamist elementidele vektorist `nimed`? Kontrolli ka elementide järjekorda.")

test_error()

# Final message the student will see upon completing the exercise
success_msg("Sellised ongi indeksid! ")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:89ff2d98a8
## Lihtsad vektorid
Võib juhtuda, et läheb vaja  pikka indeksite vektorit. Fuktsiooni `c()` kaudu oleks sellise vektori loomine tülikas. Õnneks, pakub `R` selle jaoks lihtsaid lahendusi.

Täisarvulise vektori loomiseks saab kasutada  `algus:lõpp` meetodit, mis loob vektori täisarvudega alates arvust `algus` kuni arvuni `lõpp`. Kahe järgmise rea tulemused on samad: 

`1:5`  
`c(1,2,3,4,5)`

*** =instructions
  * **Näide 1.** Uuri, kuidas on loodud täisarvuline vektor väärtustega 1 kuni 5 (kaasaarvatud).
  * **Näide 2.** Uuri, kuidas on loodud täisarvuline vektor väärtustega 2, 4, ..., 10.
  * **Näide 3.** Muutuja `temperatuur` sisaldab ühe kuu õhutemperatuure (mõõdetud kell 12:00 Otepääl). Uuri, kuidas on sellest võetud seitsme päeva temperatuurid alatest vektori 5. elemendist.
  * **Ülesanne 1.** Kasuta märki `:`, et luua täisarvuline vektor väärtustega 1, 2, ..., 10.
  * **Ülesanne 2.** Võta vektorist `temperatuur` elemendid alatest  2. kuni 20-ni sammuga 2. Temperatuuri väärtused peavad vastama vektori `temperatuur` elementidele indeksitega: 2, 4, .. , 20.

*** =hint
*  Kõigepealt läheb vaja vektorit elementidega 2, 4, .. , 20. Uuri näidet, kuidas sellist vektorit luua.
  *  Seejärel kasuta neid väärtuseid koos kandiliste sulgudega `[ ]`.

*** =pre_exercise_code
```{r}
temperatuur <- c(16,14,17,13,11,19,20,18,17,17,17,14,13,16,16,15,14,14,13,10)
```

*** =sample_code
```{r}
# Näide 1. Vektor väärtustega 1,2,..,5:
1:5

# Näide 2. Vektor väärtustega 2, 4, .. , 10:
(1:5)*2

# Näide 3.
# Vektor temperatuur on eelnevalt loodud, uuri selle väärtuseid:
temperatuur

# Ühe nädala temperatuurid alates 5. elemendist (5, 6, 7, 8, 9, 10, 11):
temperatuur[5:11]

# Ülesanne 1. Vektor väärtustega 1,2,..,10:


# Ülesanne 2. Võta vektorist `temperatuur` 2., 4., ..., 20. väärtused:

```

*** =solution
```{r}
# Näide 1. Vektor väärtustega 1,2,..,5:
1:5

# Näide 2. Vektor väärtustega 2, 4, .. , 10:
(1:5)*2

# Näide 3.
# Vektor temperatuur on eelnevalt loodud, uuri selle väärtuseid:
temperatuur

# Ühe nädala temperatuurid alates 5. elemendist (5, 6, 7, 8, 9, 10, 11):
temperatuur[5:11]

# Ülesanne 1. Vektor väärtustega 1,2,..,10:
1:10

# Ülesanne 2. Võta vektorist `temperatuur` 2., 4., ..., 20. väärtused:
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
Programmeerimis- ja simuleerimisülesannetes on vaja sageli korrata ühte ja sama tegevust mitu korda (näiteks jaotuse kontrollimiseks). Tsükkel `for` on kõige levinum viis korduste teostamiseks. Selle süntaks näeb välja järgmiselt:

`for (loendur in vektor) {`<br/> 
        <span style="display:inline-block; width: 1cm;"></span> `käsk`<br/> 
 <span style="display:inline-block; width: 1cm;"></span>` veel käske`<br/> 
`}`


Tsükkel `for` läbib kõiki väärtuseid täisarvulises vektoris suurendades iga kord loenduri väärtust ühe võrra. Tsükli alguses võrdub loendur vektori esimese elemendiga, seejärel teisega jne.

Loogiliste sulgude vahel asub tsükli "keha", mis koosneb käskudest. Käsud võivad omakorda kasutada loenduri jooksvat väärtust. Käske korratakse kuni loendur saavutab vektori viimase väärtuse.

*** =instructions
 
 *   Pane tähele, et siin keskkonnas DataCamp tuleks tsükli käivitamiseks kõik vastavad käsud ära märgistada ja seejärel vajutada `Ctrl+Enter` või nuppu `Submit` (terve harjutuse koodi käivitamiseks).
 *   Näites 1 läbib tsükkel kõiki tähti etteantud vektoris.
 *   Näites 2 läbib tsükkel numbreid 1 kuni 5 ja liidab igale numbrile juurde 5.
 *   Koosta tsükkel, mis väljastab teksti `One more time!` 27 korda (ütleme, et Daft Punk'i samanimelise laulu auks).
 *  Vihjed: (1) Pea meeles, et käsk `1:n` loob täisarvulise vektori pikkusega `n`. (2) Tsükli sees tuleks kasutada funktsiooni `print()` teksti väljastamiseks.


*** =hint
 * Pole vahet, kuidas sa oma loenduri nimetad. Näites 2 on kasutatud muutuja nime  `i` loenduri jaoks.
 * Oma ülesandes pole vaja kasutada loenduri jooksvat väärtust.
 * Ära unusta panna prinditavat teksti jutumärkidesse!

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

# Kirjuta oma tsükkel, mis väljastab  "One more time!" 27 korda:

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

# Kirjuta oma tsükkel, mis väljastab  "One more time!" 27 korda:
for(i in 1:27) {
  print("One more time!")
}
```

*** =sct
```{r}
test_output_contains("'One more time!'", times = 27, incorrect_msg = "Kas prindid tsüklis teksti 'One more time!' koos hüümärgiga 27 korda?")

# test if the students code produces an error
test_error()

# Final message the student will see upon completing the exercise
success_msg("Suurepärane töö! Kordused on tarkuse ema :)")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:6ff62531f7
## Punkthinnang
Tuleme tagasi statistika juurde ja uurime siin parameetrite hindamist: meil on olemas juhuslik valim ühest üldkogumist ning kasutades valimiandmeid püüame teha järeldusi üldkogumi parameetrite kohta.

Lihtsamatel juhtudel huvitume ühe ainsa tunnuse keskväärtuse hindamisest. Kuna andmeid on kogutud vaid ühe üldkogumi osa pealt, siis saame leida vaid hinnangu üldkogumi keskmisele. Kõige levinumad parameetrid, mida hinnatakse, on üldkogumi keskväärtus $\mu$ ja üldkogumi standardhälve $\sigma$. Nende hinnangud valimis on vastavalt valimikeskmine $\bar x$ ja valimi standardhälve $s$. 

Statistikas tähistatakse tavaliselt hinnanguid katusemärgi (hat) abil. Näiteks, võib edaspidi kohata tähistust  üldkogumi keskväärtuse hinnangule kujul $\hat{\mu} = \bar{x}$.
*** =instructions

 *   Ühe kuu temperatuuride vektor on juba loodud. Vaata.
  *  **Ülesanne 1.** Hinda temperatuuride keskväärtust. Kui sa ei mäleta, millist funktsiooni kasutada, siis võid googeldada või kasutada vihjet.
  *  **Ülesanne 2.** Hinda temperatuuride standardhälvet. Inglise keeles on standardhälve *standard deviation*.
  *  **Ülesanne 3.** Kombineeri mõlemad hinnangud ühte vektorisse (asenda `NA`). Pane ka tähele, kuidas käsus `c()` saab väärtustele anda nimesid.
  *  Väljasta saadud vektori väärtused ümardades neid 2 komakohani, käivitates olemasolevat funktsiooni `round()` (midagi rohkem ei pea sellele lisama).
 
*** =hint

 *   Valimikeskmist saab leida funktsiooni  `mean()` abil.
 *   Valimi standardhälvet saab leida funktsiooni  `sd()` abil.

*** =pre_exercise_code
```{r}
temperatuur <- c(16,14,17,13,11,19,20,18,17,17,17,14,13,16,16,15,14,14,13,10)
```

*** =sample_code
```{r}
# vektor temperatuur on juba loodud
temperatuur

# Ülesanne 1. Temperatuuride keskväärtuse hinnang:
mu_hat <- 
  
# Ülesanne 2. Temperatuuride standardhälbe hinnang:
sigma_hat <- 

# Ülesanne 3. Hinnangute kombineerimine vektorisse ja ümardamine:
hinnangud <- c("mu_hat" = NA, "sigma_hat" = NA)

round(hinnangud, digits = 2)

```

*** =solution
```{r}
# vektor temperatuur on juba loodud
temperatuur

# Ülesanne 1. Temperatuuride keskväärtuse hinnang:
mu_hat <- mean(temperatuur)
  
# Ülesanne 2. Temperatuuride standardhälbe hinnang:
sigma_hat <- sd(temperatuur)

# Ülesanne 3. Hinnangute kombineerimine vektorisse ja ümardamine:
hinnangud <- c("mu_hat" = mu_hat, "sigma_hat" = sigma_hat)

round(hinnangud, digits = 2)
```

*** =sct
```{r}
# submission correctness tests

test_function("mean", args=c("x"))
test_object("mu_hat", incorrect_msg = "Palun leia muutuja `mu_hat` väärtust. Kasuta õiget funktsiooni keskmise leidmiseks.")
test_object("sigma_hat", incorrect_msg = "Palun leia muutuja `sigma_hat` väärtust kasutades funktsiooni `sd()`.")

test_output_contains("round(hinnangud, 2)", incorrect_msg = "Asenda väärtused `NA` vektoris `hinnangud` nõutud väärtustega!")

# test if the students code produces an error
test_error()

# Final message the student will see upon completing the exercise
success_msg("Väga kena! Said punkte punkthinnangute eest!")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:265c07e646
## Vahemikhinnang ehk usaldusintervall

On selge, et juhusliku valimi põhjal leitud keskmine ise on ka juhusliku loomuga. Seetõttu tekib vajadus seda juhuslikust kuidagi iseloomustada. Üks võimalus on vahemikhinnang, mille keskpunktiks on leitud valimikeskmine.

On tõestatud, et piisavalt suure valimi korral ($n\geq 60$) sisaldab järgmine vahemik üldkogumi keskväärtust  $100 \cdot (1-\alpha)$%  100-st:

$$\bar{x} \pm \bar z_{\alpha / 2} \cdot \frac{s}{\sqrt{n}}$$

kus $s$ on valimi standardhälve, $n$ on valimi maht ja $\bar z_{\alpha / 2}$ on jaotuse $N(0,1)$ täiendkvantiil. Sageli nimetatakse osa

$$\frac{s}{\sqrt{n}}$$

suuruse $\bar{x}$ standardveaks.

Mõnikord on keeruline aru saada, kust tekib siin normaaljaotus ja millepärast peaks kasutama $\bar z_{\alpha/2}$? Vastused peituvad valimikeskmise $\bar x$ jaotuses ja varsti me seda ka uurime.


*** =instructions

1. Vektor `tulemused` on kättesaadav. See sisaldab 1. kontrolltöö andmeid. Uuri, kuidas on leitud valimimaht (läbi selle vektori pikkuse).
2. Leia `mu_hat` (valimikeskmise) (asendades NA)
3. Leia `s` (valimistandardhälbe). 
4. Kasutades `mu_hat` ja `s`, leia standardviga (ruutjuure leidmiseks rakenda funktsiooni `sqrt()`).
5. Uuri, kuidas on leitud muutuja `z`, mis vastab täiendkvantiili $\bar z_{\alpha/2}$ väärtusele usaldusnivool 99% ($\alpha$ = 0.01).
6. Leia vahemikhinnangu alumine ja ülemine piir ülalpool toodud valemi järgi.
7. Pane ühte vektorisse keskväärtuse hinnangu `mu_hat` ning vahemikhinnangu alumise ja ülemise piiri väärtused, asendades `NA`.
8. Kirjuta ise käsk, mis väljastab väärtuseid vektorist `hinnangud` ümardatuna ühe komakohani (vihje: `round()`).
  
*** =hint
*  Standardvea valemiks on $\frac{s}{\sqrt{n}}$.

*** =pre_exercise_code
```{r}
set.seed(7)
tulemused <- rnorm(175, 15, 1.5)
tulemused <- round(tulemused, 1)

```

*** =sample_code
```{r}
# (Vektor tulemused on juba loodud)
# 1. Valimi maht:
n <- length(tulemused)

# 2. Valimikeskmine:
mu_hat <- NA

# 3. Valimi standardhälve:
s <- NA

# 4. Leia standardviga asendades NA:
st_viga <- NA

# 5. Täiendkvantiili väärtus:
z <- qnorm(0.01/2, lower.tail = F) 

# 6. Vahemikhinnangu alumine ja ülemine piir:
al_piir <- mu_hat - NA
yl_piir <- mu_hat + NA

# 7. Kolm arvu ühte vektorisse:
hinnangud <- c("punkthinnang" = NA, "alumine99%" = NA, "ülemine99%" = NA)

# 8. Ümarda hinnangud 1 kohani peale koma:

```

*** =solution
```{r}
# (Vektor tulemused on juba loodud)
# 1. Valimi maht:
n <- length(tulemused)

# 2. Valimikeskmine:
mu_hat <- mean(tulemused)

# 3. Valimi standardhälve:
s <- sd(tulemused)

# 4. Leia standardviga asendades NA:
st_viga <- s/sqrt(n)

# 5. Täiendkvantiili väärtus:
z <- qnorm(0.01/2, lower.tail = F) 

# 6. Vahemikhinnangu alumine ja ülemine piir:
al_piir <- mu_hat - z*st_viga
yl_piir <- mu_hat + z*st_viga

# 7. Kolm arvu ühte vektorisse:
hinnangud <- c("punkthinnang" = mu_hat, "alumine99%" = al_piir, "ülemine99%" = yl_piir)

# 8. Ümarda hinnangud 1 kohani peale koma:
round(hinnangud, digits = 1)

```

*** =sct
```{r}
test_object("mu_hat", incorrect_msg = "Palun leia muutuja `mu_hat` väärtust kasutades funktsiooni `mean()`.")
test_object("s", incorrect_msg = "Palun leia muutuja `s` väärtust kasutades funktsiooni `sd()`.")
test_object("st_viga", incorrect_msg = "`st_viga` on leitud valesti, kontrolli!")
test_object("al_piir", incorrect_msg = "`al_piir` on leitud valesti, kontrolli!")
test_object("yl_piir", incorrect_msg = "`yl_piir` on leitud valesti, kontrolli!")
test_output_contains("round(hinnangud, digits = 1)")

# test if the students code produces an error
test_error()

# Final message the student will see upon completing the exercise
success_msg("Oled cool usaldusnivool 99%!")
```




--- type:NormalExercise lang:r xp:100 skills:1 key:8213107e60
## Valimikeskmise jaotus

Mäletad, et valimikeskmise jaotuse leidmine  on nagu teatud sorti mäng: kui oleks võimalik võtta juhuslike valimeid uuesti ja uuesti ning igakord arvutada valimikeskmist, siis tulemuseks saaksime valimikeskmise jaotuse.

Reaalses elus me seda teha ei saa, kuna meil on olemas vaid üks valim. Või siiski saame? Teeskleme korraks, et meil on olemas kogu üldkogumi andmed. Vaatame, mis juhtub, kui me korduvalt

    * võtame valimeid sellest üldkogumist
    * arvutame igakord valimikeskmise ja
    * salvestame saadud väärtuse.

Tulemusena saadud jaotus vastabki valimikeskmise jaotusele, mis tähendab, et me saame jaotust simuleerida! See meetod (kannab nimetust bootstrap = taasvalik) on väga levinud statistikas.

*** =instructions
*  (1. kontrolltöö tulemuste vektor on kättesaadav. Teeskleme siin, et tegemist on kogu üldkogumi andmetega.)
*  1. Käivita käsud, mis loovad muutujaid `N` ja `keskmised` ning väljastavad tühja keskmiste vektori väärtuseid.
  *  2. Käivita tsükkel `for`. Mida ta teostab?
  *  3. Väljasta keskmiste vektor uuesti.
  *  4. Uuri, mida väljastab käsk `summary()`.
  *  **Ülesanne 1.** Kirjuta käsk, mis joonestab vektori `keskmised` põhjal histogrammi. Kas meenutab normaaljaotust?
  *  **Ülesanne 2.**Uuri `help`-is, kuidas muuta käsku `hist()` nii, et see väljastaks `y`-teljele sageduste asemel osakaale. Graafiku kuju ei muutu!

*** =hint

 *   Funktsioon `hist()` joonistab sagedustega histogrammi ja argument `freq = F` muudab sagedusi osakaaludeks.
 *   Käsu `?hist` abil saab kuvada abi funktsiooni `hist()` kohta.
 
*** =pre_exercise_code
```{r}
set.seed(7)
tulemused <- rnorm(175, 15, 1.5)
tulemused <- round(tulemused, 1)

set.seed(888)
```

*** =sample_code
```{r}
# 1. Tühi vektor pikkusega N
N <- 1000
keskmised <- numeric(N)
keskmised

# 2. Korda N korda: 
  # (1) võta juhuslik valim pikkusega  n = 70  vektorist tulemused
  # (2) leia valimikeskmine
  # (3) salvesta saadud keskmine vektorisse keskmised
for(i in 1:N) {
  valim <- sample(tulemused, size = 70, replace = T)
  keskmised[i] <- mean(valim)
}

# 3. Prindi keskmiste vektor uuesti välja:
keskmised

# 4. Funktsioon summary:
summary(keskmised)

# Ülesanded 1 ja 2. Visualiseeri keskmised histogrammi abil:


```

*** =solution
```{r}
# 1. Tühi vektor pikkusega N
N <- 1000
keskmised <- numeric(N)
keskmised

# 2. Korda N korda: 
  # (1) võta juhuslik valim pikkusega  n = 70  vektorist tulemused
  # (2) leia valimikeskmine
  # (3) salvesta saadud keskmine vektorisse keskmised
for(i in 1:N) {
  valim <- sample(tulemused, size = 70, replace = T)
  keskmised[i] <- mean(valim)
}

# 3. Prindi keskmiste vektor uuesti välja:
keskmised

# 4. Funktsioon summary:
summary(keskmised)

# Ülesanded 1 ja 2. Visualiseeri keskmised histogrammi abil:
hist(keskmised, freq = F)


```

*** =sct
```{r}

# submission correctness tests

test_output_contains("numeric(N)")
test_output_contains("keskmised")
test_function("summary", args=c("object"))
test_function("hist", args=c("x","freq"), incorrect_msg = c("Funktsiooni `hist` 1. argumendiks on uuritava vektori nimi", "Osakaalude joonistamiseks y-teljele lisa funktsiooni `hist` argumediks `freq = FALSE`"), args_not_specified_msg=c("Funktsiooni `hist` 1. argumendiks on uuritava vektori nimi", "Osakaalude joonistamiseks y-teljele lisa funktsiooni `hist` argumediks `freq = FALSE`"))

# test if the students code produces an error
test_error()

# Final message the student will see upon completing the exercise
success_msg("Väga tubli töö!")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:76ded038cc
## Tsentraalne piirteoreem

Nüüd uurime vahemikhinnangut üldkogumi keskväärtusele veel kord:

$$\bar{x} \pm \bar z_{\alpha / 2} \cdot \frac{s}{\sqrt{n}}$$

kus $\bar z_{\alpha / 2}$ on jaotuse $N(0,1)$ $\alpha/2$-täiendkvantiil. Milline on seos normaaljaotuse ja valimikeskmise jaotuse vahel?

Valimikeskmine on summa jagatud $n$-ga. Vastavalt tsentraalsele piirteoreemile on summa asümptootilise normaaljatusega (st, et mida suurem on valimimaht $n$, seda "ilusamat" normaaljatust saame).

Ülalpool toodud vahemikhinnang põhinebki asümptootilise normaaljaotuse eeldusel. Antud harjutuses uurime, et tegelikult töötab tsentraalne piirteoreem üsna hästi suuremahuliste valimite korral.

*** =instructions
 * Kasutame eelmises harjutuses loodud keskmiste vektorit.
 * **Ülesanne 1.** Joonista selle vektori põhjal histogramm, mille vertikaalteljel on osakaalud.
 * **Ülesanne 2.** Leia selle vektori keskmine `mu_hat` ja standardhälve `s`.
 * **Ülesanne 3.** Kasuta neid argumentidena funktsioonis `dnorm()` nii, et `mean =` leitud väärtusega `mu_hat` ja `sd = ` leitud väärtusega `s`.
 * **Ülesanne 4.** Täienda  rida `curve()`, asendades väärtused `NA`. See joonistab normaaljaotuse tihedusfunktsioonile vastavat kõverjoont.
 * Kas histogramm ja normaaljaotuse joon langevad kokku? Kui jah, siis valimikeskmise jaotuseks  sobibki  normaaljaotus.
 
*** =hint
 * `mu_hat` on valimikeskmine, mille leidmiseks kasuta funktsiooni `mean()`.
   * standardhälvet saab leida funktsiooni `sd()` abil.
   
*** =pre_exercise_code
```{r}
set.seed(7)
tulemused <- rnorm(175, 15, 1.5)
tulemused <- round(tulemused, 1)


# Loo tühi vektor pikkusega N
N <- 1000
keskmised <- numeric(N)

# Prindi tühi keskmiste vektor välja:
keskmised

# Korda N korda: 
  # (1) võta juhuslik valim pikkusega  n = 70  vektorist tulemused
  # (2) leia valimikeskmine
  # (3) salvesta saadud keskmine vektorisse keskmised
for(i in 1:N) {
  valim <- sample(tulemused, size = 70, replace = T)
  keskmised[i] <- mean(valim)
}
```

*** =sample_code
```{r}
# Ülesanne 1. Loo histogramm vektori 'keskmised' põhjal. y-teljel - osakaalud!


# Ülesanne 2. Leia vektori 'keskmised' keskmise:
mu_hat <- NA

# Ülesanne 3. Leia vektori 'keskmised' standardhälve:
s <- NA

# Ülesanne 4. Normaaljatuse kõver, mis põhineb leitud väärtustel (asenda 'NA'!)
curve(dnorm(x, mean = NA, sd = NA), add = T)
```

*** =solution
```{r}
# Ülesanne 1. Loo histogramm vektori 'keskmised' põhjal. y-teljel - osakaalud!
hist(keskmised, freq=F)

# Ülesanne 2. Leia vektori 'keskmised' keskmise:
mu_hat <- mean(keskmised)

# Ülesanne 3. Leia vektori 'keskmised' standardhälve:
s <- sd(keskmised)

# Ülesanne 4. Normaaljatuse kõver, mis põhineb leitud väärtustel (asenda 'NA'!)
curve(dnorm(x, mean = mu_hat, sd = s), add = T)
```

*** =sct
```{r}
test_object("mu_hat", incorrect_msg = "Palun leia muutuja `mu_hat` väärtust kasutades funktsiooni `mean()`.")
test_object("s", incorrect_msg = "Palun leia muutuja `s` väärtust kasutades funktsiooni `sd()`.")

test_function("dnorm", args = c("mean","sd"))

# test if the students code produces an error
test_error()

# Final message the student will see upon completing the exercise
success_msg("Suurepäraselt tehtud!! Sa teed tõeliselt suuri edusamme!")

```
