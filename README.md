# Coin-Counting-ML-Model-SLIPD-Campus
This is a trained Machine learning model 

🛠️ Technologies and Data Used :
When extracting objects like coins from an image, the workflow relies on specific data structures and libraries commonly used in Python development environments.

🧮 The Data (Pixels as Matrices): An input image is not seen as a picture by the computer, but as a massive grid of numbers (a matrix). Each number represents a pixel's color and brightness.

👁️ Computer Vision Libraries: Frameworks like OpenCV (cv2) or Scikit-Image are typically used to mathematically alter these pixel matrices.

📊 Visualization Tools: The 1000x800 figure generated in my notebook is created using Matplotlib, which plots the processed image arrays back into a visual format humans can easily view.

🧠 About the Algorithm Used
🔪 Canny Edge Detection: The algorithm sweeps across the image matrix looking for high-contrast borders, turning a standard photo into a black-and-white outline.

⭕ Contour Finding: Once edges are drawn, a contour algorithm traces closed loops. If a loop is roughly circular and meets a certain size threshold, the algorithm flags it as a "coin."

📐 Regression Analysis
When extracting the coins, Regression is the mathematical engine used to predict exact numerical values, specifically for location and confidence.

📦 Bounding-Box Regression: To extract the coin, the algorithm must predict four continuous numbers: the X and Y coordinates of the coin's center, and the Width and Height of the box enclosing it. The regression model calculates the difference between its guessed coordinates and the real coordinates, constantly adjusting its math until the box fits perfectly.

📉 Understanding the Graph
📏 The Axes (The Variables):

Bottom Axis (X-Axis): This represents the actual, physical diameter of the coins in millimeters. This is known as the Independent Variable because it is a set physical fact that doesn't change.

Left Axis (Y-Axis): This represents how many pixels wide the coin appears on the screen. This is the Dependent Variable because the number of pixels depends on how big the actual coin is.

🟡 The Dots (The Data): Each dot represents a single detected object in the image. The gold dots highlight the "5 distinct coins" mentioned in your project. Notice how the dots don't form a perfectly straight line? In the real world, lighting, shadows, and the camera angle cause slight variations in how many pixels an object takes up.

📈 The Red Line (The Regression): This is the Line of Best Fit. The regression algorithm looked at all the scattered dots and used math to draw a straight line straight through the middle of them, keeping the distance from the line to every single dot as small as possible.

Why is this useful? Because of this red line, the computer can now predict things it hasn't seen yet. If you slide a brand-new coin under the camera that measures exactly 23 mm wide, the computer can follow the red line and instantly predict that it will take up roughly 360 pixels on the screen, allowing it to accurately draw a bounding box around it.

📂 Datasets & Workflow
💡 This is not a complex ML Model.

📸 1. The Original Photo (coins.jpg): This is exactly what it sounds like: the starting picture file of the coins. It is the raw image you feed into the program.

💻 2. The Computer's Version (image): Computers cannot "see" photos like humans do; they only read numbers. This step translates the original photo into a giant grid of numbers (representing colors and pixels) so the code can read and edit it.

🔲 3. The Outlines (unique_boxes): Imagine drawing a tight, invisible square around every single coin in the photo. This is just a list of measurements (where the box starts, how wide it is, and how tall it is) so the computer knows exactly where each coin is located.

🪙 4. The Cut-Out Coins (extracted_coins): This is your final result. The program uses the outlines from the previous step like a cookie cutter. It chops up the main photo into smaller pieces, giving you a separate, individual picture of every single coin.

🎯 Confidence Scoring
💯 Logistic Regression (Confidence Scoring): The system uses a regression curve to predict a value between 0.0 and 1.0 representing how confident it is that the object inside the box is actually a coin (e.g., a score of 0.95 means 95% confident).
