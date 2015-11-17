#ArrayList

Package: [java.util.ArrayList](http://docs.oracle.com/javase/7/docs/api/java/util/ArrayList.html)

---

- Een ArrayList is, net zoals een array, een object waarin je soortgelijke gegevens (objecten of waarden van hetzelfde type) kan stockeren.  
- Het merendeel van de ontwikkelaars verkiezen een ArrayList boven een Array vanwege de functionaliteit en de flexibiliteit die een ArrayList biedt.  
- Het probleem met Arrays is dat ze een vaste lengte hebben. ArrayLists hebben geen vaste lengte en zijn dus makkelijk uitbreidbaar.  
Als je uit een Array een elementen verwijderd, zal het geheugengebruik hetzelfde blijven omdat de Array niet krimpt.  
Anderzijds kan een ArrayList dynamisch groeien en krimpen volgens de behoefte.  


##Een array aanmaken.

Merk op dat een ArrayList **enkel objecten** ondersteunt en **geen primitieve types**!

````java
ArrayList <Double> puntenLijst = new ArrayList <> ();   
````

##Veel gebruikte methoden.

````java
puntenLijst.add(7.5);           // voeg de waarde 7.5 achteraan de lijst toe 
puntenLijst.add(4.3, 2);        // voeg de waarde 4.3 op de tweede positie toe 
puntenLijst.set(2, 4.6);        // vervang het tweede element door de waarde 4.6
puntenLijst.remove(3);          // verwijder het derde element uit de lijst
puntenLijst.removeRange(2, 5);  // verwijder het tweede t.e.m. het vierde element uit de lijst
puntenLijst.get(2);             // haal het tweede element uit de lijst op
puntenLijst.clear();            // maak de lijst leeg
puntenLijst.size();             // geef het aantal elementen in de lijst
puntenLijst.toArray();          // maak van de lijst een gewone array
puntenLijst.contains(4.6);      // is true indien de lijst de waarde 4.6 bevat
puntenLijst.indexOf(4.6);       // geef te eerste positie binnen de lijst die de waarde 4.6 bevat
puntenLijst.lastIndexOf(4.6);   // geef te laatste positie binnen de lijst die de waarde 4.6 bevat
Collections.shuffle(puntenLijst);   // plaats elementen in willekeurige volgorde
Collections.reverse(puntenLijst);   // plaats elementen in omgekeerde volgorde
Collections.sort(puntenLijst);      // sorteer de elementen van laag naar hoog
Collections.sort(puntenLijst, Collections.reverseOrder());  // sorteer de elementen van hoog naar laag
````

##Elementen uit een ArrayList ophalen/wijzigen.

- Binnen een **for-lus** kan je waardes **uitlezen en aanpassen**.  
- Binnen een **for-each-lus** kan je enkel waardes **uitlezen**. (Aanpassen is niet mogelijk.)

###Met een for-lus.

````java
ArrayList <Double> puntenLijst = new ArrayList <> ();
puntenLijst.add(7.5);
puntenLijst.add(8.2);
puntenLijst.add(5.0);
puntenLijst.add(12.6);
Collections.sort(puntenLijst);
for (int i = 0; i < puntenLijst.size(); i++) {
    System.out.println("" + puntenLijst.get(i));    // schrijf waarde uit
    puntenLijst.set(i, puntenLijst.get(i)+1);       // verhoog vervolgens de waarde met 1
}
System.out.println("---------------------");
System.out.println(puntenLijst);
````

Uitvoer: 

````java
5.0
7.5
8.2
12.6
---------------------
[6.0, 8.5, 9.2, 13.6]
````

###Met een for-each-lus.

````java
ArrayList <Double> puntenLijst = new ArrayList <> ();
puntenLijst.add(7.5);
puntenLijst.add(8.2);
puntenLijst.add(5.0);
puntenLijst.add(12.6);
Collections.sort(puntenLijst);
for(double waarde: puntenLijst) {
    System.out.println(waarde);
}
System.out.println("---------------------");
System.out.println(puntenLijst);
````

Uitvoer: 

````java
5.0
7.5
8.2
12.6
---------------------
[5.0, 7.5, 8.2, 12.6]
````

##Een ArrayList kopiëren (ondiepe kopie of shallow copy).

````java
ArrayList <Double> puntenLijst = new ArrayList <> ();
puntenLijst.add(7.5);
puntenLijst.add(8.2);
puntenLijst.add(5.0);
ArrayList <Double> copyLijst = new ArrayList <> (puntenLijst);
puntenLijst.set(1, 1.25);
System.out.println("puntenLijst = " + puntenLijst);
System.out.println("copyLijst = " + copyLijst);
````

Uitvoer: 

````java
puntenLijst = [7.5, 1.25, 5.0]
copyLijst = [7.5, 8.2, 5.0]
````
