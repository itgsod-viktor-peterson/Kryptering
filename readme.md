# Kryptering #

Den här uppgiften går ut på att skriva en krypteringsfunktion

## Bedömningsmatris ##

### Planering ###

| Förmågor                         | E 																																   | C | A |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|---|---|
| Aktivitetsdiagram och pseudokod  | Du använder pseudokod och/eller aktivitetsdiagram för att planera dina uppgifter utifrån exempel, eller i samråd med utbildaren.  | Som för E, men utan exempel eller handledning |   |
| Anpassning					   | Du anpassar med viss säkerhet planeringen till uppgiften 																		   |   | Som för E, men med säkerhet
| Utformning                       | Du väljer med viss säkerhet lämpliga kontrollstrukturer, metoder, variabler, datastrukturer och algoritmer | | Som för E, men du väljer med säkerhet, och motiverar utförligt dina val.|
| Utvärdering | Med viss säkerhet utvärderar du, med enkla omdömen, programmets prestanda, använder datalogiska begrepp, och bedömer din egen förmåga | som för E, men med nyanserade omdömen | Som för C, men med säkerhet, och med förbättringsförslag

### Syntax och Teori ###
| Förmågor                                       | E 																			| C | A |
|------------------------------------------------|------------------------------------------------------------------------------|---|---|
| Datatyper					                     | Du kan redogöra för och använda de vanligaste datatyperna                    |   |   |
| Grundläggande syntax		                     | Du kan redogöra för och använda programmeringsspråkets grundläggande syntax  |   |   |
| Villkor och IF-satser		                     | Du kan redogöra för och använda villkor och IF-satser                        |   |   |
| Loopar & iteration                             | Du kan redogöra för och använda loopar och iterera över listor               |   |   |

### Kodning och kodningsstil ###

| Förmågor                                      | E                                                                         | C                                               | A                                              |
|-----------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------|------------------------------------------------|
| Komplexitet									| Du kan skriva enkla program                                               | Du kan skriva lite mer avancerade program       | Du kan skriva komplexa program
| Sekventiell- & funktionsbaserad programmering | Du använder dig av sekventiell programmering och fördefinerade funktioner | Du skapar och använder enkla funktioner         | Du skapar mer komplexa funktioner              |
| Objektorienterad programmering                | Du använder dig av av fördefinerade klasser och objekt                    | Du skapar och använder enkla klasser och objekt | Du skapar och använder mer komplicerade klasser och objekt  |
| Struktur		 				                | Du skriver kod som är delvis strukturerad, har en konsekvent kodningsstil och tydlig namngivning | Som för E, men du skriver kod som är helt strukturerad |   			   |
| Felsökning                                    | Du felsöker på egen hand enkla syntaxfel | Som för E, men systematiskt, och dessutom även körtidsfel och programmeringslogiska fel | Som för C, men med effektivitet   	   |
| Undantagshantering                            |     																		| Du validerar användardata						  | Som för C, men du skriver även kod som använder undantagshantering |
| Dokumentering 								| Du skriver kod som är delvis kommenterad									|  												  | Du skriver kod som är utförligt kommenterad    |

### Datastrukturer ###

| Förmågor        | E 														   | C 																     | A 									 |
|-----------------|------------------------------------------------------------|---------------------------------------------------------------------|---------------------------------------|
| Listor          | Du kan redogöra för och använda dig av listor (Array)      |   																     |   									 |
| Hashtabeller    | Du kan redogöra för vad hashtabeller (Hash) är             | Du kan använda dig av hashtabeller 							     |   									 |

## Beskrivning ##

Krypteringsalgoritmen är en enkel förskjutningsalgoritm.

Tänk dig följande lista med bokstäver:

    Bokstav: A B C D E F G H I J  K  L  M  N  O  P  Q  R  S  T  U  V  W  X  Y  Z
    Index:   0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25

När man skall kryptera en sträng, t.ex `HELLO` letar man reda på varje bokstavs position i listan ovan.
Postitionen för `H` är 7, `L` är 11, osv

Du byter sen ut tecknet mot det tecken som finns på tecknets nuvarande position + förskjutningen.
Om det nya positionen inte får plats i listan fortsätter du räkna från början av listan

En förskjutning på 3 kan man visualisera på följande vis

    Bokstav:    A B C D E F G  H  I  J  K  L  M  N  O  P  Q  R  S  T  U  V  W  X  Y  Z
    Index:      0 1 2 3 4 5 6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25

    Ny Index:   3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25  0  1  2
    Ny Bokstav: D E F G H I J  K  L  M  N  O  P  Q  R  S  T  U  V  W  X  Y  Z  A  B  C

För vår exempelsträng `HELLO` skulle alltså ge följande resultat:

    H => K
    E => H
    L => O
    L => O
    O => R

För att avkryptera ett meddelande förskjuter man positionen åt andra hållet,
det vill säga, ett ord som krypterats med en förskjutning på 4 avkrypteras genom en förskjutning på *minus* 4

## Genomförande ##

### Versionshantering ###

Skapa ett **privat** repository för projektet på Github, och bjud in mig.
Gör *regelbundna* commits med beskrivande meddelande och synka åtminstone en gång per dag.

### Flödesschema ###

Innan du börjar koda ska du skapa ett flödesschema för programmet.
Flödesschemat ska checkas in i github.

### Kodning ###

Programmet skall utvecklas testdrivet.

Utveckla först krypteringsfunktionen, och se till att alla tester för den blir gröna innan du går över
till avkrypteringsfunktionen

#### Kryptering ####

Skapa funktionen `encrypt` i `lib/encryption.rb`

Testerna finns i `/spec/encryption_spec.rb`.

Kör `rspec /spec/encryption_spec.rb` för att köra testerna.

#### Avkryptering ####

Skapa funktionen `decrypt` i `lib/encryption.rb`

Testerna finns i `/spec/decryption_spec.rb`. Läs dem för att förstå hur funktionen skall fungera.
Kör `rspec /spec/decryption_spec.rb` för att köra testerna.

### Utvärdering ###

Efter programmet är avslutat skall du utvärdera hur projektet gick.