# 🌐 Prime Grid Visualization

This project visualizes prime number and non-prime number patterns within a customizable grid, ordered strictly from top-left to bottom-right (row-major order).

The visualization is built using Three.js for 3D rendering and detailed CSS2DRenderer for labeling the numbers within the cells.

## ✨ Concept

The grid fills cells sequentially, starting from the top-left corner:
* **Element at (Row $i$, Column $j$) = Sequence Number $S + (i \times W + j)$**
* Where $S$ is the `Starting Number`, $W$ is the `Width`, and $H$ is the `Height`.

If the sequence number is a prime number, the cell is rendered with a distinct green color (Prime). Otherwise, it is rendered in a darker, less prominent tone (Non-Prime).

## 🛠️ Features

* **Dynamic Grid Control:** Users can adjust the grid's Width, Height, and Starting Number.
* **Visualization:** Displays the structure of the numbers in 3D space.
* **Camera Controls:** Fully draggable 3D camera (OrbitControls) for various viewing angles.
* **Advanced Lighting:** Adjustable ambient, fill, and rim lighting for better depth perception.
* **Optimized Performance:** Includes basic measures for handling large grid dimensions.

## ⚙️ Running the Project

This project assumes a modern web environment (HTML, CSS, JavaScript).

1. **Prerequisites:** You need a local web server (e.g., VS Code Live Server, `http-server`, or Python's SimpleHTTPServer) to run the HTML file due to module imports and JavaScript module constraints.
2. **Setup:** Ensure `prime.html` is accessible from your server's root directory.
3. **Execution:** Open `prime.html` in your web browser.

### Controls Overview

The control panel allows full manipulation of the visualization:

| Control | Effect |
| :--- | :--- |
| **Grid Dimensions** | Sets the total number of cells ($\text{Width} \times \text{Height}$). |
| **Starting Number** | Determines the number placed at the absolute top-left cell (0, 0). |
| **Grid Regeneration** | Must be clicked after changing dimensions/start number to update the 3D scene. |
| **Camera Controls** | Use mouse drag/scroll to pan and zoom. The **Reset Camera** button restores the standard top-down view. |
| **Display Toggles** | Toggle visibility of the structural grid lines and number labels. |

## 💡 Technical Details

The core logic relies on the `isPrime` function, which efficiently checks for primality up to $\sqrt{N}$ using an optimized $6k \pm 1$ testing approach.

**File Structure:**
```
.
├── prime.html    # Main entry point and visualization logic (incorporates all JS/CSS)
```

**Key Technologies Used:**
* **Three.js:** For 3D scene management, rendering, and object placement.
* **CSS2DRenderer:** Used to overlay 2D number labels accurately onto the 3D mesh positions.
* **React (Implied):** While not explicitly used, the component-based structure hints at a framework capable of state management.

## ⚠️ Usage Notes

* **Performance:** Very large grids (e.g., $> 100 \times 100$) may cause browser performance slowdowns due to the high number of rendered meshes and labels.
* **Ordering:** The calculation strictly adheres to **row-major order** (across $X$ first, then down $Z$).

