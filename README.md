# MESHCORE_WEB_UI_Communicator_RO
aceasta este o interfata WEB pentru reteaua Meshcore, cu companion serial (in limba romana)

 Acest WEB UI s-a dezvoltat din necesitatea unei conexiuni sigure, pentru atunci cand sunt in shack sau la birou, pentru comoditatea de a lucra de la tastatura adevarata, nu de pe un display cu touch minuscul..
  prefer conexiunea seriala vs bluetooth, pentru stabilitate, cea BLE este mereu intrerupta, de drivere, ori de Windows sau de software, ori din cauza companion-ului; astfel nu am avut nicio singura data probleme..
Utilizarea acestei interfete este deosebit de simpla (scopul ptr care am creat-o), fara a instala softuri adiacente, fisiere .bat, scripturi, python ori alte complicatii cu care un user obisnuita se descurca mult mai greu deci, doar click pe fisier, se deschide interogarea de selectare a portului, in acest moment introduceti cablul USB, selectati portul detectat si ..SUCCES !!
Aveti acum un terminal de comunicatii digitale sigur, robust si eficient !

  Descriere:

  
# MeshCore WebUI — Companion Radio Interface
### YU\YO2LDK BaseStation KN05HQ · EU_868

---

## Ce este

**MeshCore WebUI** este o interfață web completă pentru rețeaua radio **MeshCore** (firmware open-source pentru dispozitive LoRa — Heltec, TTGO, RAK etc.), dezvoltată și extinsă pe parcursul unui proces iterativ de debugging, optimizare și adăugare de funcționalități noi față de versiunea originală.

Aplicația rulează direct în browser (Chrome/Edge cu Web Serial API) și se conectează prin USB la nodul local MeshCore, oferind un panou de control complet pentru monitorizarea și comunicarea în rețeaua mesh LoRa.

---

## Facilități principale

###  Rețea și noduri
- **Listă noduri** cu sincronizare automată la conectare și refresh manual
- **Badge-uri per nod**: `direct` (verde), `2 rpt` / `3 rpt` (amber), `prop` (albastru — propagare flood), `RPT` (violet — repetor MeshCore)
- **Hop count persistent** — numărul de repetori se salvează și nu dispare la advert-uri noi
- **Informații detaliate**: SNR, RSSI, uptime, baterie, coordonate GPS, ruta TRACE completă
- **Hartă Leaflet** cu markeri pentru nodurile cu GPS, curățare automată a markerilor orfani
- **Export TXT** complet cu toate nodurile, rute TRACE, statistici semnal, link Google Maps per nod
- **Export/Import JSON** pentru backup și restaurare listă noduri

###  Mesagerie cu tabs per canal
- **Tabs dinamice** deasupra zonei de mesaje: ALL · SYS · DM · CH0–CH5 · canale private
- **Sincronizare bidirecțională** tab ↔ selector TX — schimbarea tabului schimbă automat canalul de emisie și invers
- **Badge mesaje necitite** (roșu) per tab
- **6 canale publice** (CH0–CH5) + **6 sloturi canale private** cu cheie AES-128
- **Direct Messages** (DM) cu selector nod, confirmare livrare ACK
- **Istoric mesaje** cu export JSON/CSV, restaurare sesiune anterioară

###  Bot automat pe canal privat
- Bot configurat pe orice canal privat cu cheie AES-128
- **Keyword configurabil** din UI (default: `cq`) — răspunde automat la cuvântul cheie
- Răspuns automat cu: RSSI, SNR, Noise floor, hop count, ruta, uptime, baterie, timp UTC
- **Cooldown anti-flood** (8 secunde între răspunsuri)
- Ignoră propriile mesaje (anti-echo TX)

###  Hartă și waterfall SDR like
- **Hartă Leaflet** interactivă cu nodurile GPS
- **Waterfall spectrum** în timp real la 869.618 MHz (EU_868)
- **Ruta TRACE** vizualizată grafic pe hartă

###  Configurare
- **3 teme**: Dark · Slate · Light
- **Canale private**: 6 sloturi cu nume, index și cheie AES-128 (32 hex chars)
- **Panoul BOT**: canal, nume, keyword, cheie AES, buton generare cheie aleatorie
- **WX meteo**: stație meteo configurabilă cu afișare date

###  Monitorizare
- **SERIAL RAW** cu filtrare și căutare
- **SNR/RSSI/Noise** în timp real în bara de jos
- **Uptime, baterie, erori** firmware afișate în topbar
- **Ping/Trace** cu măsurare timp și afișare rută completă

---

## Avantaje față de app-ul oficial MeshCore (Android/iOS)

| Caracteristică     | WebUI  | App oficial  |
|---|---|---|
| Tabs per canal     |  ✅     |    ❌      |
| Bot automat        |  ✅     |    ❌      |
| Export fisiere     |  ✅     |    ❌      |
| Waterfall spectrum |  ✅     |    ❌      |
| Badge hop count    |  ✅     |   partial   |
| Badge nod (RPT)    |  ✅     |    ❌      |
| Statistici semnal  |  ✅     |    ❌      |
| Hartă  TRACE       |  ✅     |   partial   |
| e ok si offline    |  ✅     |    ✅      |
| Conectare USB      |  ✅     |    ❌      |

---

## Cerințe tehnice

- **Browser**: Chrome sau Edge (Web Serial API — nu funcționează în Firefox)
- **Conexiune**: USB la nodul MeshCore local (Heltec V3, TTGO LoRa32 etc.)
- **Firmware**: MeshCore v11+ (v1.15.0+)
- **Bandă**: EU_868 (869.618 MHz, SF8, BW62.5, CR8)
- **Fișier**: un singur `.html` — fără instalare, fără server, fără dependențe externe

---

## Rețeaua YO/YU CS (Caraș-Severin)

Interfața a fost dezvoltată și testată în cadrul rețelei MeshCore active din județul Caraș-Severin, România, cu noduri active la:
- **ROU-CS-SemenicMt-N / SE** — repetor pe vârful Semenic   * TNX YO2LYN - STEFAN ! *
- **SRB-VOJ-YO2LDK RPT** — repetor cross-border Serbia
- **ROU-CS-Resita-Bot** — nod cu bot activ
- **YU\YO2LDK BaseStation KN05HQ** — stația de bază locală

Rețeaua numără deocamdata  **243+ noduri** active în zona Balcanilor de Vest, mereu in crestere..

---

*  Dezvoltat  de YO2LDK · MeshCore EU_868 · Mai 2026*  SDR like, waterfall interface, animated background Mesh network and many bug's removed, not was possible without AI help..  *


