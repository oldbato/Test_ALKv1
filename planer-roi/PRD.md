# PRD — Planer budżetu i ROI

## Cel
Aplikacja szkolna ALK do podziału rocznego budżetu marketingowego i obliczania oczekiwanego zysku oraz ROI.

## Funkcje
- Budżet roczny w PLN.
- Kategorie początkowe: Social media, WWW / SEO, Radio, Inne.
- Dodawanie, usuwanie i zmiana nazw kategorii.
- Dla każdej kategorii: udział budżetu (%) i oczekiwany ROI (%).
- Wyniki na żywo: inwestycja, zysk netto oraz nakłady + zysk.
- Podsumowanie: przydzielony budżet, suma zysku, cały budżet + zysk i ROI całego rocznego budżetu.
- Wizualizacja podziału oraz eksport CSV.

## Obliczenia
Dla budżetu B, udziału u i ROI r:
- Inwestycja = B × u / 100.
- Zysk = inwestycja × r / 100.
- Nakłady + zysk kategorii = inwestycja + zysk.
- ROI rocznego budżetu = suma zysków / B × 100.
- Kwota całego planu = B + suma zysków, w tym niewydane środki.

ROI 20% oznacza 20 zł zysku netto na 100 zł inwestycji. ROI nie jest sumowany bez ważenia udziałami. Nieprzydzielone środki mają ROI 0%.

## Walidacja
- Budżet: skończona liczba ≥ 0.
- Udział kategorii: 0–100%.
- ROI kategorii: skończona liczba ≥ −100%.
- Suma udziałów > 100%: komunikat błędu, brak wyników całości i zablokowany CSV.
- Suma < 100%: pokazanie niewydanej kwoty.
- Budżet 0: ROI całości wyświetlany jako „—”.

## Kryteria akceptacji
1. 100 000 zł; 50% przy ROI 20%, 50% przy ROI 40% → zysk 30 000 zł, kwota 130 000 zł, ROI 30%.
2. 100 000 zł; 50% przy ROI 20% → zysk 10 000 zł, niewydane 50 000 zł, kwota 110 000 zł, ROI całości 10%.
3. 100 000 zł; 100% przy ROI −100% → strata 100 000 zł, kwota 0 zł, ROI −100%.
4. Zmiana pól aktualizuje wyniki bez przeładowania.
5. Dodawanie i usuwanie kategorii aktualizuje podsumowanie.

## Technologia i ograniczenia
Samodzielny HTML z CSS i JavaScript, bez zależności, backendu i instalacji. Dane przetwarzane lokalnie; odświeżenie przywraca przykład. Brak logowania i trwałego zapisu. Wynik jest prognozą z danych użytkownika. Testy obliczeń i składni JS wykonano; pełna weryfikacja wizualna przeglądarki pozostaje do wykonania.
