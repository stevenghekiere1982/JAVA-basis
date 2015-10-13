#Herhalingen


##For lus

```java
// for-lus
for (van; tot; teller verhogen){
    // herhaalt n-maal dezelfde instructie.
}
```

##While lus

Deze lus wordt vaak gebruikt in situaties waarbij het aantal stappen op voorhand onbekend is.
De lus stopt op het moment dat de voorwaarde `false` (onwaar) is.

Vergeet binnen een while-lus vooral niet de waarde van de teller met één te verhogen (`i++`),
anders blijft de lus oneindig lopen!

```java
// while-lus
while (voorwaarde) {
    // voer instructie uit en verhoog de teller
}
```

##Do-while lus

Deze lus is bijna identiek aan de While-lus.   
Een While-lus wordt **enkel** uitgevoerd indien de voorwaarde true is. Indien de startvoorwaarde al false is, wordt de lus helemaal niet uitgevoerd.   
In tegenstelling tot een while-lus, wordt een do-while-lus **altijd minstens één maal** uitgevoerd, ook al is de beginvoorwaarde false. De test gebeurt immers helemaal op het einde, nadat de
bewerking reeds is uitgevoerd.

```java
// while-lus
do {
    // voer instructie uit en verhoog de teller
} while (voorwaarde);
```

In onderstaand voorbeeld geven een for, een while en een do-while lus net hetzelfde resultaat.

```java
int van = 10, tot = 20;
int i;
String resultaat;
        
System.out.println("For statement:");
resultaat = "";
i = van;
for (i = van; i <= tot; i++) {
     resultaat += i + ", ";
}
System.out.println(resultaat);
        
System.out.println("While statement:");
resultaat = "";
i = van;
while (i <= tot) {
    resultaat += i + ", ";
    i++;
}
System.out.println(resultaat);
        
System.out.println("Do-while statement:");
resultaat = "";
i = van;
do {
    resultaat += i + ", ";
    i++;
} while (i <= tot);
System.out.println(resultaat);
```

Resultaat:

```java
For statement:
10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 
While statement:
10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 
Do-while statement:
10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 
```

Vervang nu in de broncode de waarde van `tot` door een kleiner getal dan de waarde van `van` (bijvoorbeeld `tot = 5`) en voer de instructies opnieuw uit.
Je krijgt dan onderstaand resultaat:

```java
For statement:

While statement: 

Do-while statement:
10,
```





