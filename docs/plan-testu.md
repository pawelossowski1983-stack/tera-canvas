# TeraCanvas – plan testu prototypu

Prototyp: `prototyp/index.html` (otwórz dwukrotnym kliknięciem). Mapa ekranów i scenariuszy dla moderatora: dopisz `#mapa` na końcu adresu.

## Założenia i jak je sprawdzamy

| Założenie | Scenariusz lub ekran | Potwierdzenie | Nie potwierdziło się, gdy |
| --- | --- | --- | --- |
| Terapeutka przeprowadzi etap „Myśli automatyczne” sama, bez pomocy (brief) | Scenariusz A | Dochodzi do etapu „Gorąca myśl” i nie prosi o pomoc | Poprosi o pomoc na którymkolwiek etapie |
| Pacjent bez instrukcji doda myśl jako kartę i wybierze gorącą myśl (brief) | Scenariusz B | Dodaje myśli i wybiera jedną, zanim ktokolwiek mu to wytłumaczy | Zapyta, co ma zrobić, albo nie doda myśli lub nie wybierze gorącej myśli, zanim terapeuta mu to wytłumaczy |
| Scena działa płynnie i czytelnie w jednym pliku HTML przy ok. 800 px, obok okna wideo (brief) | Wszystkie etapy przy oknie ok. 800 px. Licznik klatek jest na `#mapa` | Ruch jest płynny, tekst czytelny, nic nie wychodzi poza ekran | Pojawią się zacięcia animacji, nieczytelny tekst albo elementy wychodzące poza ekran |
| Terapeutka bez podpowiedzi znajdzie panel wskazówek, Pauzę i Oddech (propozycja) | Scenariusze A i C | Używa ich sama, gdy zadanie tego wymaga | Szuka ich dłużej niż chwilę albo pyta, gdzie są |

## Zadania dla testera

**Scenariusz A: tester to terapeutka.** Moderator wchodzi na `#mapa` i uruchamia scenariusz A.

1. „Jesteś w trakcie konsultacji online i chcesz przejść z pacjentem analizę myśli. Zaproś go do ćwiczenia.”
2. „Pacjent jest już z Tobą. Rozpocznij i poprowadź go do momentu, w którym wybieracie jedną myśl do dalszej pracy.”
3. „Sprawdź, co warto zapytać pacjenta na tym etapie.”

Moderator gra pacjenta i podaje na głos treść: sytuację i dwie, trzy myśli.

**Scenariusz B: tester to pacjent.** Moderator uruchamia scenariusz B z `#mapa` i przekazuje testerowi ekran.

1. „Terapeuta przysłał Ci link. Właśnie go kliknąłeś. Wejdź na spotkanie.”
2. „Przypomnij sobie niedawną, drobną sytuację, która Cię zdenerwowała (albo wymyśl ją). Rób to, o co prosi aplikacja.”

Moderator przechodzi etapy skrótem: `Ctrl+Shift+→` dalej, `Ctrl+Shift+←` wstecz. Nie tłumaczy, co tester ma zrobić.

**Scenariusz C: tester to terapeutka.** Moderator uruchamia scenariusz C z `#mapa`. Ładuje się przykładowa sytuacja.

1. „Pacjent ocenia, jak silne były jego emocje. Przejdź z nim przez resztę ćwiczenia, aż do podsumowania.”
2. „W połowie pacjent mówi, że jest mu ciężko i potrzebuje chwili. Zareaguj tak, jak zrobiłabyś na sesji.”
3. „Pokaż pacjentowi, co się zmieniło, i zakończ sesję.”

## Pytania po teście

1. Co było od razu zrozumiałe, a co musiałeś lub musiałaś rozgryzać?
2. Co Cię zaskoczyło? Czy coś w ruchu, pogodzie lub przewodniku przeszkadzało albo rozpraszało?
3. Czy to było bardziej jak podróż, czy jak wypełnianie formularza? Po czym to poznajesz?
4. Czego zabrakło?
5. Czy skorzystałbyś lub skorzystałabyś z takiej aplikacji? W jakiej sytuacji?

## Jak prowadzić test

- Przed każdym testerem odśwież stronę. To resetuje wszystkie dane.
- Nie podpowiadaj. Obserwuj i notuj, gdzie tester się zawahał.
- Uwagi o treściach przykładowych (emocje, pytania pomocnicze, zniekształcenia, przykładowa sytuacja) notuj osobno od uwag o obsłudze aplikacji.
- Test techniczny przeprowadź na laptopie, na którym prototyp będzie używany, z oknem zajmującym połowę ekranu i z oknem wideo obok. Odczytaj licznik klatek z `#mapa`.
- To test prototypu, nie terapia. Testerzy pracują na fikcyjnej lub drobnej sytuacji i niczego osobistego nie muszą ujawniać.

## Poza zakresem prototypu

- Własne wideo i audio (rozmowa zostaje w komunikatorze).
- Interfejs w stylu formularza.
- Konta pacjentów i historia sesji.
- Inne ćwiczenia z biblioteki (przycisk „Inne ćwiczenia” pokazuje tylko komunikat).
- AI oceniające odpowiedzi lub podpowiadające interpretacje oraz automatyczne alarmy.
- Deploy na produkcję i serwer.
- Prawdziwa synchronizacja między dwiema przeglądarkami (w prototypie symuluje ją przełącznik ról).
