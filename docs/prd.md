# Dokument wymagań produktu (PRD) - VibeTravels

## 1. Przegląd produktu

Aplikacja VibeTravels to MVP, które ma za zadanie uprościć planowanie wycieczek poprzez przekształcanie prostych notatek o podróżach w kompleksowe i personalizowane plany wycieczek. Wykorzystanie AI do analizy tekstu i preferencji użytkownika pozwoli na szybkie wygenerowanie planu, który odpowiada na rzeczywiste potrzeby turystyczne. Projekt ma być wdrożony w ciągu 4 tygodni przy udziale jednego programisty TypeScript (Angular, NestJS) i uwzględnia wykorzystanie technologii Supabase.

## 2. Problem użytkownika

Użytkownicy mają chęć odwiedzenia wybranych miejsc, ale nie wiedzą, co warto tam zobaczyć ani jaka jest historia danego miejsca. Ręczne planowanie wymaga dużo czasu i wiedzy, czego efektem są standardowe, często nieatrakcyjne plany wycieczek. Problem komplikuje też brak spersonalizowanych informacji, które uwzględniałyby indywidualne preferencje, liczbę osób czy wiek uczestników. VibeTravels ma rozwiązać ten problem, wykorzystując AI do przekształcenia prostych notatek w szczegółowe i angażujące plany podróży.

## 3. Wymagania funkcjonalne

1. Zarządzanie notatkami

   - Tworzenie notatek dotyczących przyszłych wycieczek
   - Odczytywanie i przeglądanie zapisanych notatek
   - Edycja oraz usuwanie notatek

2. System kont użytkowników

   - Rejestracja i logowanie
   - Weryfikacja tożsamości podczas logowania
   - Bezpieczny dostęp do konta i danych

3. Strona profilu użytkownika

   - Możliwość wypełnienia profilu preferencji turystycznych (m.in. preferowane atrakcje, styl zwiedzania, ulubione tematy)
   - Edycja zapisanych danych

4. Integracja z AI

   - Przekształcanie prostych notatek zawierających: miejsce docelowe, długość wyjazdu, opcjonalny preferowany okres, liczbę uczestników i ich wiek w szczegółowe plany wycieczkowe
   - Uwzględnienie indywidualnych preferencji użytkownika z profilu
   - Mechanizm walidacji i optymalizacji generowanych planów, aby zmniejszyć potrzebę ręcznych poprawek

5. Mechanizmy ograniczenia wykorzystania AI
   - Implementacja limitu zapytań do AI (limit czasowy + budżetowy) w celu kontrolowania kosztów oraz zapobiegania nadużyciom

## 4. Granice produktu

1. Funkcjonalności nieobjęte MVP:

   - Współdzielenie planów wycieczkowych między kontami
   - Zaawansowana obsługa oraz analiza multimediów (np. zdjęć)
   - Rozbudowane planowanie czasu, logistyki i rezerwacji

2. Ograniczenia technologiczne oraz operacyjne:
   - Integracja z zewnętrzną usługą AI – zależność od dostępności i kosztów
   - Implementacja na platformie Supabase, co wymaga adaptacji i ewentualnego rozwiązania barier technologicznych
   - Ograniczenia wynikające z limitu zapytań do AI, który musi zostać ustalony (czasowy, budżetowy lub hybrydowy)

## 5. Historyjki użytkowników

### US-001

- Tytuł: Rejestracja i logowanie
- Opis: Użytkownik rejestruje się w aplikacji, tworząc konto, a następnie loguje się za pomocą bezpiecznego mechanizmu weryfikacji, aby uzyskać dostęp do swoich danych.
- Kryteria akceptacji:
  - Użytkownik musi podać unikalny adres email i hasło przy rejestracji.
  - System wysyła potwierdzenie rejestracji (email weryfikacyjny).
  - Po weryfikacji użytkownik może zalogować się przy użyciu podanych danych.
  - Błąd logowania jest komunikowany wyraźnie i zrozumiale.

### US-002

