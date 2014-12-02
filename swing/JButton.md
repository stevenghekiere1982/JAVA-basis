#JButton

Package: [javax.swing.JButton](http://docs.oracle.com/javase/7/docs/api/javax/swing/JButton.html)

---

````java
class Paneel extends JPanel { 
    private JButton btn;
    public Paneel() {
        btn = new JButton();
        btn.setText("Dit is een knop");
        add(btn);
    }
}
````
Of korter:
````java
class Paneel extends JPanel { 
    private JButton btn = new JButton("Dit is een knop");
    public Paneel() {
        add(btn);
    }
}
````
##Extra opties
Als voorbeeld een JButton in een null-layout.
````java
class Paneel extends JPanel { 
    private JButton btn = new JButton("Dit is een knop");
    public Paneel() {
        setLayout(null);
        btn.setBounds(10, 10, 150, 25);             // links, top, breedte, hoogte
        btn.setBackground(Color.YELLOW);            // achtergrondkleur
        btn.setHorizontalAlignment(JButton.RIGHT);  // rechts uitlijnen
        btn.setForeground(Color.BLUE);              // tekstkleur 
        btn.setEnabled(false);                      // tekst niet selecteerbaar (krijgt grijze achtergrond)
        add(btn);
    }
}
````