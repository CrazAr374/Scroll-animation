# Scroll Animation with Canvas and GSAP

This project implements a smooth scroll-triggered animation using a series of images, rendered onto an HTML canvas. The animation is controlled by the GSAP (GreenSock Animation Platform) library, particularly its `ScrollTrigger` plugin. The project uses Tailwind CSS for basic styling and structure.

## Project Structure

```
.
├── index.html        # Main HTML file
├── frame/            # Folder containing the image frames
│   └── frame_0001.jpeg
│   └── frame_0002.jpeg
│   └── ...           # Up to frame_0382.jpeg
└── Untitled (4).png  # Favicon
```

## Features

- **Scroll-triggered Animation**: As the user scrolls down the page, a series of images (382 in total) are rendered to simulate an animation on the canvas.
- **GSAP Integration**: GSAP's `ScrollTrigger` plugin is used to control the animation based on the scroll position.
- **Responsive Canvas**: The canvas automatically adjusts its size based on the browser window, ensuring the animation fits the screen.

## Prerequisites

Make sure to have the following files and libraries set up:
- A folder named `frame/` containing image frames numbered from `frame_0001.jpeg` to `frame_0382.jpeg`.
- The GSAP and ScrollTrigger CDN included in the `<head>` section of the HTML.

## Setup and Usage

1. **Image Frames**:
   - Place all your image frames (from `frame_0001.jpeg` to `frame_0382.jpeg`) inside the `frame/` folder.
   - Ensure the filenames are correctly numbered with four digits (e.g., `frame_0001.jpeg`, `frame_0002.jpeg`).

2. **HTML Structure**:
   - The HTML file contains a `canvas` element inside a `div` with Tailwind CSS classes applied. The images will be rendered onto this canvas during scrolling.

3. **Tailwind CSS**:
   - Tailwind CSS is included via CDN to handle basic styling and structure. You can customize or extend the styling using Tailwind's utility classes.

4. **GSAP & ScrollTrigger**:
   - GSAP and the ScrollTrigger plugin are included via CDN to handle the scroll-triggered animation.
   - Ensure GSAP and ScrollTrigger are loaded correctly by including the following scripts in the `<head>`:
     ```html
     <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
     <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
     ```

5. **Canvas Rendering**:
   - The canvas adjusts dynamically to the browser's width and height.
   - Each image frame is preloaded and rendered onto the canvas based on the scroll position, using the `loadImage` function.

6. **Scroll Animation**:
   - The `gsap.timeline` is set up with `ScrollTrigger`, which listens to scroll events and triggers the animation by updating the `frame.currentIndex`.
   - This index is then used to load and render the corresponding image frame onto the canvas.

## Customization

- **Image Frames**: To use your own animation, replace the images in the `frame/` folder with your own. Ensure they are named sequentially in the format `frame_XXXX.jpeg`.
- **Number of Frames**: If you use a different number of frames, update the `maxIndex` value in the `frame` object accordingly.
  ```javascript
  const frame = {
    currentIndex: 0,
    maxIndex: YOUR_FRAME_COUNT - 1, // Replace with the actual number of frames
  };
  ```

- **Scrub Speed**: You can control how quickly the animation responds to scrolling by adjusting the `scrub` option in the `ScrollTrigger` settings:
  ```javascript
  scrub: 2, // Adjust this value for faster or slower animation
  ```

## License

This project is open-source and free to use. Feel free to modify it for personal or commercial purposes.

## Credits

- [GSAP (GreenSock Animation Platform)](https://greensock.com/gsap/)
- [Tailwind CSS](https://tailwindcss.com/)

If you have any questions or need further assistance, feel free to reach out!
