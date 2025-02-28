# Image Downloader for e621, e926, and Danbooru


## Usage
1. **Open the Script in Google Colab**:

2. **Configure Settings**:
   - `search_url`: Paste the URL with the tags you want to search (e.g., `https://e621.net/posts?tags=hug`).
   - `max_images`: Set the maximum number of images to download. (use `-1` for all image)
   - `include_gif_video`: Set to `True` to include GIFs, WebM, and MP4 files (default is `False`).
   - `save_path`: Define the folder where images will be saved (e.g., `/content/e621_test_2`).

3. **Run the Script**:
   - Execute the cell in Colab.
   - The script will:
     - Fetch posts based on the tags.
     - Download the specified number of images.
     - Create a ZIP file and trigger an automatic download.

4. **Example**:
   ```python
   search_url = "https://e621.net/posts?tags=hug"
   max_images = 10
   include_gif_video = False
   save_path = "/content/e621_test_2"
   ```
---

## Notes
- **API Limits**: Each platform allows a maximum of 320 posts per API request. The script handles pagination automatically.
- **File Formats**: By default, only `jpg`, `jpeg`, and `png` are downloaded. Enable `include_gif_video` for additional formats.
- **Errors**: The script includes basic error handling for API failures, JSON parsing issues, and download errors.
