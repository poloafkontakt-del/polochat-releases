# PoloChat Cloud BETA — zásady soukromí

Kontakt provozovatele: **poloafkontakt@gmail.com**.

Tato část popisuje volitelný cloudový režim. Běžný desktop a původní místní rozšíření mají odlišné ukládání podle dosavadních zásad.

## Co pro cloud potřebujeme

- Identifikátor, přezdívku a případně profilový obrázek účtu, který si uživatel sám připojí na Twitchi či Kicku.
- Přístupový a obnovovací token udělený platformou pro schválené funkce. Heslo platformy do PoloChatu nezadáváš.
- Vlastní cloudovou relaci, seznam vybraných kanálů a veřejné zprávy z těchto kanálů.
- Běžné technické údaje připojení. Aplikační omezení požadavků používá krátkodobý otisk adresy spojení; poskytovatel hostingu může mít své provozní záznamy.

PoloChat Cloud čte zprávy a na tvůj výslovný pokyn odesílá zprávy pod připojeným účtem. Zprávy ostatních diváků se zobrazují tak, jak je poskytne platforma. Cloudová beta nemá přístup k historii prohlížení, cookies jiných webů ani ostatním kartám.

## Ukládání a poskytovatelé

Serverová část je připravená pro stávající službu PoloChatu na Renderu. Účty, tokeny a kanály jsou v databázi šifrované pomocí AES-256-GCM; klíč je oddělený v prostředí služby. Připojení k databázi používá TLS s ověřením certifikátu.

Databázi poskytuje **Neon**, projekt PoloChat na bezplatném plánu v oblasti **AWS Europe Central 1 (Frankfurt, Německo)**. Server běží na Renderu. Připravené cloudové ukládání se použije až po propojení databáze a zapnutí cloudového režimu; samotné vytvoření databáze nepřenáší účty Twitche ani Kicku.

OAuth tokeny ani cloudová přihlašovací cookie nejsou přístupné JavaScriptu chatové stránky. Cookie vlastní relace je Secure a HttpOnly, omezená na cestu `/cloud`, s platností nejvýše 7 dní. Při odhlášení se relace odvolá a cookie odstraní.

## Jak dlouho

- Aktivní seznam účtů a kanálů zůstává do smazání cloudového profilu nebo ukončení bety.
- Pokud použiješ losování, ukládají se také jeho nastavení, přezdívky a identifikátory přihlášených účastníků, vybraní vítězové a omezená historie losování. Tyto údaje jsou součástí stejného šifrovaného cloudového profilu. V cloudové betě je omezený počet účastníků a uložených minulých losování.
- U anket se uchovávají jejich identifikátory, stav pořadatele a údaje pro obnovení ankety. Společná služba anket ověřuje připojený Twitch/Kick účet, aby omezila opakované hlasování. Přihlašovací tokeny se nepředávají ostatním účastníkům.
- Zprávy nejsou dlouhodobě archivované v databázi. Server drží nejvýše 250 zpráv na profil v provozní paměti. Po posledním odpojení se přibližně za 5 minut čtečky a tato paměť zruší; restart ji vymaže také.
- Poskytovatelé infrastruktury mohou uchovávat krátkodobé technické záznamy a zálohy podle vlastních podmínek.

## Ovládání

V nastavení můžeš odhlásit aktuální relaci nebo smazat cloudový profil včetně připojených účtů a uložených kanálů. Smazání se týká aktivních záznamů PoloChatu; zpracování případných infrastrukturních záloh se řídí jejich retenční dobou. Odstranění cloudového profilu neodhlašuje samostatně připojený desktop. Úplné odvolání oprávnění aplikace provedeš také v nastavení připojených aplikací Twitche/Kicku.

Cloud nepoužíváme k prodeji chatových zpráv ani k reklamnímu sledování. Pro dotazy a požadavky na odstranění dat kontaktuj poloafkontakt@gmail.com.

Moderátorské akce se provádějí jen na pokyn uživatele přes příslušnou platformu. Další oprávnění pro moderaci se vyžádají zvlášť. Platforma ověřuje oprávnění k akcím a může uchovávat vlastní moderátorské záznamy.

Aktualizováno 25. 10. 2026. Tyto zásady se vztahují na volitelnou cloudovou betu PoloChatu.



## PoloPoints — společné účty a virtuální body

Po zapnutí PoloPoints ukládáme do samostatných tabulek stejné databáze Neonu serverově ověřené identifikátory a zobrazované názvy propojených Twitch/Kick účtů, jejich vazbu na společný účet, vlastnictví kanálů a oprávnění ve streamerském obchodě. Účty se nespojují podle přezdívky; druhou platformu připojuje uživatel výslovně. OAuth tokeny zůstávají ve stávajícím šifrovaném trezoru a nejsou součástí bodových tabulek ani účetních exportů.

Samostatně pro každého streamera vedeme peněženky, změny zůstatků, důvody a časy změn, identitu oprávněného aktéra, nabídku virtuálních odměn, objednávky, jejich vyřízení a vrácení bodů. K prokázání aktivity a zabránění opakovanému připsání ukládáme identifikátory, časy a omezené příznaky serverem přijatých veřejných chatových událostí; bodové tabulky neukládají celý text zpráv. Samotné otevření videa neprokazuje sledování a nepřipisuje body. Body nejsou skutečné peníze a beta neprovádí platby.

Bodové tabulky nejsou samostatně šifrovány aplikačním master key jako OAuth trezor. Přístup k nim zajišťuje server s ověřenou relací, kontrolou vlastníka/administrátora a oddělením obchodů; přenos do databáze používá ověřené TLS. Uživatel vidí vlastní zůstatky a objednávky, oprávněný vlastník či administrátor svého obchodu příslušné peněženky, objednávky a audit.

Odhlášení, odpojení platformy ani smazání cloudového profilu automaticky neodstraňuje účetní a auditní historii PoloPoints. Zachování záznamů umožňuje ověřit změny, zabránit dvojímu připsání a řešit reklamace; automatická doba výmazu v této betě zatím není nastavena. Požadavky na přístup, opravu nebo odstranění těchto údajů řeší podpora poloafkontakt@gmail.com. Infrastrukturní zálohy mají vlastní dobu uchování. Vypnutí funkce zastaví její používání a záznamy zachová.
