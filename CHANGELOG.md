# TRS-80 Model 1 (Rev G) Replica - E1 - Changelog

## Versioning

I've devised a versioning system for my replica projects. This system provides clarity about each of my version's significance. My version identifier consistently follows the original revision details, allowing for a clear distinction between the original manufacturer's revision and my own.

Here's the format for the versioning:
- The initial character is always an "E," representing my last name. This choice ensures that others can adopt the same versioning style if needed.
- The following character is a number, with "1" signifying a 1-1 re-implementation of the original. Numbers beyond "1" denote various board variations, such as new designs features, more modern components, or different interface ports.
- The final character represents my actual revision of that board. Using a character for this purpose distinguishes it from the re-implementation type mentioned above, and it allows for up to 26 revisions to refine the project.

## 12th Dec 2023 - E1A Prototype

Completed test. Fully functional.

## 28th Dec 2023 - E1B

- A few traces were modified to more closely resemble the original.

![Optimized trace shape at edge-connector](/Changelog/E1B_1.png)
![Increase trace size frm 0.3mm to 0.5mm](/Changelog/E1B_2.png)

- Missing pads from the bottom of the PCB, also found on the original, were put-back to simplify the soldering of components.

![Missing pads on bottom of E1A](/Changelog/E1B_0.png)

- The holes for several through-hole components (diodes) were enlarged. Previously, these holes were a bit tight.

## 20th Feb 2024 - E1B (no version change; only local files)

- New file "Labels" in SVG format was added to help identify components.
- Various updates to the BOM by Jay Newirth.

## 3rd March 2024 - E1B (no version change; only local files)

- Assembly Guide as PDF (suggested by Jay Newirth)

## 14th March 2024 - E1B (no version change; only local files)

- Updated BOM to remove 2N6287 as alternative. Has worked, but transistor introduces a lot of noise in 5V rail, causing a shaky video output.
