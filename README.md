# DE10 Pin Assignments

This repository provides a complete pin assignment file for the DE10 FPGA board, exported from Quartus.
It includes full mappings for HPS, DDR3, GPIO, VGA, Audio, ADC, and basic peripherals like switches, LEDs, keys, and HEX displays.

---

## 📁 File

* `de10_pin_assignments.csv`
  Full pin assignment table (Quartus CSV export format)

---

## 📥 How to Import

Follow these steps to import the pin assignments into your project using Intel Quartus Prime:

1. Open your project in Quartus
2. Go to:

   ```
   Assignments → Import Assignments...
   ```
3. Select:

   ```
   de10_pin_assignments.csv
   ```
4. Click **OK**

---

## ⚠️ Important Notes

* Make sure your **Top-level entity** is set correctly:

  * Go to: `Assignments → Settings → General`
  * Set it to match your module name (e.g., `top`)

* Signal names in your code must match the CSV exactly
  Example:

  ```verilog
  input  [9:0] SW;
  output [9:0] LEDR;
  ```

  → CSV uses:

  ```
  SW[0]
  LEDR[0]
  ```

* This file contains many signals (HPS, DDR3, etc.).
  You do **not** need to use all of them — only the signals present in your design will be applied.

* If import fails:

  * Ensure the file is not modified by Excel (no broken format)
  * Avoid extra spaces or encoding issues
  * Try saving as **ANSI**

---
