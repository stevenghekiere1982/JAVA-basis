#Keuzes (switch)

---

##Switch

Net zoals een `if-else if-else` test je met een `switch` een variabele in functie van een aantal voorgedefinieerde waardes.

```java
int getal = Integer.parseInt(g.getText());
String txt = "";
switch (getal) {
    case 0:
        txt = "U hebt voor getal 0 gekozen.";       
        break;
    case 1:
        txt = "U hebt voor getal 1 gekozen.";       
        break;
    case 2:
        txt = "U hebt voor getal 2 gekozen.";       
        break;
    default:
        txt = "U hebt niet voor 0, 1 of 2 gekozen";
}
lbl.setText(txt);
```

De variabele *getal* wordt vergeleken met de eerste case voorwaarde. Indien beide waardes
overeenstemmen, worden de bijbehorende statements uitgevoerd. *Break* zorgt ervoor dat men niet in een volgende case terechtkomt. Indien de voorwaarde niet waar is, gaan we verder naar de volgende case enz…  
Indien geen enkele voorwaarde voldoet, wordt het *default* statement uitgevoerd.

**Let op dat je de *break* niet vergeet!** Anders loopt het programma altijd verder in de volgende case en bekom je een foutief resultaat.

###Zelfde resultaat met: if-else

 Het resultaat van onderstaande code is identiek aan deze van voorgaand voorbeeld.

```java
int getal = Integer.parseInt(g.getText());
String txt = "";
if(getal == 0) {
    txt = "U hebt voor getal 0 gekozen.";
} else if (getal == 1) {
    txt = "U hebt voor getal 1 gekozen.";
} else if (getal == 2) {
    txt = "U hebt voor getal 2 gekozen.";
} else {
     txt = "U hebt niet voor 0, 1 of 2 gekozen";
}
lbl.setText(txt);
```

###Beperkingen met switch-statement

Er zijn heel wat beperkingen op het switch-statement in Java. Zie vergelijkend overzicht in onderstaande tabel.

| type   |  if-else  | switch |
| ----   | ----     -| -------|
| byte   |  x | x |
| short  |  x | x |
| int    |  x | x |
| long   |  x | - |
| float  |  x | - |
| double |  x | - |
| char   |  x | x |
| boolean|  x | - |
| String |  - | - |
