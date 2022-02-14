# Assignment Januari

## Deadlines

Taken

* Groepsgenoot kiezen + Topic Distributed Applicatie
  * Contactmoment: 1 Maart [link appointmentplanner](https://appointmentplanner.ucll.be/happening/iBSjl8GF)
  * Contactmoment: 1 Juli [link appointmentplanner](https://appointmentplanner.ucll.be/happening/YmjIyum8)
  * Excel [link](https://ucll-my.sharepoint.com/:x:/g/personal/u0124976_ucll_be/EYl4gnJTj9ZAvAr3NpoJ1EgBtQ4L86Vs20v3JlDKECnWNg)
  * Deadline: 2 Juli
* Schets OTP applicatie (monolith-ish design = ok)
  * Deadline bij eindpresentatie
* Schets volledig distributed applicatie flow (incl. pub/sub)
  * Deadline bij eindpresentatie
* Uitbreiding
  * Deadline bij eindpresentatie
* Eindpresentatie
  * Deadline 8 December

## Taken

### Groepsgenoot kiezen

Groepsgrootte is maximum 2 personen. Als je alleen wil werken, is dit mogelijk maar de opdracht wijzigt niet.

### Topic Distributed Applicaties

Jullie kiezen zelf een geschikt topic voor een distributed applicatie. Dit moet complex genoeg zijn zodat jullie 1. een Pub/Sub systeem moeten kunnen gebruiken ~~en 2. distributie d.m.v. distributed Erlang / full mesh kunnen implementeren~~.

Enkele **voorbeelden**:

* ~~Een live chatroom systeem met meerdere webservers. Idealiter, zou dit video moeten bevatten maar om de scope te beperken mogen dit berichtjes zijn (dat met zo weinig mogelijk latency moeten aankomen).~~
  * ~~Er is ook een direct messaging systeem, wat gebruik zou kunnen maken van pub/sub.~~
* Map met verschillende lagen (bijv. een MMO map). Dit via een pub/sub proberen te implementeren.
  * Spelers moeten elkaar kunnen aanvallen (moet niets complex zijn)
  * Spelers moeten elkaar direct kunnen messagen (voice chat alternatief - zo min mogelijk latency)
  * _Note: Je mag ook het distributed en pub/sub gedeelte omdraaien. In deze context is dit niet vreemd._
* Webinterface waar men scripts upload (e.g. code snippets)
  * Pub/Sub voor queueing mechanisme
  * Distributed Elixir voor snelle queue afname + orchestratie tussen verschillende nodes wie wat doet, wat bij een crash, etc...
* ~~Auction house systeem~~
  * ~~Distributed Elixir voor realtime updates en notificaties~~
  * ~~Pub/Sub voor inventory management / mail notifications~~
* Game server / manager / tracker
  * Distributed Elixir/Erlang voor spellen te tracken (in bijv. een toernooi). Inclusief load balancing over nodes.
  * Pub/Sub voor scores te communiceren naar mensen met interesse naar een bep. game.
* Zip parser van medische data
  * Distributed Elixir voor snel jobs te accepten, propageren door cluster en failover processen te configureren.
  * Pub/Sub voor queueing mechanisme
* ... Nog een idee? Maak een PR!

_**BELANGRIJK**: Vanwege veel gelijkaardige projecten in het 1ste semester, zijn live chat systemen en auction house onderwerpen niet meer toegelaten._

**Minimum requirements**:

* ~~Je applicatie moet **minstens** 2 verschillende applicatie nodes in je distributed Elixir/Erlang cluster hebben draaien~~
* Je moet minstens 2 exhanges met meerdere queues gebruiken met een aparte consumer (die niet in de cluster staat). De exchanges en queue's moeten uitgebreider zijn dan de voorbeeldopgaven.

### Schets OTP applicatie

Een schets van een OTP applicatie houdt de volgende aspecten in:

* Een tree structuur van de processen die je in gedachten hebt
* Je laat de flow zien van bepaalde acties d.m.v. een sequence diagram of andere **duidelijke** tool / overview. Correctheid van het diagram wordt niet geevalueerd, maar wel de correctheid van de communicatie / structuur!
* Hoe zit het met crashes / fault tolerancy? Wat mag wanneer crashen?

Dit begin je dan vervolgens uit te werken.

**Minimum requirements**:

* 2 deelbomen uitwerken dat de applicatie complex genoeg maakt voor de opgave.
* 2 groepen processen, users en domein-specifieke entiteiten zijn 2 veelvoorkomende groepen.

### Schets volledige distributed applicatie

Hier leg je de volledige application flow uit. Welke acties gaan door een distributed Elixir / Erlang systeem? Waarvoor gebruik je Pub/Sub? Welke topics / exchanges zijn er?

Dit kan je doen met [draw.io](draw.io). Maak eerst een template van je infrastructuur, en teken dan met pijlen hoe verschillende stappen van communicatie zullen verlopen.

**Minimum requirements**:

* Schema dat de RabbitMQ logica inhoudt. Dit houdt dus in: 
  * Je applicaties
  * Je exchanges (met bijhorende informatie)
  * (Dynamische) queues
  * Data flow

### Uitbreiding

Voorzie dat elke deelapplicatie in je distributed architectuur berichten logt en centraliseert op 1 applicatie. Communicatie zal dus, hoogstwaarschijnlijk (maar niet verplicht!), over RabbitMQ gaan. Ga ervan uit dat er veel logging trafiek is wat niet op 1 thread verwerkt kan worden.

### Presentatie

Hier laten jullie de werking van de applicatie zien d.m.v. een demonstratie + presentatie waar jullie alles in bundelen. Code + presentatie (pdf) wordt ingeleverd via Github Classroom.

Logischerwijze zal je applicatie moeten werken in de context van je gekozen onderwerp.
