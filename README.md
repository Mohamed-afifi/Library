Image Annotation and OCR Extraction
This Python script processes annotated images, crops sub-images based on annotations, and extracts metadata along with OCR information. The program is designed to work with specific journal types such as "Akher Saa," "Al Aroussa," "AlMusawwar," and "AlKawakeb."

Requirements
Python 3.x
OpenCV (cv2)
OpenPyXL (openpyxl)
Segment Anything (segment_anything)
Torch (torch)
Supervision (supervision)
Arabic OCR (ArabicOcr)
Usage
Ensure that all the required libraries are installed. You can use the following command to install dependencies:

bash
Copy code
pip install opencv-python openpyxl segment-anything torch supervision
Download the Arabic OCR library (ArabicOcr) and make sure it's accessible.

pip install 'git+https://github.com/facebookresearch/segment-anything.git'

pip install -q roboflow supervision

!wget -q 'https://dl.fbaipublicfiles.com/segment_anything/sam_vit_h_4b8939.pth'

!pip install ArabicOcr

!pip install openpyxl

from google.colab import drive

drive.mount('/content/drive')

Adjust the folder_path variable to point to the directory containing the annotated images.

Run the script:

bash
Copy code
python image_annotation_ocr.py
Input Structure
The annotated images should be placed in the specified folder (folder_path).
The script assumes specific journal types based on file names ("Akher-Saa," "Al Aroussa," "AlMusawwar," "AlKawakeb").
Output Structure
Cropped sub-images will be saved in the images folder.
Metadata, including journal name, public number, polishing year, page number, general OCR, and Arabic OCR, will be stored in the output.xlsx file.
Notes
The script utilizes the segment_anything library for automatic mask generation.
The Arabic OCR extraction relies on the ArabicOcr library.
Ensure that the file names of the annotated images match the expected patterns for each journal type.
License
This project is licensed under the MIT License.

