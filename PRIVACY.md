# PoloChat BETA — zásady soukromí

Aktualizováno: 20. října 2026. Vztahuje se k rozšíření PoloChat BETA 0.4.6 a jeho propojení s aplikací PoloChat Desktop.

## Provozovatel a kontakt

PoloChat, projekt spravovaný účtem [poloafkontakt-del](https://github.com/poloafkontakt-del).
Podpora a žádosti týkající se dat: **poloafkontakt@gmail.com**. Technické chyby lze hlásit také přes [podporu PoloChatu](https://github.com/poloafkontakt-del/polochat-releases/issues). Do veřejných hlášení nevkládejte hesla, přístupové tokeny, soukromé konverzace ani jiné citlivé údaje.

## Co rozšíření dělá

PoloChat BETA je doplněk běžící aplikace PoloChat Desktop na stejném počítači. Spojuje sledované chaty do jednoho okna a umožňuje uživateli zadávat zprávy a další chatové akce. Samostatná desktopová aplikace zajišťuje připojení účtů a komunikaci s platformami. Instalace rozšíření sama o sobě účty nepřihlašuje.

## Zpracovávané údaje a účel

- Identifikátory a zobrazované názvy připojených účtů a kanálů, profilové obrázky a stav přihlášení: zobrazení účtů a správné přiřazení chatů a příkazů.
- Obsah sledovaných chatových zpráv, přezdívky, časy, odznaky, emoty, odpovědi a oznámení o odměnách: čtení, místní historie, vyhledání adresáta odpovědi a zobrazení chatu.
- Text, který uživatel zadá do chatu, a uživatelem zvolené moderátorské akce: předání vybrané platformě přes desktop. Oprávnění a omezení kontroluje příslušná platforma.
- Nastavení vzhledu, vybrané kanály, skupiny a rozložení: zapamatování uživatelských voleb.
- Otázky, odpovědi a hlasy v anketách a údaje o účastnících losování: funkce anket a losování, pokud je uživatel používá.

Rozšíření nečte obecnou historii prohlížení, hesla, cookies jiných webů ani obsah ostatních otevřených karet. Nežádá oprávnění k libovolným webům, cookies, historii nebo sledování všech karet. Nepřebírá přístupové ani obnovovací tokeny platforem do svého rozhraní; přihlášení zajišťuje desktop a příslušná platforma.

## Uložení a doba uchování

Rozšíření ukládá nastavení a omezenou místní historii (nejvýše 250 uložených zpráv pro jeho profil) do úložiště svého profilu v prohlížeči. Novější zprávy postupně nahrazují starší. Místní historie se sama neodesílá jako centrální archiv provozovateli PoloChatu. Úložiště rozšíření není samostatně šifrovaný trezor; přístup k počítači a profilu chraňte zabezpečením zařízení.

Data rozšíření lze odstranit odebráním rozšíření a jeho místních dat v prohlížeči. To nesmaže zprávy již publikované na platformách ani samostatná data desktopové aplikace. Účty lze odhlásit v PoloChatu; přístup aplikace lze také odvolat v nastavení příslušné platformy. Exporty a stažená hlášení zůstávají v místě, kam si je uživatel uložil.

Desktop uchovává vlastní nastavení, historii a údaje potřebné pro přihlášení odděleně od rozšíření. Údaje sdílených anket může zpracovávat beta služba PoloChatu po dobu potřebnou pro jejich provoz. Úplné odstranění údajů provozovaných službou lze řešit prostřednictvím podpory; pro údaje uložené na platformách platí pravidla těchto platforem.

## Přenosy a příjemci

Rozšíření komunikuje se schválenou desktopovou aplikací na témže zařízení přes HTTP/WebSocket na localhost portech 3000 nebo 3001. Toto místní spojení nejde přes internet. Před prvním plným ovládáním je nutné potvrzení v desktopu. Internetovou komunikaci s Twitch, Kick, YouTube a dalšími zapnutými službami zajišťuje desktop; zprávy a příkazy jsou odesílány podle akcí uživatele.

Přihlášení a obnova přihlášení mohou využívat autorizační službu PoloChatu na Renderu. Sdílené ankety využívají službu PoloChatu, která přijímá obsah ankety, hlasy a údaje potřebné k ověření účtu. Obrázky emotů, odznaků, profilů a GIFů se mohou načítat přímo z příslušných CDN; jejich poskytovatel při požadavku obdrží běžné síťové údaje, například IP adresu. Instalaci a aktualizace rozšíření zajišťuje Chrome Web Store; desktopové distribuční balíčky jsou hostované na GitHubu. Poskytovatelé infrastruktury mohou vytvářet vlastní technické a bezpečnostní záznamy podle svých pravidel.

Zpětná vazba v rozhraní vytváří místní textový soubor. Sama se automaticky neodesílá; uživatel rozhoduje, komu soubor předá.

## Omezené použití údajů

Údaje používáme k poskytování a zlepšování popsaných chatových funkcí. Rozšíření nemá reklamní analytiku ani sledovací SDK. Údaje neprodáváme, nepoužíváme k cílení reklamy a neposkytujeme je pro účely nesouvisející s popsanou funkcí. Předání se omezuje na poskytování uživatelem zvolených funkcí, potřebnou infrastrukturu a případné zákonné povinnosti.

Použití informací získaných z Google API bude v souladu se zásadami Chrome Web Store pro uživatelská data včetně požadavků Limited Use. Přístup k jednotlivým platformám se rovněž řídí jejich vlastními zásadami soukromí a oprávněními, která jim uživatel udělí.

## Změny

Při podstatné změně práce s údaji aktualizujeme tuto stránku a podle povahy změny také informace v rozhraní a obchodě. Beta může obsahovat chyby; tato skutečnost nemění popsané účely zpracování.
