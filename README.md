# Assessment of the effectiveness of various datasets in locating overload in CLT structures using AI

Dataset and associated Jupyter notebooks for validating the effectiveness of various datasets in identifying overloads in a CLT structure using machine learning algorithms 

---

## File organization

The files are organized based on the sequential execution of the phases of the associated research project and according to the datasets on which each of those phases is based. A preliminary phase is included (files named **“0_<filename>”**) related to the identification of the variables to be used by the machine learning algorithms. In this previous phase, the datasets used are **“2_OMA_600.csv” ->** and **“0_IdentifyModes_XY.csv” ->** (for the case of filtered data).

Each of these phases generally consists of 3 files: 
- **“X_<dataset_name>.csv” ->** Dataset on which the corresponding analysis is performed.
- **“X_0_EDA_<dataset_name>.ipynb”** -> Preliminary exploratory analysis of the variables.
- **“X_1_ClasificationMulticlass_<dataset_name>.ipynb”** -> Training and validation of machine learning models using the corresponding dataset.

In the case of RMS, an additional dataset (**“1_RMS_validation_C2.csv”**) is included with data to validate the robustness of the proposed methodology.

The execution of these notebooks had been carried out through Google Colab, though the actual uploaded version have been modified in order to allow its local execution.

Furthermore, when uploading files to GitHub, there was a restriction preventing the upload of files larger than 25 MB. Consequently, the data files for steps 2 (600 s) and 3 (60 s), which exceeded this limit, were compressed into the file *Large_files.zip*.

---

## Variables

This section represents an analysis of the different variables of the various datasets available. First of all, there are some of them that are shared no matter the type of data that is being considered (modal parameters or RMS):

- **Cuadricula** -> Position in which the weight is located (scenarios 0 to 9 but in a grid-based numbering system, A1 to C3).
- **Peso** -> The amount of weight on the structure
- **Fecha** -> Datetime in which the data were generated.

On the one hand, the RMS data includes columns from **Sigma0** to **Sigma 23**, which indicate the RMS value of the corresponding acceloremeter.

On the other hand, the OMA data includes the modal parameters obtained, whose quantity depends on 2 parameters: **i** (number of modes identified) and **j** (number of accelerometers available).

- **fi** -> Natural frequency associated to mode i. Represents the frequency at which the structure oscillates freely.
- **xi** ->  Damping coefficients associated to mode i. Indicates the system’s ability to dissipate energy.
- **phi_re_i_j** -> Real part of the modal shape associated to mode i and accelerometer j. Describes the deformation or movement pattern of the structure for each of its natural modes.
- **phi_im_i_j** -> Imaginary part of the modal shape associated to mode i and accelerometer j. Describes the deformation or movement pattern of the structure for each of its natural modes.
