

Stock management — Admin/Manager get an "Add Product" button (Stock page) to create products with barcode, name, category, price, quantity, min stock, expiry, and supplier link. Manager/Admin can edit or clear price; Storekeeper can edit quantity but the price field is locked for them. Delete is restricted to Admin/Manager.

Live product feed to POS — Everything added in Stock instantly becomes scannable/sellable at the cashier's POS — no separate product list to maintain.

Barcode scanning — the POS barcode field accepts keyboard-wedge scanners (auto-adds on Enter) and there's a "Scan (Camera)" button that opens a live camera view using the browser's native `BarcodeDetector` API, with a manual-entry fallback for browsers that don't support it.

Printer support — a printer status badge in the topbar (click to connect/disconnect, simulating a receipt printer), and a "Print Receipt" button on completed sales that fires `window.print()` with a print-only receipt layout (everything else is hidden from the print output).

Suppliers — Add/Edit/Delete suppliers, and every product can be tied to one; reorder suggestions and the supplier directory pull from live stock data.

Staff & shifts— Add/Edit/Remove staff, toggle on/off shift with a click, and the Dashboard "Staff on Shift" table and shift grid update live from that data.

Permissions are role-gatedthroughout (Admin/Manager: full control; Storekeeper: stock qty + suppliers, no price/no sales; Cashier: sell + print only; Accountant: reports/print only) — matching the demo logins already built into the file.

| Role | Username | Password | 2FA |
|---|---|---|---|
| Owner/Admin | `admin@theftguard.ke` | `Admin@2026` | Yes — code `123456` |
| Manager | `peter.manager` | `Manager@2026` | No |
| Cashier | `jane.cashier` | `Cashier@2026` | No |
| Storekeeper | `mary.store` | `Store@2026` | No |
| Accountant | `acct.finance` | `Acct@2026` | No |

Note these are hardcoded in the `ROLES` object in the script for demo purposes — before this goes anywhere near real use, you'll want to swap this out for a proper backend with hashed passwords rather than credentials sitting in client-side JS.
