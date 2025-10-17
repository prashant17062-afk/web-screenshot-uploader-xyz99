# Screenshot Uploader & Viewer

## Summary
This web application provides a simple, client-side interface for uploading and displaying PNG screenshots directly within the browser. It is designed for ease of use, allowing users to quickly preview image files without server-side processing. This tool is ideal for academic submissions or personal use where a quick local preview of a screenshot is needed.

## Setup Instructions
This application is entirely client-side, meaning it runs directly in your web browser without requiring a web server or complex environment setup.

1.  **Save the file:** Save the provided `index.html` content into a file named `index.html` on your local computer.
2.  **Open in browser:** Navigate to the saved `index.html` file using your file explorer and open it with any modern web browser (e.g., Chrome, Firefox, Edge, Safari).

## Usage
1.  **Open the application:** Launch `index.html` in your web browser as described in the Setup Instructions.
2.  **Select a file:** Click on the "Choose File" button (or similar, depending on your browser) that appears next to the `Screenshot Input` label.
3.  **Upload a screenshot:** A file dialog will open. Navigate to the location of your `.png` screenshot file, select it, and click "Open" or "Choose".
4.  **View the screenshot:** The selected `.png` image will immediately appear in the display area below the input field. If you select an invalid file type, an error message will be displayed.

## Main Code Logic
The core functionality of this application is implemented using HTML for structure, CSS for styling, and JavaScript for interactivity.

*   **HTML Structure (`index.html`):** Defines the user interface, including a file input element (`<input type="file" id="screenshotInput">`) configured to accept only `.png` files via the `accept=".png"` attribute. An image display area (`<div id="screenshotDisplay">`) is also provided.
*   **CSS Styling:** Ensures a clean, modern, and user-friendly interface.
*   **JavaScript (`<script>` tag):**
    *   An event listener is attached to the `screenshotInput` element to detect when a file is selected (`'change'` event).
    *   Upon file selection, it checks if a file exists and if its type is `image/png`.
    *   The `FileReader` API is utilized to read the contents of the selected file. Specifically, `reader.readAsDataURL(file)` converts the image file into a Base64 encoded string (Data URL).
    *   Once the `FileReader` completes reading (`reader.onload` event), an `<img>` element is dynamically created.
    *   The `src` attribute of the new `<img>` element is set to the generated Data URL, effectively embedding and displaying the image directly in the browser without needing to upload it to a server.
    *   The newly created `<img>` element is then appended to the `screenshotDisplay` div, replacing any previous content.
    *   Error handling is included to prompt the user if a non-PNG file is selected.

## License
This project is licensed under the MIT License. Please see the license header within the `index.html` file for details.

## Contact
For questions or feedback, please contact [Your Name/Email/GitHub Profile].