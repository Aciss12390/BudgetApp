# BudgetApp

Prosta aplikacja desktopowa WPF do zarządzania domowym budżetem. Projekt pozwala dodawać przychody i wydatki, kontrolować saldo, ustawiać miesięczne limity wydatków dla kategorii oraz zapisywać/wczytywać dane z pliku JSON i bazy SQLite.

## Struktura rozwiązania

- `BudgetApp.sln` – główne rozwiązanie.
- `BudgetApplication` – aplikacja WPF (interfejs użytkownika, MVVM).
- `BudgetApp` – biblioteka z logiką domenową (modele + usługi).

## Najważniejsze funkcje

- Dodawanie transakcji:
  - **przychód** lub **wydatek**,
  - data, kwota, opis i kategoria.
- Automatyczne przeliczanie **salda**.
- Ustawianie limitów budżetowych per:
  - rok,
  - miesiąc,
  - kategoria.
- Ostrzeżenia o przekroczeniu limitu (`LimitWarning`).
- Zapis i odczyt danych:
  - JSON (`budget.json`),
  - SQLite (`budget.db`).

## Domyślne kategorie

Aplikacja startuje z pięcioma kategoriami:

1. Jedzenie
2. Transport
3. Rachunki
4. Rozrywka
5. Inne

## Wymagania

- **.NET 9 SDK**
- **Windows** (UI WPF wymaga środowiska Windows)

## Uruchomienie

W katalogu `BudgetApp`:

```bash
dotnet restore

dotnet run --project BudgetApplication/BudgetApplication.csproj
```

## Budowanie

```bash
dotnet build BudgetApp.sln
```

## Jak działają zapisy danych

Po kliknięciu odpowiednich przycisków w interfejsie aplikacja zapisuje/odczytuje dane do plików w katalogu uruchomieniowym aplikacji:

- `budget.json`
- `budget.db`

## Użyte technologie

- C#
- WPF
- MVVM
- `Microsoft.Data.Sqlite`
- `System.Text.Json`

## Możliwe kierunki rozwoju

- filtrowanie transakcji po miesiącu i kategorii,
- wykresy wydatków,
- edycja/usuwanie transakcji,
- eksport raportów (np. CSV/PDF),
- testy jednostkowe logiki `BudgetManager`.
