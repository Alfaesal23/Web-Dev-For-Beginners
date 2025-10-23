<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "90b19cde5b79b29e91babd3138cd8035",
  "translation_date": "2025-10-23T00:19:44+00:00",
  "source_file": "1-getting-started-lessons/3-accessibility/README.md",
  "language_code": "fi"
}
-->
# Luodaan saavutettavia verkkosivuja

![Kaikki saavutettavuudesta](../../../../translated_images/webdev101-a11y.8ef3025c858d897a403a1a42c0897c76e11b724d9a8a0c0578dd4316f7507622.fi.png)
> Sketchnote: [Tomomi Imura](https://twitter.com/girlie_mac)

## Ennakkokysely
[Ennakkokysely](https://ff-quizzes.netlify.app/web/)

> Verkon voima on sen universaalisuudessa. Pääsy kaikille, riippumatta vammaisuudesta, on olennainen osa.
>
> \- Sir Timothy Berners-Lee, W3C:n johtaja ja World Wide Webin keksijä

Tässä on jotain, mikä saattaa yllättää sinut: kun rakennat saavutettavia verkkosivustoja, et ainoastaan auta vammaisia ihmisiä—olet itse asiassa tekemässä verkosta paremman kaikille!

Oletko koskaan huomannut jalkakäytävien kulmissa olevia ramppeja? Ne suunniteltiin alun perin pyörätuoleille, mutta nyt ne auttavat myös lastenvaunujen kanssa liikkuvia, tavarantoimittajia, matkustajia matkalaukkujen kanssa ja pyöräilijöitä. Juuri näin saavutettava verkkosuunnittelu toimii—ratkaisut, jotka auttavat yhtä ryhmää, hyödyttävät usein kaikkia. Aika siistiä, eikö?

Tässä oppitunnissa tutkimme, kuinka luoda verkkosivustoja, jotka toimivat kaikille, riippumatta siitä, miten he selaavat verkkoa. Opit käytännön tekniikoita, jotka ovat jo sisäänrakennettu verkkostandardeihin, pääset kokeilemaan testityökaluja ja näet, kuinka saavutettavuus tekee sivustoistasi käyttäjäystävällisempiä kaikille.

Oppitunnin lopussa sinulla on varmuus tehdä saavutettavuudesta luonnollinen osa kehitysprosessiasi. Valmis tutkimaan, kuinka harkitut suunnitteluratkaisut voivat avata verkon miljardeille käyttäjille? Sukelletaanpa!

> Voit käydä tämän oppitunnin [Microsoft Learnissa](https://docs.microsoft.com/learn/modules/web-development-101/accessibility/?WT.mc_id=academic-77807-sagibbon)!

## Apuvälineiden ymmärtäminen

Ennen kuin siirrymme koodaukseen, otetaan hetki ymmärtääksemme, miten eri kykyiset ihmiset todella kokevat verkon. Tämä ei ole pelkkää teoriaa—näiden todellisten navigointitapojen ymmärtäminen tekee sinusta paljon paremman kehittäjän!

Apuvälineet ovat hämmästyttäviä työkaluja, jotka auttavat vammaisia ihmisiä vuorovaikuttamaan verkkosivustojen kanssa tavoilla, jotka saattavat yllättää sinut. Kun opit, miten nämä teknologiat toimivat, saavutettavien verkkokokemusten luominen muuttuu paljon intuitiivisemmaksi. Se on kuin oppisi näkemään koodisi jonkun toisen silmin.

### Ruudunlukijat

[Ruudunlukijat](https://en.wikipedia.org/wiki/Screen_reader) ovat melko kehittyneitä teknologioita, jotka muuntavat digitaalisen tekstin puheeksi tai pistekirjoitukseksi. Vaikka niitä käytetään pääasiassa näkövammaisten ihmisten toimesta, ne ovat myös erittäin hyödyllisiä oppimisvaikeuksista, kuten lukihäiriöstä, kärsiville käyttäjille.

Ajattelen ruudunlukijaa kuin todella älykästä kertojaa, joka lukee kirjaa sinulle. Se lukee sisällön ääneen loogisessa järjestyksessä, ilmoittaa interaktiiviset elementit kuten "painike" tai "linkki" ja tarjoaa pikanäppäimiä sivulla liikkumiseen. Mutta tässä on juttu—ruudunlukijat voivat tehdä taikojaan vain, jos rakennamme verkkosivustoja asianmukaisella rakenteella ja merkityksellisellä sisällöllä. Tässä sinä astut kuvaan kehittäjänä!

**Suosittuja ruudunlukijoita eri alustoilla:**
- **Windows**: [NVDA](https://www.nvaccess.org/about-nvda/) (ilmainen ja suosituin), [JAWS](https://webaim.org/articles/jaws/), [Narrator](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1/?WT.mc_id=academic-77807-sagibbon) (sisäänrakennettu)
- **macOS/iOS**: [VoiceOver](https://support.apple.com/guide/voiceover/welcome/10) (sisäänrakennettu ja erittäin kyvykäs)
- **Android**: [TalkBack](https://support.google.com/accessibility/android/answer/6283677) (sisäänrakennettu)
- **Linux**: [Orca](https://wiki.gnome.org/Projects/Orca) (ilmainen ja avoimen lähdekoodin)

**Kuinka ruudunlukijat navigoivat verkkosisältöä:**

Ruudunlukijat tarjoavat useita navigointimenetelmiä, jotka tekevät selaamisesta tehokasta kokeneille käyttäjille:
- **Järjestelmällinen lukeminen**: Lukee sisällön ylhäältä alas, kuten kirjaa seuraten
- **Maamerkkien navigointi**: Hyppää sivun osioiden välillä (otsikko, navigointi, pääsisältö, alatunniste)
- **Otsikon navigointi**: Siirtyy otsikoiden välillä ymmärtääkseen sivun rakenteen
- **Linkkilistat**: Luo lista kaikista linkeistä nopeaa pääsyä varten
- **Lomakekentät**: Navigoi suoraan syöttökenttien ja painikkeiden välillä

> 💡 **Tämä yllätti minut**: 68 % ruudunlukijoiden käyttäjistä navigoi ensisijaisesti otsikoiden avulla ([WebAIM-kysely](https://webaim.org/projects/screenreadersurvey9/#finding)). Tämä tarkoittaa, että otsikkorakenteesi on kuin kartta käyttäjille—kun teet sen oikein, autat ihmisiä löytämään sisältösi nopeammin!

### Testausprosessin rakentaminen

Hyviä uutisia—tehokas saavutettavuustestaus ei tarvitse olla ylivoimaista! Kannattaa yhdistää automaattiset työkalut (ne ovat loistavia ilmeisten ongelmien havaitsemisessa) ja käytännön testaus. Tässä on järjestelmällinen lähestymistapa, joka auttaa havaitsemaan suurimman osan ongelmista ilman, että koko päivä menee hukkaan:

**Välttämätön manuaalinen testausprosessi:**

```mermaid
graph TD
    A[Start Testing] --> B{Keyboard Navigation}
    B --> C[Tab through all interactive elements]
    C --> D{Screen Reader Testing}
    D --> E[Test with NVDA/VoiceOver]
    E --> F{Zoom Testing}
    F --> G[Zoom to 200% and test functionality]
    G --> H{Color/Contrast Check}
    H --> I[Verify all text meets contrast ratios]
    I --> J{Focus Management}
    J --> K[Ensure focus indicators are visible]
    K --> L[Testing Complete]
```

**Vaiheittainen testauslista:**
1. **Näppäimistön navigointi**: Käytä vain Tab, Shift+Tab, Enter, Space ja nuolinäppäimiä
2. **Ruudunlukijatestaus**: Ota NVDA, VoiceOver tai Narrator käyttöön ja navigoi silmät kiinni
3. **Zoomaustestaus**: Testaa 200 % ja 400 % zoomaustasoilla
4. **Värikontrastin tarkistus**: Tarkista kaikki tekstit ja käyttöliittymäkomponentit
5. **Fokusindikaattorin testaus**: Varmista, että kaikki interaktiiviset elementit ovat näkyvissä

✅ **Aloita Lighthousella**: Avaa selaimesi kehitystyökalut, suorita Lighthouse-saavutettavuusauditointi ja käytä tuloksia manuaalisen testauksen painopistealueiden ohjaamiseen.

### Zoomaus- ja suurennustyökalut

Tiedätkö, kuinka joskus zoomaat puhelimellasi, kun teksti on liian pientä, tai siristät silmiäsi kannettavan näytön edessä kirkkaassa auringonvalossa? Monet käyttäjät luottavat suurennustyökaluihin tehdäkseen sisällöstä luettavaa joka päivä. Tämä koskee heikkonäköisiä, vanhuksia ja kaikkia, jotka ovat joskus yrittäneet lukea verkkosivua ulkona.

Modernit zoomausteknologiat ovat kehittyneet pelkästä suurentamisesta. Ymmärtämällä, miten nämä työkalut toimivat, voit luoda responsiivisia suunnitelmia, jotka pysyvät toimivina ja houkuttelevina kaikilla suurennustasoilla.

**Modernit selainten zoomausominaisuudet:**
- **Sivun zoomaus**: Skaalaa kaikki sisältö suhteellisesti (teksti, kuvat, asettelu) - tämä on suositeltu menetelmä
- **Vain tekstin zoomaus**: Suurentaa fonttikokoa säilyttäen alkuperäisen asettelun
- **Pinch-to-zoom**: Mobiilieleiden tuki tilapäiseen suurennukseen
- **Selaintuki**: Kaikki modernit selaimet tukevat zoomausta jopa 500 % ilman toiminnallisuuden rikkoutumista

**Erikoistuneet suurennusohjelmistot:**
- **Windows**: [Magnifier](https://support.microsoft.com/windows/use-magnifier-to-make-things-on-the-screen-easier-to-see-414948ba-8b1c-d3bd-8615-0e5e32204198) (sisäänrakennettu), [ZoomText](https://www.freedomscientific.com/training/zoomtext/getting-started/)
- **macOS/iOS**: [Zoom](https://www.apple.com/accessibility/mac/vision/) (sisäänrakennettu edistyneillä ominaisuuksilla)

> ⚠️ **Suunnitteluharkinta**: WCAG vaatii, että sisältö pysyy toimivana, kun sitä zoomataan 200 %. Tällä tasolla vaakasuuntainen vieritys tulisi olla minimaalista, ja kaikki interaktiiviset elementit tulisi olla saavutettavissa.

✅ **Testaa responsiivinen suunnittelusi**: Zoomaa selaimesi 200 % ja 400 %. Mukautuuko asettelusi sulavasti? Voitko edelleen käyttää kaikkia toimintoja ilman liiallista vieritystä?

## Modernit saavutettavuustestityökalut

Nyt kun ymmärrät, miten ihmiset navigoivat verkossa apuvälineiden avulla, tutkitaan työkaluja, jotka auttavat sinua rakentamaan ja testaamaan saavutettavia verkkosivustoja.

Ajattele asiaa näin: automaattiset työkalut ovat loistavia ilmeisten ongelmien havaitsemisessa (kuten puuttuva alt-teksti), kun taas käytännön testaus auttaa varmistamaan, että sivustosi tuntuu hyvältä käyttää todellisessa maailmassa. Yhdessä ne antavat sinulle varmuuden siitä, että sivustosi toimivat kaikille.

### Värikontrastin testaus

Hyviä uutisia: värikontrasti on yksi yleisimmistä saavutettavuusongelmista, mutta se on myös yksi helpoimmista korjata. Hyvä kontrasti hyödyttää kaikkia—näkövammaisista käyttäjistä ihmisiin, jotka yrittävät lukea puhelimiaan rannalla.

**WCAG-kontrastivaatimukset:**

| Tekstityyppi | WCAG AA (Minimi) | WCAG AAA (Parannettu) |
|--------------|------------------|-----------------------|
| **Normaali teksti** (alle 18pt) | 4.5:1 kontrastisuhde | 7:1 kontrastisuhde |
| **Suuri teksti** (18pt+ tai 14pt+ lihavoitu) | 3:1 kontrastisuhde | 4.5:1 kontrastisuhde |
| **UI-komponentit** (painikkeet, lomakerajat) | 3:1 kontrastisuhde | 3:1 kontrastisuhde |

**Välttämättömät testityökalut:**
- [Colour Contrast Analyser](https://www.tpgi.com/color-contrast-checker/) - Työpöytäsovellus värinvalitsimella
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) - Verkkopohjainen välittömällä palautteella
- [Stark](https://www.getstark.co/) - Suunnittelutyökalun lisäosa Figmaan, Sketchiin, Adobe XD:hen
- [Accessible Colors](https://accessible-colors.com/) - Löydä saavutettavia väripaletteja

✅ **Luo parempia väripaletteja**: Aloita brändiväreistäsi ja käytä kontrastitarkistimia luodaksesi saavutettavia variaatioita. Dokumentoi nämä suunnittelujärjestelmäsi saavutettavina värikoodeina.

### Kattava saavutettavuusauditointi

Tehokkain saavutettavuustestaus yhdistää useita lähestymistapoja. Mikään yksittäinen työkalu ei havaitse kaikkea, joten testirutiinin rakentaminen eri menetelmillä varmistaa kattavan tarkastuksen.

**Selaimeen perustuva testaus (sisäänrakennettu kehitystyökaluihin):**
- **Chrome/Edge**: Lighthouse-saavutettavuusauditointi + Saavutettavuuspaneeli
- **Firefox**: Saavutettavuusinspektori yksityiskohtaisella puunäkymällä
- **Safari**: Auditointivälilehti Web Inspectorissa VoiceOver-simulaatiolla

**Ammattilaistason testauslaajennukset:**
- [axe DevTools](https://www.deque.com/axe/devtools/) - Teollisuusstandardin mukainen automaattinen testaus
- [WAVE](https://wave.webaim.org/extension/) - Visuaalinen palaute virheiden korostuksella
- [Accessibility Insights](https://accessibilityinsights.io/) - Microsoftin kattava testauspaketti

**Komentorivi ja CI/CD-integraatio:**
- [axe-core](https://github.com/dequelabs/axe-core) - JavaScript-kirjasto automaattiseen testaukseen
- [Pa11y](https://pa11y.org/) - Komentorivipohjainen saavutettavuustestityökalu
- [Lighthouse CI](https://github.com/GoogleChrome/lighthouse-ci) - Automatisoitu saavutettavuuspisteytys

> 🎯 **Testaustavoite**: Pyri Lighthouse-saavutettavuuspisteisiin 95+ lähtötasona. Muista, että automaattiset työkalut havaitsevat vain noin 30-40 % saavutettavuusongelmista—manuaalinen testaus on edelleen välttämätöntä!

## Saavutettavuuden rakentaminen alusta alkaen

Saavutettavuuden avain menestykseen on sen sisällyttäminen perustaan alusta alkaen. Tiedän, että voi olla houkuttelevaa ajatella "lisään saavutettavuuden myöhemmin", mutta se on kuin yrittäisi lisätä ramppia taloon sen rakentamisen jälkeen. Mahdollista? Kyllä. Helppoa? Ei todellakaan.

Ajattele saavutettavuutta kuin talon suunnittelua—on paljon helpompaa sisällyttää pyörätuolisaavutettavuus alkuperäisiin arkkitehtisuunnitelmiin kuin muokata kaikkea myöhemmin.

### POUR-periaatteet: Saavutettavuuden perusta

Web Content Accessibility Guidelines (WCAG) perustuvat neljään keskeiseen periaatteeseen, jotka muodostavat POUR. Älä huoli—nämä eivät ole kuivaa akateemista teoriaa! Ne ovat käytännöllisiä ohjeita sisällön luomiseen, joka toimii kaikille.

Kun opit POUR-periaatteet, saavutettavuuspäätösten tekeminen muuttuu paljon intuitiivisemmaksi. Se on kuin henkinen tarkistuslista, joka ohjaa suunnittelupäätöksiäsi. Puretaanpa ne:

**🔍 Havainnollinen**: Tiedon tulee olla esitettävissä tavoilla, jotka käyttäjät voivat havaita käytettävissä olevilla aisteillaan

- Tarjoa tekstivaihtoehtoja ei-tekstisisällölle (kuvat, videot, äänet)
- Varmista riittävä värikontrasti kaikelle tekstille ja käyttöliittymäkomponenteille
- Tarjoa tekstitykset ja transkriptiot multimedia-sisällölle
- Suunnittele sisältö, joka pysyy toimivana, kun sitä suurennetaan jopa 200 %
- Käytä useita aistillisia ominaisuuksia (ei vain väriä) tiedon välittämiseen

**🎮 Käytettävä**: Kaikkien käyttöliittymäkomponenttien tulee olla käytettävissä saatavilla olevilla syöttötavoilla

- Tee kaikki toiminnot saavutettaviksi näppäimistön navigoinnin avulla
- Anna käyttäjille riittävästi aikaa lukea ja olla vuorovaikutuksessa sisällön kanssa
- Vältä sisältöä, joka aiheuttaa kohtauksia tai tasapainohäiriöitä
- Auta käyttäjiä navigoimaan tehokkaasti selkeällä rakenteella ja maamerkeillä
- Varmista, että interaktiivisilla elementeillä on riittävät kohdekoot (vähintään 44px)

**📖 Ymmärrettävä**: Tiedon ja käyttöliittymän toiminnan tulee olla selkeää ja ymmärrettävää

- Käytä selkeää, yksinkertaista kieltä, joka sopii kohdeyleisöllesi
- Varmista, että sisältö näkyy ja toimii ennakoitavalla, johdonmukaisella tavalla
- Tarjoa selkeät ohjeet ja virheilmoitukset käyttäjän syötteille
- Auta käyttä
Väri on tehokas viestinnän väline, mutta sen ei koskaan pitäisi olla ainoa tapa välittää tärkeää tietoa. Suunnittelu, joka menee värin tuolle puolen, luo kestävämpiä ja inklusiivisempia kokemuksia, jotka toimivat monenlaisissa tilanteissa.

**Suunnittele värinäköeroja huomioiden:**

Noin 8 % miehistä ja 0,5 % naisista kärsii jonkinlaisesta värinäköerosta (usein kutsutaan värisokeudeksi). Yleisimmät tyypit ovat:
- **Deuteranopia**: Vaikeus erottaa punaista ja vihreää
- **Protanopia**: Punainen näyttää himmeämmältä
- **Tritanopia**: Vaikeus sinisen ja keltaisen erottamisessa (harvinainen)

**Inklusiiviset väristrategiat:**

```css
/* ❌ Bad: Using only color to indicate status */
.error { color: red; }
.success { color: green; }

/* ✅ Good: Color plus icons and context */
.error {
  color: #d32f2f;
  border-left: 4px solid #d32f2f;
}
.error::before {
  content: "⚠️";
  margin-right: 8px;
}

.success {
  color: #2e7d32;
  border-left: 4px solid #2e7d32;
}
.success::before {
  content: "✅";
  margin-right: 8px;
}
```

**Peruskontrastivaatimusten yli:**
- Testaa värivalintasi värisokeussimulaattoreilla
- Käytä kuvioita, tekstuureja tai muotoja värikoodauksen rinnalla
- Varmista, että interaktiiviset tilat ovat erottuvia ilman väriä
- Mieti, miltä suunnittelusi näyttää korkean kontrastin tilassa

✅ **Testaa värien saavutettavuus**: Käytä työkaluja, kuten [Coblis](https://www.color-blindness.com/coblis-color-blindness-simulator/), nähdäksesi, miltä sivustosi näyttää käyttäjille, joilla on erilaisia värinäköeroja.

### Kohdistusindikaattorit ja vuorovaikutussuunnittelu

Kohdistusindikaattorit ovat digitaalinen vastine kursorille—ne osoittavat näppäimistön käyttäjille, missä he ovat sivulla. Hyvin suunnitellut kohdistusindikaattorit parantavat kaikkien käyttäjien kokemusta tekemällä vuorovaikutuksesta selkeää ja ennakoitavaa.

**Modernit kohdistusindikaattorien parhaat käytännöt:**

```css
/* Enhanced focus styles that work across browsers */
button:focus-visible {
  outline: 2px solid #0066cc;
  outline-offset: 2px;
  box-shadow: 0 0 0 4px rgba(0, 102, 204, 0.25);
}

/* Remove focus outline for mouse users, preserve for keyboard users */
button:focus:not(:focus-visible) {
  outline: none;
}

/* Focus-within for complex components */
.card:focus-within {
  box-shadow: 0 0 0 3px rgba(74, 144, 164, 0.5);
  border-color: #4A90A4;
}

/* Ensure focus indicators meet contrast requirements */
.custom-focus:focus-visible {
  outline: 3px solid #ffffff;
  outline-offset: 2px;
  box-shadow: 0 0 0 6px #000000;
}
```

**Kohdistusindikaattorien vaatimukset:**
- **Näkyvyys**: Vähintään 3:1 kontrastisuhde ympäröiviin elementteihin
- **Leveys**: Vähintään 2px paksuus koko elementin ympärillä
- **Pysyvyys**: Pitäisi pysyä näkyvissä, kunnes kohdistus siirtyy muualle
- **Erottuvuus**: Pitäisi visuaalisesti erottua muista käyttöliittymän tiloista

> 💡 **Suunnitteluvinkki**: Hyvät kohdistusindikaattorit käyttävät usein yhdistelmää reunaviivaa, varjostusta ja värimuutoksia varmistaakseen näkyvyyden eri taustoilla ja konteksteissa.

✅ **Tarkista kohdistusindikaattorit**: Käy läpi verkkosivustosi välilehtien avulla ja tarkista, mitkä elementit sisältävät selkeät kohdistusindikaattorit. Ovatko jotkin vaikeasti havaittavissa tai puuttuvat kokonaan?

### Semanttinen HTML: Saavutettavuuden perusta

Semanttinen HTML on kuin avustavien teknologioiden GPS-järjestelmä verkkosivustollesi. Kun käytät oikeita HTML-elementtejä niiden tarkoituksenmukaisella tavalla, tarjoat näytönlukijoille, näppäimistöille ja muille työkaluille yksityiskohtaisen kartan, joka auttaa käyttäjiä navigoimaan tehokkaasti.

Tässä on vertaus, joka todella avasi silmäni: semanttinen HTML on kuin hyvin järjestetty kirjasto, jossa on selkeät kategoriat ja hyödylliset opasteet, verrattuna varastoon, jossa kirjat ovat satunnaisesti levällään. Molemmissa paikoissa on samat kirjat, mutta kummasta haluaisit etsiä jotain? Juuri niin!

**Saavutettavan sivurakenteen rakennuspalikat:**

```html
<!-- Landmark elements provide page navigation structure -->
<header>
  <h1>Your Site Name</h1>
  <nav aria-label="Main navigation">
    <ul>
      <li><a href="/home">Home</a></li>
      <li><a href="/about">About</a></li>
      <li><a href="/services">Services</a></li>
    </ul>
  </nav>
</header>

<main>
  <article>
    <header>
      <h1>Article Title</h1>
      <p>Published on <time datetime="2024-10-14">October 14, 2024</time></p>
    </header>
    
    <section>
      <h2>First Section</h2>
      <p>Content that relates to this section...</p>
    </section>
    
    <section>
      <h2>Second Section</h2>
      <p>More related content...</p>
    </section>
  </article>
  
  <aside>
    <h2>Related Links</h2>
    <nav aria-label="Related articles">
      <ul>
        <li><a href="/related-1">First related article</a></li>
        <li><a href="/related-2">Second related article</a></li>
      </ul>
    </nav>
  </aside>
</main>

<footer>
  <p>&copy; 2024 Your Site Name. All rights reserved.</p>
  <nav aria-label="Footer links">
    <ul>
      <li><a href="/privacy">Privacy Policy</a></li>
      <li><a href="/contact">Contact Us</a></li>
    </ul>
  </nav>
</footer>
```

**Miksi semanttinen HTML muuttaa saavutettavuutta:**

| Semanttinen elementti | Tarkoitus | Näytönlukijan hyöty |
|-----------------------|-----------|---------------------|
| `<header>` | Sivun tai osion otsikko | "Banneri-maamerkki" - nopea navigointi yläosaan |
| `<nav>` | Navigointilinkit | "Navigointimaamerkki" - navigointiosioiden lista |
| `<main>` | Sivun pääsisältö | "Päämaamerkki" - siirtyminen suoraan sisältöön |
| `<article>` | Itsenäinen sisältö | Ilmoittaa artikkelin rajat |
| `<section>` | Teemalliset sisältöryhmät | Tarjoaa sisällön rakenteen |
| `<aside>` | Liittyvä sivupalkin sisältö | "Täydentävä maamerkki" |
| `<footer>` | Sivun tai osion alatunniste | "Sisältötieto-maamerkki" |

**Näytönlukijan supervoimat semanttisen HTML:n avulla:**
- **Maamerkkien navigointi**: Siirtyminen nopeasti sivun pääosioiden välillä
- **Otsikkoluettelot**: Sisällysluettelon luominen otsikkorakenteesta
- **Elementtilistat**: Kaikkien linkkien, painikkeiden tai lomakekontrollien listaaminen
- **Kontekstin ymmärtäminen**: Sisältöosioiden välisten suhteiden hahmottaminen

> 🎯 **Nopea testi**: Kokeile navigoida sivustollasi näytönlukijalla käyttämällä maamerkkien pikavalintoja (D maamerkille, H otsikolle, K linkille NVDA:ssa/JAWS:ssa). Onko navigointi loogista?

✅ **Tarkista semanttinen rakenne**: Käytä selaimesi DevToolsin saavutettavuuspaneelia nähdäksesi saavutettavuuspuun ja varmistaaksesi, että merkintäsi luo loogisen rakenteen.

### Otsikkohierarkia: Loogisen sisällysluettelon luominen

Otsikot ovat ehdottoman tärkeitä saavutettavan sisällön kannalta—ne ovat kuin selkäranka, joka pitää kaiken koossa. Näytönlukijoiden käyttäjät tukeutuvat vahvasti otsikoihin ymmärtääkseen ja navigoidakseen sisällössäsi. Ajattele sitä kuin tarjoaisit sisällysluettelon sivullesi.

**Tässä on otsikoiden kultainen sääntö:**
Älä koskaan ohita tasoja. Etene aina loogisesti `<h1>`:stä `<h2>`:een, sitten `<h3>`:een ja niin edelleen. Muistatko, kun teit sisällysluetteloita koulussa? Se on täsmälleen sama periaate—et hyppäisi "I. Pääkohta" suoraan "C. Alakohta" ilman "A. Alakohtaa" välissä, eikö?

**Täydellinen otsikkorakenne-esimerkki:**

```html
<!-- ✅ Excellent: Logical, hierarchical progression -->
<main>
  <h1>Complete Guide to Web Accessibility</h1>
  
  <section>
    <h2>Understanding Screen Readers</h2>
    <p>Introduction to screen reader technology...</p>
    
    <h3>Popular Screen Reader Software</h3>
    <p>NVDA, JAWS, and VoiceOver comparison...</p>
    
    <h3>Testing with Screen Readers</h3>
    <p>Step-by-step testing instructions...</p>
  </section>
  
  <section>
    <h2>Color and Contrast Guidelines</h2>
    <p>Designing with sufficient contrast...</p>
    
    <h3>WCAG Contrast Requirements</h3>
    <p>Understanding the different contrast levels...</p>
    
    <h3>Testing Tools and Techniques</h3>
    <p>Tools for verifying contrast ratios...</p>
  </section>
</main>
```

```html
<!-- ❌ Problematic: Skipping levels, inconsistent structure -->
<h1>Page Title</h1>
<h3>Subsection</h3> <!-- Skipped h2 -->
<h2>This should come before h3</h2>
<h1>Another main heading?</h1> <!-- Multiple h1s -->
```

**Otsikoiden parhaat käytännöt:**
- **Yksi `<h1>` per sivu**: Yleensä pääsivun otsikko tai ensisijainen sisältöotsikko
- **Looginen eteneminen**: Älä koskaan ohita tasoja (h1 → h2 → h3, ei h1 → h3)
- **Kuvaileva sisältö**: Tee otsikoista merkityksellisiä, vaikka ne luettaisiin kontekstista irrallaan
- **Visuaalinen muotoilu CSS:llä**: Käytä CSS:ää ulkoasuun, HTML-tasoja rakenteeseen

**Näytönlukijan navigointitilastot:**
- 68 % näytönlukijoiden käyttäjistä navigoi otsikoiden avulla ([WebAIM-kysely](https://webaim.org/projects/screenreadersurvey9/#finding))
- Käyttäjät odottavat loogista otsikkorakennetta
- Otsikot tarjoavat nopeimman tavan ymmärtää sivun rakennetta

> 💡 **Pro-vinkki**: Käytä selaimen laajennuksia, kuten "HeadingsMap", visualisoidaksesi otsikkorakenteesi. Sen pitäisi näyttää hyvin järjestetyltä sisällysluettelolta.

✅ **Testaa otsikkorakenteesi**: Käytä näytönlukijan otsikkonavigointia (H-näppäin NVDA:ssa) hypätäksesi otsikoiden välillä. Kertooko eteneminen loogisesti sisällön tarinan?

### Kehittyneet visuaalisen saavutettavuuden tekniikat

Peruskontrastin ja värin lisäksi on olemassa kehittyneitä tekniikoita, jotka auttavat luomaan todella inklusiivisia visuaalisia kokemuksia. Nämä menetelmät varmistavat, että sisältösi toimii eri katseluolosuhteissa ja avustavien teknologioiden kanssa.

**Keskeiset visuaalisen viestinnän strategiat:**

- **Monimuotoinen palaute**: Yhdistä visuaaliset, tekstuaaliset ja joskus äänivihjeet
- **Progressiivinen paljastaminen**: Esitä tietoa helposti sulavina osina
- **Johdonmukaiset vuorovaikutusmallit**: Käytä tuttuja käyttöliittymäkonventioita
- **Responsiivinen typografia**: Skaalaa teksti sopivasti eri laitteilla
- **Lataus- ja virhetilat**: Tarjoa selkeää palautetta kaikista käyttäjän toimista

**CSS-apuvälineet saavutettavuuden parantamiseksi:**

```css
/* Screen reader only text - visually hidden but accessible */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

/* Skip link for keyboard navigation */
.skip-link {
  position: absolute;
  top: -40px;
  left: 6px;
  background: #000000;
  color: #ffffff;
  padding: 8px 16px;
  text-decoration: none;
  border-radius: 4px;
  font-weight: bold;
  transition: top 0.3s ease;
  z-index: 1000;
}

.skip-link:focus {
  top: 6px;
}

/* Reduced motion respect */
@media (prefers-reduced-motion: reduce) {
  .skip-link {
    transition: none;
  }
  
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}

/* High contrast mode support */
@media (prefers-contrast: high) {
  .button {
    border: 2px solid;
  }
}
```

> 🎯 **Saavutettavuuskuvio**: "Ohita linkki" on välttämätön näppäimistön käyttäjille. Sen pitäisi olla sivun ensimmäinen kohdistettava elementti ja hypätä suoraan pääsisältöön.

✅ **Toteuta ohitusnavigointi**: Lisää ohituslinkit sivuillesi ja testaa niitä painamalla Tab heti sivun latauduttua. Niiden pitäisi näkyä ja antaa sinun siirtyä pääsisältöön.

## Merkityksellisen linkkitekstin luominen

Linkit ovat käytännössä verkkosivujen moottoriteitä, mutta huonosti kirjoitettu linkkiteksti on kuin tienviitta, jossa lukee vain "Paikka" sen sijaan, että siinä lukisi "Chicago Downtown". Ei kovin hyödyllistä, eikö?

Tässä on jotain, mikä hämmästytti minua, kun opin sen ensimmäistä kertaa: näytönlukijat voivat kerätä kaikki sivun linkit ja näyttää ne yhtenä suurena listana. Kuvittele, että joku antaisi sinulle hakemiston kaikista sivusi linkeistä. Olisiko jokainen niistä järkevä yksinään? Tätä testiä linkkitekstisi täytyy läpäistä!

### Linkkinavigointimallien ymmärtäminen

Näytönlukijat tarjoavat tehokkaita linkkinavigointiominaisuuksia, jotka perustuvat hyvin kirjoitettuun linkkitekstiin:

**Linkkinavigointimenetelmät:**
- **Järjestyksessä lukeminen**: Linkit luetaan osana sisällön virtausta
- **Linkkilistan luominen**: Kaikki sivun linkit kootaan hakukelpoiseksi hakemistoksi
- **Pikasiirtyminen**: Hyppää linkkien välillä näppäimistön pikavalinnoilla (K NVDA:ssa)
- **Hakutoiminto**: Etsi tiettyjä linkkejä kirjoittamalla osittainen teksti

**Miksi konteksti on tärkeää:**
Kun näytönlukijan käyttäjät luovat linkkilistan, he näkevät jotain tällaista:
- "Lataa raportti"
- "Lue lisää"
- "Klikkaa tästä"
- "Tietosuojakäytäntö"
- "Klikkaa tästä"

Vain kaksi näistä linkeistä tarjoaa hyödyllistä tietoa, kun ne luetaan kontekstista irrallaan!

> 📊 **Käyttäjävaikutus**: Näytönlukijan käyttäjät skannaavat linkkilistoja ymmärtääkseen sivun sisällön nopeasti. Geneerinen linkkiteksti pakottaa heidät palaamaan jokaisen linkin kontekstiin, mikä hidastaa merkittävästi selauskokemusta.

### Yleiset linkkitekstin virheet, joita tulee välttää

Ymmärtämällä, mikä ei toimi, voit tunnistaa ja korjata saavutettavuusongelmia olemassa olevassa sisällössä.

**❌ Geneerinen linkkiteksti, joka ei tarjoa kontekstia:**

```html
<!-- Meaningless when read from a link list -->
<p>Our sustainability efforts are detailed in our recent report. 
   <a href="/sustainability-2024.pdf">Click here</a> to view it.</p>

<!-- Repeated generic text throughout the page -->
<div class="article-card">
  <h3>Web Accessibility Guide</h3>
  <p>Learn the fundamentals...</p>
  <a href="/accessibility-guide">Read more</a>
</div>
<div class="article-card">
  <h3>Color Contrast Tips</h3>
  <p>Improve your design...</p>
  <a href="/color-contrast">Read more</a>
</div>

<!-- URLs as link text (difficult for screen readers to announce) -->
<p>Visit https://www.w3.org/WAI/WCAG21/quickref/ for WCAG guidelines.</p>

<!-- Vague action words -->
<a href="/contact">Go</a> | <a href="/about">See</a> | <a href="/help">View</a>
```

**Miksi nämä mallit epäonnistuvat:**
- **"Klikkaa tästä"** ei kerro käyttäjille mitään kohteesta
- **"Lue lisää"** toistettuna useita kertoja aiheuttaa hämmennystä
- **Raakatunnukset** ovat vaikeita näytönlukijoille lausua selkeästi
- **Yksittäiset sanat** kuten "Mene" tai "Katso" puuttuvat kuvailevasta kontekstista

### Erinomaisten linkkitekstien kirjoittaminen

Kuvaileva linkkiteksti hyödyttää kaikkia—näkevät käyttäjät voivat nopeasti skannata linkkejä, ja näytönlukijan käyttäjät ymmärtävät kohteet välittömästi.

**✅ Selkeät, kuvailevat linkkitekstiesimerkit:**

```html
<!-- Descriptive text that explains the destination -->
<p>Our comprehensive <a href="/sustainability-2024.pdf">2024 sustainability report (PDF, 2.1MB)</a> details our environmental initiatives.</p>

<!-- Specific, unique link text for each card -->
<div class="article-card">
  <h3>Web Accessibility Guide</h3>
  <p>Learn the fundamentals of inclusive design...</p>
  <a href="/accessibility-guide">Read our complete web accessibility guide</a>
</div>
<div class="article-card">
  <h3>Color Contrast Tips</h3>
  <p>Improve your design with better color choices...</p>
  <a href="/color-contrast">Explore color contrast best practices</a>
</div>

<!-- Meaningful text instead of raw URLs -->
<p>The <a href="https://www.w3.org/WAI/WCAG21/quickref/">WCAG 2.1 Quick Reference guide</a> provides comprehensive accessibility guidelines.</p>

<!-- Descriptive action links -->
<a href="/contact">Contact our support team</a> | 
<a href="/about">About our company</a> | 
<a href="/help">Get help with your account</a>
```

**Linkkitekstin parhaat käytännöt:**
- **Ole tarkka**: "Lataa neljännesvuosittainen talousraportti" vs. "Lataa"
- **Sisällytä tiedostotyyppi ja koko**: "(PDF, 1.2MB)" ladattaville tiedostoille
- **Mainitse, jos linkit avautuvat ulkoisesti**: "(avautuu uuteen ikkunaan)" tarvittaessa
- **Käytä aktiivista kieltä**: "Ota yhteyttä" vs. "Yhteystiedot"
- **Pidä lyhyenä**: Pyri 2–8 sanaan, jos mahdollista

### Kehittyneet linkkisaavutettavuuskuviot

Joskus visuaaliset suunnittelurajoitukset tai tekniset vaatimukset vaativat erityisiä ratkaisuja. Tässä on kehittyneitä tekniikoita yleisiin haastaviin tilanteisiin:

**ARIA:n käyttö lisäkontekstin tarjoamiseksi:**

```html
<!-- When button text must be short but needs more context -->
<a href="/report.pdf" 
   aria-label="Download 2024 annual financial report, PDF format, 2.3MB">
  Download Report
</a>

<!-- When the full context comes from surrounding content -->
<h3 id="sustainability-heading">Sustainability Initiative</h3>
<p>Our efforts to reduce environmental impact...</p>
<a href="/sustainability-details" 
   aria-labelledby="sustainability-heading"
   aria-describedby="sustainability-summary">
  Learn more
</a>
<p id="sustainability-summary">Detailed breakdown of our 2024 environmental goals and achievements</p>
```

**Tiedostotyyppien ja ulkoisten kohteiden ilmoittaminen:**

```html
<!-- Method 1: Include information in visible link text -->
<a href="/annual-report.pdf">
  Download our 2024 annual report (PDF, 2.3MB)
</a>

<!-- Method 2: Use screen reader-only text for file details -->
<a href="/annual-report.pdf">
  Download our 2024 annual report
  <span class="sr-only">(PDF format, 2.3MB)</span>
</a>

<!-- Method 3: External link indication -->
<a href="https://example.com" 
   target="_blank" 
   aria-describedby="external-link-warning">
  Visit external resource
</a>
<span id="external-link-warning" class="sr-only">
  (opens in new window)
</span>

<!-- Method 4: Using CSS for visual indicators -->
<a href="https://example.com" class="external-link">
  External resource
</a>
```

```css
/* Visual indicator for external links */
.external-link::after {
  content: " ↗";
  font-size: 0.8em;
  color: #666;
}

/* Screen reader announcement for external links */
.external-link::before {
  content: "External link: ";
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  overflow: hidden;
}
```

> ⚠️ **Tärkeää**: Kun käytät `target="_blank"`, kerro aina käyttäjille, että linkki avautuu uuteen ikkunaan tai välilehteen. Odottamattomat navigointimuutokset voivat olla hämmentäviä.

✅ **Testaa linkkikontekstisi**: Käytä selaimesi kehittäjätyökaluja luodaksesi listan kaikista sivusi linkeistä. Voitko ymmärtää jokaisen linkin tarkoituksen ilman ympäröivää kontekstia?

## ARIA: HTML-saavutettavuuden tehostaminen

[Accessible Rich Internet Applications (ARIA)](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) on kuin universaali kääntäjä monimutkaisten verkkosovellustesi ja avustavien teknologioiden välillä. Kun pelkkä HTML ei riitä ilmaisemaan kaikkea, mitä interaktiiviset komponenttisi tekevät, ARIA astuu kuvaan täyttämään nämä aukot.

Ajattelen ARIA:a kuin hyödyllisten merkintöjen lisäämistä HTML:ään—vähän kuin näyttämöohjeita näytelmäkäsikirjoituksessa, jotka auttavat näyttelijöitä ymmärtämään roolinsa ja suhteensa.

**Tärkein sääntö ARIA:sta**: Käytä aina ensin semanttista HTML:ää ja lisää sitten ARIA parantaaksesi sitä. Ajattele ARIA:a mausteena, ei pääruokana. Sen pitäisi selventää ja parantaa HTML-rakennetta, ei koskaan korvata sitä. Perusta kuntoon ensin!

### Strateginen ARIA:n käyttö

ARIA on tehokas, mutta sen mukana tulee vastuu. Väärin käytettynä ARIA voi heikentää saavutettavuutta enemmän kuin sen puuttuminen. Tässä tilanteet, joissa sitä kannattaa käyttää ja miten se tehdään oikein:

**✅ Käytä ARIA:a, kun:**
- Luot mukautettuja interaktiivisia widgettejä (haitarit, välilehdet, karusellit)
- Rakennat dynaamista sisältöä, joka muuttuu ilman sivun uudelleenlatausta
- Tarjoat lisäkontekstia monimutkaisille käyttöliittymäsuhteille
- Ilmoitat lataustiloista tai reaaliaikaisista sisällön päivityksistä
- Luot sovellusmaisia käyttöliittymiä mukautetuilla kontrolleilla

**❌ Vältä ARIA:a, kun:**
- Tavalliset HTML-elementit tarjoavat jo tarvittavat semantiikat
- Et ole varma, miten toteuttaa se oikein
- Se toistaa tietoa, joka on jo annettu semanttisella HTML:llä
- Et ole testannut sitä todellisilla avustavilla teknologioilla

> 🎯 **ARIA:n kultainen sääntö**: "Älä muuta semantiikkaa, ellei se ole ehdottoman välttämätöntä, varmista aina näppäimistön saavut
5. **Aloita yksinkertaisesti**: Monimutkaisissa ARIA-toteutuksissa on suurempi virheiden riski

**🔍 Testausprosessi:**

```mermaid
graph TD
    A[Write ARIA code] --> B[Validate HTML]
    B --> C[Test with keyboard only]
    C --> D[Test with screen reader]
    D --> E[Test across browsers]
    E --> F{Issues found?}
    F -->|Yes| G[Fix and re-test]
    F -->|No| H[Implementation complete]
    G --> B
```

**🚫 Yleisiä ARIA-virheitä, joita kannattaa välttää:**

- **Ristiriitainen tieto**: Älä kumoa HTML:n semantiikkaa
- **Liiallinen merkintä**: Liian paljon ARIA-tietoa voi hämmentää käyttäjiä
- **Staattinen ARIA**: ARIA-tilojen päivittämisen unohtaminen sisällön muuttuessa
- **Testaamattomat toteutukset**: ARIA, joka toimii teoriassa mutta epäonnistuu käytännössä
- **Puuttuva näppäimistötuki**: ARIA-roolit ilman vastaavia näppäimistötoimintoja

> 💡 **Testausresurssit**: Käytä työkaluja, kuten [accessibility-checker](https://www.npmjs.com/package/accessibility-checker), ARIA:n automaattiseen validointiin, mutta testaa aina myös oikeilla ruudunlukijoilla saadaksesi täydellisen kokemuksen.

✅ **Opi asiantuntijoilta**: Tutustu [ARIA Authoring Practices Guide](https://w3c.github.io/aria-practices/) -oppaaseen, joka sisältää testattuja malleja ja monimutkaisten interaktiivisten widgettien toteutuksia.

## Kuvien ja median saavutettavuus

Visuaalinen ja audiosisältö ovat olennainen osa nykyaikaisia verkkokokemuksia, mutta ne voivat luoda esteitä, jos niitä ei toteuteta huolellisesti. Tavoitteena on varmistaa, että median tarjoama tieto ja tunnevaikutus tavoittavat jokaisen käyttäjän. Kun tämän oppii, siitä tulee luonnollista.

Erilaiset mediat vaativat erilaisia saavutettavuusratkaisuja. Se on kuin ruoanlaittoa—et käsittelisi herkkää kalaa samalla tavalla kuin tuhtia pihviä. Näiden erojen ymmärtäminen auttaa valitsemaan oikean ratkaisun kuhunkin tilanteeseen.

### Strateginen kuvien saavutettavuus

Jokaisella verkkosivustosi kuvalla on tarkoitus. Tämän tarkoituksen ymmärtäminen auttaa sinua kirjoittamaan parempaa vaihtoehtoista tekstiä ja luomaan osallistavampia kokemuksia.

**Neljä kuva-tyyppiä ja niiden alt-tekstistrategiat:**

**Informatiiviset kuvat** - välittävät tärkeää tietoa:
```html
<img src="../../../../translated_images/chart.31c7eb0eb5c4450deba10b6f236732dfee8e8a11f6c0d8f31d2c2efb9d4c00ef.fi.png" alt="Sales increased 25% from Q1 to Q2 2024">
```

**Koristeelliset kuvat** - pelkästään visuaalisia, ilman informatiivista arvoa:
```html
<img src="../../../../translated_images/decorative-border.b2f3c4d6634fb79d57fb6357835906c16938df3d5651c1314c196c3b1c52df98.fi.png" alt="" role="presentation">
```

**Toiminnalliset kuvat** - toimivat painikkeina tai ohjaimina:
```html
<button>
  <img src="search-icon.svg" alt="Search">
</button>
```

**Monimutkaiset kuvat** - kaaviot, diagrammit, infografiikat:
```html
<img src="../../../../translated_images/complex-chart.c831f461a363b446a688be5ccacde20d011221758c902cb082cfd4293534ef17.fi.png" alt="Quarterly sales data" aria-describedby="chart-description">
<div id="chart-description">
  <p>Detailed description: Sales data shows a steady increase across all quarters...</p>
</div>
```

### Videoiden ja audion saavutettavuus

**Videovaatimukset:**
- **Tekstitykset**: Puhutun sisällön ja äänitehosteiden tekstiversio
- **Äänikuvaukset**: Visuaalisten elementtien kerronta näkövammaisille käyttäjille
- **Transkriptiot**: Kaiken audio- ja visuaalisen sisällön tekstiversio

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track kind="captions" src="captions.vtt" srclang="en" label="English">
  <track kind="descriptions" src="descriptions.vtt" srclang="en" label="Audio descriptions">
</video>
```

**Audiovaatimukset:**
- **Transkriptiot**: Kaiken puhutun sisällön tekstiversio
- **Visuaaliset indikaattorit**: Pelkästään audiosisällön osalta tarjoa visuaalisia vihjeitä

### Modernit kuvatekniikat

**Koristeellisten kuvien käyttö CSS:n avulla:**
```css
.hero-section {
  background-image: url('decorative-hero.jpg');
  /* Decorative images in CSS don't need alt text */
}
```

**Responsiiviset kuvat saavutettavuuden kanssa:**
```html
<picture>
  <source media="(min-width: 800px)" srcset="large-chart.png">
  <source media="(min-width: 400px)" srcset="medium-chart.png">
  <img src="../../../../translated_images/small-chart.c50c7b1bbcce43d8d24fbfbab8f691fe47d8f25fb7c70857c9eae21d5f22862e.fi.png" alt="Website traffic increased 40% after accessibility improvements">
</picture>
```

✅ **Testaa kuvien saavutettavuus**: Käytä ruudunlukijaa navigoidaksesi sivulla, jossa on kuvia. Saatko tarpeeksi tietoa sisällön ymmärtämiseksi?

## Näppäimistönavigointi ja fokuksen hallinta

Monet käyttäjät navigoivat verkossa pelkästään näppäimistön avulla. Tähän kuuluvat motorisia vammoja omaavat henkilöt, tehokäyttäjät, jotka pitävät näppäimistöä nopeampana kuin hiirtä, sekä kaikki, joiden hiiri on lakannut toimimasta. Varmistamalla, että sivustosi toimii hyvin näppäimistön syötteellä, teet siitä tehokkaamman kaikille.

### Välttämättömät näppäimistönavigointimallit

**Standardit näppäimistötoiminnot:**
- **Tab**: Siirtää fokuksen eteenpäin interaktiivisten elementtien läpi
- **Shift + Tab**: Siirtää fokuksen taaksepäin
- **Enter**: Aktivoi painikkeet ja linkit
- **Space**: Aktivoi painikkeet, valitsee valintaruudut
- **Nuolinäppäimet**: Navigoi komponenttiryhmien sisällä (radiopainikkeet, valikot)
- **Escape**: Sulkee modaalit, pudotusvalikot tai peruuttaa toiminnot

### Fokuksen hallinnan parhaat käytännöt

**Näkyvät fokusindikaattorit:**
```css
/* Ensure focus is always visible */
button:focus-visible {
  outline: 2px solid #4A90A4;
  outline-offset: 2px;
}

/* Custom focus styles for different components */
.card:focus-within {
  box-shadow: 0 0 0 3px rgba(74, 144, 164, 0.5);
}
```

**Ohituslinkit tehokkaaseen navigointiin:**
```html
<a href="#main-content" class="skip-link">Skip to main content</a>
<a href="#navigation" class="skip-link">Skip to navigation</a>

<nav id="navigation">
  <!-- navigation content -->
</nav>
<main id="main-content">
  <!-- main content -->
</main>
```

**Oikea tab-järjestys:**
```html
<!-- Use semantic HTML for natural tab order -->
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" tabindex="0">
  
  <label for="email">Email:</label>
  <input type="email" id="email" tabindex="0">
  
  <button type="submit" tabindex="0">Submit</button>
</form>
```

### Fokuksen lukitseminen modaalissa

Kun modaalidialogi avataan, fokus tulisi lukita modaalin sisälle:

```javascript
// Modern focus trap implementation
function trapFocus(element) {
  const focusableElements = element.querySelectorAll(
    'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
  );
  
  const firstElement = focusableElements[0];
  const lastElement = focusableElements[focusableElements.length - 1];

  element.addEventListener('keydown', (e) => {
    if (e.key === 'Tab') {
      if (e.shiftKey && document.activeElement === firstElement) {
        e.preventDefault();
        lastElement.focus();
      } else if (!e.shiftKey && document.activeElement === lastElement) {
        e.preventDefault();
        firstElement.focus();
      }
    }
    
    if (e.key === 'Escape') {
      closeModal();
    }
  });
  
  // Focus first element when modal opens
  firstElement.focus();
}
```

✅ **Testaa näppäimistönavigointi**: Kokeile navigoida verkkosivustollasi pelkästään Tab-näppäimen avulla. Pääsetkö kaikkiin interaktiivisiin elementteihin? Onko fokusjärjestys looginen? Ovatko fokusindikaattorit selvästi näkyvissä?

## Lomakkeiden saavutettavuus

Lomakkeet ovat kriittisiä käyttäjän vuorovaikutukselle ja vaativat erityistä huomiota saavutettavuuden suhteen.

### Tunnisteiden ja lomakekontrollien yhdistäminen

**Jokaisella lomakekontrollilla tulee olla tunniste:**
```html
<!-- Explicit labeling (preferred) -->
<label for="username">Username:</label>
<input type="text" id="username" name="username" required>

<!-- Implicit labeling -->
<label>
  Password:
  <input type="password" name="password" required>
</label>

<!-- Using aria-label when visual label isn't desired -->
<input type="search" aria-label="Search products" placeholder="Search...">
```

### Virheiden käsittely ja validointi

**Saavutettavat virheilmoitukset:**
```html
<label for="email">Email Address:</label>
<input type="email" id="email" name="email" 
       aria-describedby="email-error" 
       aria-invalid="true" required>
<div id="email-error" role="alert">
  Please enter a valid email address
</div>
```

**Lomakevalidoinnin parhaat käytännöt:**
- Käytä `aria-invalid` osoittamaan virheelliset kentät
- Tarjoa selkeät ja tarkat virheilmoitukset
- Käytä `role="alert"` tärkeiden virheilmoitusten ilmoittamiseen
- Näytä virheet sekä välittömästi että lomakkeen lähetyksen yhteydessä

### Kenttäryhmät ja ryhmittely

**Ryhmittele liittyvät lomakekontrollit:**
```html
<fieldset>
  <legend>Shipping Address</legend>
  <label for="street">Street Address:</label>
  <input type="text" id="street" name="street">
  
  <label for="city">City:</label>
  <input type="text" id="city" name="city">
</fieldset>

<fieldset>
  <legend>Preferred Contact Method</legend>
  <input type="radio" id="contact-email" name="contact" value="email">
  <label for="contact-email">Email</label>
  
  <input type="radio" id="contact-phone" name="contact" value="phone">
  <label for="contact-phone">Phone</label>
</fieldset>
```

## Saavutettavuusmatkasi: Tärkeimmät opit

Onnittelut! Olet juuri saanut perustiedot todella osallistavien verkkokokemusten luomiseksi. Tämä on todella innostavaa! Verkkosaavutettavuus ei ole vain vaatimusten täyttämistä—se on erilaisten tapojen tunnistamista, joilla ihmiset ovat vuorovaikutuksessa digitaalisen sisällön kanssa, ja suunnittelua tämän monimuotoisuuden huomioimiseksi.

Olet nyt osa kasvavaa kehittäjäyhteisöä, joka ymmärtää, että hyvä suunnittelu toimii kaikille. Tervetuloa joukkoon!

**🎯 Saavutettavuustyökalupakkisi sisältää nyt:**

| Periaate | Toteutus | Vaikutus |
|----------|----------|----------|
| **Semanttinen HTML-perusta** | Käytä oikeita HTML-elementtejä niiden tarkoituksen mukaisesti | Ruudunlukijat voivat navigoida tehokkaasti, näppäimistöt toimivat automaattisesti |
| **Osallistava visuaalinen suunnittelu** | Riittävä kontrasti, merkityksellinen värien käyttö, näkyvät fokusindikaattorit | Selkeä kaikille missä tahansa valaistusolosuhteissa |
| **Kuvaileva sisältö** | Merkityksellinen linkkiteksti, alt-teksti, otsikot | Käyttäjät ymmärtävät sisällön ilman visuaalista kontekstia |
| **Näppäimistön saavutettavuus** | Tab-järjestys, näppäimistökomennot, fokuksen hallinta | Motorinen saavutettavuus ja tehokäyttäjien tehokkuus |
| **ARIA-parannukset** | Strateginen käyttö semanttisten aukkojen täyttämiseksi | Monimutkaiset sovellukset toimivat apuvälineiden kanssa |
| **Kattava testaus** | Automatisoidut työkalut + manuaalinen tarkistus + oikeiden käyttäjien testaus | Havaitse ongelmat ennen kuin ne vaikuttavat käyttäjiin |

**🚀 Seuraavat askeleesi:**

1. **Sisällytä saavutettavuus työnkulkuusi**: Tee testauksesta luonnollinen osa kehitysprosessiasi
2. **Opi oikeilta käyttäjiltä**: Pyydä palautetta apuvälineitä käyttäviltä ihmisiltä
3. **Pysy ajan tasalla**: Saavutettavuustekniikat kehittyvät uusien teknologioiden ja standardien myötä
4. **Puolusta osallistamista**: Jaa tietosi ja tee saavutettavuudesta tiimisi prioriteetti

> 💡 **Muista**: Saavutettavuusrajoitukset johtavat usein innovatiivisiin, elegantteihin ratkaisuihin, jotka hyödyttävät kaikkia. Jalkakäytävien rampit, tekstitykset ja ääniohjaus alkoivat saavutettavuusominaisuuksina ja muuttuivat valtavirran parannuksiksi.

**Liiketoiminnan näkökulmasta se on täysin järkevää**: Saavutettavat verkkosivustot tavoittavat enemmän käyttäjiä, sijoittuvat paremmin hakukoneissa, aiheuttavat vähemmän ylläpitokustannuksia ja välttävät oikeudelliset riskit. Mutta rehellisesti sanottuna? Todellinen syy välittää saavutettavuudesta on paljon syvällisempi. Saavutettavat verkkosivustot ilmentävät verkon parhaita arvoja—avoimuutta, osallistavuutta ja ajatusta siitä, että kaikilla on oikeus tietoon.

Olet nyt valmis rakentamaan tulevaisuuden osallistavaa verkkoa. Jokainen luomasi saavutettava sivusto tekee internetistä vieraanvaraisemman paikan kaikille. Se on aika mahtavaa, kun sitä ajattelee!

## Lisäresurssit

Jatka saavutettavuuden oppimismatkaasi näiden olennaisten resurssien avulla:

**📚 Viralliset standardit ja ohjeet:**
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/) - Virallinen saavutettavuusstandardi pikaoppaalla
- [ARIA Authoring Practices Guide](https://w3c.github.io/aria-practices/) - Kattavat mallit interaktiivisille widgeteille
- [WebAIM Guidelines](https://webaim.org/) - Käytännönläheistä ja aloittelijaystävällistä saavutettavuusohjeistusta

**🛠️ Työkalut ja testausresurssit:**
- [axe DevTools](https://www.deque.com/axe/devtools/) - Teollisuusstandardin mukainen saavutettavuustestaus
- [A11y Project Checklist](https://www.a11yproject.com/checklist/) - Vaiheittainen saavutettavuuden tarkistus
- [Accessibility Insights](https://accessibilityinsights.io/) - Microsoftin kattava testauspaketti
- [Color Oracle](https://colororacle.org/) - Värisokeussimulaattori suunnittelutestaukseen

**🎓 Oppiminen ja yhteisö:**
- [WebAIM Screen Reader Survey](https://webaim.org/projects/screenreadersurvey9/) - Oikeiden käyttäjien mieltymykset ja käyttäytyminen
- [Inclusive Components](https://inclusive-components.design/) - Modernit saavutettavat komponenttimallit
- [A11y Coffee](https://a11y.coffee/) - Nopeat saavutettavuusvinkit ja näkemykset
- [Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/) - W3C:n kattavat saavutettavuusresurssit

**🎥 Käytännön oppiminen:**
- [Accessibility Developer Guide](https://www.accessibility-developer-guide.com/) - Käytännön toteutusohjeet
- [Deque University](https://dequeuniversity.com/) - Ammattimaiset saavutettavuuskoulutukset

## GitHub Copilot Agent -haaste 🚀

Käytä Agent-tilaa suorittaaksesi seuraavan haasteen:

**Kuvaus:** Luo saavutettava modaalidialogikomponentti, joka demonstroi oikeaa fokuksen hallintaa, ARIA-attribuutteja ja näppäimistönavigointimalleja.

**Ohje:** Rakenna täydellinen modaalidialogikomponentti HTML:llä, CSS:llä ja JavaScriptillä, joka sisältää: oikean fokuksen lukituksen, ESC-näppäimen sulkemiseen, klikkauksen ulkopuolelle sulkemiseen, ARIA-attribuutit ruudunlukijoille ja näkyvät fokusindikaattorit. Modaalin tulisi sisältää lomake, jossa on asianmukaiset tunnisteet ja virheiden käsittely. Varmista, että komponentti täyttää WCAG 2.1 AA -standardit.


## 🚀 Haaste

Ota tämä HTML ja kirjoita se mahdollisimman saavutettavaksi käyttäen oppimiasi strategioita.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Turtle Ipsum - The World's Premier Turtle Fan Club</title>
    <link href='../assets/style.css' rel='stylesheet' type='text/css'>
  </head>
  <body>
    <header class="site-header">
      <h1 class="site-title">Turtle Ipsum</h1>
      <p class="site-subtitle">The World's Premier Turtle Fan Club</p>
    </header>
    
    <nav class="main-nav" aria-label="Main navigation">
      <h2 class="nav-header">Resources</h2>
      <ul class="nav-list">
        <li><a href="https://www.youtube.com/watch?v=CMNry4PE93Y">"I like turtles" video</a></li>
        <li><a href="https://en.wikipedia.org/wiki/Turtle">Basic turtle information</a></li>
        <li><a href="https://en.wikipedia.org/wiki/Turtles_(chocolate)">Chocolate turtles candy</a></li>
      </ul>
    </nav>
    
    <main class="main-content">
      <article>
        <h1>Welcome to Turtle Ipsum</h1>
        <p class="intro">
          <a href="/about">Learn more about our turtle community</a> and discover fascinating facts about these amazing creatures.
        </p>
        <p class="article-text">
          Turtle ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </p>
      </article>
    </main>
    
    <footer class="footer">
      <section class="newsletter-signup">
        <h2>Stay Updated</h2>
        <button type="button" onclick="showNewsletterForm()">Sign up for turtle news</button>
      </section>
      
      <nav class="footer-nav" aria-label="Footer navigation">
        <h2>Site Pages</h2>
        <ul>
          <li><a href="../">Home</a></li>
          <li><a href="../semantic">Semantic HTML example</a></li>
        </ul>
      </nav>
      
      <p class="footer-copyright">&copy; 2024 Instrument. All rights reserved.</p>
    </footer>
  </body>
</html>
```

**Tehdyt parannukset:**
- Lisätty asianmukainen semanttinen HTML-rakenne
- Korjattu otsikkohierarkia (yksi h1, looginen eteneminen)
- Lisätty merkityksellinen linkkiteksti "klikkaa tästä" sijaan
- Sisällytetty asianmukaiset ARIA-tunnisteet navigointiin
- Lisätty lang-attribuutti ja asianmukaiset meta-tunnisteet
- Käytetty button-elementtiä interaktiivisille elementeille
- Jäsennelty alatunnisteen sisältö asianmukaisilla maamerkeillä

## Luentojälkeinen kysely
[Luentojälkeinen kysely](https://ff-quizzes.netlify.app/web/en/)

## Kertaus ja itseopiskelu

Monilla valtioilla on lakeja saavutettavuusvaatimuksista. Tutustu kotimaasi saavutettavuuslakeihin. Mitä katetaan ja mitä ei? Esimerkkinä [tämä valtion verkkosivusto](https://accessibility.blog.gov.uk/).

## Tehtävä
 
[Analysoi ei-saavutettava verkkosivusto](assignment.md)

Lähde: [Turtle Ipsum](https://github.com/Instrument/semantic-html-sample) by Instrument

---

**Vastuuvapauslauseke**:  
Tämä asiakirja on käännetty käyttämällä tekoälypohjaista käännöspalvelua [Co-op Translator](https://github.com/Azure/co-op-translator). Vaikka pyrimme tarkkuuteen, huomioithan, että automaattiset käännökset voivat sisältää virheitä tai epätarkkuuksia. Alkuperäinen asiakirja sen alkuperäisellä kielellä tulisi pitää ensisijaisena lähteenä. Kriittisen tiedon osalta suositellaan ammattimaista ihmiskäännöstä. Emme ole vastuussa väärinkäsityksistä tai virhetulkinnoista, jotka johtuvat tämän käännöksen käytöstä.