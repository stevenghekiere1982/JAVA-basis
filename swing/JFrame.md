#JFrame

Package: [javax.swing.JFrame](http://docs.oracle.com/javase/7/docs/api/javax/swing/JFrame.html)

---

Elke applicatie bestaat uit een venster (een **frame**) dat later wordt ingevuld componenten zoals: teksten, knoppen, teksvelden, een menubalk, enz...

## Basisstructuur van een leeg frame.

De opstartklasse zorgt alleen voor het maken van een JFrame-object. Het frame is voorlopig leeg, en heeft enkel een titel en een sluitknop. Om het vesnter ook inhoud te geven, voegen we later een [JPanel](JPanel.md) toe.

**LET OP:** de *naam van de opstartklasse* (gebruikt op lijnen 4 en 6) MOET identiek zijn aan de *naam van het java-bestand*. In dit voorbeeld noemt het java-bestand ***voorbeeld.java***.

```java
import javax.swing.*;

public class Voorbeeld extends JFrame {

    public static void main(String[] args) {
        JFrame frame = new Voorbeeld();
        frame.setSize(600, 200);        // buitenafmetingen van het venster
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setTitle("Titel van het venster");
        frame.setVisible(true);         // toon het venster (NIET VERGETEN!!!) 
    }
}
```

Of vervang op lijn 6 `JFrame frame = ...` door `Voorbeeld frame = ...`. Dit geeft hetzelfde resultaat.

```java
JFrame frame = new Voorbeeld();
// wordt dan 
Voorbeeld frame = new Voorbeeld();
```

## Een frame met een gekleurde achtergrond.

Importeer **java.awt.\*** (lijn 1) en kleur de achtergrond geel (lijn 7).  
De default kleurwaardes vindt u in [java.awt.Color](http://docs.oracle.com/javase/7/docs/api/java/awt/Color.html).

```java
import java.awt.*;          // Package toevoegen!
import javax.swing.*;

public class Voorbeeld extends JFrame {
    public static void main(String[] args) {
        JFrame frame = new Voorbeeld();
        frame.getContentPane().setBackground(Color.yellow);
        frame.setSize(600, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setTitle("Titel van het frame");
        frame.setVisible(true);
    }
}
```