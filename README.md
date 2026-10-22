# MojFilm – Android aplikacija

Aplikacija otvara stranicu za grupno gledanje unutar sebe, bez adresne trake i bez prikazivanja linka korisniku.

## Šta aplikacija radi
- Otvara stranicu preko cijelog ekrana, bez adresne trake
- Adresa je u kodu spremljena kodirano (ne vidi se kao običan tekst)
- Linkovi na drugim stranicama otvaraju se u browseru, a ne u aplikaciji
- Mikrofon (i kamera) za glasovni chat – traži dozvolu kad stranica zatraži
- Video preko cijelog ekrana, dugme "Nazad" vraća na prethodnu stranicu
- Ostaješ prijavljen (cookies se čuvaju)
- Ekran "Nema internet konekcije" s dugmetom za ponovni pokušaj
- Upload fajlova (npr. profilna slika)

## Kako dobiti APK

### Opcija A – GitHub (bez instaliranja ičega)
1. Napravi novi repozitorij na github.com
2. Uploaduj SVE fajlove iz ovog foldera (uključujući skriveni folder `.github`)
3. Otvori tab **Actions** → sačekaj da build završi (~3–5 min)
4. Klikni na završeni build → dolje pod **Artifacts** preuzmi `MojFilm-apk`
5. Raspakuj zip i instaliraj `app-release.apk` na telefon (dozvoli "nepoznate izvore")

### Opcija B – Android Studio (na računaru)
1. File → Open → odaberi ovaj folder
2. Build → Build App Bundle(s) / APK(s) → Build APK(s)
3. APK je u `app/build/outputs/apk/`

## Promjena adrese
Adresa je u `MainActivity.java` u konstanti `ENC` (Base64). Novu vrijednost dobiješ npr. na base64encode.org.

## Napomene
- APK je potpisan "debug" ključem. Svaki GitHub build pravi novi ključ, pa za nadogradnju treba prvo deinstalirati staru verziju. Za stalne nadogradnje ili Google Play napravi vlastiti keystore.
- "Skriven link" znači da ga korisnik ne vidi u aplikaciji. Neko ko namjerno raspakuje APK ili prati mrežni saobraćaj i dalje može saznati adresu – to se kod web-aplikacija ne može potpuno spriječiti. Prava zaštita je prijava/registracija na samom serveru.
