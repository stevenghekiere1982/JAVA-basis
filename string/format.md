#String.Format()

Package: [java.lang.String](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html)

---

Voor het formatteren van getallen in de uitvoer, gebruik je best  `String.format(Locale l, String format, Object... args)`. De landinstelling (`Local l`) is optioneel.

- Het formaat begint steeds met **%**
- Het formaat eindigt op **f** (voor kommagetallen), op **d** (voor gehele getallen) of op **s** (voor strings)
- Het aantal cijfers wordt aangegeven met **x.y**.  
**x** is het totaal aantal karakters van de string (incl. komma).  
**y** is het aantal cijfers na de komma.
- String links uitlijnen: begin het formaat met **%-**
- Voorloopnullen tonen: begin het formaat met **%0**

###Kommagetallen formatteren (formaat eindigt steeds op d)

`int g = 12345`  (witruimtes worden ter illustratie weergegeven met een -teken).

| format specifier | resultaat |
| ---------------- | --------- |
| "" + g| 12345 |
| String.format("%d", g)| 12345 |
| String.format("%10d", g)| -----12345 |
| String.format("%-10d", g)| 12345----- |
| String.format("%010d", g)| 0000012345 |

###Gehele getallen formatteren (formaat eindigt steeds op f)

`double g = 1234.56`  (witruimtes worden ter illustratie weergegeven met een -teken). Let ook op de punt en de komma!

| format specifier | resultaat |
| ---------------- | --------- |
| "" + g| 12345.56 |
| String.format("%.1f", g)| 1234,6 |
| String.format("%10.3f", g)| --1234,560 |
| String.format("%-10.3f", g)| 1234,560-- |
| String.format("%010.3f", g)| 001234,560 |

###Strings formatteren (formaat eindigt steeds op s)

`String str = "abc"`  (witruimtes worden ter illustratie weergegeven met een -teken).

| format specifier | resultaat |
| ---------------- | --------- |
| String.format("%s", str)| abc |
| String.format("%6s", str)| ---abc |
| String.format("%-6s", str)| abc--- |

###Lindinstelling

De formattering voor punten en komma's wordt bepaald door de landinstelling van je systeem. Je kan de formattering wijzigen door als eerste paramater de gewenste landinstelling toe te voegen. Zie [Field Summary](http://docs.oracle.com/javase/7/docs/api/java/util/Locale.html)

| format specifier | resultaat |
| ---------------- | --------- |
| String.format("%.2f", g)| 1234,56 |
| String.format(Locale.US, "%.2f", g)| 1234.56 |
| String.format(Locale.FRANCE ,"%.2f", g)| 1234,56 |

## Links

- http://docs.oracle.com/javase/tutorial/java/data/numberformat.html