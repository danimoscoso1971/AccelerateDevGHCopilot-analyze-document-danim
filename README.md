 # Library App

 ## Description
 A small .NET 9 sample that models a library lending system. It includes a console UI, a JSON-backed infrastructure for persistence, core domain services and entities, and unit tests.

 ## Project Structure
 - src/
     - Library.ApplicationCore/
         - Library.ApplicationCore.csproj
         - Entities/
             - Patron.cs
             - Loan.cs
             - Book.cs
             - BookItem.cs
             - Author.cs
         - Interfaces/
             - IPatronRepository.cs
             - ILoanRepository.cs
             - IPatronService.cs
             - ILoanService.cs
         - Services/
             - PatronService.cs
             - LoanService.cs
     - Library.Console/
         - Library.Console.csproj
         - Program.cs
         - ConsoleApp.cs
         - CommonActions.cs
         - ConsoleState.cs
         - appSettings.json
         - Json/
             - Authors.json
             - Books.json
             - BookItems.json
             - Patrons.json
             - Loans.json
     - Library.Infrastructure/
         - Library.Infrastructure.csproj
         - Data/
             - JsonData.cs
             - JsonPatronRepository.cs
             - JsonLoanRepository.cs
 - tests/
     - UnitTests/
         - UnitTests.csproj
         - PatronFactory.cs
         - LoanFactory.cs
         - (unit tests exercising services)

 ## Key Classes and Interfaces
 - Domain entities
   - `Library.ApplicationCore.Entities.Patron` — `src/Library.ApplicationCore/Entities/Patron.cs`
   - `Library.ApplicationCore.Entities.Loan` — `src/Library.ApplicationCore/Entities/Loan.cs`
   - `Library.ApplicationCore.Entities.Book` — `src/Library.ApplicationCore/Entities/Book.cs`
   - `Library.ApplicationCore.Entities.BookItem` — `src/Library.ApplicationCore/Entities/BookItem.cs`
   - `Library.ApplicationCore.Entities.Author` — `src/Library.ApplicationCore/Entities/Author.cs`
 - Services & contracts
   - `IPatronService` / `PatronService` — `src/Library.ApplicationCore/Interfaces/IPatronService.cs`, `src/Library.ApplicationCore/Services/PatronService.cs`
   - `ILoanService` / `LoanService` — `src/Library.ApplicationCore/Interfaces/ILoanService.cs`, `src/Library.ApplicationCore/Services/LoanService.cs`
   - Repository interfaces: `IPatronRepository`, `ILoanRepository` — `src/Library.ApplicationCore/Interfaces/`
 - Infrastructure
   - `Library.Infrastructure.Data.JsonData` — loads and saves JSON files, provides population helpers (`src/Library.Infrastructure/Data/JsonData.cs`)
   - `JsonPatronRepository` — patron search/get/update backed by `JsonData` (`src/Library.Infrastructure/Data/JsonPatronRepository.cs`)
   - `JsonLoanRepository` — loan get/update backed by `JsonData` (`src/Library.Infrastructure/Data/JsonLoanRepository.cs`)
 - Console UI / startup
   - `ConsoleApp` — interactive application loop (`src/Library.Console/ConsoleApp.cs`)
   - `Program` — dependency injection, configuration and startup (`src/Library.Console/Program.cs`)

 ## Usage
 - Run console application:
   - `dotnet run --project src/Library.Console/Library.Console.csproj`
     Entry point: `src/Library.Console/Program.cs` which resolves and runs `src/Library.Console/ConsoleApp.cs`.
 - Configuration and data:
   - JSON paths configured in `src/Library.Console/appSettings.json`.
   - Example data located under `src/Library.Console/Json/`.
 - Run unit tests:
   - `dotnet test tests/UnitTests/UnitTests.csproj`

 ## License
 No license is specified. Add a `LICENSE` file at the repository root to define terms.
