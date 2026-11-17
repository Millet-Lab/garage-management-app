# Garage Management System
A desktop management application built with C# (WPF) and PostgreSQL, designed to streamline daily 
operations for an automotive repair garage. Training project for CRUD + MVVM architecture. In progress.

## Preview
![Application Screenshot](docs/screenshot.png)

## Key Features
* [ ] **Customer Management:** Add, update, delete and search client contact details and service history.
* [ ] **Vehicle Tracking:** Register vehicles by number plate, make, model, VIN, and mileage; update, delete, review history.
* [ ] **Repair & Service Orders:** Create, track, and update maintenance jobs, parts used, and labour hours.
* [ ] **Invoicing:** Generate and review repair invoices for completed work, review unpaid invoices.
* [ ] **Stock Management**: Add, update, delete, restock, review stock flow, display pieces with a critical stock and the top 10 of the most used pieces.
* [ ] **Appointment Management**: Add, update, cancel, view garage planning

## Tech Stack & Architecture
* **User Interface:** C# / WPF (.NET 8)
* **Architecture:** MVVM (Model-View-ViewModel)
* **Database:** PostgreSQL
* **Data Access:** Entity Framework Core (Npgsql) *(or replace with Npgsql / Dapper)*

## Prerequisites
* Windows 10 or 11
* [.NET SDK](https://microsoft.com)
* [PostgreSQL](https://postgresql.org) installed and running locally

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com
   cd garage-management-wpf
   ```
2. **Configure the database connection**
   Duplicate `src/GarageManagement.Wpf/appsettings.example.json`, rename it to `appsettings.json`, and update it with your local PostgreSQL credentials:
   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Host=localhost;Port=5432;Database=garage_db;Username=postgres;Password=YOUR_PASSWORD"
     }
   }
   ```
3. **Initialise the database**
   * **If using Entity Framework Core:** Run the following command to apply migrations:
     ```bash
     dotnet ef database update --project src/GarageManagement.Wpf
     ```
   * **If using raw SQL:** Execute the `database/schema.sql` script in pgAdmin or `psql` to create the required tables (`Clients`, `Vehicles`, `Repairs`, `Invoices`).

4. **Run the application**
   Open `GarageManagement.sln` in Visual Studio and press **F5**, or run it via the terminal:
   ```bash
   dotnet run --project src/GarageManagement.Wpf
   ```

## Licence
This project is licensed under the MIT Licence. See the [LICENSE](LICENSE) file
