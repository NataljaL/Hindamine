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
## Indices and brackets

Vectors in R store multiple values of the same data type. The values in vectors have indices: the first value in a vector has a index 1, the second value 2 and so on.

You can set or get a single value from a vector by using indices and brackets [ ]. Using an index number inside the brackets gives access to a single value from the vector. Using a vector of indices gives access to multiple values (another vector).

It is also possible to rearrange the values in a vector by using indices. Look at the example code to see how indices work.

*** =instructions

  *  Create the names vector.
  *  See how the indices work by executing the example lines.
  *  Use brackets and indices on names to create a new vector girls with values "Liisa" and "Anna" (in that order).
  *  Use brackets and indices on names to create a new vector boys with values "Pekka" and "Heikki" (in that order).

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
