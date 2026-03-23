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

## 🛠️ Testowania API
Projekt wykorzystuje autoryzację opartą na tokenach **JWT (JSON Web Token)**. Aby pobrać dane z bazy, postępuj zgodnie z poniższymi krokami w programie Postman:

**1. Rejestracja nowego konta**

Utwórz użytkownika, aby móc się później zalogować.
* **Metoda:** `POST`
* **URL:** `https://localhost:5001/api/account/register`
* **Body (raw JSON):**
  
   ```json
   {
      "email": "test@test.com",
      "password": "password",
      "confirmPassword": "password",
      "natonality": "Polish",
      "dateOfBirth": "1999-01-01"
   }
   ```

**2. Logowanie i uzyskanie tokena**

Zaloguj się, aby otrzymać klucz dostępu, który jest niezbędny do autoryzacji zapytań.
* **Metoda:** `POST`
* **URL:** `https://localhost:5001/api/account/login`
* **Body (raw JSON):**

   ```json
   {
      "email": "test@test.com",
      "password": "password"
   }
   ```
* **Akcja:** Skopiuj długi ciąg znaków (token), który pojawi się w odpowiedzi.

**3. Pobieranie danych o restauracjach (z autoryzacją)**

Teraz możesz wysłać zapytanie o dane, używając pobranego tokena.
* **Metoda:** `GET`
* **URL:** `https://localhost:5001/api/restaurant/`
* **Parametry (Zakładka Params):**
   * `PageNumber` : `1`
   * `PageSize` : `5` (lub 10, 15)
* **Nagłówki (Zakładka Headers):**
   * **Key:** `Authorization`
   * **Value:** `Bearer <WKLEJ_TUTAJ_SKOPIOWANY_TOKEN>`
 
   (Pamiętaj o spacji między słowem Bearer a tokenem!)

   ---
### 🎓 Podziękowania / Credits
Projekt został zrealizowany w celach edukacyjnych na podstawie kursu:
"Praktyczny kurs ASP.NET Core REST Web API od podstaw (C#)" Autor: Jakub Kozera (Udemy).
