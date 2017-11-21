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



--- type:NormalExercise lang:r xp:100 skills:1 key:23abc9f934
## Indeksid ja sulud

Olete vektoritega juba varem kokku puutunud. Siin uurime neid veel kord. Vektorite abil saab hoida sama tüüpi väärtuseid ja nendele väärtustele vastavad vektoris indeksid: esimesel vektori elemendil on indeks 1, teisel 2 jne.

Väärtust saab muuta/vaadata, kasutades selleks vektori nime järel nurksulgudes vastavat indeksit, näiteks `linnad[1]`. Kasutades nurksulgudes ühe indeksi asemel indeksite vektorit, saab vektorist välja võtta mitut elementi korraga, näiteks `linnad[1:3]` annab kolme esimest elementi vektoris `linnad`.

Indeksite abil on võimalik elementide asukohta vahetada. Uuri järgmises näiteks, kuidas saab manipuleerida indeksitega.

*** =instructions

  *  Loome vektori `nimed` (käsk on juba kirjutatud).
  *  Uuri indeksite tööd käivitades näitekäske.
  *  Nurksulgude ja vektori `nimed` abil loo uus vektor `tydrukud`, mis sisaldab nimesid "Liisa" ja "Anna" (just sellises järjekorras).
  *  Nurksulgude ja vektori `nimed` abil loo uus vektor `poisid`, mis sisaldab nimesid "Peeter" and "Heikki" (just sellises järjekorras).

*** =hint

  *  Note that space between the vector object and bracets produces an error.
  *  Index vectors c(1,2) and c(2,1) do not produce the same outcome. The order of the values is different.

*** =pre_exercise_code

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
tydrukud <- names[c(3, 4)]
poisid <- names[c(2, 1)]
```
*** =sct
```{r}

test_object("tydrukud", incorrect_msg = "Vektor pole õige. Kas kasutasid viitamist elementidele vektorist `nimed?`")
test_object("poisid", incorrect_msg = "Vektor pole õige. Kas kasutasid viitamist elementidele vektorist `nimed? Kontrolli ka elementide järjekorda.`")

test_error()

# Final message the student will see upon completing the exercise
success_msg("Sellised siis indeksid... ")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:8e0ac16859
## Lihtsad vektorid

Võib juhtuda, et vaja läheb pikka indeksite vektorit. Fuktsiooni `c()` kaudu oleks sellise vektori loomine tõlikas. Õnneks, pakub `R` selle jaoks lihtsaid lahendusi.

Täisarvulise vektori jaoks saab kasutada meetodit `algus:lõpp`, mis loob vektorit kõikide täisarvudega alates arvust `algus` kuni arvuni `lõpp`. Kahe järgmise rea tulemused on samad: 

`1:5`  
`c(1,2,3,4,5)`

*** =instructions

  *  Create an integer vector with values from 1 to 5.
  *  Create an integer vector with even values from 2 to 10.
  *  Create object attitude and give the values in it names matching the indices.
  *  Access index values 1-5 of attitude
  *  Use : to create an integer vector with the values 1, 2, ..., 10
  *  Access every second value of the attitude vector, starting from the 2. value until the 20th value. These values correspond to the even numbered indeces of the vector: 2, 4, .. , 20

*** =hint

  *  First you will need an index vector with values 2, 4, .. , 20. The example shows how to create such a vector
  *  You can then use the index vector together with brackets ([ ]) to complete the task

*** =pre_exercise_code
```{r}
learning2014 <- read.table("http://www.helsinki.fi/~kvehkala/JYTmooc/learning2014.txt", sep = "\t", header = TRUE)
```
*** =sample_code
```{r}
# learning2014 is available

# Create an integer vector with values 1,2,..,5
1:5

# Create an integer vector with even values 2, 4, .. , 10
(1:5)*2

# Create object attitude and give the data points names 1, 2, ..
attitude <- learning2014$attitude
names(attitude) <- 1:length(attitude)

# Access the values 5 - 10 of attitude
attitude[5:10]

# Create an integer vector with values 1,2,..,10


# Access every second value of attitude from 2. to the 20th index

```

*** =solution
```{r}
# learning2014 is available

# Create an integer vector with values 1,2,..,5
1:5

# Create an integer vector with even values
(1:5)*2

# Create object attitude and give the data points names 1, 2, ..
attitude <- learning2014$attitude
names(attitude) <- 1:length(attitude)

# Access the values 5 - 10 of attitude
attitude[5:10]

# Create an integer vector with values 1,2,..,10
1:10

# Access every second value of attitude from 2. to the 20th index
attitude[(1:10)*2]
```

*** =sct
```{r}
# submission correctness tests

test_student_typed("1:10", not_typed_msg = "Did you use `:` to create and print out the specified integer vector?")
test_output_contains("attitude[(1:10)*2]")

# test if the students code produces an error
test_error()

# Final message the student will see upon completing the exercise
success_msg("Great work!")
```