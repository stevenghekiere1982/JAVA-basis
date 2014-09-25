#Custom Code Templates#


````java
public void paintComponent(Graphics g){
    super.paintComponent(g);
    g.setColor(Color.red);
    g.drawString("txt to draw", 20, 20);
}
````

#tmaction
````java
class btnHandler implements ActionListener {
    public void actionPerformed(ActionEvent e) {
        btn.setText("Click");
     }
}
````

#tmpaint

````java
public void paintComponent(Graphics g){
    super.paintComponent(g);
    g.setColor(Color.red);
    g.drawString("txt to draw", 20, 20);
}
````

#tmpanel

````java
class Paneel extends JPanel
{
    private final JButton btn;
    private final JTextField txt;
    
    public Paneel() {
        btn = new JButton("Button");
        add(btn);
        btn.addActionListener(new btnHandler());
        txt = new JTextField("Textfield", 20);
        add(txt);
    }
    
    class btnHandler implements ActionListener {
        public void actionPerformed(ActionEvent e) {
            btn.setText("Click");
        }
    }
}
````



