# Kompleksowa lista kontrolna audytu strony internetowej (Web Audit Checklist)

> Opracowana na podstawie wiodących światowych standardów i systemów projektowania: **Google Material Design 3 (M3)**, **W3C WCAG 2.2**, **Google Core Web Vitals**, **Nielsen Norman Group (NN/g)**, **Google Search Central** oraz **OWASP**.

---

## 📌 Jak korzystać z listy kontrolnej
- Oznaczaj zweryfikowane punkty jako `[x]`.
- Korzystaj z rekomendowanych narzędzi badawczych w każdej sekcji.
- W przypadku szybkiego audytu skup się na punktach oznaczonych jako 🔴 **[Krytyczny]**.

---

## 1. System projektowania i UI (Google Material Design 3)

| Status | Kryterium | Źródło / Wymaganie | Opis |
| :---: | :--- | :--- | :--- |
| [ ] | **Siatka adaptacyjna (Responsive Grid & Breakpoints)** | Google Material 3 | Zastosowano elastyczną siatkę adaptacyjną (4 kolumny na Mobile <600dp, 8 kolumn na Tablet 600–840dp, 12 kolumn na Desktop >840dp). Całkowity brak poziomego paska przewijania na ekranach od 320px wzwyż. |
| [ ] | **Modułowa skala odstępów (Spacing 8dp Grid)** | Google Material 3 | Wszelkie odstępy (padding, margin, gap) bazują na siatce o skoku 4px / 8px (np. 4, 8, 12, 16, 24, 32, 48px), zapewniając spójny rytm wizualny. |
| [ ] | **Skala typograficzna (Type Scale)** | Google Material 3 | Zachowano ścisłą hierarchię stylów: *Display*, *Headline*, *Title*, *Body*, *Label*. Podstawowy tekst czytelny (`Body Large/Medium`) ma rozmiar minimum 16px (1rem). |
| [ ] | **Wysokość linii i długość wiersza (Readability)** | Material Typography | Długość wiersza w blokach tekstowych wynosi od 45 do 75 znaków. Interlinia (line-height) to optymalnie 140–160% rozmiaru fontu. |
| [ ] | **Role kolorów (Color Roles & Dynamic Color)** | Google Material 3 | Kolory są przypisane zgodnie z rolami semantycznymi: *Primary*, *Secondary*, *Tertiary*, *Surface*, *Background*, *Error* oraz ich kontenery parzyste (np. tekst `On-Primary` na tle `Primary`). |
| [ ] | **Elewacja tonalna i powierzchnie (Elevation)** | Google Material 3 | Hierarchia warstw realizowana jest za pomocą elewacji tonalnej (Tonal Elevation) i subtelnych cieni (poziomy 1–5). Okna modalne, menu rozwijane i karty wyraźnie odcinają się od tła. |
| [ ] | **Rozmiar celów dotykowych (Touch Targets)** 🔴 | Google Material 3 | Minimalny rozmiar elementów interaktywnych (przyciski, linki, ikony, checkboxy) wynosi **48×48 dp/px**. Odstęp między sąsiednimi celami to minimum 8px. |
| [ ] | **Stany interaktywne elementów (Interactive States)** | Google Material 3 | Wszystkie elementy klikalne posiadają czytelne stany: *Default*, *Hover*, *Focus* (pierścień fokusu), *Pressed/Active* (efekt Ripple lub przyciemnienie), *Disabled*. |
| [ ] | **Celowa animacja i przejścia (Motion & Easing)** | Google Material 3 | Czas trwania mikrointerakcji mieści się w granicach 150–400 ms. Zastosowano naturalne krzywe akceleracji (easing: standard, emphasized). Animacje nie opóźniają pracy użytkownika. |
| [ ] | **Obsługa trybu ciemnego (Dark Theme)** | Google Material 3 | Kolory w trybie ciemnym nie są przejaskrawione; tło bazowe to zrównoważony ciemny odcień szarości/grafitu zamiast czystej czerni `#000` (z wyjątkiem trybów pure-OLED). Zachowano czytelny kontrast. |

