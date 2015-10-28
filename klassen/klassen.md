#Klassen en objecten

Klassen en objecten vormen de basis van OOP.    
Je kan Java niet begrijpen zonder goed met klassen en objecten overweg te kunnen.


##OOP begrippen

###Object

- Alles rondom ons is een **object**.
- Elk object heeft **attributen** (of *eigenschappen*, *kenmerken*, ...).
- Elk object heeft **methoden** (of *functies*, *gedrag*, *acties* ondernemen...).

###Klasse

- Een klasse is een **blauwdruk** (ontwerp) die definieert hoe een object eruit ziet (*attributen*) en hoe het object zich gedraagt (*methoden*).
- Van één klasse kan je meerdere (soortgelijke) objecten **instantiëren**.

###Message

- Het aanroepen van een methode noemt men een **message** (of *boodschap*).

##Een klasse 'Rechthoek' ontwerpen

###Attributen van de klasse Rechthoek

- Deze klasse heeft twee **attributen** (eigenschappen), namelijk een *lengte* en een *breedte*.
- Omwille van **information hiding** is het in JAVA gebruikelijk om alle attributen  `private` te maken. De attributen zijn dus niet rechtstreeks toegankelijk buiten de klasse, enkel binnen de klasse.
- Voor grote projecten is het aangewezen om alle klassen in een eigen bestand te plaatsen en ben je **verplicht** de klasse **Rechthoek** op te slaan in het bestand **Rechthoek.java**.

```java
// Klasse Rechthoek in apart bestand Rechthoek.java
package voorbeeldrechthoek;
public class Rechthoek {
    private double lengte, breedte;
}
```

- Voor kleine projecten mag je de klasse aan de opstartklasse toevoegen, maar dan laat je `public` weg.

```java
// Klasse Rechthoek in opstartklasse 
package voorbeeldrechthoek;
public class VoorbeeldRechthoek {
   public static void main(String[] args) {
        ...
    } 
}

// Laat public weg.
class Rechthoek {
    private double lengte, breedte;
}
```

###Minimale methoden van de klasse Rechthoek (getters, setters)
- Aangezien de *attributen* niet publiek toegankelijk zijn, gaan we via **setters** attribuutwaardes wijzigen en via **getters** attribuutwaardes opvragen.
- **Getter** (*accessor* of toegang tot):  
De naam begint met **get** (of **is** voor een *boolean*), gevolgd door de naam van het attribuut.  
Dus **getLengte()** en **getBreedte()**.  
- **Setter** (*mutator* of veranderen):  
De naam begint met **set**, gevolgd door de naam van het *attribuut*.  
Dus **setLengte(4)** en **setBreedte(3)**.

Tip: In NetBeans volstaat het om enkel de attributen van een klasse aan te maken. *Getters*, *setters* en later ook *constructors* en de methode `toString()` kan je automatisch genereren door met de rechtermuistoets in de code te klikken en vanuit het snelmenu *Insert Code* te kiezen. 

```java
public class Rechthoek {
    private double lengte, breedte;

    // Getters
    public double getLengte() {
        return lengte;
    }
    public double getBreedte() {
        return breedte;
    }

    // Setters
    public void setLengte(double lengte) {
        this.lengte = lengte;
    }
    public void setBreedte(double breedte) {
        this.breedte = breedte;
    }
}
```

En in de opstartklasse:

```java
public class VoorbeeldRechthoek {
   public static void main(String[] args) {
       
       // De klasse Rechthoek instantiëren (= het object r1 aanmaken)
       Rechthoek r1 = new Rechthoek();

       System.out.println("Lengte = " + r1.getLengte());
       System.out.println("Breedte = " + r1.getBreedte());
       
       r1.setLengte(5.2);
       System.out.println("Lengte = " + r1.getLengte());
    } 
}
```

Geeft als output:

```java
Lengte = 0.0
Breedte = 0.0
Lengte = 5.2
```

###Extra methoden toevoegen

Stel dat je  de oppervlakte en de omtrek van de rechthoek wilt kennen, dan kan je deze berekeningen in twee eigen methoden onderbrengen. Vaak worden deze methoden ook voorafgaan door *get*, maar dit is niet verplicht.

```java
public class Rechthoek {
    private double lengte, breedte;

    // Getters

    // Setters
    
    // Extra methoden
     public String getOmtrek() {
        return "Omtrek rechthoek =  " + (lengte*2 + breedte*2);
    }
    public String getOpp() {
        return "Oppervlakte rechthoek =  " + (lengte*breedte);
    }
}
```

En in de opstartklasse:

```java
public class VoorbeeldRechthoek {
   public static void main(String[] args) {
       
        Rechthoek r1 = new Rechthoek();
        r1.setLengte(5);
        r1.setBreedte(2);
        System.out.println( r1.getOmtrek() );
        System.out.println( r1.getOpp() );
    } 
}
```

Geeft als output:

```java
Omtrek rechthoek =  14.0
Oppervlakte rechthoek =  10.0
```

##Constructors

- Een *constructor* is een methode die **automatisch** wordt opgeroepen zodra je een object instantieert.
- Als je zelf geen *constructor* schrijft, wordt de **default constructor** aangemaakt en krijgen alle attribuutvariabelen een default waarde:  
int (0), double (0.0), boolean (false), char (''), String (null).
- Als je zelf één of meerdere *constructors* schijft, zal JAVA zelf geen *default constructor* meer aanmaken!
- De naam van de constructor **moet** hetzelfde zijn als de naam van de klasse en heeft **geen returntype**.
- Je mag meerdere *constructors* aanmaken. (= *constructor overloading*.)

