# DE10 Pin Assignments

This repository provides a clean and ready-to-use pin assignment file for the DE10 FPGA board, compatible with Intel Quartus.

---

## 📁 File

* `de10_standard.csv`
  Standard pin mapping for switches, LEDs, and basic I/O on the DE10 board.

---

## ⚙️ Requirements

* Intel Quartus Prime
* DE10 FPGA board (e.g., DE10-Lite / DE10-Nano)

---

## 📥 How to Import Pin Assignments

Follow these steps to import the CSV file into your Quartus project:

1. Open your project in Quartus.
2. Go to **Assignments → Import Assignments...**
3. Select the file:

   ```
   de10_standard.csv
   ```
4. Click **OK** to apply.

---

## ⚠️ Important Notes

* Make sure your **top-level module name** is correctly set:

  * Go to: `Assignments → Settings → General`
  * Set **Top-level entity** to match your Verilog module (e.g., `top`)

* Signal names in the CSV must match your code exactly.
  Example:

  ```verilog
  input  [9:0] SW;
  output [9:0] LEDR;
  ```

  → CSV must use:

  ```
  SW[0], PIN_...
  LEDR[0], PIN_...
  ```

* Ensure the CSV format is strictly:

  ```
  To,Location
  SIGNAL_NAME,PIN_NAME
  ```

* Save the file with **ANSI encoding** (avoid UTF-8 BOM issues).

---

## 🧪 Example

```verilog
module top (
    input  wire [9:0] SW,
    output wire [9:0] LEDR
);
    assign LEDR = SW;
endmodule
```

---

## 📌 Notes

* This file is intended for quick setup and testing.
* You can modify or extend the CSV to include HEX displays, KEY buttons, etc.

---

## 🚀 License

Free to use for learning and development.
