# Restaurant API 🍕

Kompletne **Web API** zbudowane w technologii **ASP.NET Core 6.0**, służące do zarządzania systemem restauracji. Projekt realizuje pełną logikę biznesową od zarządzania zasobami po zaawansowaną autoryzację użytkowników.

## 🛠 Technologie i Biblioteki
* **Framework:** .NET 6.0
* **ORM:** Entity Framework Core (SQL Server)
* **Mapowanie:** AutoMapper
* **Walidacja:** FluentValidation (walidacja DTO i zapytań)
* **Bezpieczeństwo:** JWT Authentication, Authorization Policies
- **Logowanie:** NLog (obsługa logów do plików)
- **Dokumentacja:** Swagger (OpenAPI)

## 🌟 Kluczowe Funkcjonalności
* **CRUD Restauracji i Dań:** Pełne zarządzanie bazą danych lokali i ich menu.
* **Autoryzacja oparta na zasobach:** Tylko twórca restauracji może ją edytować lub usunąć (`ResourceOperationRequirement`).
* **Paginacja i Filtrowanie:** Zaawansowane wyszukiwanie restauracji z obsługą stron i sortowania (`RestaurantQuery`).
* **Obsługa Błędów:** Customowe Middleware do mapowania wyjątków na odpowiednie kody HTTP (`ErrorHandlingMiddleware`).
* **Logowanie czasu zapytań:** Middleware mierzący wydajność endpointów (`RequestTimeMiddleware`).

## ⚙️ Jak uruchomić?
1. Sklonuj repozytorium: `git clone https://github.com/WiktrN/Projekt-ASP.NET-Core-REST-Web-API.git`
2. W pliku `appsettings.json` zaktualizuj `ConnectionString` do swojej bazy danych.
3. W konsoli Package Manager Console uruchom: `Update-Database`.
4. Uruchom projekt komendą `dotnet run` lub z poziomu Visual Studio.
5. Dokumentacja Swagger dostępna pod: `https://localhost:7147/swagger` (port może się różnić).

---
### Credits
Projekt zrealizowany na podstawie kursu **"Praktyczny kurs ASP.NET Core REST Web API od podstaw"** (Udemy). Rozbudowany o własne poprawki i konfigurację pod .NET 6.
