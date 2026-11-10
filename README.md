# Stålarena – flerspiller

Stålarena er et arenaskytespill i 90-tallsstil som kjører i nettleseren. Du kan spille alene mot boter, eller lage et rom og spille mot familie og venner på mobil, Mac og PC.

Hele spillet ligger i én fil: `index.html`.

## Legg spillet på nett

Flerspiller virker bare når spillet ligger på en vanlig nettside. Det virker ikke inne i Claude. Velg én av måtene under. Begge er gratis.

### Netlify Drop (raskest, ingen koding)

1. Gå til https://app.netlify.com/drop
2. Dra mappen `stalarena-online` (eller zip-filen) inn i vinduet.
3. Du får en adresse som ligner på `https://tilfeldig-navn.netlify.app`.
4. Lag en gratis konto når Netlify spør, ellers slettes siden etter en time.

Når du vil oppdatere spillet, drar du den nye mappen inn på samme side i Netlify.

### GitHub Pages

1. Lag et nytt, offentlig repository på GitHub, for eksempel `stalarena`.
2. Last opp `index.html` med «Add file» og «Upload files».
3. Gå til «Settings» og deretter «Pages».
4. Velg «Deploy from a branch», grenen `main` og mappen `/ (root)`, og trykk «Save».
5. Etter et par minutter ligger spillet på `https://<brukernavnet-ditt>.github.io/stalarena/`.

## Slik spiller dere sammen

1. Den som lager rommet åpner spillet på en PC eller Mac, skriver navnet sitt og trykker **Lag rom**.
2. Du får en kode på fem tegn og en lenke. Send lenken til de andre, for eksempel på SMS.
3. De andre åpner lenken, skriver navnet sitt og trykker **Bli med**. Koden er allerede fylt inn.
4. Når alle er med, trykker verten **Start kampen**. Kommer noen senere, blir de med midt i kampen.

Det kan være med opptil 8 personer i et rom. Boter fyller opp resten hvis dere vil det.

## Godt å vite

- **Verten må holde spillet åpent.** Hele kampen kjører hos den som lagde rommet. Lukker verten fanen, slutter kampen for alle. Fanen kan ligge i bakgrunnen, men maskinen må ikke gå i dvale.
- **De fleste nettverk virker.** Spillerne kobles direkte sammen (WebRTC) via den gratis tjenesten PeerJS. Noen jobb- og skolenettverk stenger for dette. Prøv da mobilnett eller et annet Wi-Fi.
- **Best på samme Wi-Fi.** Hjemme på samme nett er forsinkelsen nesten null. Over internett merkes litt forsinkelse, men spillet retter opp for det.
- **Mobil:** Snu telefonen på tvers. Venstre tommel styrer, høyre tommel sikter. Hold SKYT og dra for å sikte mens du skyter.

## Test på din egen maskin

Legg til `?lokal` i adressen, for eksempel `https://…/index.html?lokal`. Åpne den i to faner i samme nettleser. Lag rom i den ene fanen og bli med i den andre. Da går trafikken mellom fanene i stedet for over nettet.

## Slik er spillet bygget

- **Verten bestemmer.** Vertens nettleser kjører hele kampen: bevegelse, treff, skade, poeng, pickups og boter. Den sender en oppdatering til alle 20 ganger i sekundet.
- **Du beveger deg med en gang.** Din egen nettleser beregner bevegelsene dine med en gang du trykker. Når svaret fra verten kommer, retter den opp eventuelle små avvik uten at bildet hopper.
- **Andre spillere vises jevnt.** De andre vises 0,1 sekund på etterskudd, slik at de glir jevnt mellom oppdateringene.
- **Treff er rettferdige.** Når du skyter med Pulsgeværet eller Splintkanonen, spoler verten de andre tilbake til der du så dem. Da teller treffet selv med litt forsinkelse.

## Ideer til neste versjon

- Flere baner, og at verten kan velge bane i lobbyen
- Lag mot lag og «ta flagget»
- Flere våpen og skins
- Egne lyder og musikk
- En egen liten server for nettverk som stenger direkte tilkobling
