#JTextField

Package: [javax.swing.JTextField](http://docs.oracle.com/javase/7/docs/api/javax/swing/JTextField.html)

````java
class Paneel extends JPanel { 
    private JTextField txt;
    public Paneel() {
        txt = new JTextField(20);
        txt.setText("Dit is een tekstveld");
        add(txt);
    }
}
````
Of korter:
````java
class Paneel extends JPanel { 
    private JTextField txt = new JTextField("Dit is een tekstveld", 20);
    public Paneel() {
        add(txt);
    }
}
````
##Extra opties
Als voorbeeld een JTextField in een null-layout.
````java
class Paneel extends JPanel { 
    private JTextField lbl = new JTextField("Dit is een tekstveld");
    public Paneel() {
        setLayout(null);
        txt.setBounds(10, 10, 150, 25);                 // links, top, breedte, hoogte
        txt.setBackground(Color.PINK);                  // achtergrondkleur
        txt.setHorizontalAlignment(JTextField.RIGHT);   // rechts uitlijnen
        txt.setForeground(Color.BLUE);                  // tekstkleur
        txt.setEditable(false);                         // tekst niet wijzigbaar, wel selecteerbaar
        txt.setEnabled(false);                          // tekst niet selecteerbaar (krijgt grijze achtergrond)
    }
}
````