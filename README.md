# Stratasys Fortus True Print Cost Calculator

**[Try the live calculator →](https://openfilament.com/stratasys-print-cost-calculator/)**

A free, open-source calculator that shows what a print job on a Stratasys Fortus FDM printer really costs. Enter the model volume, support volume and build time from Insight or GrabCAD Print, and it breaks the job down into material, consumables, chamber energy, machine overhead, labor and scrap.

Built by [OpenFilament](https://openfilament.com), open filament for Stratasys uPrint, Dimension and Fortus printers.

![Cost calculator showing a $385.83 total for an ULTEM 9085 job on a Fortus 450mc](docs/preview.png)

## What it calculates

| Cost component | How it's worked out |
| --- | --- |
| **Model & support material** | Volume × price per in³, adjusted for canister tail and purge loss. OEM canister or open filament pricing. |
| **Build sheet & tip wear** | One build sheet per job, plus liquefier tip wear per in³ printed. Nylon 12CF uses hardened tip pricing. |
| **Chamber & machine electricity** | Print time plus cold-chamber warmup × chamber power draw × your electricity rate, with optional HVAC heat-removal load. |
| **Maintenance & depreciation** | Machine hours × an hourly overhead rate: refurbished/in-house PM, new CapEx with an OEM contract, or marginal only. |
| **Support removal** | Soluble support wash tank chemistry and bath heat. Breakaway materials (ULTEM, PPSF) cost $0 here. |
| **Operator touch labor** | Hands-on hours × labor rate. |
| **Scrap allowance** | A failure buffer applied to the subtotal. |

It also shows the **out-of-pocket** cost (material, consumables, energy and support wash only), the **effective cost per in³** and the **cost per build hour**.

### Supported printers and materials

- **Printers:** Fortus 360mc, 400mc, 380mc, 450mc, 900mc and Stratasys F900
- **Materials:** ABS-M30 / ASA / ABS-ESD7, PC / PC-ABS / PC-ISO, Nylon 12CF, ULTEM 9085, ULTEM 1010 / PPSF

High-temperature materials are blocked on printers that can't run them, and the calculator switches to a compatible combination with a note explaining why.

## Embed it on your site

The calculator is a single self-contained HTML file with no dependencies beyond Google Fonts.

1. Copy the contents of [`fortus-cost-calculator.html`](fortus-cost-calculator.html).
2. Paste it into a Custom HTML block (WordPress), an embed block, or straight into your page.
3. Keep the "Cost calculator by [OpenFilament](https://openfilament.com/stratasys-print-cost-calculator/)" credit at the bottom.

All styles are scoped to `.fortus-calc-wrapper` and won't affect the rest of your page. It follows the visitor's light or dark mode; to keep it light-only, delete the two blocks starting with `@media (prefers-color-scheme: dark)` and `:root[data-theme="dark"]`.

## Customizing rates

Everything a shop would want to tune is under **Rates & overrides** in the calculator itself: electricity rate, canister tail loss, labor hours and rate, scrap risk, and custom model and support prices per in³.

To change the built-in defaults, edit the two lookup tables near the top of the `<script>`:

- `MACHINES`: chamber power multiplier, warmup scale, build sheet size, and hourly overhead rates per printer
- `MATERIALS`: OEM and open filament prices per in³, chamber power draw, warmup time, build sheet and tip costs, and wash costs

## Assumptions

The built-in prices and rates are estimates meant as a starting point, not quotes. OEM canister pricing changes over time and varies by reseller and contract. For the most accurate numbers, enter your own prices under **Rates & overrides**.

## License

[MIT](LICENSE) © 2026 [OpenFilament LLC](https://openfilament.com)

You're free to use, modify and embed this calculator. If you embed it publicly, please keep the credit link.

---

Stratasys, Fortus, Insight, GrabCAD and ULTEM are trademarks of their respective owners. This project is not affiliated with or endorsed by Stratasys Ltd.

**[Open the live calculator at OpenFilament →](https://openfilament.com/stratasys-print-cost-calculator/)**
