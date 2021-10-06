# Assignment Januari

## Deadlines

Taken

* Groepsgenoot kiezen
  * Start 22 September
  * Deadline 06 Oktober
* Topic Distributed Applicatie
  * Start 22 September
  * Deadline ~~13~~ 20 Oktober
* Schets OTP applicatie (monolith-ish design = ok)
  * Start 13 Oktober
  * Deadline 10 November
* Schets volledig distributed applicatie flow (incl. pub/sub)
  * Start 10 November
  * Deadline 17 November
* Eindpresentatie
  * Deadline 8 December

## Taken

### Groepsgenoot kiezen

Groepsgrootte is maximum 2 personen. Als je alleen wil werken, is dit mogelijk maar de opdracht wijzigt niet.

### Topic Distributed Applicaties

Jullie kiezen zelf een geschikt topic voor een distributed applicatie. Dit moet complex genoeg zijn zodat jullie 1. een Pub/Sub systeem moeten kunnen gebruiken en 2. distributie d.m.v. distributed Erlang / full mesh kunnen implementeren.

Enkele voorbeelden:

* Een live chatroom systeem met meerdere webservers. Idealiter, zou dit video moeten bevatten maar om de scope te beperken mogen dit berichtjes zijn (dat met zo weinig mogelijk latency moeten aankomen).
  * Er is ook een direct messaging systeem, wat gebruik zou kunnen maken van pub/sub.
* Map met verschillende lagen (bijv. een MMO map). Dit via een pub/sub proberen te implementeren.
  * Spelers moeten elkaar kunnen aanvallen (moet niets complex zijn)
  * Spelers moeten elkaar direct kunnen messagen (voice chat alternatief - zo min mogelijk latency)
  * _Note: Je mag ook het distributed en pub/sub gedeelte omdraaien. In deze context is dit niet vreemd._
* Webinterface waar men scripts upload (e.g. code snippets)
  * Pub/Sub voor queueing mechanisme
  * Distributed Elixir voor snelle queue afname + orchestratie tussen verschillende nodes wie wat doet, wat bij een crash, etc...
* Auction house systeem
  * Distributed Elixir voor realtime updates en notificaties
  * Pub/Sub voor inventory management / mail notifications
* Game server / manager / tracker
  * Distributed Elixir/Erlang voor spellen te tracken (in bijv. een toernooi). Inclusief load balancing over nodes.
  * Pub/Sub voor scores te communiceren naar mensen met interesse naar een bep. game.
* Zip parser van medische data
  * Distributed Elixir voor snel jobs te accepten, propageren door cluster en failover processen te configureren.
  * Pub/Sub voor queueing mechanisme
* ... Nog een idee? Maak een PR!

**Requirements**:

* Je applicatie moet **minstens** 2 verschillende applicatie nodes in je distributed Elixir/Erlang cluster hebben draaien
* Je moet minstens 2 topics gebruiken met een aparte consumer (die niet in de cluster staat).

### Schets OTP applicatie

Een schets van een OTP applicatie houdt de volgende aspecten in:

* Een tree structuur van de processen die je in gedachten hebt
* Je laat de flow zien van bepaalde acties d.m.v. een sequence diagram of andere **duidelijke** tool / overview. Correctheid van het diagram wordt niet geevalueerd, maar wel de correctheid van de communicatie / structuur!
* Hoe zit het met crashes / fault tolerancy? Wat mag wanneer crashen?

Dit begin je dan vervolgens uit te werken.

### Schets volledige distributed applicatie

Hier leg je de volledige application flow uit. Welke acties gaan door een distributed Elixir / Erlang systeem? Waarvoor gebruik je Pub/Sub? Welke topics / exchanges zijn er?

Dit kan je doen met [draw.io](draw.io). Maak eerst een template van je infrastructuur, en teken dan met pijlen hoe verschillende stappen van communicatie zullen verlopen.

### Presentatie

Hier laten jullie de werking van de applicatie zien d.m.v. een demonstratie + presentatie waar jullie alles in bundelen. Code + presentatie (pdf) wordt ingeleverd via Github Classroom.
