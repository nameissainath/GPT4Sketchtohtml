import streamlit as st
import base64

from openai import OpenAI

# Function to encode the image to base64
def encode_image(image_file):
    return base64.b64encode(image_file.getvalue()).decode("utf-8")


# Configuring the Streamlit page with a more engaging title and layout
st.set_page_config(page_title="Sketch to HTML Converter 🎨✨", layout="wide", initial_sidebar_state="collapsed")

st.title("✏️ Sketch to HTML: GPT-4 Web Wizard 🌐")

# Creating a sidebar for user inputs, making it interactive and user-friendly

st.sidebar.title("User Input")
api_key = st.sidebar.text_input("Enter your OpenAI API Key")
uploaded_file = st.sidebar.file_uploader("Upload an image", type=["jpg", "png", "jpeg"])
show_details = st.sidebar.checkbox("Add details about the image")

if show_details:
    additional_details = st.sidebar.text_area("Additional details about the image")

# Main content area
st.write("## Uploaded Image")
if uploaded_file:
    st.image(uploaded_file, caption=uploaded_file.name, use_column_width=True)

# Analysis section
if st.sidebar.button("Analyze the Scientific Image"):
    if not uploaded_file:
        st.warning("Please upload an image.")
    elif not api_key:
        st.warning("Please enter your OpenAI API key.")
    else:
        # Initialize the OpenAI client with the API key
        client = OpenAI(api_key=api_key)

        with st.spinner("Analyzing the image ..."):
            base64_image = encode_image(uploaded_file)

          # Construct the prompt for image to sketch analysis
            prompt_text = (
               "You are an expert tailwind developer."
"A user will provide you with a low-fidelity wireframe of an application and you will return a single html file that uses tailwind to create the website."
"Use creative license to make the application more fleshed out. "
"Respond only with the html file."
)



            if show_details and additional_details:
                prompt_text += f"\n\nAdditional Context Provided by the User:\n{additional_details}"

            # Create the payload for the completion request
            messages = [
                {
                    "role": "user",
                    "content": [
                        {"type": "text", "text": prompt_text},
                        {
                            "type": "image_url",
                            "image_url": f"data:image/jpeg;base64,{base64_image}",
                        },
                    ],
                }
            ]

            try:
                full_response = ""
                for completion in client.chat.completions.create(
                    model="gpt-4-vision-preview", messages=messages, max_tokens=1200, stream=True
                ):
                    if completion.choices[0].delta.content is not None:
                        full_response += completion.choices[0].delta.content
                        st.markdown(full_response)
            except Exception as e:
                st.error(f"An error occurred: {e}")
