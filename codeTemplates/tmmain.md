#Code Template: tmmain

````java
package __packageName;
import java.awt.*;          // Graphics
import java.awt.event.*;    // Event handlers
import javax.swing.*;

public class __ClassName extends JFrame {    
    public static void main(String[] args) {
        JFrame frame = new __ClassName();
        frame.setSize(600, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setTitle("Titel");
        frame.setContentPane( new Paneel() );
        frame.setVisible(true);
    }  
}    

class Paneel extends JPanel {
    private JButton btn;
    private JTextField txt;
    
    // Paneel (constructor)
    public Paneel() {
        setBackground(Color.WHITE);
        btn = new JButton("Button");
        add(btn);
        btn.addActionListener(new BtnHandler());
        txt = new JTextField("Textfield", 20);
        add(txt);
    }
    
    // Event handler (interne klasse)
    class BtnHandler implements ActionListener {
        public void actionPerformed(ActionEvent e) {
            btn.setText("Click");
            repaint();      // voer paintComponent() opnieuw uit
        }
    }
    
    // Paint component (interne klasse)
    public void paintComponent(Graphics g){
        super.paintComponent(g);    // wis inhoud van JPanel
        g.setColor(Color.red);
        g.drawString("Txt", 20, 20);
    }
}
````

##Hoe gebruiken.

1. Maak een nieuw project.
2. Wis de volledige code en voeg deze template toe.  
Type `tmpaint` gevolgd door een tab.
3. Wijzig op de eerste lijn  `__packageName` door de naam van uw package.
4. Bewaar de pagina.
5. Selecteer `__ClassName` en vervang de naam met de toetscombinatie `Ctrl+r` door de naam van uw klasse.
