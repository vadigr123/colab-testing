# > Image Downloader for e621, e926, and Danbooru


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


# > File Downloader and Uploader

## Usage
#### Downloading Files
1. **Open the Script in Google Colab**:
2. **Configure Settings**:
   - `urls`: Enter one or more URLs separated by commas (e.g., `http://example.com/file1.zip, http://example.com/file2.zip`).
   - `download_folder`: Define the folder where files will be saved (e.g., `/content/downloads`).

3. **Run the Script**:
   - Execute the cell.
   - The script will download each file to the specified folder and print a confirmation (e.g., `✅ Downloaded: filename`).

4. **Example**:
   ```python
   urls = "https://example.com/test.safetensors"
   download_folder = "/content/downloads"
   ```

#### Uploading to Hugging Face (Optional)
1. **Run the Upload Section**:
   - Files from `local_folder` will be uploaded to the specified `remote_folder` in your Hugging Face repository.

2. **Example**:
   ```python
   token = "your-hf-token"
   repo_id = "yourusername/your-repo"
   local_folder = "/content/downloads"
   remote_folder = "models"
   ```

#### Uploading to GitHub (Optional)
1. **Run the Upload Section**:
   - Files from `local_folder` will be uploaded to the specified `remote_folder` in your GitHub repository.

2. **Example**:
   ```python
   github_token = "your-github-token"
   repo_name = "yourusername/your-repo"
   local_folder = "/content/downloads"
   remote_folder = "files"
   ```

---

## Notes
- **URL Format**: Ensure URLs are valid and accessible. The script uses `wget` for downloads.
- **Hugging Face**: Requires a valid API token with write access to the repository.
- **GitHub**: Requires a Personal Access Token with `repo` scope.
- **Error Handling**: The script assumes basic functionality; add error handling for production use (e.g., checking if URLs are valid or if files already exist).
