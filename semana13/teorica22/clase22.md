# Teórica 22 (SIN) - 16/4/2026

## DFDs

>Se me pidió hacer los DFDs de nivel 1 y 2 para terminar el Manual del Analista

### DFD de nivel 1

![DFD Nivel 1](./DFD%20Nivel%201%20SIN-A.png)

```eraser
// DFD Nivel 1
// External Entities
Seller [shape: rectangle]
Customer [shape: rectangle]

// Sub-processes of 3.0 Sales & billing
P3_1 [shape: oval, label: "3.1 Receive\nOrder"]
P3_2 [shape: oval, label: "3.2 Verify\nStock Availability"]
P3_3 [shape: oval, label: "3.3 Process\nPayment"]
P3_4 [shape: oval, label: "3.4 Record Sale\n& Emit Receipt"]

// Data Store (From Level 0)
DB [shape: cylinder, label: "Central Database"]

// Data Flows
Customer > P3_1: Product Request
Seller > P3_1: Order_Information
P3_1 > P3_2: Item Details to Check

// Inventory verification loop
DB > P3_2: Current_Stock_Levels
P3_2 > Seller: Stock Status (Available / Out of Stock)

// Payment and System Entry
P3_2 > P3_3: Confirmed Items for Sale
Customer > P3_3: Cash Payment
P3_3 > P3_4: Payment Confirmation

// Final Database updates and output (Matches Level 0 flows)
P3_4 > DB: New_Sale_Entry
P3_4 > DB: Update_Inventory_Record
P3_4 > Seller: Printed_Receipt
Seller > Customer: Deliver Product & Receipt
```

### DFD de nivel 2

![DFD Nivel 2](./DFD%20Nivel%202%20SIN-A.png)

```eraser
// DFD Nivel 2 SIN-A
// Entities and Data Sources outside this specific sub-process
Seller [shape: rectangle]
P3_3 [shape: oval, label: "3.3 Process\nPayment"]

// Sub-processes of 3.4 Record Sale & Emit Receipt
P3_4_1 [shape: oval, label: "3.4.1 Register\nTransaction Data"]
P3_4_2 [shape: oval, label: "3.4.2 Deduct\nInventory Quantities"]
P3_4_3 [shape: oval, label: "3.4.3 Format &\nGenerate Receipt"]

// Data Store (From Level 0)
DB [shape: cylinder, label: "Central Database"]

// Data Flows
// The flow comes from the previous payment process
P3_3 > P3_4_1: Validated Payment & Items

// Database entries
P3_4_1 > DB: New_Sale_Entry
P3_4_1 > P3_4_2: Sold Items Details
P3_4_2 > DB: Update_Inventory_Record

// Receipt generation
P3_4_1 > P3_4_3: Confirmed Sale Details
P3_4_3 > Seller: Printed_Receipt
```

>Ambos diagramas hechos en [Eraser](https://www.eraser.io/)

## Estudiar para el Parcial

En el documento `Estudiar para el Parcial.docx`, hay preguntas y respuestas que cubren los temas vistos en clase, esto para el **Segundo Parcial**.