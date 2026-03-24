# Teórica 14 (SIN) - 12/3/2026

Se terminó:
* Digrama Entidad Relación
* Diagrama de clases (me tocó a mí)

---

## Diagrama Entidad Relación

Hecho en **Lucidchart**: `Diagrama en blanco.png`

![Diagrama Entidad Relación](./Diagrama%20en%20blanco.png)

## Diagrama de clases

Hecho en [PlantText](https://www.planttext.com/):
* Diagrama en formato **PNG**: `Diagrama de clases SIN-A.png`
* Diagrama en formato UML: `diagrama_clases_plantuml_export.puml`

### Imagen

![Diagrama de clases](./Diagrama%20de%20clases%20SIN-A.png)

### Código UML

```plantuml
@startuml
skinparam classAttributeIconSize 0
skinparam monochrome true
skinparam shadowing false

class Product {
  - product_id: Integer
  - name: String
  - sku_code: String
  - sale_price: Float
  - purchase_price: Float
  - current_stock: Integer
  - min_stock_level: Integer
  + updateStock(quantity: Integer): void
  + calculateProfitMargin(): Float
  + isLowStock(): Boolean
}

class Category {
  - category_id: Integer
  - category_name: String
}

class Supplier {
  - supplier_id: Integer
  - company_name: String
  - contact_name: String
}

class Purchase {
  - purchase_id: Integer
  - purchase_date: Date
  - total_cost: Float
  + completePurchase(): void
}

class Customer {
  - customer_id: Integer
  - full_name: String
  - email: String
}

class Sale {
  - sale_id: Integer
  - sale_date: Date
  - total_amount: Float
  + calculateTotal(): Float
  + processSale(): void
}

class SaleDetail {
  - detail_id: Integer
  - quantity: Integer
  - unit_price: Float
  + calculateSubtotal(): Float
}

class User {
  - user_id: Integer
  - user_name: String
  - password: String
  + authenticate(password: String): Boolean
  + hasPermission(permission: String): Boolean
}

class Role {
  - role_id: Integer
  - role_name: String
}

' Relaciones
Category "1" -- "0..*" Product : contains >
Supplier "1" -- "0..*" Purchase : provides >
Purchase "1" -- "1..*" Product : includes >
Product "1" -- "0..*" SaleDetail : sold_in >
Sale "1" *-- "1..*" SaleDetail : consists_of >
Customer "1" -- "0..*" Sale : makes >
User "1" -- "0..*" Sale : registers >
Role "1" -- "0..*" User : assigned_to >

@enduml
```