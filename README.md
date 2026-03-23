# Restaurant API 🍕

Kompletny system backendowy typu **REST Web API** zbudowany w technologii **ASP.NET Core 6.0**. Projekt umożliwia kompleksowe zarządzanie bazą danych restauracji, ich menu oraz kontami użytkowników z uwzględnieniem ról i zaawansowanych polityk bezpieczeństwa.

## 🛠️ Stack Techniczny
* **Framework:** .NET 6.0
* **Baza danych:** SQL Server (LocalDB)
* **ORM:** Entity Framework Core
* **Mapowanie:** AutoMapper
* **Walidacja:** FluentValidation
* **Logowanie zdarzeń:** NLog
* **Dokumentacja:** Swagger / OpenAPI

## 🚀 Kluczowe Funkcjonalności
* **Zarządzanie Restauracjami & Daniami:** Pełny zestaw operacji CRUD.
* **Autoryzacja i Uwierzytelnianie:** System oparty na **JWT Bearer Token**.
* **Bezpieczeństwo zasobów:** Implementacja polityk sprawdzających uprawnienia (np. `MinimumAge`, `ResourceOperation`).
* **Paginacja i Filtrowanie:** Efektywne pobieranie danych dzięki `RestaurantQuery`.
* **Globalna Obsługa Wyjątków:** Dedykowane middleware mapujące błędy na kody HTTP.
* **Monitorowanie:** Middleware mierzący czas wykonania zapytania.

## 🖥️ Dokumentacja API (Swagger)
Projekt posiada wbudowany interfejs Swagger, który pozwala na interaktywne testowanie wszystkich endpointów.
1. Uruchom aplikację.
2. Przejdź pod adres: `https://localhost:[PORT]/swagger` (port znajdziesz w konsoli po uruchomieniu).


## ⚙️ Instrukcja uruchomienia
1. Sklonuj repozytorium: `git clone https://github.com/WiktrN/Projekt-ASP.NET-Core-REST-Web-API.git`
2. Upewnij się, że masz zainstalowany **SQL Server Management Studio**.
3. Zaktualizuj `ConnectionString` w `appsettings.json` (jeśli korzystasz z innej instancji niż LocalDB).
4. Wykonaj migrację bazy danych:
   ```bash
   dotnet ef database update
   ```
   
   ---
### 🎓 Podziękowania / Credits
Projekt został zrealizowany w celach edukacyjnych na podstawie kursu:
"Praktyczny kurs ASP.NET Core REST Web API od podstaw (C#)" Autor: Jakub Kozera (Udemy).
