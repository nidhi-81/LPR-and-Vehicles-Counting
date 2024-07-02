# License Plate Recognition and Vehicles Counting

This project demonstrates a implementation of automatic car number plate recognition using Python. The code captures an image of a car, processes the image to detect and isolate the number plate, performs Optical Character Recognition (OCR) on the isolated number plate, and stores the recognized car number and entry time in a MySQL database.

The LPR process typically involves several key steps:

1. Image Capture:
    - Images of vehicles are captured using cameras. These images can be in the form of still photos or video frames.

2. Preprocessing:
    - The captured images are preprocessed to enhance their quality and prepare them for further analysis. This may include steps like noise reduction, image resizing, and color conversion.

3. Number Plate Detection:
    - The system detects the region of the image that contains the number plate. This involves using image processing techniques such as edge detection and contour finding.

4. Character Segmentation:
    - Once the number plate is isolated, the individual characters on the plate are segmented. This step involves identifying the boundaries of each character.

5. Optical Character Recognition (OCR):
    - OCR technology is applied to the segmented characters to convert them from images to text. Tesseract-OCR is one of the popular open-source OCR engines used for this purpose.

6. Data Storage and Retrieval:
    - The recognized text (vehicle registration number) along with additional information such as the time of capture is stored in a database for future reference and analysis.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/LPR-and-Vehicles-Counting.git
    cd LPR-and-Vehicles-Counting
    ```

2. Install the required Python packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Install Tesseract-OCR:
    - [Download and install Tesseract-OCR](https://github.com/tesseract-ocr/tesseract)

4. Update the path to the Tesseract executable in the code:
    ```python
    pytesseract.pytesseract.tesseract_cmd = r'C:\Path\To\Tesseract\tesseract.exe'
    ```

5. Set up MySQL and create the necessary database and table.

## Usage

1. Place the image you want to process (e.g., `image7.jpg`) in the project directory.

2. Run the script:
    ```bash
    python script.py
    ```

3. The script will process the image, extract the car number, display intermediate images at various stages, and store the extracted car number along with the entry time in the MySQL database.

## Requirements
- Python
- OpenCV
- Matplotlib
- NumPy
- Imutils
- Pytesseract
- MySQL Connector
- Tesseract-OCR

## Database Setup
1. Install MySQL and create a database named `cars`.
2. Create a table named `data` with the following structure:
    ```sql
    CREATE TABLE data (
        id INT AUTO_INCREMENT PRIMARY KEY,
        car_number VARCHAR(255),
        entry_time DATETIME
    );
    ```
