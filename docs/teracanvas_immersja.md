# TeraCanvas: immersyjne doświadczenie terapeutyczne

Świetny kierunek dla TeraCanvas, ale z jednym zastrzeżeniem na start: w
kontekście terapeutycznym **immersja ma uspokajać, nie olśniewać**. Ruch
powinien być „oddechem" aplikacji, a nie fajerwerkami. Analogia: to ma
być bardziej spacer po japońskim ogrodzie niż przejażdżka
rollercoasterem w Energylandii 🙂

## Technologie (realne dla solo + vibe coding, pasują do Vercel/Supabase)

-   **Next.js + React** -- baza, świetnie się deployuje na Vercel.
-   **Motion (dawniej Framer Motion)** -- płynne przejścia elementów,
    „morfowanie" kart, gesty. Najłatwiejszy start, AI generuje do niego
    dobry kod.
-   **View Transitions API** -- przejścia między ekranami bez
    „przeładowania"; element z jednego kroku płynnie staje się elementem
    następnego. To klucz do wrażenia „to nie są strony".
-   **Rive** -- interaktywne postaci ze *state machine*: postać reaguje
    na wpisaną emocję, oddycha w rytmie ćwiczenia, kiwa głową. Lepsze od
    Lottie, bo reaguje na dane, a nie tylko odtwarza animację.
-   **GSAP** -- choreografia dłuższych sekwencji (np. „intro" sesji jak
    scena filmowa). Darmowy także komercyjnie.
-   **React Three Fiber (Three.js)** -- opcjonalnie: delikatne 3D tło
    (mgła, światło, cząsteczki). Używaj oszczędnie, ciężkie dla
    słabszych telefonów.
-   **Howler.js / Tone.js** -- ambient i subtelne dźwięki reakcji (np.
    ciche „dzwonienie" po zapisaniu myśli).
-   **Supabase Realtime** -- obecność terapeutki w trybie współpracy
    jako miękkie światło/kursor zamiast „ikonki użytkownika".

## Pomysły na doświadczenia

-   **Jedna ciągła scena zamiast ekranów** -- sesja to „podróż" przez
    krajobraz; kolejne ćwiczenia pojawiają się jak kolejne miejsca na
    ścieżce.
-   **Przewodnik-postać (Rive)** -- abstrakcyjna, ciepła forma (np.
    świetlik, kropla), nie maskotka z kreskówki. Prowadzi, zadaje
    pytania, reaguje mimiką.
-   **Ćwiczenie oddechowe, w którym oddycha cały interfejs** -- tło,
    światło i postać rozszerzają się i kurczą razem.
-   **Zapis myśli (CBT)** -- myśl automatyczna pojawia się jako ciężka,
    ciemna chmura; z każdym kontrargumentem jaśnieje i robi się lżejsza.
-   **Zniekształcenia poznawcze** -- „bańki" z myślami, które klient
    łapie i przypina do kategorii (katastrofizacja, czytanie w
    myślach...).
-   **Skala emocji jako pogoda** -- suwak 0--10 zmienia krajobraz: od
    burzy do słońca. Natychmiastowa, wizualna informacja zwrotna.
-   **Zakończenie jako „pocztówka"** -- podsumowanie sesji w formie
    ładnej grafiki do eksportu (pasuje do Twojego usuwania danych po 24
    h).

## Rzeczy, o których łatwo zapomnieć

-   **`prefers-reduced-motion`** -- obowiązkowo tryb „spokojny" dla osób
    z lękiem, migreną, zaburzeniami przedsionkowymi.
-   **Ruch wolny i miękki** -- długie czasy (400--800 ms), krzywe typu
    ease-out, bez skoków i błysków.
-   **Budżet czasu** -- przy 8 h/tydzień zrób „pełną immersję" w
    **jednym** ćwiczeniu (np. oddech lub zapis myśli), resztę na
    prostszych przejściach Motion.
