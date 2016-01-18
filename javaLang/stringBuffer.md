#StringBuffer

Package: [java.lang.StringBuffer](http://docs.oracle.com/javase/7/docs/api/java/lang/StringBuffer.html)

---

## String vs StringBuffer.

Bij **veel wijzigingen** kan je beter  een **StringBuffer** gebruiken dan een **String**.

- String is een niet te wijzigen (immutable) object (eenmaal gemaakt, kan dit niet worden gewijzigd).
- Bij veranderen van String wordt **nieuw object gemaakt** en wijst String-referentie naar het nieuw object.  
  Het oude String-object gaat verloren.
- Een StringBuffer is een variabele (in feite een collectie) waarin automatisch voldoende ruimte wordt voorzien voor stringmanipulaties.
- Initieel bevat StringBuffer-object 16 tekens/cellen.  
Als de bufferruimte vol is, wordt automatisch een nieuwe collectie van dubbele grootte aangemaakt (en de inhoud van de StringBuffer daarin gekopieerd).  


###De methode toString().

Terugkeerwaarde = String-object met inhoud van (string in) het StringBuffer-object.

````java
char a = 'a', z = 'z';
StringBuffer s1 = new StringBuffer();
StringBuffer s2 = new StringBuffer();
for (int i = a; i <= z; i++) {      // loop met int
    s1.append((char) i);
}
System.out.println(s1.toString());
System.out.println("----------------------");
for (char i = a; i <= z; i++) {      // loop met char
    s2.append(i);
}
System.out.println(s2.toString());
````

Uitvoer: 

````java
abcdefghijklmnopqrstuvwxyz
----------------------
abcdefghijklmnopqrstuvwxyz
````

###De methode charAt(int i, char c).

Vervang het karakter op positie *i* door het karakter *c*.


````java
StringBuffer b = new StringBuffer("bal");
b.setCharAt(1, 'o');
System.out.println(b.toString());
````

Uitvoer: 

````java
bol
````