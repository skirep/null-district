# NULL DISTRICT

**La ciutat oblida. Tu, no.**

Una experiència hacker cyberpunk de **Dejoco Arts**: un cyberdeck amb tres terminals escrivibles, un sistema de fitxers persistent i una campanya narrativa sobre una ciutat que comercia amb els records dels seus habitants.

## Començar

Escriu aquestes comandes al terminal:

```text
mail 1
scan
submit handshake
```

NYX envia els contractes següents per correu. `contracts` mostra el progrés, `hint` dona una pista concreta i `help` explica totes les comandes.

## Què hi pots fer

- Escriure comandes amb historial ↑/↓ i autocompleció amb Tab.
- Obrir tres shells independents amb fitxers i progressió compartits.
- Navegar amb `ls`, `cd`, `pwd`, `tree` i llegir amb `cat` o `grep`.
- Crear i modificar fitxers amb `edit`, `write`, `append`, `echo`, `touch`, `mkdir`, `cp`, `mv` i `rm`.
- Connectar-te als nodes ficticis amb `scan` i `connect`.
- Desxifrar pistes narratives, recuperar documents i editar la configuració del districte.
- Completar cinc contractes amb dues decisions finals, guanyar crèdits, comprar mòduls i fer tres encàrrecs lliures.
- Conservar les notes, els fitxers remots modificats, els historials, els mòduls, la reputació i la decisió final.
- Ampliar el terminal, canviar entre tres temes i activar sons discrets d’interfície.

## Persistència

El desament és **local al navegador**, amb `localStorage`, una clau exclusiva `null-district.save.v1` i format versionat. No hi ha sincronització al núvol, comptes ni multijugador.

Cada comanda, edició o canvi de shell desa l’estat. Un error de desament s’avisa a la interfície i no s’anuncia com a èxit. Els canvis d’una altra pestanya bloquegen noves escriptures fins que es recarregui, per evitar sobreescriure una partida més recent. Les dades corruptes es conserven i es poden exportar des de SISTEMA.

**BACKUP** exporta un JSON complet. **RESTAURA** valida el JSON abans de demanar confirmació per substituir la partida actual. Pots utilitzar-lo per continuar en un altre dispositiu. Esborrar les dades del navegador, fer servir mode privat o canviar d’origen web pot fer que la partida local deixi d’estar disponible; conserva backups si la vols mantenir.

Límits: 32.768 caràcters per fitxer, 524.288 caràcters de contingut total, 1.000 entrades al sistema de fitxers, 150 comandes d’historial i aproximadament 55.000 caràcters de transcripció per terminal. Els imports estan limitats a 2 MB.

## Execució i publicació

Sense dependències, compilació, secrets ni serveis de pagament. Serveix la carpeta amb un servidor estàtic:

```sh
python3 -m http.server 8080
```

GitHub Pages: branca `main`, carpeta `/ (root)`. Tots els recursos són locals i relatius. `.nojekyll` desactiva el processament de Jekyll. La ciutat és un dibuix procedural en Canvas; els efectes de pluja respecten la preferència de moviment reduït.

## Verificació

```sh
node --check engine.js
node --check app.js
node --test tests/engine.test.cjs
```

Les proves cobreixen els dos recorreguts finals, recompenses úniques, claus i accessos, notes i operacions de fitxers, shells independents, quotes, col·lisions de rutes, recuperació de la partida serialitzada, imports no vàlids, rastre i encàrrecs lliures.

Al navegador s’ha completat una campanya mitjançant comandes, s’ha utilitzat l’editor i s’ha verificat que recarregar conserva la nota, el node connectat, els crèdits i la configuració elèctrica. El disseny inclou adaptacions per a pantalles estretes; falta una prova amb un mòbil físic.

## Món fictici

Tota l’activitat de xarxa és simulada i passa en memòria local. No s’executen comandes del sistema operatiu, no es fa servir `eval`, no es contacten servidors externs i els noms dels nodes no són destinacions de xarxa. `decrypt` és un enigma narratiu amb transformació ROT13; no és criptografia de seguretat.

No hi ha analítica, cookies de seguiment ni connexions a tercers. El contingut dels fitxers es mostra com a text, també quan conté HTML.
