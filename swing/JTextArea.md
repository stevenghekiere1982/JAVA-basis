#JTextField

Package: [javax.swing.JTextArea](http://docs.oracle.com/javase/7/docs/api/javax/swing/JTextArea.html)

````java
class Paneel extends JPanel { 
    private JTextArea area;
    public Paneel() {
        area = new JTextArea(10,30);  // 10 rijen, 30 kolommen
        area.setText("Lijn 1 \nLijn 2");
        add(area);
    }
}
````
Of korter:
````java
class Paneel extends JPanel { 
    private JTextArea area = new JTextArea("Lijn 1 \nLijn 2", 10, 30);
    public Paneel() {
        add(area);
    }
}
````
##Extra opties
````java
class Paneel extends JPanel { 
    private JTextArea area;
    public Paneel() {
        area = new JTextArea();
        area.setPreferredSize(new Dimension(300, 200));   // 300px breed , 200px hoog
        area.setText("Lijn 1 \nLijn 2");
        area.setFont(new Font("MonoSpaced",Font.PLAIN,11));
        //area.setEditable(false);
        add(area);
        add( new JScrollPane(area) );  //schuifbalk(en) plaatsen. Altijd NA add(area) !!!
    }
}
````