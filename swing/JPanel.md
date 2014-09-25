#JPanel

Package: [javax.swing.JPanel](http://docs.oracle.com/javase/7/docs/api/javax/swing/JPanel.html)

---

Een  *JPanel* is een container waaron we verschillende componenten kunnen plaatsen. Met behulp van deze componenten maken we de gebruikersinterface (*GUI*).

De *GUI* is een aparte klasse met (bijvoorbeeld) de naam *Paneel*.

##FlowLayout

De *FlowLayout* is de standard lay-out manager. Hij legt alle componenten in één enkele rij en begint een nieuwe rij wanneer het venster niet voldoende breed is.

Onderstaand voorbeeld toont rood paneel met een knop ([JButton](JButton.md)) een tekstveld ([JTextField](JTextField.md)) en een label () in een FlowLayout.

```java
import java.awt.*;
import javax.swing.*;

public class Voorbeeld extends JFrame {

    public static void main(String[] args) {
        JFrame frame = new Voorbeeld();
        frame.setSize(600, 200);
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
        setBackground(Color.red);       // kleur achtergrond van Paneel
        btn = new JButton("Dit is een knop");
        txt = new JTextField("Dit is een tekstveld", 20);
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
    private JTextField txt = new JTextField("Dit is een tekstveld", 20);
    private JLabel lbl = new JLabel("Dit is een label");

    public Paneel() {
        setBackground(Color.red);       // kleur achtergrond van Paneel
        add(btn);
        add(txt);
        add(lbl);
    }
}
```
