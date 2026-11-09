# Teaching exercises: QEC decoding

Interactive web pages for teaching quantum error correction (QEC) **decoding** in the course *Fundamentals 3*. Each page is one self-contained **exercise**: the student does something hands-on (places errors, reads syndromes, picks corrections) and learns a concept by doing it.

## Delivery

- Hosted as a static site on **GitHub Pages**, publicly reachable without login.
- Students reach each exercise by scanning a **QR code** shown in the lecture slides, so they open the pages on their **phones**. Design every page mobile-first: touch input, works at ~360px width, no horizontal scroll, readable without zooming. It must still work on a laptop.
- Each exercise gets a short, stable URL (`/<exercise-slug>/`), because the QR code printed in the slides points at it. Treat a published slug as permanent; renaming one breaks a QR code already in a presentation.

## Structure

- One folder per exercise, containing an `index.html`. The repository root `index.html` lists all exercises.
- Plain HTML, CSS, and JavaScript with no build step, so GitHub Pages serves the repo as-is. Libraries come from a CDN with a pinned version.
- Shared look lives in one stylesheet (e.g. `assets/blueprint.css`); exercises link it rather than copying styles.

## Visual style: blueprint

Every page looks like a technical blueprint:

- Deep blue paper background with a faint fine grid plus a coarser major grid.
- Drawings in thin white / pale-cyan line work; qubits, stabilizers, and lattices drawn as outlined schematic shapes rather than filled colour blobs.
- Technical lettering: monospace or drafting-style font, uppercase labels, dimension-line style annotations, a title block in a corner.
- Highlights (errors, syndromes, corrections) use a small set of accent colours that read on blue; define them once as CSS variables in the shared stylesheet.

## Writing an exercise

- Lead with one clear task for the student, stated in a sentence or two at the top.
- Give immediate visual feedback on each action (syndrome lights up, correction succeeds or causes a logical error).
- Keep text short: students are reading on a phone during a lecture.
- Use standard QEC notation and terminology (stabilizer, syndrome, data/ancilla qubit, logical error, MWPM, etc.).
