# Image-Demoireing
reduces/eliminates moire patterns
Removes moiré patterns (the coloured wavy lines you get when photographing a screen) from images. This project has a small web page where you upload an image and get the cleaned result, plus the code to train the model that does the cleaning.

Important: this project does not include trained weights.

What's in the folder
File	What it does
app.py	The web page (Gradio). Upload an image, get the cleaned image back.
infer.py	Cleans one image from the command line; also used by the app. Handles big photos in tiles.
model.py	The model (DemoireNet, a small residual U-Net).
train.py	Trains the model on pairs of moiré and clean images.
requirements.txt	Python packages needed.
run_windows.bat	Windows: double-click to install everything and start the app.
SPACE_README.md	Settings file for Hugging Face Spaces. Hosting there now needs a paid plan, so you can ignore it.
Requirements
Python 3.10 or newer (add it to PATH when installing on Windows)
An NVIDIA GPU is recommended for training. Running the app works fine on a normal CPU.
Quick start

Windows: double-click run_windows.bat. The first run installs packages, which takes several minutes.

Any system, by hand:

python -m venv .venv
.venv\Scripts\activate            (Mac/Linux: source .venv/bin/activate)
pip install -r requirements.txt
python app.py

Then open http://127.0.0.1:7860 in your browser (it usually opens by itself), upload a photo, and press Submit. The Tile size slider controls memory use: lower it if the app runs out of memory on big photos.
