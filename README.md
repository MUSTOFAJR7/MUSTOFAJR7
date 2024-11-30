- 👋 Hi, I’m @MUSTOFAJR7

- import requests

def download_image(image_url, save_path):
    try:
        # Send a GET request to the image URL
        response = requests.get(image_url, stream=True)
        response.raise_for_status()  # Check if the request was successful
        
        # Open a file in binary write mode and write the content
        with open(save_path, "wb") as file:
            for chunk in response.iter_content(1024):
                file.write(chunk)
        
        print(f"Image downloaded successfully and saved to {save_path}")
    except Exception as e:
        print(f"An error occurred: {e}")

# Example usage
image_url = "https://example.com/image.jpg"  # Replace with your image URL
save_path = "downloaded_image.jpg"          # Replace with your desired file path
download_image(image_url, save_path)
