# forcodex
# NPU-2N explorer

A single self-contained page (`index.html`) that explains, layer by layer, a
2nm-class neural processing unit with about 1,000 TOPS: what is inside it, who
is needed to build it, and how it is designed and manufactured.

It is a concept study. Every number is labelled **target**, **estimate** or
**industry fact**, in the 3D view and in the spec table below it.

## Run it

Open `index.html` in a current desktop browser, or serve the folder:

```sh
python3 -m http.server 8000   # then open http://localhost:8000
```

Three.js 0.170 is loaded from the jsDelivr CDN, so the page needs a network
connection and WebGL 2. There are no other assets and no build step.

## What is in it

| Mode | Shows |
| --- | --- |
| Architecture | Six zoom levels: card, package, die floorplan, one NPU core, one MAC element, transistor and metal stack |
| Data-flow | An LLM request moving from HBM through L2 and the scratchpad into the systolic arrays; prefill and decode, the bottleneck, and power, heat and utilisation overlays |
| Team | Org graph of 15 roles tied to the blocks they own, with headcount and external dependencies |
| Timeline | 3D Gantt chart from spec to volume, cost range and the 2nm-specific risks |
| Ladder | Five stage gates from simulator to a custom 2nm chip, for a small team |

Controls: drag to orbit, right-drag to pan, scroll to zoom. Click a part marked
"→", or keep scrolling in at the zoom limit, to dive a level; scroll out or
press Esc to go back up. Keys 0–5 jump to a level, L toggles labels, R resets
the camera.

## Editing the numbers

All figures live in one data block near the top of the inline script
(`const K = {...}` and the tables after it). The 3D scene, the side panels and
the spec table are generated from it, so a change there updates all three.
