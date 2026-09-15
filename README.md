[README.md](https://github.com/user-attachments/files/32255438/README.md)
# Administrația Publică Locală — ghid interactiv

Aplicație web **într-un singur fișier** (`index.html`) despre administrația publică locală din România: organizare, autorități, acte administrative, finanțe publice locale, achiziții publice, patrimoniu, servicii publice, urbanism, control și transparență.

Fără dependențe externe, fără framework, fără cont, fără colectare de date. Funcționează și offline, prin dublu clic pe fișier.

---

## Cuprins (21 de capitole)

| Secțiune | Capitole |
|---|---|
| Cadrul general | Despre APL · Principii și cadru constituțional · Unitățile administrativ-teritoriale |
| Autorități și personal | Consiliul local · Primarul și viceprimarul · Consiliul județean și prefectul · Secretarul general, aparatul de specialitate și funcția publică |
| Acte și transparență | Actele administrative și controlul de legalitate · Transparență, acces la informații și participare |
| Bani publici | Finanțele publice locale și bugetul · Execuția bugetară, ALOP și contabilitatea publică · Impozite și taxe locale · Achizițiile publice |
| Patrimoniu și servicii | Patrimoniul UAT · Serviciile publice de utilități · Urbanism și autorizarea construcțiilor |
| Control și integritate | Control, audit și integritate |
| Instrumente | Calendar și termene-cheie · Noutăți legislative · Glosar și abrevieri · Resurse și legislație |

## Funcționalități

- **Căutare instantanee** în tot conținutul, cu evidențierea termenului și salt direct la paragraful găsit (tastați `/` pentru a activa caseta de căutare).
- **Două instrumente de calcul:**
  - *componența consiliului local* — din numărul de locuitori rezultă numărul de consilieri, cvorumul de ședință și majoritățile simplă, absolută și calificată;
  - *pragurile de achiziție* — din valoarea estimată și obiectul contractului rezultă procedura aplicabilă (praguri valabile din 1 ianuarie 2026).
- **Temă deschisă / întunecată**, memorată în browser.
- **Navigare pe capitole**, cuprins automat în fiecare capitol, butoane „anterior / următor”.
- **Adaptare la telefon și tabletă**; tabelele lungi se derulează orizontal.
- **Tipărire / export PDF** din butonul ⎙ (tipărește tot capitolul curent).

## Publicare pe GitHub Pages

1. Creați un repository nou (de exemplu `ghid-apl`) și încărcați fișierul `index.html` în rădăcina acestuia.
2. În repository: **Settings → Pages**.
3. La *Source* alegeți **Deploy from a branch**, branch-ul `main`, folderul `/ (root)`, apoi **Save**.
4. După 1–2 minute, site-ul este disponibil la adresa `https://<utilizator>.github.io/<repository>/`.

Nu este nevoie de niciun pas de build, de `package.json` sau de fișier de configurare.

## Cum se modifică conținutul

Tot textul se află în structura `DATA` din interiorul fișierului `index.html`, sub forma unei liste de capitole. Fiecare capitol are un identificator, un titlu și o listă de blocuri:

```js
{
  id:"consiliul-local", group:"Autorități și personal", ico:"👥",
  title:"Consiliul local",
  eyebrow:"Autoritate deliberativă",
  lede:"Descriere scurtă, afișată sub titlu.",
  blocks:[
    {t:"h",  x:"Titlu de subcapitol"},
    {t:"p",  x:"Paragraf, care acceptă <b>marcaje HTML</b>."},
    {t:"ul", x:["primul punct","al doilea punct"]},
    {t:"table", head:["Coloana 1","Coloana 2"], rows:[["a","b"]], cap:"Notă sub tabel."},
    {t:"note", k:"info", b:"Titlul casetei", x:"Text evidențiat. k poate fi: info, law, warn, ok."},
    {t:"steps", x:[{t:"Pasul 1", x:"explicație"}]},
    {t:"cards", x:[{i:"📌", t:"Titlu", x:"descriere"}]},
    {t:"defs",  x:[{t:"Termen", x:"definiție"}]},
    {t:"links", x:[{t:"Titlu", u:"https://…", x:"descriere"}]},
    {t:"chips", x:["etichetă 1","etichetă 2"]}
  ]
}
```

Un capitol nou se adaugă introducând un obiect similar în lista `DATA`; meniul lateral, cuprinsul și indexul de căutare se actualizează automat.

Pragurile de achiziții se actualizează într-un singur loc, în obiectul `PRAG`:

```js
var PRAG = { ad_ps:270120, ad_l:900400, eu_ps_sub:1077624, eu_l:26960556, eu_soc:3741750 };
```

## Surse

Codul administrativ (OUG nr. 57/2019), Legea nr. 273/2006 privind finanțele publice locale, Legea nr. 227/2015 (Codul fiscal, Titlul IX), Legea nr. 98/2016 și HG nr. 395/2016, Legea nr. 52/2003, Legea nr. 544/2001, Legea nr. 554/2004, Legea nr. 51/2006, Legea nr. 350/2001 și Legea nr. 50/1991, Legea nr. 94/1992, Legea nr. 176/2010. Pragurile de achiziție pentru 2026–2027 rezultă din Regulamentele delegate (UE) 2025/2150, 2025/2151 și 2025/2152 și din notificarea ANAP.

## Limitări

Material informativ și educativ. Nu constituie consultanță juridică sau financiară și nu înlocuiește textul actelor normative în vigoare. Verificați forma consolidată pe [legislatie.just.ro](https://legislatie.just.ro) înainte de a folosi informația într-un act administrativ.
