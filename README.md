# Coin-Counting-ML-Model-SLIPD-Campus
This is a trained Machine learning model 

Technologies and Data used:

When extracting objects like coins from an image, the workflow relies on specific data structures and libraries commonly used in Python development environments.

The Data (Pixels as Matrices): An input image is not seen as a picture by the computer, but as a massive grid of numbers (a matrix). Each number represents a pixel's color and brightness.

Computer Vision Libraries: Frameworks like OpenCV (cv2) or Scikit-Image are typically used to mathematically alter these pixel matrices.

Visualization Tools: The 1000x800 figure generated in my notebook is created using Matplotlib, which plots the processed image arrays back into a visual format humans can easily view.

About the algorithm used :

Canny Edge Detection: The algorithm sweeps across the image matrix looking for high-contrast borders, turning a standard photo into a black-and-white outline.

Contour Finding: Once edges are drawn, a contour algorithm traces closed loops. If a loop is roughly circular and meets a certain size threshold, the algorithm flags it as a "coin."

Regression : linear

When extracting the coins, Regression is the mathematical engine used to predict exact numerical values, specifically for location and confidence.

Bounding-Box Regression: To extract the coin, the algorithm must predict four continuous numbers: the X and Y coordinates of the coin's center, and the Width and Height of the box enclosing it. The regression model calculates the difference between its guessed coordinates and the real coordinates, constantly adjusting its math until the box fits perfectly.

<img width="1000" height="600" alt="image" src="https://github.com/user-attachments/assets/80c77c60-4d79-4d2e-a738-031e21e088f2" />


Logistic Regression (Confidence Scoring): The system uses a regression curve to predict a value between 0.0 and 1.0 representing how confident it is that the object inside the box is actually a coin (e.g., a score of 0.95 means 95% confident).
