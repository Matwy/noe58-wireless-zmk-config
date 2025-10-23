# noe58 Wireless ZMK Config

Configurazione ZMK personalizzata per tastiera Lily58 wireless.

## Nome Bluetooth
Il dispositivo apparirà come: **noe58-Togna**

## Setup Tastiera Italiana

Questa configurazione è ottimizzata per l'uso con il **layout tastiera italiano** del sistema operativo.

### Configurare Windows per layout italiano

1. **Aggiungi layout italiano**:
   - Impostazioni → Ora e lingua → Lingua e area
   - Lingua preferita → Italiano → Opzioni
   - Aggiungi tastiera → Italiano

2. **Imposta come predefinito**:
   - Rimuovi o disabilita altre tastiere (es. US)
   - Lascia solo "Italiano"

3. **Verifica**:
   - L'icona della tastiera nella barra delle applicazioni dovrebbe mostrare "ITA"
   - Le lettere accentate (à, è, é, ì, ò, ù) saranno disponibili normalmente

### Come digitare lettere accentate

Con il layout italiano, le lettere accentate sono disponibili nativamente:
- **à, è, ì, ò, ù**: Tasti diretti (vicino al tasto Invio o con combinazioni standard del layout IT)
- **é**: Solitamente con Shift + è
- **Altri accenti**: Usa i dead keys del layout italiano standard

## Caratteristiche

### Layout Lower Layer
- **Tasti funzione F11-F12**:
  - F11 sopra ESC
  - F1-F10 sopra i numeri 1-0
  - F12 sopra backtick
- **Simboli**: !, @, #, $, %, ^, &, *, (, ), ~, _, +, {, }, |
- **Controlli Bluetooth**: Sulla quarta riga (clear, BT1-5)

### Combo shortcuts Windows
- **A+S insieme** = Desktop virtuale sinistro (Ctrl+Win+Left)
- **K+L insieme** = Desktop virtuale destro (Ctrl+Win+Right)
- **X+C insieme** = Delete

## Build Firmware

Il firmware viene compilato automaticamente tramite GitHub Actions quando fai push su GitHub.

Dopo la build, scarica i file `.uf2` dagli **Artifacts** e caricali sulla tastiera:
1. File per lato sinistro: `lily58_left-nice_nano_v2-zmk.uf2`
2. File per lato destro: `lily58_right-nice_nano_v2-zmk.uf2`

### Caricare il firmware

1. Collega il lato della tastiera via USB
2. Premi due volte velocemente il pulsante RESET sul Nice Nano
3. Apparirà un drive USB chiamato "NICENANO"
4. Copia il file `.uf2` corrispondente nel drive
5. Il drive si disconnetterà automaticamente
6. Ripeti per l'altro lato

## File di configurazione

- `config/lily58.keymap`: Layout tastiera e comportamenti
- `config/lily58.conf`: Configurazioni sistema (nome Bluetooth, potenza TX, etc.)
- `config/west.yml`: Dipendenze ZMK

## Link Utili

- [ZMK Firmware](https://zmk.dev/)
- [ZMK Keycodes](https://zmk.dev/docs/codes)
- [Lily58 Info](https://github.com/kata0510/Lily58)
- [Nice Nano](https://nicekeyboards.com/nice-nano/)
