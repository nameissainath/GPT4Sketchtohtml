# Sketch to HTML Converter with GPT-4 Web Wizard 🎨✨

## Overview

The "Sketch to HTML Converter" is a Streamlit application powered by OpenAI's GPT-4 Web Wizard. It allows users to upload sketches or wireframes and receive fully functional HTML code generated using Tailwind CSS. This tool streamlines the process of turning creative ideas into web interfaces with ease.

## Getting Started

To use this application, follow these steps:

1. **Clone the Repository**:
   - Clone this repository to your local machine:
     ```
     git clone <repository-url>
     ```

2. **Create a Virtual Environment**:
   - It's recommended to create a virtual environment to isolate the project's dependencies. You can do this using Python's `venv` module. Navigate to the project directory and run:
     ```
     python -m venv venv
     ```
   - Activate the virtual environment:
     - On Windows:
       ```
       venv\Scripts\activate
       ```
     - On macOS and Linux:
       ```
       source venv/bin/activate
       ```

3. **Install Dependencies**:
   - Install the required Python packages by running:
     ```
     pip install -r requirements.txt
     ```

4. **Obtain OpenAI API Key**:
   - You need to have an OpenAI API key to use this application. You can obtain one by signing up on the [OpenAI website](https://beta.openai.com/signup/).
   - Once you have the API key, enter it in the "Enter your OpenAI API Key" field in the Streamlit sidebar.

5. **Run the Application**:
   - Start the Streamlit application by running the following command in your terminal:
     ```
     streamlit run <your-app-filename>.py
     ```

6. **Usage**:
   - In the Streamlit web interface, you can use the sidebar to upload a sketch or wireframe.
   - Optionally, you can add more context or details about the sketch in the text area.
   - Click the "Generate HTML" button to initiate the conversion.

7. **Results**:
   - After conversion, the application will provide you with fully functional HTML code generated from your sketch using Tailwind CSS.
   - If you provided additional context, it will be incorporated into the HTML code.

## Example

Here's an example of how to use the application:

1. Enter your OpenAI API key in the sidebar.
2. Upload a sketch or wireframe.
3. Optionally, add more context or details about the sketch.
4. Click the "Generate HTML" button.
5. The application will provide you with HTML code that represents your sketch as a web interface.

## Dependencies

The application relies on the following Python libraries:

- Streamlit
- OpenAI Python SDK

You can find the complete list of dependencies in the `requirements.txt` file.

## Contributing

Contributions are welcome! If you have any suggestions, bug reports, or feature requests, please feel free to open an issue or create a pull request in this repository.

## License

This application is licensed under the MIT License. You can find the full license text in the `LICENSE` file.

## Acknowledgments

- OpenAI for providing the GPT-4 Web Wizard model and the API key.
- Streamlit for the fantastic framework that makes building interactive web applications with Python straightforward.

## Contact

Enjoy using the Sketch to HTML Converter with GPT-4 Web Wizard! 🚀
