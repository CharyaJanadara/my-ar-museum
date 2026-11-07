# Mini AR Museum Exhibit

A marker-based WebAR app built with **A-Frame** and **AR.js**. Point your camera at the **Hiro marker** and a small museum exhibit appears on top of it.

**Live demo (HTTPS):** https://charyajanadara.github.io/my-ar-museum/
**Group:** 54

## How to use it

1. Open the live demo link on a phone or laptop and click **Allow** for the camera.
2. Show the Hiro marker (printed, or on another screen) so the whole black border is visible.
3. The banner turns **green** when the marker is found and **red** when it is lost.
4. Tap the **blue box** to make it grow or shrink.
5. Tap the **ball** to change its colour.

## Features (task checklist)

| Requirement | How it is done |
|---|---|
| Hiro marker scene | `<a-marker preset="hiro">` holds a plane, box, sphere, cylinder, cone and `<a-text>` labels |
| Animation | Box and penguin rotate (`rotation`); ball bounces (`position`) |
| 3D model | `Penguin.glb`, loaded with `gltf-model` through `<a-assets>` |
| Interaction | `color-changer` (ball colour) and my own `grow-box` component (box scale) |
| Status banner | `marker-status` component listens for `markerFound` and `markerLost` |
| Hosting | Published over HTTPS and tested on a phone |

## How the code is organised

- `index.html` contains the whole app: scripts, custom components, styling and the AR scene.
- `Penguin.glb` is the 3D model.

### Custom components

- **`color-changer`**: on `click`, moves to the next colour in an array and updates the entity's `color`.
- **`grow-box`**: on `click`, toggles the entity's `scale` between `1 1 1` and `1.4 1.4 1.4`.
- **`marker-status`**: on `markerFound` / `markerLost`, changes the banner's text and background colour.

Taps are detected with raycasting: tappable objects have `class="clickable"` and the camera uses `raycaster="objects: .clickable"`.

## Running it locally

1. Open the folder in VS Code.
2. Right-click `index.html` and choose **Open with Live Server** (localhost is allowed to use the camera).
3. Allow the camera and show the Hiro marker.

Phones need HTTPS for the camera, so use the live demo link instead of a local network address.

## Credits

- **3D model:** "<MODEL NAME>" by <AUTHOR>, from <WEBSITE / URL>, licensed under <LICENCE>.
- **Libraries:** [A-Frame 1.3.0](https://aframe.io) and [AR.js 3.4.5](https://github.com/AR-js-org/AR.js).
- **Marker:** the standard AR.js Hiro marker.
