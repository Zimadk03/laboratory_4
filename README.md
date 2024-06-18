# UML - Запись к врачу через мобильное приложение:
```mermaid
classDiagram
class Hotel {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Room {
  +Int RoomNumber
  +String Type
  +Boolean Availability
  +Decimal Price
}

class Guest {
  +String Name
  +String Phone
  +String Address
}

class Booking {
  +Int ID
  +Guest Guest
  +Room Room
  +String PaymentMethod
  +String Status
  +DateTime CheckInDate
  +DateTime CheckOutDate
}

class RoomType {
  +String Type
  +Decimal Price
}

RoomType <|-- Room
Hotel <|-- Room
Guest <|-- Booking
Booking ..> Room
```
# UML - Заказ такси через мобильое приложение:
```mermaid
classDiagram
class TaxiCompany {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Driver {
  +String Name
  +String Phone
  +String CarModel
  +String CarNumber
}

class Customer {
  +String Name
  +String Phone
  +String Address
}

class Ride {
  +Int ID
  +Customer Customer
  +Driver Driver
  +String PickupLocation
  +String DropoffLocation
  +Decimal Fare
  +String PaymentMethod
  +String Status
  +DateTime RequestTime
  +DateTime PickupTime
  +DateTime DropoffTime
}

class CarType {
  +String Type
  +Decimal BaseFare
  +Decimal PerKmFare
}

Driver <|-- CarType
TaxiCompany <|-- Driver
Customer <|-- Ride
Ride ..> Driver
```
# UML - Запись к врачу через мобильное приложение:
```mermaid
classDiagram
class MedicalCenter {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Doctor {
  +String Name
  +String Specialization
  +String Schedule
}

class Patient {
  +String Name
  +String Phone
  +String Address
}

class Appointment {
  +Int ID
  +Patient Patient
  +Doctor Doctor
  +DateTime AppointmentDate
  +String Status
}

class AppointmentType {
  +String Type
  +Decimal Price
}

Doctor <|-- AppointmentType
MedicalCenter <|-- Doctor
Patient <|-- Appointment
Appointment ..> Doctor
```
# UML - Покупка тура в турагенстве:
```mermaid
classDiagram
class TravelAgency {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Tour {
  +String Destination
  +DateTime DepartureDate
  +DateTime ReturnDate
  +Decimal Price
  +String Description
  +String ImageUrl
}

class Customer {
  +String Name
  +String Phone
  +String Address
}

class Booking {
  +Int ID
  +Customer Customer
  +Tour Tour
  +String PaymentMethod
  +String Status
  +DateTime BookingDate
}

class TourOption {
  +Int ID
  +Tour Tour
  +String OptionName
  +Decimal OptionPrice
}

TourOption .. Tour
Booking .. Customer
Booking ..> TourOption
TravelAgency <|-- Tour
Customer <|-- Booking
Booking <|-- TourOption
```
# UML - Создание сайта автомагазина:
```mermaid
classDiagram
class AutomobileStore {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Car {
  +String Make
  +String Model
  +Int Year
  +Decimal Price
  +String Description
  +String ImageUrl
}

class Customer {
  +String Name
  +String Phone
  +String Address
}

class Order {
  +Int ID
  +Customer Customer
  +Car Car
  +String PaymentMethod
  +String Status
  +DateTime OrderDate
}

class OrderItem {
  +Int ID
  +Car Car
  +Int Quantity
}

OrderItem .. Car
Order .. Customer
Order ..> OrderItem
AutomobileStore <|-- Car
Customer <|-- Order
Order <|-- OrderItem
```
# UML - Оптовая закупка овощей из фермы на склад магазина:
```mermaid
classDiagram
class Farm {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Vegetable {
  +String Name
  +String Description
  +Decimal Price
}

class Store {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Warehouse {
  +String Address
  +Int Capacity
}

class PurchaseOrder {
  +Int ID
  +Store Store
  +Farm Farm
  +Vegetable Vegetable
  +Int Quantity
  +String PaymentMethod
  +String Statuses
  +DateTime Date/Time
}

class OrderItem {
  +Int ID
  +Vegetable Vegetable
  +Int Quantity
}

OrderItem .. Vegetable
PurchaseOrder .. Store
PurchaseOrder .. Farm
PurchaseOrder ..> OrderItem
Farm <|-- Vegetable
Store <|-- PurchaseOrder
PurchaseOrder <|-- OrderItem
Store <|-- Warehouse
```
# UML - Заказ шкафа в квартиру с необходимостью вызова замерщика:
```mermaid
classDiagram
class FurnitureStore {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Wardrobe {
  +String Model
  +String Description
  +Decimal Price
}

class Measurer {
  +String Name
  +String Phone
  +String Address
}

class Customer {
  +String Name
  +String Phone
  +String Address
}

class Order {
  +Int ID
  +Customer Customer
  +Wardrobe Wardrobe
  +Measurer Measurer
  +String PaymentMethod
  +String Statuses
  +DateTime Date/Time
  +String DeliveryAddress
}

class OrderItem {
  +Int ID
  +Wardrobe Wardrobe
  +Int Quantity
}

OrderItem .. Wardrobe
Order .. Customer
Order ..> OrderItem
FurnitureStore <|-- Wardrobe
Customer <|-- Order
Order <|-- OrderItem
Measurer <|-- Order
```
# UML - Заказ продуктов в магазине через мобильное приложение:
```mermaid
classDiagram
class Store {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Product {
  +String Name
  +String Description
  +Decimal Price
}

class Customer {
  +String Name
  +String Phone
  +String Address
}

class Order {
  +Int ID
  +Customer Customer
  +OrderItem Product
  +String PaymentMethod
  +String Statuses
  +DateTime Date/Time
  +String DeliveryAddress
}

class OrderItem {
  +Int ID
  +Product Product
  +Int Quantity
}

OrderItem .. Product
Order .. Customer
Order ..> OrderItem
Store <|-- Product
Customer <|-- Order
Order <|-- OrderItem
```
# UML - Оптовая закупка компьютеров в университет:
```mermaid
classDiagram
class University {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Computer {
  +String Model
  +String Specification
  +Decimal Price
}

class Vendor {
  +String Name
  +String Phone
  +String Address
}

class PurchaseOrder {
  +Int ID
  +University University
  +Vendor Vendor
  +Computer Computer
  +Int Quantity
  +String PaymentMethod
  +String Statuses
  +DateTime Date/Time
}

PurchaseOrder .. University
PurchaseOrder .. Vendor
PurchaseOrder ..> Computer
University <|-- PurchaseOrder
Vendor <|-- PurchaseOrder
PurchaseOrder <|-- Computer
```
# UML - Прохождение онлай-курсов по программированию:
```mermaid
classDiagram
class Course {
  +String Name
  +String Description
  +Decimal Price
  +String Level
  +String Language
}

class Student {
  +String Name
  +String Email
  +String Address
}

class Enrollment {
  +Int ID
  +Student Student
  +Course Course
  +String PaymentMethod
  +String Statuses
  +DateTime Date/Time
}

class CourseProgress {
  +Int ID
  +Enrollment Enrollment
  +Int ProgressPercentage
  +DateTime LastAccessed
}

CourseProgress .. Enrollment
Enrollment .. Student
Enrollment ..> CourseProgress
Course <|-- Enrollment
Student <|-- Enrollment
Enrollment <|-- CourseProgress
```
# UML - Заказ и доставка еды из ресторана:
```mermaid
classDiagram
class Restaurant {
  +String Name
  +String Address
  +String Phone
  +String Website
}

class Menu {
  +String Dish
  +String Description
  +Decimal Price
}

class Customer {
  +String Name
  +String Phone
  +String Address
}

class Order {
  +Int ID
  +Customer Customer
  +OrderItem Dish
  +String PaymentMethod
  +String Statuses
  +DateTime Date/Time
  +String DeliveryAddress
}

class OrderItem {
  +Int ID
  +Menu Dish
  +Int Quantity
}

OrderItem .. Menu
Order .. Customer
Order ..> OrderItem
Restaurant <|-- Menu
Customer <|-- Order
Order <|-- OrderItem
```
# laboratory_4
