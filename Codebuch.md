# Ruegen-Ranger-Pretest Codebuch #
Codebuch Stand 2021-01-07<br>
erstellt von Artur Stolinsky (as383@hdm-stuttgart.de)

## Inhalt
- Edgelist_Rügen-Ranger_Pretest.csv (Edgelist)
- Nodelist_Rügen-Ranger_Pretest.csv (Nodelist)
- Codebuch.md (Codierung der Datensätze)

## Ursprung und Datenerhebung

Im Pretest werden exemplarisch zehn vom Presserat öffentlich gerügte Artikel in einem Gesamtnetzwerk dargestellt. Die Daten wurden auf der Website des Presserats unter folgendem Link erhoben: (https://www.presserat.de/ruegen-presse-uebersicht.html). Die Artikel aus dem Pretest stammen von 1990 und 2020.

Das Netzwerk ist ein *gerichtetes three-mode Akteursnetzwerk*. Ausgangsgangspunkt für das Netzwerk ist der Presserat.

## Weitere Anmerkungen

Dieses Codebuch kann auch für das gesamte Projekt verwendet werden. Die Edges und Nodes bleiben dieselben, nur der Umfang des Gesamtnetzwerks ist erhöht.

# Nodes und dazugehörige Attribute

### Presserat

Die Node für den Presserat. Sie soll im Zentrum des Netzwerks dargestellt werden. Diese Kategorien besitzt folgende ***Attribute***:

**id**

eindeutige Codierung des Knoten, wird als Name angegeben (z.B. Pressekodex)

**name**

Vollständiger Name des Knotens

**type**

Unterscheidung zwischen Presserat, Ziffer und Publikationsmedium

1 = Presserat<br>
2 = Ziffer<br>
3 = Publikationsmedium


### Ziffern Pressekodex

Diese Nodes stehen für einzelne Ziffern des Pressekodex, gegen die verstoßen worden ist. Sie werden im Netzwerk zwischen dem Presserat und den gerügten Artikeln dargestellt. Ziffern, gegen die von keinem Artikel verstoßen worden sind, werden nicht in Nodelist und Netzwerk berücksichtigt. Die Ziffern 3, 5 und 14 - 16 werden nicht berücksichtigt.
Diese Kategorie besitzt folgende ***Attribute***:

**id**

eindeutige Codierung des Knoten, wird als "Ziffer" + Zahl angegeben (z.B. Ziffer10)

**name**

Vollständiger Name des Knotens (z.B. Pressekodex Ziffer 1)

**type**

Unterscheidung zwischen Presserat, Ziffer und Publikationsmedium

1 = Presserat<br>
2 = Ziffer<br>
3 = Publikationsmedium


### Gerügte Artikel

Diese Nodes stehen für die Artikel, die eine Rüge vom Presserat erhalten haben. Sie werden außen im Netzwerk dargestellt. Diese Kategorie besitzt folgende ***Attribute***:

**id**

eindeutige Codierung des Knoten, wird als "Publikationsmedium" + "Chronologische Nummerierung der Rüge für Publikationsmedium angegeben (z.B. Maedchen1)

**name**

Vollständiger Name des Knotens (z.B. Grazia Magazin (1067/19/3))

**infos**

Aktenzeichen im Archiv des Presserats (z.B. (0031/20/2))

**region**

Handelt es sich um ein regionales oder überregionales Publikationsmedium?

1 = überregional<br>
2 = regional

**type**

Unterscheidung zwischen Presserat, Ziffer und Publikationsmedium

1 = Presserat<br>
2 = Ziffer<br>
3 = Publikationsmedium

**year**

Jahr, in dem die Rüge erteilt wurde. Die möglichen Zahlen reichen von 1990 bis 2020.

**published**

Definiert die Verfügbarkeit des Artikels

1 = online<br>
2 = offline<br>
3 = beides

**author**

Name des Autors/der Autorin des gerügten Artikels (mit einer Spalte Abstand einzutragen, da evtl. nur Zusatzinfo)


# Edge-Attribute

**weight**

Art der Rüge

1 = öffentliche Rüge<br>
2 = nicht-öffentliche Rüge

**relationship**

1 = Pressekodex<br>
2 = verstößt gegen

**year**

Definiert das Jahr, in dem die Rüge erteilt worden ist
