#Javadoc

**Javadoc** is een documentatiegenerator uit de Java Development Kit (JDK), waarmee HTML-pagina's met API-documentatie worden gemaakt. API documentatie wordt gebruikt om een programma te beschrijven, het geeft aan in welke packages en klassen een Java programma is ingedeeld, welke variabelen en methoden er zijn, en wat ze precies doen in het programma.

Commentaar voor javadoc-informatie plaats je tussen `/**` en `*/`

| Element |  Omschrijving  |
| ------- | ---------------|
| @author | Naam van de programmeur |
| @version | Geeft het versienummer van een methode of klasse aan |
| @param | Definieert een parameter van een methode. Verplicht voor iedere parameter |
| @return | Documenteert de teruggegeven waarde. Moet niet gebruikt worden voor methoden die een void teruggeven. |
| @returns | Een synoniem voor @return |
| @see | Geeft een verwijzing aan naar een andere methode of klasse |
|  | 
| @deprecated | Markeert de methode als verouderd (deprecated) |
| @exception | Geeft aan wanneer een uitzondering (exception) veroorzaakt kan worden (thrown) door een methode — zie ook @throws. |
| @since | Geeft aan wanneer een methode toegevoegd is aan de klasse |
| @throws | Documenteert de veroorzaakte uitzondering (thrown exception). Een synoniem voor @exception, geïntroduceerd in Javadoc 1.2 |

##Javadoc genereren vanuit NetBeans

 - Klik met de rechtermuistoets op het project en kies "generate Javadoc" uit jet snelmenu.
 - Je vindt de gegenereerde HTML-bestanden in de map "/dist/javadoc/".