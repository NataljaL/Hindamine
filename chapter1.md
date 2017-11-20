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

  *  DataCamp-i keskkonna eripära on see, et kui on tarvis käivitada koodi, mis jätkub mitmel real, siis tuleks esmalt need read ära märkida ja seejärel vajutada `Ctrl+Enter` või nuppu.
  *  Execute the 3 rows long for-loop expression
  *  Click submit answer to move on to the next exercise

*** =hint

   * If you cannot paint (select) the expression for some reason, you can just click submit answer instead.

*** =pre_exercise_code
```{r}
# pre exercise code here
```


*** =sample_code
```{r}
# Execute me!
for(i in 1:6) {
  print("I am a loop")
}
```



*** =solution
```{r}
# Execute me!
for(i in 1:6) {
  print("I am a loop")
}
```



*** =sct
```{r}
test_error()
success_msg("Good work!")
```

