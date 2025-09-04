
import cv2
import numpy as np

# Load an image
image_path = "path/to/your/image.jpg"
image = cv2.imread(image_path)

if image is None:
    print("Error: Could not load image.")
else:
    # Convert to grayscale
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

    # Apply a Gaussian blur
    blurred_image = cv2.GaussianBlur(gray_image, (5, 5), 0)

    # Perform edge detection using Canny
    edges = cv2.Canny(blurred_image, 100, 200)

    # Display or save the processed image
    # cv2.imshow("Edges", edges)
    # cv2.waitKey(0)
    # cv2.destroyAllWindows()
    cv2.imwrite("output_edges.jpg", edges)
    print("Image processing complete. Edges saved to output_edges.jpg")
