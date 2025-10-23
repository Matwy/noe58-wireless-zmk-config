# noe58 Wireless ZMK Config

Configurazione ZMK personalizzata per tastiera Lily58 wireless.

## Nome Bluetooth
Il dispositivo apparirà come: **noe58-Togna**

## Caratteristiche

### Layout Lower Layer
- **F11-F12**: F11 sopra ESC, F1-F10 sopra i numeri, F12 sopra backtick
- **Lettere accentate italiane**: à, è, é, ì, ò, ù nelle posizioni corrispondenti alle lettere base
- **Combo shortcuts Windows**:
  - A+S insieme = Desktop virtuale sinistro (Ctrl+Win+Left)
  - K+L insieme = Desktop virtuale destro (Ctrl+Win+Right)

### Posizionamento lettere accentate (Lower Layer)
- **è** sopra E
- **ù** sopra U
- **ì** sopra I
- **ò** sopra O
- **à** sopra A
- **é** sul tasto encoder sinistro

## Setup Unicode (OBBLIGATORIO per lettere accentate)

Le lettere accentate usano il modulo **zmk-unicode** che richiede l'installazione di **WinCompose** su Windows.

### Installazione WinCompose

1. **Download WinCompose**:
   - Vai su: https://github.com/samhocevar/wincompose/releases
   - Scarica l'ultima versione (es. `WinCompose-Setup-0.9.11.exe`)

2. **Installa WinCompose**:
   - Esegui il file .exe scaricato
   - Segui la procedura di installazione guidata
   - Configura per avviarsi automaticamente all'avvio di Windows

3. **Verifica installazione**:
   - Dopo l'installazione, WinCompose apparirà nella system tray (icona a forma di tasto)
   - L'icona diventa colorata quando è attivo

4. **Test funzionamento**:
   - Premi il tasto Lower sulla Lily58
   - Premi il tasto sopra la A (dovrebbe apparire **à**)
   - Se funziona, l'installazione è corretta!

### Risoluzione problemi

**Le lettere accentate non funzionano**:
- Verifica che WinCompose sia in esecuzione (icona nella system tray)
- Riavvia WinCompose
- Assicurati di aver compilato il firmware dopo aver aggiunto il modulo zmk-unicode

**WinCompose non si avvia**:
- Verifica compatibilità con la tua versione di Windows
- Esegui come amministratore
- Controlla i log di WinCompose per errori

## Build Firmware

Il firmware viene compilato automaticamente tramite GitHub Actions quando fai push su GitHub.

### File modificati
- `config/west.yml`: Aggiunto modulo zmk-unicode
- `config/lily58.keymap`: Layout personalizzato con Unicode e combo
- `config/lily58.conf`: Nome Bluetooth personalizzato

## Struttura Codici Unicode

Lettere accentate italiane mappate:
- à = U+00E0
- è = U+00E8
- é = U+00E9
- ì = U+00EC
- ò = U+00F2
- ù = U+00F9

## Link Utili

- [ZMK Firmware](https://zmk.dev/)
- [ZMK Unicode Module](https://github.com/urob/zmk-unicode)
- [WinCompose](https://github.com/samhocevar/wincompose)
- [Lily58 Info](https://github.com/kata0510/Lily58)

## Note

- Il layout è ottimizzato per uso su Windows con WinCompose
- Per altri sistemi operativi, modificare `input-mode` in `lily58.keymap`:
  - Linux (IBus): `UC_LNX`
  - macOS: `UC_MAC`
  - Windows (WinCompose): `UC_WINC` (già configurato)
