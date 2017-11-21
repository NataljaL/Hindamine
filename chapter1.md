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
* sfsd
* sdgdd
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
1+2
```

*** =solution
```{r}
1+2
```

*** =sct
```{r}
test_error()
success_msg("Hea töö!")
```
