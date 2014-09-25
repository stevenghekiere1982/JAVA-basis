JAVA-basis (Swing)
==========

Samenvatting cursus JAVA basis Thomas More Kempen: Elektronica-ICT.

U kan deze samenvatting offline lezen met de [MarkView plug-in](http://shaneweng.com/blog/view-markdown-file-with-markview/) voor Chrome. Vink zeker de optie "Allow access to file URLs" aan in [chrome://extensions/](chrome://extensions/)

## Inhoudstafel

- [NetBeans shortcuts](#netbeans-shortcuts)
- [NetBeans Code Templates](#netbeans-code-templates)
- [JAVA packages](#java-packages)
- [Primitieve data-types](#primitieve-data-types)
- [Links](#links)

## NetBeans shortcuts

| Shortcut        | Actie  |
| ------------- | -----|
| `Ctrl+r` | Naam van een variabele globaal vervangen |
| `Ctrl+shift+c` | Zet een gans blok code in/uit commentaar |
| `Ctrl+shift+i` | Voeg ontbrekende imports toe |
| `Alt-Shift-F` | Herformateer decode |

## NetBeans Code Templates

Code Templates zijn lettercombinaties waarmee u snel een basisitructuur op de pagina plaatste.   
U vindt deze terug onder het menu: Tools -> Options -> Editor -> Code Templates (Language: Java).  

Typ de lettercombinatie gevolgd door een tab om de code te plaatsen.

Enkele voorbeelden van voorgedefinieerde templates:

| Lettercombinatie | Actie  |
| ------------- | -----|
| `psvm` | methode main() |
| `sout` | methoden System.out.println() |
| `soutv` | methode System.out.println() met variabele |

U kan natuurlijk ook eigen templates toevoegen. Enkele voorbeelden

| Lettercombinatie |  | Actie  |
| ------------- | ----- | -----|
| `tmmain` | [code](codeTemplates/tmmain.md) | volledig basisiscript inc. JFrame, JPanel, ActionListener en paintComponent  |
| `tmaction` | [code](codeTemplates/custom.md#tmaction) | ActionListener |
| `tmpaint` | [code](codeTemplates/custom.md#tmpaint) | paintComponent |
| `tmpanel` | [code](codeTemplates/custom.md#tmpanel) | JPanel met ActionListener |

##JAVA packages

*   **javax.swing.\***

    > [JFrame](swing/JFrame.md) - [JPanel](swing/JPanel.md)   
    > [JButton](swing/JTextField.md) - [JLabel](swing/JLabel.md) - [JTextField](swing/JTextField.md)  
    > border - BorderFactory - JScrollPane 
*   **java.awt.event.\***

    >  ActionEvent - ActionListener
*   **java.awt.\***

    >  Color - FlowLayout - Font - Graphics - GridLayout - Polygon
*   **java.lang.\***

    >  Boolean - Char - Double - Integer - Math - Object - String - StringBuffer - System
*   **java.util.\***

    >  ArrayList - Local

## Primitieve data-types

Java kent **acht primitieve data-typen** die géén objecten zijn:  
`boolean`, `char`, `byte`, `short`, `int`, `long`, `float` en `double`.  
Deze datatypen zijn puur bestemd om allerlei waarden op te slaan en rekenkundig bewerkingen op uit te voeren.  

Voor elk van deze datatypen bestaat wel een zogenaamde wrapper object (omhulzen, omwikkelen): `Boolean`, `Character`, `Byte`, `Short`, `Integer`, `Long`, `Float` en `Double`. 
Met zo'n wrapper-object kun je o.a. de primitieve datatypen converteren naar strings (met de *toString()* methode) of omgekeerd (met o.a. de *parse* methoden). Ook kun je hiermee primitieve datatypen converteren naar wrapper objecten of omgekeerd.

###Gehele getallen

| type |  wrapper  |bits | String naar getal| getal naar String | getal naar String |
| ------------- | -----|----------------- | -------------| ---- | ---- |
| byte |  Byte | 8 | Byte.parseByte("string") | Byte.toString(getal) | "" + getal |
| short | Short| 16 | Short.parseShort("string") | Short.toString(getal) | "" + getal | 
| int |Integer| 32 |  Integer.parseInt("string") | Integer.toString(getal) | "" + getal |
| long | Long|64 | Long.parseLong("string") | Long.toString(getal) |  "" + getal |

### Gebroken getallen

| type |  wrapper  |bits | String naar getal| getal naar String | getal naar String |
| ------------- | -----|----------------- | -------------|  --- | ---- |
| float | Float| 32 | Float.parseFloat("5.7") | Float.toString(getal) | "" + getal |
| double | Double|  64 |  Double.parseDouble("5.7") | Double.toString(getal) | "" + getal |

### Overige

| overige |  wrapper  | waarde |
| ------------- | -----| ------------- |
| char | Character |één 16-bit [Unicode](http://nl.wikipedia.org/wiki/Unicode) karakter | 
| boolean | Boolean|  `true` of `false` |

Extra info: [http://balusc.blogspot.be/2006/04/java-tutorial-datatypen.html](http://balusc.blogspot.be/2006/04/java-tutorial-datatypen.html)


## Links

- [http://www.tutorialspoint.com/java/](http://www.tutorialspoint.com/java/)
- [https://sites.google.com/site/cursusguielien/](https://sites.google.com/site/cursusguielien/)
