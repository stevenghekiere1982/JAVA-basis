JAVA-basis (Swing)
==========

Samenvatting cursus JAVA basis Thomas More Kempen: Elektronica-ICT.

U kan deze samenvatting offline lezen met de [markdown-preview plug-in](https://github.com/volca/markdown-preview) voor Chrome. Vink zeker de optie "Allow access to file URLs" aan in [chrome://extensions/](chrome://extensions/)

## Inhoudstafel

- [NetBeans shortcuts](#netbeans-shortcuts)
- [NetBeans Code Templates](#netbeans-code-templates)
- [JAVA packages](#java-packages)
- [Primitieve data-types](#primitieve-data-types)
- [Keuzes en herhalingen](#keuzes-en-herhalingen)
- [UML-diagrammen](UML/uml.md)
- [Klassen en objecten](#Klassen-en-objecten)
- [Links](#links)

## NetBeans shortcuts

| Shortcut        | Actie  |
| ------------- | -----|
| `Ctrl+r` | Naam van een variabele globaal vervangen |
| `Ctrl+shift+c` | Zet een volledig blok code in/uit commentaar |
| `Ctrl+shift+i` | Voeg ontbrekende imports toe |
| `Alt-Shift-F` | Herformateer decode |

## NetBeans Code Templates

Code Templates zijn lettercombinaties waarmee u snel een basisstructuur op de pagina plaatste.   
U vindt deze terug onder het menu: Tools -> Options -> Editor -> Code Templates (Language: Java).  

Typ de lettercombinatie gevolgd door een tab om de code te plaatsen.

Enkele voorbeelden van voorgedefinieerde templates:

| Lettercombinatie | Actie  |
| ------------- | -----|
| `psvm` | methode main() |
| `sout` | methoden System.out.println() |
| `soutv` | methode System.out.println() met variabele |
| `if` | if statement |
| `ife` | if-else statement |
| `ws` | switch statement |

U kan natuurlijk ook eigen templates toevoegen. Enkele voorbeelden

| Lettercombinatie |  | Actie  |
| ------------- | ----- | -----|
| `tmmain` | [code](codeTemplates/tmmain.md) | volledig basisscript inc. JFrame, JPanel, ActionListener en paintComponent  |
| `tmaction` | [code](codeTemplates/custom.md#tmaction) | ActionListener |
| `tmpaint` | [code](codeTemplates/custom.md#tmpaint) | paintComponent |
| `tmpanel` | [code](codeTemplates/custom.md#tmpanel) | JPanel met ActionListener |

##JAVA packages

*   **javax.swing.\***

    > [JFrame](swing/JFrame.md) - [JPanel](swing/JPanel.md)   
    > [JButton](swing/JButton.md) - [JLabel](swing/JLabel.md) - [JTextField](swing/JTextField.md)  
    > border - BorderFactory - JScrollPane 
*   **java.awt.event.\***

    >  ActionEvent - ActionListener
*   **java.awt.\***

    >  Color - FlowLayout - Font - Graphics - GridLayout - Polygon
*   **java.lang.\***

    >  Boolean - Char - Double - Integer - Math - Object - String - StringBuffer - System
*   **java.util.\***

    >  [Array](javaUtil/array.md) - ArrayList - Local - [Calendar](http://tutorials.jenkov.com/java-date-time/java-util-calendar.html)

## Primitieve data-types

Java kent **acht primitieve datatypes** die géén objecten zijn:  
`boolean`, `char`, `byte`, `short`, `int`, `long`, `float` en `double`.  
Deze datatypes zijn puur bestemd om allerlei waarden op te slaan en rekenkundige bewerkingen op uit te voeren.  

Voor elk datatype bestaat wel een zogenaamd wrapper object (omhulzen, omwikkelen): `Boolean`, `Character`, `Byte`, `Short`, `Integer`, `Long`, `Float` en `Double`. 
Met zo'n wrapper-object kun je o.a. de primitieve datatypes converteren naar strings (met de *toString()* methode) of omgekeerd (met o.a. de *parse* methoden). Ook kun je hiermee primitieve datatypes converteren naar wrapper objecten of omgekeerd.

###Gehele getallen

| type |  wrapper  |bits | String (bv: "5") naar getal| getal naar String | Type Casting |
| ------------- | -----|------------------ |  ---- | ---- | ----|
| byte |  Byte | 8 | Byte.parseByte("string") | "" + getal | (byte) getal |
| short | Short| 16 | Short.parseShort("string") | "" + getal |  (short) getal |
| int |Integer| 32 |  Integer.parseInt("string") | "" + getal | (int) getal |
| long | Long|64 | Long.parseLong("string") |  "" + getal | (long) getal |

### Kommagetallen

| type |  wrapper  |bits | String (bv: "5.7") naar getal| getal naar String | Type Casting |
| ------------- | -----|----------------- |  --- | ---- | ----|
| float | Float| 32 | Float.parseFloat("string") | "" + getal | (float) getal |
| double | Double|  64 |  Double.parseDouble("string") | "" + getal | (double) getal |

### Overige

| overige |  wrapper  | waarde |
| ------------- | -----| ------------- |
| char | Character |één 16-bit [Unicode](http://nl.wikipedia.org/wiki/Unicode) karakter | 
| boolean | Boolean|  `true` of `false` |

Extra info: [http://balusc.blogspot.be/2006/04/java-tutorial-datatypen.html](http://balusc.blogspot.be/2006/04/java-tutorial-datatypen.html)

##Strings

*   **Strings (en getallen) formatteren**

    > [String.Format()](string/format.md)

##Keuzes en herhalingen

| type   | [if-else](keuze_herhaling/if.md)  | [switch](keuze_herhaling/switch.md) | [equals](keuze_herhaling/equals.md)  | [for](keuze_herhaling/for.md) | [while](keuze_herhaling/for.md) | [do-while](keuze_herhaling/for.md) |
| ------ | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| byte   | x | x | - | x | x | x |
| short  | x | x | - | x | x | x |
| int    | x | x | - | x | x | x |
| long   | x | - | - | x | x | x |
| float  | x | - | - | x | x | x |
| double | x | - | - | x | x | x |
| char   | x | x | - | x | x | x |
| boolean| x | - | x | - | - | - |
| String | - | - | x | - | - | - |


##Klassen en objecten

*   **Klassen en objecten**

    > [Klassen vs objecten](klassen/klassen.md) - [UML diagram](UML/uml.md) - [StarUML](http://staruml.io/) - [Javadoc](javadoc/javadoc.md)  
    
## Array vs. ArrayList
 
 - [8 belangrijke verschillen tussen Array en ArrayList](http://javahungry.blogspot.com/2015/03/difference-between-array-and-arraylist-in-java-example.html)   

## Links

- [http://www.tutorialspoint.com/java/](http://www.tutorialspoint.com/java/)
- [https://sites.google.com/site/cursusguielien/](https://sites.google.com/site/cursusguielien/)
- [http://www.java2s.com/](http://www.java2s.com/)
- [animal classification](http://kendeanagudo.hubpages.com/hub/Facts-about-Animals-Its-Types-and-Classification#)
