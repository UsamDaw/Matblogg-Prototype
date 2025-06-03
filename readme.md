# Matblogg Prototype

Dette er en enkel matblogg nettside der brukere kan dele og lagre oppskrifter her på nett. Alt er bygget med HTML, CSS, JavaScript og Firebase (Firestore og Authentication).

---

## Hvordan nettsiden fungerer

Når du besøker nettsiden for første gang, vil du se hjemmesiden for **Oppskrifter på nett**. Her kan du bla gjennom alle tilgjengelige oppskrifter, uavhengig av om du har en konto eller ikke.

For å registrere en ny bruker trykker du “Logg inn”, og kan da skrive inn brukernavn, e-post og passord. Brukernavnet blir lagret for profilen din slik at det vises på oppskrifter og i chatten, mens e-posten og passordet bare brukes til innlogging.

Når du logger inn, får du din egen side for oppskrifter. Her kan du:

- Lage nye oppskrifter med tittel, bilde (lenke), ingredienser og fremgangsmåte
- Redigere eller slette dine egne oppskrifter
- Søke i dine egne oppskrifter med søkefeltet
- Gå til “Online oppskrifter” og bla gjennom alle oppskrifter som er delt av alle brukere

Klikker du på en oppskrift, får du opp bildet, ingrediensene, fremgangsmåten og hvem som har laget oppskriften. Som innlogget bruker kan du også kontakte forfatteren direkte via chat.

---

## Restriksjoner for uregistrerte brukere

Uregistrerte (ikke-innloggede) brukere har noen begrensninger:

- De får kun se og bla gjennom **Online oppskrifter**, ikke tilgang til å lage egne oppskrifter.
- De ser kun “Logg inn” knappen oppe til høyre.
- Knappen "Tilbake til min matblogg" vises ikke for dem, siden de ikke har en egen matbloggside.
- De kan ikke chatte eller kontakte oppskriftsforfattere. Prøver de å åpne chat, blir de sendt rett til innlogging/registrering.
- De kan heller ikke redigere eller slette oppskrifter.

**Kort sagt:** Uregistrerte kan bare lese og utforske, men ikke bidra selv.

---

## Hva lagres i Firestore og Authentication

### **Authentication**
Her lagres e-post og passord for alle brukere som logger seg inn eller oppretter bruker. Hver bruker får også en unik ID.

### **Firestore**

#### users
Her lagres brukernavnet for hver bruker, koblet til bruker-ID fra Authentication.

#### recipes
Hver oppskrift du lager lagres her, med tittel, bilde-URL, ingredienser, fremgangsmåte, bruker-ID (som eier oppskriften) og når den ble lagret eller sist endret.

#### chats
Når du chatter med noen, lagres samtalen i “chats”, der meldinger har hvem som har sendt, innholdet og tidspunktet. Alt er koblet til brukerne via bruker-ID.
![Image](https://github.com/user-attachments/assets/528fe1bb-a2eb-4839-9214-2ff01c98e9ba)

---

### Kort oppsummert

Matbloggen gir deg en full oversikt over alle oppskrifter lastet opp av brukerne her på nettet. Som innlogget bruker kan du også legge til egne oppskrifter, redigere og chatte – men som uregistrert kan du kun se. Alt du lager og gjør, lagres trygt i Firestore slik at du aldri mister noe.  
Brukeropplevelsen er laget for å være enkel, moderne og ryddig.

---
