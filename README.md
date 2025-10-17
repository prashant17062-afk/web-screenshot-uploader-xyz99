Screenshot Uploader and Viewer

Summary
This web application provides a simple, client-side interface for uploading and displaying PNG screenshots. It is designed for academic grading purposes, allowing users to quickly preview screenshots of web pages without requiring server-side processing.

Setup Instructions
1.  Save the provided `index.html` file to your local computer (e.g., in a folder named `screenshot-app`).
2.  Open the `index.html` file using any modern web browser (e.g., Chrome, Firefox, Edge, Safari). Simply double-click the file, or drag and drop it into an open browser window. No web server is required as all processing occurs client-side within your browser.

Usage
1.  Navigate to the `index.html` file in your web browser.
2.  Locate the "Upload Screenshot (.png only):" label and click the "Choose File" button next to it.
3.  A file selection dialog will appear. Select a `.png` image file from your local computer.
4.  Once a `.png` file is successfully selected, the image will immediately be displayed in the "Screenshot Preview:" section below the file input field.
5.  If a file that is not a `.png` type is selected, an alert message will appear, and the preview area will remain hidden or clear its previous content.

Main Code Logic
The application is entirely client-side and consists of a single `index.html` file that integrates HTML, CSS, and JavaScript:
-   **HTML Structure:** Defines the user interface, including an input element (`<input type="file" id="screenshotUpload" accept="image/png">`) specifically configured to accept PNG image files, and an image element (`<img id="screenshotPreview">`) where the uploaded screenshot will be displayed. A paragraph (`<p id="previewLabel">`) acts as a dynamic label for the preview.
-   **CSS Styling:** Provides basic, clean, and responsive styling to ensure a user-friendly interface across different devices. Initial display states for the image and label are set to `none`.
-   **JavaScript Functionality:**
    -   An event listener is attached to the `screenshotUpload` input to detect when a user selects a file (the `change` event).
    -   Upon file selection, the script first checks if a file was selected and if its MIME type (`file.type`) is `image/png`.
    -   If the file is a valid PNG, a `FileReader` object is instantiated.
    -   The `FileReader`'s `onload` event is configured to execute once the file's contents are successfully read. Inside this handler, the `src` attribute of the `screenshotPreview` image element is set to `e.target.result`, which contains the base64-encoded Data URL of the image. The image and its label are then set to `display: block` to make them visible.
    -   An `onerror` handler is included for the `FileReader` to provide user feedback if file reading fails.
    -   The `reader.readAsDataURL(file)` method initiates the asynchronous reading of the selected file.
    -   If an invalid file type is selected, an alert is shown, and the input field is reset along with hiding any previous preview.

License
This project is licensed under the MIT License.

MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Contact
For questions or feedback regarding this submission, please contact [Your Name/Student ID/Email Address - e.g., A.Developer@example.edu].