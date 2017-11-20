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
  *  Nurksulgude ja vektori `nimed` abil loo uus vektor `poisid`, mis sisaldab nimesid "Pekka" and "Heikki" (just sellises järjekorras).

*** =hint

  *  Note that space between the vector object and bracets produces an error.
  *  Index vectors c(1,2) and c(2,1) do not produce the same outcome. The order of the values is different.

*** =pre_exercise_code

*** =sample_code
```{r}
# Let's create a vector
names <- c("Matti", "Pekka", "Liisa", "Anna")

# Acess the first value of the vector
names[1]

# Change the first value of the vector
names[1] <- "Heikki"

# Acess the 1. and 3. value of the vector
names[c(1, 3)]

# Use indices and brackets to separate the names vector into two vectors of the specified ordering
girls <-
boys <-
```

*** =solution
```{r}
# Let create a vector
names <- c("Matti", "Pekka", "Liisa", "Anna")

# Acess the first value of the vector
names[1]

# Change the first value of the vector
names[1] <- "Heikki"

# Acess the 1. and 3. value of the vector
names[c(1, 3)]

# Use indices and brackets to separate the names vector into two vectors of the specified ordering
girls <- names[c(3, 4)]
boys <- names[c(2, 1)]
```
*** =sct
```{r}

test_object("girls", incorrect_msg = "Did you create `girls`?")
test_object("boys", incorrect_msg = "Did you create `boys`? Are the values in the correct order?")

test_error()

# Final message the student will see upon completing the exercise
success_msg("Such indices. Wow. Much intelligent.")
```
