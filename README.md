# PPC Generátor inzerátů

Nástroj pro PPC specialisty — generuje texty pro RSA, Performance Max, Demand Gen, DSA, Display, YouTube a Shopping kampaně.

---

## Jak nasadit (krok za krokem)

### Co budeš potřebovat
- Účet na [GitHub](https://github.com) (zdarma)
- Účet na [Vercel](https://vercel.com) (zdarma)
- API klíč od Anthropic

### Krok 1 — Získej Anthropic API klíč

1. Jdi na [console.anthropic.com](https://console.anthropic.com)
2. Zaregistruj se nebo přihlas
3. V levém menu klikni na **API Keys**
4. Klikni na **Create Key**, pojmenuj ji (např. "PPC Generátor") a zkopíruj klíč
5. Klíč začíná na `sk-ant-...` — ulož ho někam bezpečně, uvidíš ho jen jednou

### Krok 2 — Nahraj projekt na GitHub

1. Jdi na [github.com](https://github.com) a přihlas se
2. Klikni na zelené tlačítko **New** (vlevo nahoře)
3. Pojmenuj repozitář např. `ppc-generator`
4. Klikni na **Create repository**
5. Na stránce repozitáře klikni na **uploading an existing file**
6. Přetáhni do okna tyto soubory (zachovej strukturu složek):
   - `index.html`
   - `api/generate.js`
   - `vercel.json`
7. Klikni na **Commit changes**

### Krok 3 — Nasaď na Vercel

1. Jdi na [vercel.com](https://vercel.com) a klikni na **Sign Up**
2. Zvol **Continue with GitHub** — propojí se automaticky
3. Klikni na **Add New → Project**
4. Najdi svůj repozitář `ppc-generator` a klikni na **Import**
5. Nic nenastavuj, klikni rovnou na **Deploy**
6. Vercel za ~30 sekund nasadí aplikaci a dá ti URL (např. `ppc-generator-abc.vercel.app`)

### Krok 4 — Přidej API klíč (nejdůležitější krok!)

Bez tohoto kroku aplikace nebude fungovat.

1. Na stránce projektu ve Vercelu klikni na **Settings**
2. V levém menu klikni na **Environment Variables**
3. Do pole **Key** napiš přesně: `ANTHROPIC_API_KEY`
4. Do pole **Value** vlož svůj API klíč (`sk-ant-...`)
5. Klikni na **Save**
6. Jdi zpět na **Deployments** a klikni na **Redeploy** (klíč se načte až po novém nasazení)

### Krok 5 — Sdílej s kolegy

Po nasazení dostaneš URL jako `ppc-generator-abc.vercel.app`.
Tuto URL pošli kolegům — mohou nástroj ihned používat v prohlížeči, bez instalace.

---

## Vlastní doména (volitelné)

Pokud chceš mít URL jako `nastroje.vase-agentura.cz`:
1. Ve Vercelu jdi na **Settings → Domains**
2. Přidej svou doménu a Vercel ti poradí jak nastavit DNS

---

## Náklady

- **Vercel hosting**: zdarma (free tier stačí pro desítky uživatelů)
- **Anthropic API**: platíš za každý vygenerovaný výstup
  - Jedno generování = cca 0,01–0,03 USD (podle délky)
  - 100 generování denně ≈ 1–3 USD/den

## Struktura projektu

```
ppc-generator/
├── index.html        ← celý frontend (UI)
├── api/
│   └── generate.js   ← backend proxy (drží API klíč bezpečně)
├── vercel.json       ← konfigurace nasazení
└── README.md         ← tento soubor
```

---

## Podpora

Pokud něco nefunguje, zkontroluj:
- Je API klíč správně zadaný v Environment Variables?
- Udělal jsi Redeploy po přidání klíče?
- Má API klíč dostatečný kredit na [console.anthropic.com](https://console.anthropic.com)?
