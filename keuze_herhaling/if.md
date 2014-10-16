#Keuzes (if)

---

##if

Indien een bepaalde voorwaarde `waar` is, voer dan alle instructies uit binnen het if-blok.

```java
int getal = Integer.parseInt(g.getText());
String eo = "oneven";
if(getal%2 == 0) {
    eo = "even";
}
lbl.setText(getal + " is een " + eo + " getal.");
```

Indien de voorwaarde maar één instructie bevat, mag je de accolades weglaten.

```java
int getal = Integer.parseInt(g.getText());
String eo = "oneven";
if(getal%2 == 0) eo = "even";
lbl.setText(getal + " is een " + eo + " getal.");
```

##if-else

Indien een bepaalde voorwaarde `waar` is, voer dan alle instructies uit binnen het if-blok. Indien de voorwaarde `onwaar` is, voer dan de instructies binnen het else-blok uit.

```java
int getal = Integer.parseInt(g.getText());
String eo = "";
if(getal%2 == 0) {
    eo = "even";
} else {
    eo = "oneven";
}
lbl.setText(getal + " is een " + eo + " getal.");
```

Bestaat het if- en het else-statement maar uit één commando, dan kan je de structuur compacter schrijven.

```java
// normale schrijfwijze
if(getal%2 == 0) {
    eo = "even";
} else {
    eo = "oneven";
}

// verkorte schrijfwijze
// variabele = (voorwaarde) ? waarde indien waar : waarde indien niet waar ;
eo = (getal%2 == 0) ? "even" : "oneven";
```

##if-else if-else

Je kan meerdere voorwaardes controleren door extra `else if` voorwaardes toe te voegen.

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