# TeraCanvas – Karta pomysłu

Nov 5, 2026 · @Paweł Ossowski · AIDEAS Vibe Coding

## 1. Pomysł w jednym zdaniu

TeraCanvas pomaga psychoterapeutom i ich pacjentom wspólnie przechodzić ćwiczenia terapeutyczne podczas konsultacji online, żeby zamiast wypełniać tabelkę pacjent przeżył ćwiczenie jak imersyjną podróż, którą terapeuta prowadzi krok po kroku w czasie rzeczywistym.

- Aplikacja działa w przeglądarce **obok** komunikatora wideo (Zoom, Teams, Google Meet), nie zastępuje go.
- Pierwsze ćwiczenie: **Analiza myśli automatycznych** (rozbudowana tabela myśli z nurtu CBT).
- Docelowo: biblioteka ćwiczeń w tej samej konwencji.

## 2. Kto jest użytkownikiem?

Aplikacja ma dwie role, które pracują w tym samym pokoju sesji: terapeutę, który prowadzi, i pacjenta, który przechodzi ćwiczenie.

|  | Psychoterapeuta | Pacjent |
| --- | --- | --- |
| Kto to jest | Psychoterapeuta pracujący online, głównie w nurcie CBT. Główna użytkowniczka i ekspertka merytoryczna: Moja żona | Od nastolatków do dorosłych, z podstawową znajomością technologii (sama konsultacja online jej wymaga) |
| Moment, w którym przychodzi | W trakcie konsultacji online, gdy chce przejść z pacjentem ćwiczenie | Klika link wklejony przez terapeutę na czacie komunikatora |
| Urządzenie | Laptop/PC, aplikacja na ok. połowie ekranu obok okna wideo | Głównie laptop/PC (połowa ekranu); czasem telefon, wtedy aplikacja na pełnym ekranie |
| Jaki ma problem | Online trudno wspólnie wypełniać tabelkę, a udostępniony ekran z arkuszem jest niewygodny | Sucha tabelka nie działa na wyobraźnię i nie angażuje emocjonalnie |
| Co robi dziś | Stacjonarnie: papierowy arkusz wypełniany razem. Online: arkusz udostępniony na ekranie | Patrzy na cudzy ekran i dyktuje odpowiedzi |

**Zasada prostoty:** pacjent nie zakłada konta i nie konfiguruje niczego. Jeden klik w link i jest w sesji, tak jak w ćwiczeniu oddechowym.

## 3. Kluczowe funkcje

Sercem aplikacji jest imersyjna podróż przez Analizę myśli; pokój sesji i oddech ją obsługują.

1. **Imersyjna podróż „Analiza myśli” (serce aplikacji).** 10 etapów (0–9) z dokumentu *TeraCanvas – Analiza myśli: workflow do weryfikacji*, skonsultowanego z Moniką. Każdy etap to kolejna scena krajobrazu, a nie pole formularza. Pogoda reaguje na nasilenie emocji, przewodnik prowadzi pacjenta, myśli są obiektami, które można wybrać i porównać.
   1. Wprowadzenie
   2. Sytuacja
   3. Myśli automatyczne
   4. Gorąca myśl
   5. Emocje i reakcje oraz ich nasilenie (0–100)
   6. Argumenty potwierdzające
   7. Argumenty podważające
   8. Myśli alternatywne
   9. Emocje po uwzględnieniu argumentów (porównanie przed/po)
   10. Podsumowanie
2. **Wspólny pokój sesji.** Terapeuta jednym klikiem tworzy pokój i link, pacjent wchodzi bez konta. Terapeuta steruje tempem (Dalej, Wstecz, Pomiń, Pauza, Zakończ) i widzi panel ze wskazówkami prowadzenia, którego pacjent nie widzi. Obie strony mogą wpisywać treść.
3. **Przerywnik oddechowy.** Gotowy moduł z artefaktu *TeraCanvas Oddech* (rytm 4–2–6, skala napięcia przed/po), który terapeuta wpina w dowolnym momencie podróży.
4. *(opcjonalnie)* **Podsumowanie-pocztówka.** Zmiana emocji przed i po w formie wizualnej karty oraz eksport PDF generowany w przeglądarce.