##Overloading

**Overloading** betekent dat de klasse 2 of meerdere methoden met **dezelfde naam** bevat. 2 of meerdere methoden met dezelfde naam zijn toegestaan mits deze een **verschillende signatuur** hebben.

De signatuur van een methode bestaat uit:  

- **Naam** van de methode.  
- **Aantal argumenten** binnen de methode.
- **Type en volgorde** van de argumenten binnen de methode.

**Constructor overloading** betekent dat de klasse 2 of meerdere *constructors* bevat. Ook hier moet de signatuur natuurlijk verschillend zijn.

```java
public class Rechthoek {
    private double lengte, breedte;
    // Voeg (lokale) variabele 'soort' toe.
    // Deze variabele is niet publiek toegankelijk en heeft dus geen getter/setter nodig!
    private String soort = "rechthoek";

    // constructors
    public Rechthoek(){                     // no-arg constructor 
        lengte = 2.0;
        breedte = 1.0;
    }
    public Rechthoek(double x){             // constructor voor vierkant 
        soort = "vierkant";
        lengte = x;
        breedte = x;
    }
    public Rechthoek(double x, double y){   // constructor voor rechthoek/vierkant 
        lengte = x;
        breedte = y;
        if (x == y) soort = "vierkant";
    }

    // Getters

    // Setters
    
    // Extra methoden met 'soort' in verwerkt
     public String getOmtrek() {
        return "Omtrek " + soort + " = " + (lengte*2 + breedte*2);
    }
    public String getOpp() {
        return "Oppervlakte " + soort + " = " + (lengte*breedte);
    }
   
}
```

En in de opstartklasse:

```java
public class VoorbeeldRechthoek {
   public static void main(String[] args) {
       
        Rechthoek r1 = new Rechthoek();
        System.out.println("r1: lengte = " + r1.getLengte() + " breedte = " + r1.getBreedte());
        System.out.println("r1: " + r1.getOmtrek());
        System.out.println("r1: " + r1.getOpp());

        Rechthoek r2 = new Rechthoek(4, 2);
        System.out.println("r2: lengte = " + r2.getLengte() + " breedte = " + r2.getBreedte());
        System.out.println("r2: " + r2.getOmtrek());
        System.out.println("r2: " + r2.getOpp());
       
        Rechthoek v1 = new Rechthoek(3);
        System.out.println("v1: lengte = " + v1.getLengte() + " breedte = " + v1.getBreedte());
        System.out.println("v1: " + v1.getOmtrek());
        System.out.println("v1: " + v1.getOpp());
    } 
}
```

Geeft als output:

```java
r1: lengte = 2.0 breedte = 1.0
r1: Omtrek rechthoek = 6.0
r1: Oppervlakte rechthoek = 2.0
r2: lengte = 4.0 breedte = 2.0
r2: Omtrek rechthoek = 12.0
r2: Oppervlakte rechthoek = 8.0
v1: lengte = 3.0 breedte = 3.0
v1: Omtrek vierkant = 12.0
v1: Oppervlakte vierkant = 9.0
```

##De methode toString()

Elk object heeft een default methode `toString()` in zich. Deze geeft echter nutteloze informatie terug.

```java
public class VoorbeeldRechthoek {
   public static void main(String[] args) {
       
        Rechthoek r1 = new Rechthoek(5, 3);
        System.out.println(r1.toString());
        System.out.println(r1);             // verkorte notatie
    } 
}
```

Geeft als output:

```java
voorbeeldrechthoek.Rechthoek@15db9742
voorbeeldrechthoek.Rechthoek@15db9742
```

De output is de naam van de klasse, gevolgd door @ en een hashcode (hexadecimaal formaat) die het object voorstelt.  
Daarom bevatten de meeste klassen een eigen methode `toString()` die de default weergave overschrijft.  
Ziehier de `toString()` methode die we vanuit het snelmenu in NetBeans automatisch laten genereren.

```java
public class Rechthoek {
    private double lengte, breedte;
    private String soort = "rechthoek";

    // constructors

    // Getters

    // Setters
    
    // Extra methoden met 'soort' in verwerkt
    
    // toString() methode vanuit NetBeans gegenereerd
    @Override
    public String toString() {
        return "Rechthoek{" + "lengte=" + lengte + ", breedte=" + breedte + ", soort=" + soort + '}';
    }
}
```

Geeft nu als output:

```java
Rechthoek{lengte=5.0, breedte=3.0, soort=rechthoek}
Rechthoek{lengte=5.0, breedte=3.0, soort=rechthoek}
```

Je mag de inhoud van `toString()` naar eigen goeddunken wijzigen.  
Verder is de `toString()` methode zeer handig om tussentijds de toestand van de verschillende variabelen in het object te controleren.

##Het kernwoord 'this'

In de setters die NetBeans genereert, staat het kernwoord `this`.  
In Java is het gebruikelijk (niet verplicht) dat de parameters van een methode dezelfde naam krijgen als de properties. 

```java
public class Rechthoek {
    private double lengte, breedte;

    // Setters
    public void setLengte(double lengte) {
        this.lengte = lengte;
    }
}
```

- **this.lengte**: verwijst naar het attribuut lengte van het object.
- **lengte**: verwijst naar de parameter lengte van de methode setLengte.

Je mag `this` weglaten indien je voor de parameter een andere naam gebruikt. Onderstaande code is dus ook correct:

```java
public class Rechthoek {
    private double lengte, breedte;

    // Setters
    public void setLengte(double l) {
        lengte = l;
    }
}
```

