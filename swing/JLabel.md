#JLabel

Package: [javax.swing.JLabel](http://docs.oracle.com/javase/7/docs/api/javax/swing/JLabel.html)

````java
class Paneel extends JPanel { 
    private JLabel lbl;
    public Paneel() {
        lbl = new JLabel();
        lbl.setText("Dit is een label");
        add(lbl);
    }
}
````
Of korter:
````java
class Paneel extends JPanel { 
    private JLabel lbl = new JLabel("Dit is een label");
    public Paneel() {
        add(lbl);
    }
}
````
##Extra opties
Als voorbeeld een JLabel in een null-layout.
````java
class Paneel extends JPanel { 
    private JLabel lbl = new JLabel("Dit is een label");
    public Paneel() {
        setLayout(null);
        lbl.setBounds(10, 10, 150, 25);             // links, top, breedte, hoogte
        lbl.setBackground(Color.LIGHT_GRAY);        // achtergrondkleur
        lbl.setHorizontalAlignment(JLabel.RIGHT);   // rechts uitgelijnd
        lbl.setForeground(Color.RED);               // tekstkleur
        lbl.setOpaque(true);                        // om tekstkleur te tonen
        add(lbl);
    }
}
````
##JLabel met HTML-tags