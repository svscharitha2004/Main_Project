 ▶️ Running the Project in Google Colab (All Modes)

This project is fully compatible with **Google Colab** and can run in
multiple runtime configurations.

------------------------------------------------------------------------
🚀 1. Open in Google Colab

1.  Go to: https://colab.research.google.com\
2.  Click **Upload** and upload your `fraud_2.py` or `.ipynb` file\
3.  Upload dataset (`.xlsx`) to `/content/sample_data/`

------------------------------------------------------------------------

⚙️ 2. Runtime Types in Colab

  -----------------------------------------------------------------------
  Runtime Type         When to Use                       Performance
  -------------------- --------------------------------- ----------------
  CPU                  Small dataset, testing            Slow

  GPU (Recommended)    Deep learning training            Fast

  High-RAM CPU         Large dataset handling            Medium

  TPU                  Not suitable for PyTorch          Not Recommended
                       Geometric                         
  -----------------------------------------------------------------------

------------------------------------------------------------------------
 🔁 3. How to Enable Each Runtime

Enable GPU (Best Option)

1.  Runtime → Change runtime type\
2.  Select Hardware accelerator → GPU\
3.  Click Save

Check GPU:

``` python
import torch
print(torch.cuda.is_available())
```

------------------------------------------------------------------------

 Enable High-RAM

1.  Runtime → Change runtime type\
2.  Enable High-RAM (if available)

------------------------------------------------------------------------

 TPU (Not Recommended)

-   PyTorch Geometric does NOT support TPU properly\
-   Avoid selecting TPU

------------------------------------------------------------------------
 📦 4. Install Dependencies

``` bash
pip install pandas numpy matplotlib seaborn scikit-learn xlrd
pip install torch
pip install torch-geometric
pip install torch-scatter torch-sparse torch-cluster torch-spline-conv -f https://data.pyg.org/whl/torch-2.2.0+cpu.html
```

------------------------------------------------------------------------

📁 5. Upload Dataset

 Manual Upload

``` python
from google.colab import files
files.upload()
```

 Google Drive

``` python
from google.colab import drive
drive.mount('/content/drive')
```

Update path:

``` python
file_path = "/content/drive/MyDrive/PaySim.xlsx"
```

------------------------------------------------------------------------

 ▶️ 6. Run the Project

Run steps: 1. GPU check\
2. Data loading\
3. Preprocessing\
4. Graph creation\
5. Model training\
6. Evaluation\
7. Visualization

Or: Runtime → Run all

------------------------------------------------------------------------

 📊 7. Expected Outputs

-   Dataset summary\
-   Fraud distribution\
-   Outlier boxplot\
-   Confusion matrix\
-   Performance metrics\
-   Accuracy, Precision, Recall, F1 Score

 💾 8. Model Output

Saved file: paysim_gcn_model.pth

Download:

``` python
from google.colab import files
files.download("paysim_gcn_model.pth")
```

------------------------------------------------------------------------

 ⚡ 9. Performance Comparison

  Mode       Time     Recommendation
  ---------- -------- ----------------
  CPU        Slow     Testing only
  GPU        Fast     Best choice
  High-RAM   Medium   Large datasets
  TPU        N/A      Avoid

------------------------------------------------------------------------

🛠️ 10. Common Errors & Fixes

### torch-geometric install issue

``` bash
pip install torch-scatter -f https://data.pyg.org/whl/torch-2.2.0+cpu.html
```

 File not found

-   Check file path\
-   Upload dataset again

 GPU not detected

-   Enable GPU\
-   Restart runtime

Memory crash

-   Use High-RAM\
-   Reduce dataset size

------------------------------------------------------------------------
📌 Conclusion

This setup ensures smooth execution of the GCNN fraud detection model in
all Google Colab environments. GPU is strongly recommended for optimal
performance.

