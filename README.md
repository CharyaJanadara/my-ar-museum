# Mini AR Museum Exhibit

A marker-based WebAR application built using **A-Frame** and **AR.js**. Point your camera at the **Hiro marker** to view a small 3D museum exhibit placed on top of it.

**Live demo:** https://charyajanadara.github.io/my-ar-museum/  
**GitHub repository:** https://github.com/CharyaJanadara/my-ar-museum  
**Group:** 54

## How to Use

1. Open the [live demo](https://charyajanadara.github.io/my-ar-museum/) on a phone or laptop.
2. Allow camera access when your browser asks for permission.
3. Show the Hiro marker to the camera. Keep the complete black border visible.
4. The status banner turns **green** when the marker is detected and **red** when the marker is lost.
5. Tap the **blue box** to make it grow or shrink.
6. Tap the **ball** to change its colour.

## Features

| Requirement | Implementation |
|---|---|
| Hiro marker scene | The `<a-marker preset="hiro">` contains the exhibit objects and text labels. |
| Animation | The box and penguin rotate, while the ball bounces. |
| 3D model | `Penguin.glb` is loaded using `gltf-model` through `<a-assets>`. |
| Interaction | The `color-changer` component changes the ball's colour, and the `grow-box` component changes the box's scale. |
| Marker status | The `marker-status` component updates the banner when `markerFound` and `markerLost` events occur. |
| Hosting | The application is published using GitHub Pages over HTTPS. |

## Code Organisation

- **`index.html`** – Contains the application, including the scripts, custom components, styling and AR scene.
- **`Penguin.glb`** – The 3D penguin model used in the exhibit.
- **`README.md`** – Project information and instructions.

## Custom Components

- **`color-changer`** – When the ball is clicked, it moves to the next colour in an array and updates the entity's `color`.
- **`grow-box`** – When the box is clicked, it switches its scale between `1 1 1` and `1.4 1.4 1.4`.
- **`marker-status`** – Listens for `markerFound` and `markerLost` events and changes the status banner's text and background colour.

### Object Interaction

Taps are detected using raycasting. Interactive objects use `class="clickable"`, and the camera uses `raycaster="objects: .clickable"` to detect them.

## Running the Project Locally

1. Download or clone this repository.
2. Open the project folder in Visual Studio Code.
3. Right-click `index.html` and select **Open with Live Server**.
4. Allow camera access in the browser.
5. Show the Hiro marker to the camera.

**Note:** Browsers generally require HTTPS or localhost for camera access. When testing on a phone, use the HTTPS live demo link rather than a local network address.

## Technologies Used

- [A-Frame](https://aframe.io/) – version 1.3.0
- [AR.js](https://github.com/AR-js-org/AR.js) – version 3.4.5
- HTML
- JavaScript
- GitHub Pages

## Credits

- **3D model:** `Penguin.glb`. Add the model creator, original source URL and licence here if the model was obtained from an external source.
- **Libraries:** [A-Frame](https://aframe.io/) and [AR.js](https://github.com/AR-js-org/AR.js).
- **Marker:** The standard AR.js Hiro marker.

---

**Mini AR Museum Exhibit – Group 54**
