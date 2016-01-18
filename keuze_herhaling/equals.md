#Vergelijken van strings


Vergelijk strings **nooit** met een if-statement.   
Voor stringvergelijkingen gebruik je steeds de methode `equals()` of `equalsIgnoreCase()`!

```java
// for-lus
String a = "Ja", b = "Va";
String c = a + b;
        
System.out.println("Strings vergelijken met if-else:");
if(c == "JaVa") System.out.println("is gelijk aan");
else System.out.println("is niet gelijk aan!!!");
        
System.out.println("Strings vergelijken met equals()");
if(c.equals("JaVa")) System.out.println("is gelijk aan");
else System.out.println("is niet gelijk aan!!!");
```

Resultaat:

```java
Strings vergelijken met if-else:
is niet gelijk aan!!!
Strings vergelijken met equals()
is gelijk aan
```