🛠 **Narzędzia:** [Material Theme Builder](https://material-foundation.github.io/material-theme-builder/), Narzędzia deweloperskie Chrome DevTools (Device Toolbar).

---

## 2. Dostępność cyfrowa (W3C WCAG 2.1 / 2.2 AA)

| Status | Kryterium | Źródło / Kryterium sukcesu | Opis |
| :---: | :--- | :--- | :--- |
| [ ] | **Kontrast tekstu podstawowego** 🔴 | WCAG 2.2 (1.4.3) | Minimalny współczynnik kontrastu tekstu względem tła wynosi: **4.5:1** dla tekstu standardowego, **3:1** dla tekstu dużego (od 24px lub pogrubionego od 18.5px). |
| [ ] | **Kontrast elementów interfejsu** | WCAG 2.2 (1.4.11) | Obramowania aktywnych pól formularza, ikony i kontury przycisków posiadają kontrast minimum **3:1** względem przyległego tła. |
| [ ] | **Nawigacja z samej klawiatury (Keyboard-Only)** 🔴 | WCAG 2.2 (2.1.1) | Wszystkie funkcjonalności i interakcje są w pełni obsługiwane bez użycia myszy (klawisze `Tab`, `Shift+Tab`, `Enter`, `Spacja`, `Esc`, strzałki). |
| [ ] | **Widoczny wskaźnik fokusu (Focus Visible)** 🔴 | WCAG 2.2 (2.4.7) | Aktywny element nawigowany tabulatorem posiada wyraźną, kontrastową obwódkę (własność `outline: none` nie została użyta bez alternatywnego stylu). |
| [ ] | **Brak pułapek klawiaturowych (No Keyboard Traps)** | WCAG 2.2 (2.1.2) | Fokus klawiatury nie blokuje się wewnątrz okien modalnych, karuzel ani menu. Naciśnięcie klawisza `Esc` zamyka warstwy nakładkowe. |
| [ ] | **Łącze pomijania treści (Skip to Content)** | WCAG 2.2 (2.4.1) | Na samym początku kodu strony znajduje się ukryte łącze „Przejdź do treści głównej”, widoczne po pierwszym naciśnięciu Tab, omijające nagłówek. |
| [ ] | **Tekst alternatywny dla obrazów (Alt Text)** 🔴 | WCAG 2.2 (1.1.1) | Wszystkie obrazy niosące treść posiadają precyzyjny atrybut `alt="..."`. Elementy czysto dekoracyjne posiadają pusty `alt=""` lub `aria-hidden="true"`. |
| [ ] | **Powiązane etykiety formularzy (<label>)** 🔴 | WCAG 2.2 (3.3.2) | Każde pole `<input>`, `<select>`, `<textarea>` posiada powiązany znacznik `<label for="id">`. Sam placeholder nie może zastępować etykiety! |
| [ ] | **Niepoleganie wyłącznie na kolorze** | WCAG 2.2 (1.4.1) | Błędy walidacji, linki w tekście oraz statusy są komunikowane nie tylko kolorem, ale również ikoną, podkreśleniem lub opisem tekstowym. |
| [ ] | **Respektowanie prefers-reduced-motion** | WCAG 2.2 (2.3.3) | Obsłużono zapytanie mediów `@media (prefers-reduced-motion: reduce)`, wyłączające intensywne animacje, efekty paralaksy i autoodtwarzanie wideo. |

🛠 **Narzędzia:** [WAVE Evaluation Tool](https://wave.webaim.org/), [axe DevTools](https://www.deque.com/axe/devtools/), WebAIM Contrast Checker, Czytniki ekranu (NVDA na Windows, VoiceOver na macOS/iOS).

---

## 3. Wydajność i szybkość ładowania (Google Core Web Vitals)

| Status | Kryterium | Źródło / Próg | Opis |
| :---: | :--- | :--- | :--- |
| [ ] | **LCP (Largest Contentful Paint)** 🔴 | Google Web Vitals (<= 2.5s) | Czas renderowania największego widocznego elementu treści (główny baner, nagłówek H1). Cel: **poniżej 2.5 sekundy** na łączu mobilnym 4G. |
| [ ] | **INP (Interaction to Next Paint)** 🔴 | Google Web Vitals (<= 200ms) | Czas reakcji interfejsu na kliknięcie, dotknięcie lub wpisanie tekstu. Cel: **poniżej 200 ms** bez blokowania głównego wątku JavaScript. |
| [ ] | **CLS (Cumulative Layout Shift)** 🔴 | Google Web Vitals (<= 0.1) | Wskaźnik stabilności wizualnej (brak niespodziewanych przesunięć treści podczas doczytywania). Cel: **wartość poniżej 0.1**. |
| [ ] | **Wymiary elementów mediów (Width/Height)** | Google Best Practices | Wszystkie znaczniki `<img>`, `<video>` i `<iframe>` mają jawnie zdefiniowane atrybuty `width` i `height` lub styl CSS `aspect-ratio`, rezerwujący miejsce w układzie. |
| [ ] | **Nowoczesne formaty obrazów** | Google Lighthouse | Grafiki są zoptymalizowane pod kątem wagi i serwowane w formatach **WebP** lub **AVIF** zamiast ciężkich plików PNG/JPEG. |
| [ ] | **Odłożone ładowanie grafik (Lazy Loading)** | Google Lighthouse | Obrazy znajdujące się poniżej pierwszego ekranu posiadają atrybut `loading="lazy"`. Kluczowy obraz LCP ładuje się priorytetowo (`fetchpriority="high"`). |
| [ ] | **Optymalizacja fontów (font-display: swap)** | Google Lighthouse | Skonfigurowano `font-display: swap`, aby wyeliminować efekt niewidocznego tekstu (FOIT). Fonty krytyczne są wstępnie załadowane (`<link rel="preload">`). |
| [ ] | **Minifikacja i nagłówki pamięci podręcznej** | Google Lighthouse | Pliki CSS i JS są zminifikowane i oczyszczone z nieużywanego kodu. Skonfigurowano wydajne nagłówki `Cache-Control`. |

🛠 **Narzędzia:** [Google PageSpeed Insights](https://pagespeed.web.dev/), Chrome DevTools (Panele Lighthouse i Performance), WebPageTest.

---

## 4. Użyteczność i wzorce UX (Nielsen Norman Group - NN/g)

| Status | Kryterium | Heurystyka NN/g | Opis |
| :---: | :--- | :--- | :--- |
| [ ] | **Widoczność stanu systemu** | Heurystyka #1 | Podczas przetwarzania danych (wysyłka formularza, pobieranie zawartości) widoczny jest wskaźnik ładowania, spinner lub szkielet treści (Skeleton Screen). |
| [ ] | **Zgodność z realnym światem** | Heurystyka #2 | Zastosowano powszechnie zrozumiałą terminologię oraz standardowe ikony (lupa = wyszukiwanie, koszyk = zakupy, koło zębate = ustawienia). |
| [ ] | **Kontrola i wolność użytkownika** 🔴 | Heurystyka #3 | Możliwość natychmiastowego cofnięcia pomyłki. Przycisk „Wróć”, widoczny krzyżyk zamykający modal, możliwość zamknięcia okna klawiszem `Esc` lub kliknięciem w tło. |
| [ ] | **Spójność i standardy** | Heurystyka #4 | Identyczne elementy wyglądają i zachowują się tak samo w obrębie całego serwisu (jednolity wygląd przycisków, odstępów i linków). |
| [ ] | **Zapobieganie błędom** | Heurystyka #5 | Walidacja pól formularza w czasie rzeczywistym (inline validation). Pytania potwierdzające przed usunięciem kluczowych danych. |
| [ ] | **Rozpoznawanie zamiast przypominania** | Heurystyka #6 | Obecność ścieżki okruszkowej (Breadcrumbs), wyróżnienie aktywnej zakładki w menu oraz jasne podpowiedzi w złożonych polach. |
| [ ] | **Zrozumiałe komunikaty o błędach** 🔴 | Heurystyka #9 | Komunikaty o błędach sformułowane prostym językiem bez technicznego żargonu (zamiast „Błąd 500” informacja: „Nie udało się wysłać wiadomości, spróbuj ponownie za chwilę”). |

🛠 **Narzędzia:** Testy korytarzowe z użytkownikami, mapy ciepła i nagrania sesji (Hotjar, Microsoft Clarity).

---

## 5. SEO i semantyka kodu (Google Search Central & W3C)

| Status | Kryterium | Źródło | Opis |
| :---: | :--- | :--- | :--- |
| [ ] | **Pojedynczy nagłówek H1** 🔴 | Google Search Central | Na stronie znajduje się **dokładnie jeden znacznik `<h1>`**, definiujący główny temat podstrony. |
| [ ] | **Hierarchia nagłówków H2–H6** | W3C Semantic HTML | Nagłówki tworzą logiczne drzewo struktury treści (brak przeskoków np. z `h1` bezpośrednio do `h4`). Nie są używane wyłącznie do powiększenia tekstu. |
| [ ] | **Semantyczne znaczniki HTML5** | Standard W3C | Zamiast zagnieżdżonych `<div>` zastosowano znaczniki strukturalne: `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>`. |
| [ ] | **Tagi Title i Description** 🔴 | Google Search Central | Unikalny `<title>` (optymalnie do 60–70 znaków) oraz unikalny, zachęcający `<meta name="description">` (130–160 znaków). |
| [ ] | **Znacznik meta Viewport** 🔴 | Mobile-Friendly Indexing | W sekcji `<head>` zdefiniowano: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`. |
| [ ] | **Adres kanoniczny (Canonical URL)** | Google Search Central | Skonfigurowano znacznik `<link rel="canonical" href="...">` eliminujący problem duplikacji treści (duplicate content). |
| [ ] | **Karty Open Graph i Twitter** | Social Sharing | Zdefiniowano tagi `og:title`, `og:description`, `og:image`, `og:url` generujące estetyczny podgląd przy udostępnianiu linku na komunikatorach i w mediach społecznościowych. |
| [ ] | **Komplet favikonów i manifest** | Web Standards | Dodano pliki `favicon.ico`, `favicon.svg`, `apple-touch-icon.png` oraz `manifest.json`. |
| [ ] | **Dedykowana strona błędu 404** | Google Search Central | Nieistniejące adresy URL zwracają właściwy kod odpowiedzi HTTP `404 Not Found` oraz prezentują użyteczną stronę z linkiem powrotnym na stronę główną. |

🛠 **Narzędzia:** [Walidator W3C HTML](https://validator.w3.org/), Google Search Console, Test wyników z elementami rozszerzonymi (Rich Results Test), OpenGraph.xyz.

---

## 6. Responsywność i doświadczenie mobilne (Mobile-First)

| Status | Kryterium | Źródło | Opis |
| :---: | :--- | :--- | :--- |
| [ ] | **Brak przewijania poziomego (320–430px)** 🔴 | Mobile-First | Żadne tabele, duże grafiki ani kontenery o stałej szerokości nie rozpychają widoku i nie generują poziomego paska przewijania na smartfonach. |
| [ ] | **Rozmiar fontu w polach formularza na iOS** 🔴 | Apple iOS WebKit | Rozmiar fontu w polach `<input>` wynosi minimum **16px**, dzięki czemu przeglądarka Safari na iPhone nie wymusza automatycznego przybliżenia (zoomu). |
| [ ] | **Ergonomia strefy kciuka (Thumb Zone)** | Mobile UX Best Practice | Główne przyciski akcji (Call to Action) oraz dolne paski nawigacji znajdują się w strefie wygodnego dosięgnięcia kciukiem jednej dłoni. |
| [ ] | **Bezpieczne strefy ekranu (Safe Areas)** | iOS / Android Notches | Uwzględniono wcięcia w ekranie i wirtualne paski gestów poprzez zmienne CSS: `env(safe-area-inset-top)` oraz `env(safe-area-inset-bottom)`. |
| [ ] | **Właściwe typy klawiatur wirtualnych** | Mobile UX | Pola posiadają odpowiednie atrybuty: `type="tel"` dla telefonu, `type="email"`, `inputmode="numeric"` dla kwot, wywołujące dopasowaną klawiaturę numeryczną. |
| [ ] | **Zgodność międzyprzeglądarkowa** | Web Standards | Układ i funkcje przetestowano w przeglądarkach Google Chrome, Apple Safari (iOS/macOS), Mozilla Firefox oraz Microsoft Edge. |

🛠 **Narzędzia:** Chrome DevTools Device Mode, BrowserStack, testy na fizycznych urządzeniach z systemami iOS i Android.

---

## 7. Bezpieczeństwo i prywatność (OWASP & Privacy)

| Status | Kryterium | Źródło | Opis |
| :---: | :--- | :--- | :--- |
| [ ] | **Protokół HTTPS i certyfikat SSL** 🔴 | OWASP / Google Chrome | Połączenie jest w pełni szyfrowane przez HTTPS z ważnym certyfikatem SSL/TLS. Skonfigurowano automatyczne przekierowanie 301 z `http://` na `https://`. |
| [ ] | **Bezpieczne odnośniki zewnętrzne** | Web Security Standard | Wszystkie łącza otwierane w nowej karcie (`target="_blank"`) posiadają atrybut `rel="noopener noreferrer"`, chroniący przed atakami typu Reverse Tabnabbing. |
| [ ] | **Ochrona formularzy i walidacja** | OWASP Top 10 | Formularze posiadają zabezpieczenie przed spamem (np. Cloudflare Turnstile, reCAPTCHA lub honeypot), a dane są rygorystycznie walidowane po stronie serwera. |
| [ ] | **Polityka prywatności i zgoda na pliki cookies** | RODO / GDPR / ePrivacy | Dostępny jest czytelny link do Polityki Prywatności oraz mechanizm zarządzania zgodami na pliki cookies spełniający wymogi RODO. |

---

## 📊 Tabela priorytetów i rekomendowanej wagi

| Kategoria audytu | Poziom istotności | Główne standardy | Rekomendowany moment weryfikacji |
| :--- | :---: | :--- | :--- |
| **1. UI & System projektowania** | Wysoki | Google Material 3, Apple HIG | Etap projektowania UI oraz wdrażania komponentów |
| **2. Dostępność cyfrowa (A11y)** | 🔴 Krytyczny | W3C WCAG 2.2 AA | Przed każdym wydaniem wersji produkcyjnej |
| **3. Wydajność strony** | 🔴 Krytyczny | Google Core Web Vitals | Ciągły monitoring w Lighthouse i PageSpeed |
| **4. Użyteczność (UX)** | Wysoki | Nielsen Norman Group | Projektowanie ścieżek użytkownika i makiet |
| **5. SEO i semantyka** | Średni | Google Search Central, Schema.org | Przy publikacji szablonów stron |
| **6. Responsywność mobilna** | 🔴 Krytyczny | Mobile-First Indexing | Na każdym etapie kodowania frontendu |
| **7. Bezpieczeństwo danych** | 🔴 Krytyczny | OWASP Web Top 10 | Regularne audyty bezpieczeństwa |
