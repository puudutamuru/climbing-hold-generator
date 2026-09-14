# Climbing Hold Generator / Studio v2

A browser-based climbing-hold designer prototype intended to become an embeddable custom-hold configurator.

## Development branch

The Studio v2 work is isolated on `climbing-hold-studio-v2`. The existing `main` branch is unchanged.

## Studio v2 prototype

Open `studio-v2.html` from the branch in a modern browser.

It includes:

- reliable Three.js browser rendering using CDN scripts rather than the previous import-map setup
- interactive orbit / zoom / pan viewer
- parametric dimensions in millimetres
- jug, crimp, sloper, pinch, pocket and volume presets
- shape controls, mounting options and symmetry
- randomize, reset, undo and redo
- browser STL preview export
- design JSON generation
- `postMessage` integration hook for a parent webshop page
- responsive layout for embedding

## WordPress / WooCommerce plan

The intended production integration is a small WordPress/WooCommerce plugin. The designer sends validated design JSON to the parent page; the plugin stores that design as WooCommerce cart/order metadata and can later hand it to the manufacturing service.

WooCommerce's Store API supports cart items and extension data, which makes this a good fit for keeping the design ID and configuration attached to the purchase.

## Important production architecture

This branch is a **working UI/preview step**, not yet the final manufacturing CAD engine. The browser STL is a preview export. Mounting holes currently appear as visual guides rather than boolean-subtracted production holes.

For a commercial product configurator, the next production layer should:

1. send validated design JSON to a backend
2. generate the authoritative watertight manufacturing mesh server-side
3. perform real boolean screw/bolt/pocket cuts
4. validate dimensions, wall thickness, mounting face, manifold state and other manufacturing constraints
5. calculate price and create a design ID
6. attach the design JSON and production STL to the customer's WooCommerce order

The frontend should therefore be treated as the customer-facing configurator, while the server-generated STL becomes the manufacturing source of truth.
