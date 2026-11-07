# Invoice Generator

A single-file, browser-based tool for creating professional payment receipts / invoices and exporting them as PDF. Fill in the form, watch the invoice update live, and download it with one click. No build step, no backend, no data leaves your browser.

## Features

- **Live preview** – the invoice updates as you type.
- **PDF export** – downloads a high-resolution (3× scale) PDF sized exactly to the invoice, named `invoice-<invoice no>.pdf`.
- **Company branding** – upload your own logo (PNG, JPG, SVG) or use the built-in default; name, tagline, address, email and footer contact are all editable.
- **Client details** – name, address and email.
- **Invoice details** – invoice number, issue date, payment date and a configurable currency symbol/code (e.g. `BDT`, `$`).
- **Multiple line items** – add or remove items, each with a title, optional description and amount; totals are calculated automatically.
- **Payment info** – payment method and transaction reference.
- **Reset to defaults** – restores all fields to the sample data in one click.

## Usage

1. Open `index.html` in a modern browser (or serve the folder with any static server, e.g. `python3 -m http.server`).
2. Edit the details in the left sidebar: company, client, invoice details, line items and payment info.
3. Check the live preview on the right.
4. Click **⬇ Download PDF**.

## Tech

- Plain HTML, CSS and vanilla JavaScript in a single file ([index.html](index.html)).
- [html2canvas](https://html2canvas.hertzen.com/) 1.4.1 – renders the invoice to an image.
- [jsPDF](https://github.com/parallax/jsPDF) 2.5.1 – wraps the image in a PDF.
- [DM Sans](https://fonts.google.com/specimen/DM+Sans) via Google Fonts.

The libraries and font are loaded from CDNs, so an internet connection is required on first load.

## Customizing

- **Default values** (company, client, items, dates) are set in the form field `value` attributes, the `items` array at the top of the script, and the `resetForm()` function. Update all three to change the defaults.
- **Default logo** is embedded as a base64 JPEG (`DEFAULT_LOGO_JPG`); its white background is made transparent at load time.
- **Colors** are defined as CSS variables in `:root` (`--navy`, `--green`, etc.) and in the `.inv-*` invoice styles.
- **Invoice wording** (the "Payment Received" badge, "Total paid" label and thank-you note) lives in the invoice markup in `index.html`.

## Notes

- Data is not saved: reloading the page resets the form.
- The current template is a *payment receipt* (it shows a "Payment Received" badge and "Payment confirmed" box). Edit the markup if you need an unpaid-invoice layout.

## License

[MIT](LICENSE) © 2026 Ariful Islam Jahid