- Tytuł: Uzupełnienie profilu preferencji turystycznych
- Opis: Po rejestracji użytkownik zostaje skierowany do strony profilu, gdzie wypełnia preferencje dotyczące stylu zwiedzania, ulubionych atrakcji, historii miejsc oraz innych kryteriów osobistych.
- Kryteria akceptacji:
  - Użytkownik ma dostępny formularz do wprowadzania preferencji.
  - Wszystkie pola preferencyjne są obowiązkowe (z wyjątkiem pól opcjonalnych).
  - Zmiany wprowadzone w profilu są zapisywane w czasie rzeczywistym.
  - Komunikat o pomyślnym zapisaniu danych zostaje wyświetlony.

### US-003

- Tytuł: Zarządzanie notatkami podróżniczymi
- Opis: Użytkownik dodaje nową notatkę opisującą przyszły wyjazd, która zawiera dane takie jak miejsce docelowe, długość wyjazdu, opcjonalny preferowany okres, liczba uczestników i ich wiek. Użytkownik może również przeglądać, edytować i usuwać istniejące notatki.
- Kryteria akceptacji:
  - Użytkownik ma dostęp do formularza tworzenia notatki.
  - Notatka zawiera wszystkie wymagane dane.
  - Po zapisaniu notatki, jest ona widoczna na liście notatek użytkownika.
  - Użytkownik może edytować lub usunąć notatkę, a zmiany są zapisywane.

### US-004

- Tytuł: Generowanie planu wycieczki przez AI
- Opis: Użytkownik wybiera zapisaną notatkę i inicjuje proces generacji planu wycieczki, który przetwarza AI. Plan jest generowany na podstawie danych z notatki oraz preferencji użytkownika zapisanych w profilu.
- Kryteria akceptacji:
  - Użytkownik wybiera notatkę, dla której chce wygenerować plan.
  - Po zatwierdzeniu, system wywołuje integrację z AI.
  - Wygenerowany plan zawiera spersonalizowaną listę atrakcji, informacje historyczne i opcje dopasowane do preferencji użytkownika.
  - Proces generacji trwa wyraźnie krócej niż tradycyjne planowanie ręczne.
  - W przypadku przekroczenia limitu zapytań do AI, system wyświetla adekwatny komunikat z informacją o błędzie lub próbie późniejszego użycia.

### US-005

- Tytuł: Ograniczenie zapytań do AI
- Opis: Aby zapobiec nadużyciom i kontroli kosztów, system wprowadza mechanizm ograniczający liczbę zapytań do AI poprzez limit czasowy lub budżetowy (lub oba) dla każdego użytkownika.
- Kryteria akceptacji:
  - Użytkownik jest informowany o obowiązujących limitach przed wykonaniem zapytania.
  - System odrzuca zapytania, które przekraczają ustalony limit.
  - Informacje o wykorzystaniu zapytań są widoczne w panelu użytkownika.
  - W przypadku limitu, użytkownik otrzymuje komunikat z informacją o czasie koniecznym do odnowienia limitu lub o stanie budżetu.

### US-006

- Tytuł: Przeglądanie historii generowanych planów
- Opis: Użytkownik ma możliwość przeglądania listy wygenerowanych planów wycieczek, wraz z możliwością ponownego ich pobrania lub usunięcia.
- Kryteria akceptacji:
  - Lista wygenerowanych planów jest dostępna z poziomu konta użytkownika.
  - Każdy plan zawiera datę generacji oraz podsumowanie głównych informacji.
  - Użytkownik może kliknąć plan, aby zobaczyć pełne szczegóły lub usunąć wybrany plan.
  - Zmiany są aktualizowane w czasie rzeczywistym.

## 6. Metryki sukcesu

1. 90% użytkowników posiada kompletny profil preferencji turystycznych – mierzone poprzez weryfikację wypełnienia danych w panelu użytkownika.
2. 75% użytkowników generuje co najmniej 3 plany wycieczek rocznie – monitorowane poprzez system zapisu generowanych planów.
3. Szybkość generacji planów przez AI musi być znacząco lepsza niż tradycyjne planowanie. Oznacza to, że od stworzenia nowej (jeszcze pustej) notatki, do otrzymania ostatecznie zaakceptowanego planu powinno minąć mniej niż 30 minut.
4. Poziom satysfakcji użytkowników wyższy niż 4.5/5 mierzony ankietą.
