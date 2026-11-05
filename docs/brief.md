# TeraCanvas – brief prototypu

Źródło: karta pomysłu „TeraCanvas – Karta pomysłu” (brain dump).

**Pliki źródłowe dla agenta:**
- `docs/workflow-analiza-mysli.md`: treść 10 etapów (instrukcje dla pacjenta, wskazówki dla terapeuty, komponenty), role i układ obu widoków. Korzystaj z tych treści zamiast generować własne.
- `TeraCanvas Oddech.html`: wzorzec wyglądu, animacji, postaci-przewodnika i modułu oddechowego dla całej aplikacji.
## 1. Problem

Podczas sesji online psychoterapeuta chciał pokazać pacjentowi na udostępnionym ekranie tabelkę myśli automatycznych (ćwiczenie z nurtu CBT), ale nie mógł otworzyć pliku PDF albo nie mógł znaleźć w komunikatorze funkcji udostępniania ekranu.
Tło z karty: nawet gdy udostępnianie działa, wspólne wypełnianie tabelki online jest niewygodne, bo pacjent patrzy na cudzy ekran i dyktuje odpowiedzi, a sucha tabelka nie angażuje go emocjonalnie.

## 2. Użytkownik

Dwie role w jednym pokoju sesji:

- **Psychoterapeuta** pracujący online, głównie w nurcie CBT. Prowadzi ćwiczenie. Sięga po aplikację w trakcie konsultacji, gdy chce przejść z pacjentem ćwiczenie. Pracuje na laptopie lub PC, aplikacja zajmuje ok. połowę ekranu obok okna wideo (Zoom, Teams, Google Meet). Główna użytkowniczka i ekspertka merytoryczna: żona autora.
- **Pacjent**, od nastolatka do dorosłego, z podstawową znajomością technologii. Wchodzi, klikając link wklejony przez terapeutę na czacie komunikatora. Nie zakłada konta i niczego nie konfiguruje. Głównie laptop/PC (połowa ekranu), czasem telefon (pełny ekran).

## 3. Wartość

Zamiast wypełniać tabelkę, pacjent przeżywa ćwiczenie jak imersyjną podróż przez krajobraz, a terapeuta prowadzi go krok po kroku w czasie rzeczywistym. Dla terapeuty znika udostępnianie arkusza i dyktowanie odpowiedzi: obie strony wpisują treść w tym samym pokoju sesji. Dla pacjenta ćwiczenie to sceny, pogoda reagująca na emocje i myśli jako obiekty, a nie pola formularza.

Aplikacja działa obok komunikatora wideo i go nie zastępuje.

## 4. Zakres

Prototyp: jeden plik HTML, bez serwera, bazy danych i logowania, na danych fikcyjnych. Synchronizację symulujemy przełącznikiem ról (Terapeuta / Pacjent): przy szerokości ok. 800 px widoczny jest jeden widok naraz, a treść wpisana w jednym widoku od razu pojawia się w drugim. Widoki obok siebie pokazujemy tylko na szerokim ekranie (od ok. 1600 px), jako podgląd dla moderatora testu.

**Ścieżka prototypu (ćwiczenie „Analiza myśli”):**

1. **Pokój sesji.** Terapeuta jednym kliknięciem tworzy pokój i link. Pacjent wchodzi bez konta.
2. **Podróż, 10 etapów, każdy jako scena krajobrazu:** wprowadzenie; sytuacja; myśli automatyczne; gorąca myśl; emocje i reakcje z nasileniem 0–100; argumenty potwierdzające; argumenty podważające; myśli alternatywne; emocje po uwzględnieniu argumentów (porównanie przed/po); podsumowanie.
3. **Sterowanie terapeuty:** Dalej, Wstecz, Pomiń, Pauza, Zakończ. Terapeuta ma panel ze wskazówkami prowadzenia, którego pacjent nie widzi. Obie strony mogą wpisywać treść.
4. **Przerywnik oddechowy** (rytm 4–2–6, skala napięcia przed/po), który terapeuta wpina w dowolnym momencie podróży.
5. *(opcjonalnie)* **Podsumowanie-pocztówka:** zmiana emocji przed/po jako karta wizualna i eksport PDF w przeglądarce.

**Wygląd i odczucie** (wzorzec: artefakt *TeraCanvas Oddech*):

- Spokojny „żywy krajobraz o zmierzchu”. Ruch uspokaja, nie rozprasza.
- Pogoda emocji: niskie nasilenie to bezchmurnie i świetliki, wyższe to mgła i chmury, najwyższe to deszcz.
- Postać-przewodnik: świetlista, organiczna istota, która oddycha, mruga i płynie między scenami.
- Myśli jako karty lub bańki, które pacjent dodaje, wybiera (gorąca myśl) i porównuje.
- Przejścia: tekst rozmywa się i wypływa.
- Kolory: noc `#0e1b1f` (tło), mgła `#e8f0ec` (tekst), żar `#f2d3a0` (akcent, fokus), szkło `rgba(12,24,28,.55)` z rozmyciem tła.
- Typografia: *Spectral* (głos przewodnika), *Figtree* (interfejs). Przyciski jako „pigułki”, szklane karty z zaokrąglonymi rogami.
- Dźwięk: opcjonalny ambient, jeden przycisk.
- Tryb spokojny: wycisza ruch i rozmycia, włącza się sam przy systemowym „ogranicz ruch”.
- Układ działa od ok. 800 px szerokości i skaluje się do pełnego ekranu telefonu.

**Poza prototypem:**

- własne wideo i audio (rozmowa zostaje w Zoom, Teams, Google Meet),
- interfejs w stylu formularza,
- konta pacjentów i historia sesji,
- inne ćwiczenia z biblioteki,
- AI oceniające odpowiedzi lub podpowiadające interpretacje oraz automatyczne alarmy,
- deploy na produkcję i serwer,
- prawdziwa synchronizacja w czasie rzeczywistym między dwiema przeglądarkami.

## 5. Co testujemy

**Założenie o użyteczności:** terapeutka (żona autora) przeprowadzi etap „Myśli automatyczne” sama, bez pomocy.
**Nie potwierdziło się, gdy:** terapeutka podczas użytkowania prototypu poprosi o pomoc na którymkolwiek etapie.

**Założenie o użyteczności (pacjent):** pacjent bez instrukcji zrozumie, jak dodać myśl jako kartę w etapie „Myśli automatyczne” i jak wybrać gorącą myśl w etapie „Gorąca myśl”.
**Nie potwierdziło się, gdy:** pacjent zapyta, co ma zrobić, albo nie doda myśli lub nie wybierze gorącej myśli, zanim terapeuta mu to wytłumaczy.

**Założenie o technologii:** scena etapu (krajobraz, pogoda, przewodnik, karty myśli) działa płynnie i czytelnie w jednym pliku HTML przy szerokości ok. 800 px, czyli na połowie ekranu obok okna wideo.
**Nie potwierdziło się, gdy:** na scenie etapu przy szerokości ok. 800 px pojawią się zacięcia animacji, nieczytelny tekst albo elementy wychodzące poza ekran.

## Kryterium gotowości briefu (z karty)

Brief jest dobry, jeśli agent opisze główny ekran (scenę etapu w widoku pacjenta i terapeuty, na przykładzie „Myśli automatyczne”) bez zgadywania.
