# ✈️ Advanced Flight Reservation and Management System (Aviation Management System)

This project is a comprehensive automation system that digitalizes the flight operations, ticketing processes, and user authorization hierarchy of an airline company. Going beyond structural requirements, the project offers **Multithreading** simulations, **Data Persistence (Serialization)**, and a modern graphical user interface (GUI) based on **Java Swing**.

## 🏗️ Project Architecture and Package Structure

The project has been developed in a modular structure in accordance with Layered Architecture and Object-Oriented Programming (OOP) principles:

### 1. `Flight` Package (Core Data Structures)
Manages the physical components of the flight.
* **Flight:** The main class containing flight number, date, time, route, and aircraft information.
* **Plane & Seat:** Manages the aircraft capacity and the matrix layout of seats (Business/Economy).
* **Route:** Holds departure/arrival airports and distance information.

### 2. `Reservation` Package (Ticketing and Passenger)
Manages customer-oriented processes.
* **Reservation & Ticket:** Generates unique coded tickets by combining flight, passenger, and seat information.
* **Passenger:** Manages passenger identification and contact information.
* **Baggage:** Performs baggage weight tracking.

### 3. `Management` Package (Business Logic and Data Management)
The control layer that forms the brain of the system.
* **FlightManager & ReservationManager:** Ensures that data is permanently serialized into `.dat` files and updated.
* **CalculatePrice:** Executes dynamic pricing logic such as the Business class multiplier and extra baggage fees (50 TL per kg).
* **FlightSearchEngine:** Filters according to complex search criteria (departure/arrival location and time control).

### 4. `Simulation` Package (Advanced Testing and Analysis)
* **SeatSimulation:** Simulates the performance of `synchronized` usage (prevention of Race Conditions) in scenarios where 90 passengers try to buy random seats at the same time.
* **ReportSimulation:** Generates system occupancy reports in an asynchronous (Thread) structure.

## 🌟 Highlighted Features

* **Advanced User Hierarchy:** Different authorization levels including Admin (System management), Staff (Operations), and Customer (Ticket purchase).
* **Data Persistence:** All data is stored in object-based files; data is not deleted when the program is closed.
* **Exception Handling:** Custom error-throwing mechanisms for cases such as negative distance, empty flight numbers, or occupied seat selection.
* **Asynchronous Reporting:** The user interface does not freeze while generating reports; operations are executed in background threads.
* **Unit Testing:** Validation of critical functions such as baggage, price calculation, and seat management with JUnit.

## 🛠️ Technologies Used

* **Language:** Java
* **Graphical Interface:** Java Swing & AWT (MainFrame)
* **Concurrency:** Thread, ExecutorService, Synchronized
* **File Management:** Java Object Serialization (`.dat` files)
* **Testing:** JUnit 5

## 🚀 Getting Started

1. Import the project into a Java IDE (Eclipse, IntelliJ, VS Code).
2. Run the `MainFrame.java` class to launch the GUI interface.
3. Start performing operations according to your authorization level (Admin/Staff/Customer) on the login screen.
