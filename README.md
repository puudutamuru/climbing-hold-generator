# Climbing Hold Generator / Studio v2

The original prototype remains on `main`. Commercial Studio v2 development is isolated on `climbing-hold-studio-v2`.

## Studio v2 prototype

`studio-v2.html` is a browser-based customer configurator prototype with reliable Three.js script loading, interactive 3D orbit/zoom/pan, millimetre dimensions, hold presets, shape controls, mounting options, randomize/reset/undo/redo, browser STL preview export, design JSON, and a `postMessage` hook for embedding in a webshop.

## Production architecture

This is the customer-facing preview layer, not yet the final manufacturing CAD engine. The browser STL is a preview export and mounting holes are visual guides rather than production boolean cuts.

The production system should generate the authoritative watertight STL server-side from validated design JSON, perform real boolean cuts, enforce manufacturing constraints, calculate price, create a design ID, and attach the design JSON and production STL to the webshop order.
