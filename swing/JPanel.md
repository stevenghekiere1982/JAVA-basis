#JPanel

Package: [javax.swing.JPanel](http://docs.oracle.com/javase/7/docs/api/javax/swing/JPanel.html)

---

Een  *JPanel* is een container waaron we verschillende componenten kunnen plaatsen. Met behulp van deze componenten maken we de gebruikersinterface (*GUI*).

De *GUI* is een aparte klasse met (bijvoorbeeld) de naam *Paneel*.

##FlowLayout

De *FlowLayout* is de standard lay-outmanager. Hij legt alle componenten in één enkele rij en begint een nieuwe rij wanneer het venster niet voldoende breed is.

Onderstaand voorbeeld toont rood paneel met een knop ([JButton](JButton.md)) een tekstveld ([JTextField](JTextField.md)) en een label ([JLabel](JLabel.md)) in een FlowLayout.

```java
import java.awt.*;
import javax.swing.*;

public class Voorbeeld extends JFrame {

    public static void main(String[] args) {
        JFrame frame = new Voorbeeld();
        frame.setSize(300, 150);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setTitle("Titel van het frame");
        frame.setContentPane(new Paneel());
        frame.setVisible(true);
    }
}

class Paneel extends JPanel {

    private JButton btn;
    private JTextField txt;
    private JLabel lbl;

    public Paneel() {
        setBackground(Color.RED);       // kleur achtergrond van Paneel
        btn = new JButton("Dit is een knop");
        txt = new JTextField("Dit is een tekstveld", 10);
        lbl = new JLabel("Dit is een label");
        add(btn);
        add(txt);
        add(lbl);
    }
}
```

Of korter:

```java
class Paneel extends JPanel {

    private JButton btn = new JButton("Dit is een knop");
    private JTextField txt = new JTextField("Dit is een tekstveld", 10);
    private JLabel lbl = new JLabel("Dit is een label");

    public Paneel() {
        setBackground(Color.RED);       // kleur achtergrond van Paneel
        add(btn);
        add(txt);
        add(lbl);
    }
}
```

##Lay-outmanager uitschakelen

Door de lay-outmanager volledig uit te schakelen, kan je de komponenten tot op de pixel juist positioneren. Met `setBounds(x, y, width, height)` bepaal je voor elke componet de exactie positie binnen het paneel. De volgorde waarin je de componenten toevoegt, is nu onbelangrijk.

```java
class Paneel extends JPanel {

    private JButton btn = new JButton("Dit is een knop");
    private JTextField txt = new JTextField("Dit is een tekstveld");
    private JLabel lbl = new JLabel("Dit is een label");

    public Paneel() {
        setLayout(null);                    // Lay-outmanager uitschakelen
        lbl.setBounds(10, 10, 150, 20);     // links, top, breedte, hoogte
        txt.setBounds(10, 40, 150, 20);
        btn.setBounds(10, 70, 150, 20);
        add(btn);                           // volgorde van toevoegen is onbelangrijk
        add(txt);
        add(lbl);
    }
}
```

##GridLayout

De gridlay-out verdeelt het paneel in secties volgens een tabelvorm. Alle rijen zijn even breed en alle kolommen zijn even even hoog `GridLayout(rows, colomns, padding X, padding y)`. Gebruik eventueel een border om het grid van de rand te verwijderen. Border is inderdaal van de package `javax.swing.border.*`  

```java
class Paneel extends JPanel {

    private JButton btn1 = new JButton("Knop 1");
    private JButton btn2 = new JButton("Knop 2");
    private JTextField txt1 = new JTextField("Tekstveld 1");
    private JTextField txt2 = new JTextField("Tekstveld 2");
    private JLabel lbl = new JLabel("Label");

    public Paneel() {
        setLayout(new GridLayout(3, 2, 10, 10));    //rijen, kolommen, horizontale padding, vertikale padding
        Border rand = BorderFactory.createEmptyBorder(10, 10, 10, 10);  // rand(boven, links, onder, rechts)
        setBorder(rand);
        add(btn1);
        add(txt1);
        add(btn2);
        add(txt2);
        add(new JLabel(""));        // Lege cel opvullen
        add(lbl);
    }
}
```