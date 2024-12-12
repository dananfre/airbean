# airbean
Airbean - Framtidens Kaffeleverans. 

En analys av Airbean utifrån de olika delproceserna (decompisition, pattern recognition, abstraction, algorithm design)

Länk till vårt FigJam: https://www.figma.com/board/HjMmJfA5exxf0VtXwRQQLB/AirBean---Ultra-Ninjas?node-id=0-1&t=ZfH5hqIdzfP6p1Vb-1

Ett grupparbete i kursen "Introduktion till programmering och datalogiskt tänkande" på utbildningen FED24. Gruppmedlemmar: Senja Erlandsson, Markus Korhonen, Embla Holgersson och Daniel Fredriksson.

## Decomposition
Vi skapade sex kategorier(nav, produktkatalog, om oss, kassa och betalning, kundhantering samt lager och logistik). Dessa anser vi är de viktigaste beståndsdelarna till Airbean appen. Där efter utvecklade vi dessa kategorier tills de innehåll minst 3 till 4 steg. Vi upplevde detta var tillräckligt för att få en utförlig decompositon av appen. Vi ville hålla oss till det mest relevanta men ändå få upp en detaljerad karta över appen, vi upplever vårat slutresultat reflekterar detta.

Till exempel kategorin “Kassa och betalning” kom vi överens om att det mest grundläggande och det första man behöver skapa, är en “kundvagn”. Sedan kom kategorier som “betalningsalternativ”, “Säkerhet” och ett “Beställ” fält, samt har vi målat upp hur processen fungerar ungefärt. 

Om vi senare skulle koda denna app hade vi haft en tydlig decomposition som hade hjälpt oss med att förstå de olika delarna som bygger upp appen, samt hur appen är tänkt att fungera.

## Pattern Recognition
### Lagra data
Data som behöver lagras på ett strukturerat vis: produktinformation, kunddata. På kund ska orderhistorik sparas.

### Kundscenarion 
Vi försökte se vanliga scenarion hos köpare och hur återupprepning skulle kunna förenklas. Vi tittade på hur kaffemenyn skulle användas av kund, och försökte komma på konkreta mönster och bemöta dem. Vi ansåg att det viktigaste var att ha en tydlig struktur med bra grupperingar och filter för att hitta det man söker. Det kändes även viktigt att få snabb återkoppling då man lagt något i varukorgen för att kunden ska hänga med i processen. Vi tänkte även att dagliga rekommendationer skulle vara en uppskattad funktion då det ökar försäljning och många kunder handlar efter just rekommendationer.

## Abstraction
Vi abstraherar produkt och kund för att göra systemet skalbart och lätthanterligt. 

### Produkt
Alla produkter har ett unikt ID. Övrig information kan variera. Info kring samtliga produkter finns lagrad i en databas.
Egenskaper som varierar: Produktens data (pris, beskrivning, ursprungsland, osv.) kan vara olika beroende. Vi abstraherar bort oväsentliga detaljer och skapar en flexibel datastruktur som kan hantera olika typer av egenskaper.

### Kund
Varje registrerad kund har ett unikt ID i en databas. Till detta ID kopplas information kring kunden. Här lagras bland annat kundens betalinformation för “easy checkout”, samt adress. En icke registrerad kund skriver in sitt personnummer, varpå detaljer kring personens namn och adress hämtas från extern databas. En icke registrerad kund kan enkelt betala med swish. 

### Modulär uppbyggnad 
Vi dela upp systemet i separata moduler: Produkt, Kund, och Extern databasintegration. Varje modul ansvarar för sin del, vilket gör koden mer underhållbar.

### Extern datahämtning 
Vi skapar en funktion som automatiskt hämtar namn och adress från den externa databasen baserat på personnummer.

## Algorithm Design
Vi skapade ett beställningsflöde där användaren först bläddrar bland produkter, väljer en produkt och lägger den i varukorgen. Sedan loggar de in, registrerar sig eller fortsätter som “gäst” för att gå vidare till betalning.

För registrerade kunder sparas uppgifter för snabbare köp och du kan även välja “easy-checkout” där förvalt betalningsätt är valt och du kommer direkt till beställning, icke-registrerade kunder kan enkelt fylla i sina uppgifter eller hämta uppgifter med personnummer.

Detta beställningsflöde anser vi skapar en smidig upplevelse för kunden när hen beställer kaffe via Airbean. Vi har gjort dessa val baserat på att varje kund ska ska ha det så lätt som möjligt, även om de inte är medlemmar. Dock eftersom vi vill sälja medlemskap så har vi gjort det allra lättast att köpa kaffe med “easy-checkout” som medlem. Där är dina uppgifter sparade och kaffet kan nå kunden så snabbt som möjligt.


