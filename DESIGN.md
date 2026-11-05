# TeraCanvas – DESIGN.md

Wersja 1 — kierunek przyjęty na etapie prototypu, do dalszego rozwijania

Źródło: kolory i typografia z briefu, komponenty i animacje ze wzorca `docs/wzorzec-oddech.html` (TeraCanvas Oddech).

## Charakter

Spokojny, nowoczesny „żywy krajobraz o zmierzchu”. Jedna pełnoekranowa scena (canvas) z niebem, pogodą emocji i przewodnikiem. Słowa unoszą się w dolnej, wyśrodkowanej kolumnie na szklanych kartach. Ruch uspokaja, nie rozprasza. Jeden wygląd, bez trybu jasnego.

## Kolory

| Rola | Zmienna CSS | Wartość |
| --- | --- | --- |
| Tło (noc) | `--night` | `#0e1b1f` |
| Tekst podstawowy (mgła) | `--mist` | `#e8f0ec` |
| Tekst pomocniczy | `--mist-dim` | `rgba(232,240,236,.7)` |
| Akcent i fokus (żar) | `--ember` | `#f2d3a0` |
| Powierzchnia (szkło) | `--glass` | `rgba(12,24,28,.55)` z `backdrop-filter: blur(8–12px)` |
| Powierzchnia panelu | `--sheet` | `rgba(10,20,23,.92)` |
| Linia, obrys | `--line` | `rgba(232,240,236,.2)` |
| Sukces | `--ok` | `#9fd4b0` |
| Ostrzeżenie | `--warn` | `#f2d3a0` (jak żar) |
| Błąd | `--err` | `#f0a79a` |
| Skala nasilenia | gradient | `#f2d3a0` → `#7f9c97` (50%) → `#4a4f5e` |

Pogoda emocji (nasilenie 0–100): do ok. 30 bezchmurnie i świetliki; 31–65 mgła i chmury; powyżej 65 deszcz.

Kontrast: tekst podstawowy i pomocniczy na `--night` oraz `--night` na `--mist` spełniają WCAG AA. Stany sukcesu, ostrzeżenia i błędu zawsze towarzyszy tekst, nie sam kolor.

## Typografia

- Głos przewodnika (pytania, instrukcje, nagłówki): `--f-voice: "Spectral", Georgia, "Times New Roman", serif`, waga 300–400.
- Interfejs: `--f-ui: "Figtree", "Segoe UI", system-ui, sans-serif`, wagi 400–600.
- Fonty z Google Fonts, zawsze z systemowym zamiennikiem.
- Rozmiary (minimum 16 px dla tekstu):
  - instrukcja przewodnika: `clamp(1.4rem, 4.8vw, 2rem)`, interlinia 1.28;
  - nagłówek karty: 1.3rem;
  - tekst podstawowy i pomocniczy: 1rem (16 px), interlinia 1.55;
  - duża liczba (skala): 2.6rem;
  - etykiety wielkimi literami: 1rem z `letter-spacing: .08em` (we wzorcu były mniejsze, tu powiększone do 16 px).

## Odstępy i kształty

- Skala odstępów: 4, 8, 12, 16, 24, 32, 48 px. Dużo powietrza.
- Promienie: pigułki `999px`, szklane karty `20px`, panele dolne `22px 22px 0 0`.
- Boczne marginesy: minimum 16 px. Kolumna treści do 34rem, panel terapeuty do 20rem.
- Układ działa od ok. 800 px szerokości i skaluje się do telefonu.

## Komponenty

- **Przycisk główny** (`.btn`): pigułka, tło `--mist`, tekst `--night`, waga 600, padding 14×28 px, minimum 44×44 px. Hover unosi o 2 px. Jedna akcja główna na ekranie.
- **Przycisk drugorzędny** (`.btn.ghost`): szkło, obrys `--line`, tekst `--mist`.
- **Pigułka sterująca** (`.pill`): szkło, obrys, minimum 44 px wysokości; stan włączony: tło `--mist`, tekst `--night`.
- **Fokus:** zawsze `2px solid var(--ember)` z odsunięciem 3 px. Disabled: 45% krycia, kursor `not-allowed`.
- **Karta szklana:** `--glass`, obrys `--line`, rozmycie tła, promień 20 px. Służy za kartę myśli, emocji, listę argumentów i pocztówkę.
- **Karta myśli:** bańka lub karta z tekstem; wybrana jako gorąca myśl dostaje obrys `--ember` i poświatę.
- **Pole tekstowe:** szkło, obrys `--line`, tekst `--mist`, fokus jak wyżej, podpowiedź w `--mist-dim`. Błąd: obrys `--err` i komunikat pod polem.
- **Skala 0–100:** suwak z gradientem skali, kciuk 26 px z poświatą żaru, duża liczba nad nim.
- **Pasek postępu:** kropki lub cienka linia w żarze, podpis „Etap 4 z 9”.
- **Przewodnik:** świetlista, organiczna istota na niebie; oddycha, mruga, zamyka oczy przy oddechu i płynie między scenami.
- **Panel terapeuty:** szklany panel boczny (`--sheet`) ze wskazówką, pytaniami pomocniczymi i listą etapów.
- **Stan pusty i ładowanie:** krótki, ciepły tekst („Nie masz jeszcze żadnej myśli.”), ładowanie do 1 sekundy.

## Ruch i dostępność

- Przejścia: scena wygasa z rozmyciem i wypływa (`opacity .8s`, `translateY 16px`, `blur 8px`).
- **Tryb spokojny:** wyłącza ruch i rozmycia (przejścia 0.3 s liniowo, bez przesunięć). Włącza się sam przy `prefers-reduced-motion`.
- Dźwięk: opcjonalny ambient, domyślnie wyłączony, jeden przycisk.
- Elementy klikalne minimum 44×44 px, widoczne stany hover, focus i disabled.

## Ton komunikatów

Ciepły, spokojny, w drugiej osobie, krótkie zdania. Bez ocen („nie ma złych odpowiedzi”). Komunikaty o błędach nie oskarżają („Wpisz choć jedno słowo, żeby przejść dalej.”). Elementy spoza prototypu: „Ta funkcja nie jest częścią prototypu”. Stały dopisek: „Prototyp — dane fikcyjne”.
