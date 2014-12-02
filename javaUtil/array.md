#Array

Package: [java.util.Arrays](http://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html)

---

Een array is een object waarin je soortgelijke gegevens (objecten of waarden van hetzelfde primitieve type) kan stockeren.

- Een array is snel aan te maken. Je hoeft enkel [] achter het type te plaatsen.  
Bijvoorbeeld `int[] getalArray`, `String[] stringArray`, ...
- Een array bevat veel voorgedefinieerde methoden.
- Er is geen  wikkelklassen nodig voor primitieve types.
- **Nadeel**: een array heeft steeds een **vaste grootte** die je niet zomaar kan wijzigen!

## Een array aanmaken.
Lange methode:

````java
int[] arr;          // initialisatie
arr = new int[3];   // constructor voor 3 waardes
arr[0] = 1;         // Array opvullen. vertrekt steed van index 0
arr[1] = 8;
arr[2] = 6;
System.out.println("arr = " + Arrays.toString(arr));
````

Of korter:

````java
int[] arr = new int[3]; // initialisatie + consturctor
arr[0] = 1;
arr[1] = 8;
arr[2] = 6;
System.out.println("arr = " + Arrays.toString(arr));
````

Of nog korter:

````java
int[] arr = new int[] {1, 8, 6};    // Nu geen aantal tussen de rechte haakjes invullen!
System.out.println("arr = " + Arrays.toString(arr));
````

Voor alle drie de methodes is de uitvoer identiek: `arr = [1, 8, 6]`

##Elementen uit een array ophalen/wijzigen.

...

###Met een for-lus.

...

###Met een for-each-lus.

...

##Een array kopiëren.
Een array kopiëren naar een andere array gaat niet zomaar!

###Ondiepe kopie (shallow copy)

````java
int[] arr1 = new int[] {1, 8, 6};
int[] arr2 = arr1;                  // Ondiepe kopie

System.out.println("arr1 = " + Arrays.toString(arr1));
System.out.println("arr2 = " + Arrays.toString(arr2));
System.out.println("----------------");
arr1[0] = 5555;
System.out.println("arr1 = " + Arrays.toString(arr1));
System.out.println("arr2 = " + Arrays.toString(arr2));
System.out.println("----------------"); 
````

Bij een *ondiepe kopie* is **arr2** enkel een **nieuwe referentie** (verwijzing) naar hetzelfde object als **arr1**. Een aanpassing in **arr1** is eveneens zichtbaar in **arr2**!

Uitvoer: 

````java
arr1 = [1, 8, 6]
arr2 = [1, 8, 6]
----------------
arr1 = [5555, 8, 6]
arr2 = [5555, 8, 6]
````

###Diepe kopie (deep copy) met clone()

````java
int[] arr1 = new int[] {1, 8, 6};
int[] arr2 = arr1.clone();          // Diepe kopie: met methode clone()

System.out.println("arr1 = " + Arrays.toString(arr1));
System.out.println("arr2 = " + Arrays.toString(arr2));
System.out.println("----------------");
arr1[0] = 5555;
System.out.println("arr1 = " + Arrays.toString(arr1));
System.out.println("arr2 = " + Arrays.toString(arr2));
````

Bij een *diepe kopie* is **arr2** een nieuwe array met eigen waardes.  
De lengte van **arr2** is **steeds identiek** aan de lengte van **arr1**.

Uitvoer: 

````java
arr1 = [1, 8, 6]
arr2 = [1, 8, 6]
----------------
arr1 = [5555, 8, 6]
arr2 = [1, 8, 6]
````

###Diepe kopie (deep copy) met System.arraycopy()

````java
int[] arr1 = new int[] {1, 8, 6};
int[] arr2 = new int[8];

System.out.println("arr1 = " + Arrays.toString(arr1));
System.out.println("arr2 = " + Arrays.toString(arr2));
System.out.println("----------------");

System.arraycopy(arr1, 0, arr2, 0, arr1.length);
arr1[0] = 5555;
System.out.println("arr1 = " + Arrays.toString(arr1));
System.out.println("arr2 = " + Arrays.toString(arr2));
````

Bij een *diepe kopie* is **arr2** een nieuwe array met eigen waardes.  
De lengte van **arr2** kan **verschillend** zijn aan de lengte van **arr1**.

Uitvoer: 

````java
arr1 = [1, 8, 6]
arr2 = [0, 0, 0, 0, 0, 0, 0, 0]
----------------
arr1 = [5555, 8, 6]
arr2 = [1, 8, 6, 0, 0, 0, 0, 0]
````

##Algoritmen met arrays.

###Sorteren (van laag naar hoog).

````java
int[] arr1 = new int[] {1,8,6,2,4,7};
System.out.println("arr1 = " + Arrays.toString(arr1));
Arrays.sort(arr1);              // Sorteer van laag naar hoog
System.out.println("arr1 = " + Arrays.toString(arr1));
````

Uitvoer: 

````java
arr1 = [1, 8, 6, 2, 4, 7]
arr1 = [1, 2, 4, 6, 7, 8]
````

###Sorteren (van hoog naar laag).

````java
int[] arr1 = new int[] {1,8,6,2,4,7};
Arrays.sort(arr1);      // Sorteer van laag naar hoog
System.out.println("arr1 (laag > hoog) = " + Arrays.toString(arr1));
        
// Sorteer van hoog naar laag via tijdelijke array 
int[] tmp = arr1.clone();
for (int i = 0; i < arr1.length; i++) {
    tmp[arr1.length - 1 - i] = arr1[i];
}
arr1 = tmp.clone();
System.out.println("arr1 (hoog > laag) = " + Arrays.toString(arr1));
````

Uitvoer: 

````java
arr1 (laag > hoog) = [1, 2, 4, 6, 7, 8]
arr1 (hoog > laag) = [8, 7, 6, 4, 2, 1]
````

###Kleinste en grootste getal ophalen.

````java
int[] arr1 = new int[] {1,8,6,2,4,7};
Arrays.sort(arr1);
System.out.println("kleinste getal = " + arr1[0]);
System.out.println("grootste getal = " + arr1[arr1.length-1]);
````

Uitvoer: 

````java
kleinste getal = 1
grootste getal = 8
````

###Lengte van een array wijzigen.

...

##Twee-dimentionele array.

...