**Czego świadomie NIE robię w prototypie:**

- własnego wideo i audio, bo rozmowa zostaje w Zoom, Teams lub Google Meet,
- interfejsu w stylu formularza,
- kont pacjentów i historii sesji,
- innych ćwiczeń z biblioteki (to kierunek rozwoju),
- AI oceniającego odpowiedzi lub podpowiadającego interpretacje ani automatycznych alarmów,
- deployu na produkcję i serwera.

**Prototyp vs wersja docelowa:** w prototypie synchronizację symulujemy, czyli widok terapeuty i pacjenta pokazujemy obok siebie albo przez przełącznik ról. Docelowo oba widoki działają w czasie rzeczywistym w dwóch przeglądarkach.

## 4. Jak to ma wyglądać i „czuć się”?

Imersja i doświadczenie są najważniejsze: pacjent ma czuć, że bierze udział w podróży, a nie wypełnia formularz. Wzorcem stylu dla całej aplikacji jest artefakt *TeraCanvas Oddech*.

- **Charakter:** spokojny, nowoczesny, „żywy krajobraz o zmierzchu”. Ruch ma uspokajać, a nie rozpraszać.
- **Metafora:** podróż przez krajobraz. Każdy etap to kolejne miejsce na ścieżce (np. mgła przy sytuacji, rozwidlenie przy argumentach, przejaśnienie przy myśli alternatywnej), a kamera płynnie przechodzi między scenami.
- **Pogoda emocji:** niebo reaguje na nasilenie emocji. Przy niskim jest bezchmurnie i ze świetlikami, przy wyższym pojawia się mgła i chmury, przy najwyższym deszcz.
- **Postać-przewodnik:** świetlista, organiczna istota, która oddycha, mruga, zamyka oczy przy oddechu i płynie między scenami.
- **Myśli jako obiekty:** karty lub bańki, które pacjent dodaje, wybiera (gorąca myśl) i porównuje.
- **Przejścia:** tekst rozmywa się i wypływa zamiast przeskakiwać, interfejs delikatnie „oddycha”.
- **Kolory:** noc `#0e1b1f` (tło), mgła `#e8f0ec` (tekst), żar `#f2d3a0` (akcent, fokus), szkło `rgba(12,24,28,.55)` z rozmyciem tła (karty, przyciski).
- **Typografia:** *Spectral* jako głos przewodnika (pytania, instrukcje), *Figtree* jako interfejs.
- **Kształty:** przyciski w formie „pigułek”, szklane karty z zaokrąglonymi rogami, dużo powietrza.
- **Dźwięk:** opcjonalny ambient do włączenia jednym przyciskiem.
- **Tryb spokojny:** wycisza ruch i rozmycia; włącza się sam przy systemowym ustawieniu „ogranicz ruch”.
- **Układ:** działa od ok. 800 px szerokości, czyli na połowie ekranu laptopa obok okna wideo, i skaluje się do pełnego ekranu telefonu.

## 5. Test końcowy – brief dla agenta

Karta jest gotowa, jeśli agent opisze główny ekran (scenę etapu w widoku pacjenta i terapeuty) bez zgadywania.

**Prompt dla agenta:** „Oto opis mojej aplikacji: \[wklej sekcje 1–4\]. Opisz mi słowami, jak wyglądałby jej główny ekran w widoku pacjenta i w widoku terapeuty na przykładzie etapu ‘Myśli automatyczne’. Jeśli czegoś ci brakuje do zbudowania prototypu, dopytaj.”

**Następny krok:** na podstawie tej karty budujemy brief zgodnie z promptem systemowym kursu (M1-01), a potem klikalny prototyp HTML (M1-02).
