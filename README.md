# Gemini 2.5 Pro - Prescription Analyzer

This is a web-based application designed to test and explore the advanced image extraction and segmentation capabilities of Google's Gemini 2.5 Pro model. The program specifically focuses on analyzing images of handwritten or printed prescriptions to identify and extract medicine names.

## Core Functionality

The application allows a user to:
1.  **Upload an Image**: Select an image file of a prescription from their local device.
2.  **Analyze with AI**: Use the Gemini 2.5 Pro API to process the uploaded image.
3.  **Extract Text**: The AI identifies all medicine names, including dosage information written next to them.
4.  **Visualize Results**: The application draws bounding boxes directly onto the image, highlighting the exact location of each identified medicine, and lists the extracted names below the image.

This project serves as a practical demonstration of Gemini 2.5 Pro's powerful multimodal capabilities, where it not only "reads" the text in the image (Optical Character Recognition - OCR) but also understands the spatial context to provide precise location data for the extracted entities.

## Purpose of this Project

This program was created as an exploratory test to evaluate how effectively the Gemini 2.5 Pro model can handle a real-world, niche task: **extracting and segmenting text from prescription documents**.

As part of my exploration into the model's capabilities, I have been investigating its performance in both **image extraction** (getting the text) and **image segmentation** (identifying "where" the text is). This application is a test case to check if prescription texts are properly:
-   **Extracted**: Is the model accurate in transcribing handwritten and printed medical terms?
-   **Segmented**: Can the model return precise coordinates (bounding boxes) for the specific entities we ask for?

The results from this tool help gauge the model's readiness for more complex document analysis and information extraction tasks.

## How It Works

The application is built with:

1.  **HTML (`index.html`)**: Structures the web page, including the file uploader, image preview area, and results container.
2.  **CSS (`style.css`)**: Provides the styling for a clean, modern, and user-friendly interface.
3.  **JavaScript (`script.js`)**:
    *   Handles user interactions like uploading an image and clicking the "Analyze" button.
    *   Reads the uploaded image and converts it to a Base64 string.
    *   Constructs a precise prompt for the Gemini API, asking for a JSON output containing medicine names and their normalized bounding box coordinates.
    *   Sends the request to the Google AI API endpoint (`v1beta/models/gemini-2.5-pro`).
    *   Parses the JSON response from the API.
    *   Uses the HTML5 Canvas API to draw the bounding boxes over the original image based on the coordinates received.
    *   Dynamically displays the list of extracted medicine names.

## How to Use

1.  Clone or download the repository.
2.  Open the `index.html` file in your web browser.
3.  Enter your Google AI API key in the provided input field.
4.  Click "Choose Image" and select a picture of a prescription.
5.  Click the "Analyze Image with Gemini" button.
6.  The application will display a loading spinner while the API processes the request, and then show the results.



*   `index.html`: The main HTML file containing the structure of the application.
*   `style.css`: The stylesheet for the application's appearance.
*   `script.js`: The core JavaScript logic for handling image processing, API calls, and displaying results.
