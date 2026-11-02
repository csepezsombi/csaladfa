CSALÁDI GYÖKEREK – ELSŐ ONLINE TESZTVERZIÓ

1. A ZIP-et bontsd ki a saját gépeden.
2. GitHub: hozz létre egy új, Private repositoryt, például csaladfa néven.
3. Az index.html, vercel.json és README.txt fájlokat töltsd fel közvetlenül a repository gyökerébe. Ne a ZIP-et töltsd fel.
4. Vercel: Add New / Project. Importáld a GitHub repositoryt.
5. A megfelelő GitHub-repositoryhoz adj hozzáférést, nem szükséges minden repositoryt engedélyezni.
6. Válaszd a személyes Hobby csomagot. Ne adj meg kártyát és ne indíts fizetős próbát.
7. Framework Preset: Other. Root Directory: a repository gyökere. Build Command: nincs. Output Directory: a projekt gyökere (ha külön felülírás szükséges: .). Ne legyen npm build parancs.
8. Deploy. A projektben nincs buildfolyamat és nincs szükség Node-csomagok telepítésére.
9. A kapott HTTPS-webcímet állítsd be a Supabase Authentication / URL Configuration / Site URL mezőjében. A későbbi átirányításos bejelentkezéshez ez különösen fontos.
10. Próbáld ki mintaadatokkal az adminbelépést, egy személy létrehozását és az adat nyilvános megtekintését inkognitóablakban.

A publikus Supabase-kapcsolódási adatok az index.html fájlban vannak. Titkos kulcsot és jelszót soha ne adj ehhez a fájlhoz.

ELŐFELTÉTELEK
A korábban megadott SQL-ek lefutottak: family_private.admins, public.is_family_admin(), people, relationships, submissions, RLS és adminszabályok.
Authentication: új regisztráció és anonymous sign-ins kikapcsolva. A saját, kézzel létrehozott adminfelhasználód létezik.

MI MŰKÖDIK
Nyilvános csaláfanézet. Adminbelépés. Személyek létrehozása és szerkesztése. Kapcsolatok létrehozása és törlése. Személy törlése kapcsolataival együtt. JSON-export. Nyitott oldalon 60 másodpercenként frissítés, kivéve nyitott adatlapnál, illetve háttérben lévő lapnál.

MI NINCS MÉG BENNE
Nyilvános beküldés, jóváhagyási kezelőfelület, fotófeltöltés és galéria, megjegyzésfül, import és visszaállítás, jelszó-visszaállító e-mail, korlátlan méretű fa, minden összetett családi kapcsolat optimális megjelenítése.
A képgaléria-demó még nincs ebbe integrálva. Ne tekintsd a csomagot teljes, végleges terméknek.

KORLÁTOK
A fa egy párt mutat személyenként, több kapcsolat az adatlapon látszik. Legfeljebb 1000 személy és 1000 kapcsolat betöltése. A leszármazási ciklust a kezelőfelület ellenőrzi; adatbázis-szintű ciklusvédelmet még külön kell hozzáadni. Nincs undo, törlés előtt exportálj. Egy személy összes kapcsolata törlődik a személy törlésekor. A JSON-export nem tartalmaz képeket vagy beküldéseket.

A kód elkészült, de böngészős és a saját adatbázisoddal végzett integrációs teszt nem történt. Először csak mintaadatokkal használd. Ne oszd meg széles körben a webcímet a jogosultságtesztek előtt.

A supabase-js külső CDN-ről töltődik be, ezért internetkapcsolat szükséges. Az alkalmazás nem használ service_role vagy secret kulcsot, és nem tartalmaz előfizetést vagy számlázást módosító kódot.
