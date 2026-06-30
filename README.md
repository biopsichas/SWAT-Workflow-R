# 💧 SWAT+ Modelling Workflow in R

### 📅 A toolbox for preparing SWAT+ setups using the COCOA approach, calibrating and validating models, running NBS scenarios, and analyzing outputs.

This flash drive contains a completely self-contained, portable computing ecosystem. You do **not** need to install R, RStudio, or any geospatial software on your personal machine.

> **⚠️ CRITICAL STEP BEFORE RUNNING:**
> If your laptop syncs your `Desktop` or `Documents` folders automatically to **OneDrive**, **iCloud**, or any other cloud storage service, running the bundle from there will cause background system crashes. Make sure this folder is sitting on a physical, unsynced local drive partition (e.g., `C:\Workshop_bundle`) or run it directly from the workshop flash drive!

## 📂 Workshop Bundle Structure Map

Your environment is organized exactly as mapped out below. Do not move or rename any internal folders, as the launch scripts depend on this specific structure to locate software paths:

```
📁 Workshop_bundle/                  (Main Root Folder)
├── 📁 bin/                          (Internal workspace support tools: WBT, SWAT exe, etc.)
├── 📁 renv/                         (Isolated master library containing package bundles)
│   └── 📁 library/                  (Pre-installed R packages like sf and gdal)
├── 📁 R-Portable/                   (Pre-configured, self-contained R 4.5.1 core engine)
│   └── 📁 bin/x64/                  (True isolated 64-bit engine executable)
├── 📁 RStudio-Portable/             (Stand-alone desktop IDE interface)
├── 📁 Setup/                        (Contains exercise project templates and resources)
│   ├── 📁 _Workflow_docs/           (Directory for workflow documents)
│   ├── 📁 1_Setup/                  (Target directory for Module 1)
│   └── 📁 2_SWATdoctrR/, 3_CropYield/, 4_RiverDischarge/, 5_NBS/
├── 📄 renv.lock                     (System configuration environment state file)
├── 📄 README.html                   (This instruction guide)
├── ⚙️ st1_run.bat                   (Launches Module 1 Environment)
├── ⚙️ st2_run.bat                   (Launches Module 2 Environment)
└── ⚙️ st3_run.bat / st4_run.bat ...  (Launches subsequent sections)
```

## 1. Standard Step-by-Step Launch

To begin working on the corresponding sections of the course material, simply double-click the designated automation script found in the main folder:

1. Navigate to your main `Workshop_bundle` directory.
2. Locate the setup batch file for your active module (e.g., `st1_run.bat`).
3. Double-click the file. A black command window will open, automatically verify your environment health, wipe old cached states, and launch **Portable RStudio** fully connected to your data.

## 2. Automated Environment Guardrails

When you start a module, our script runs behind-the-scenes checks to make sure your computer is seeing the software exactly as intended. It tests and locks down:

- **RStudio Version:** Validates a matched build (`2026.05.0 Build 218`).
- **R Computational Engine:** Locks strictly into `R version 4.5.1 "Great Square Root"`.
- **Geospatial Libraries:** Hard-wires environment variables to use the embedded `PROJ` and `GDAL` databases directly from the drive, eliminating system path conflicts.

## 3. Advanced Troubleshooting via Command Prompt (CMD Shortcut)

If an automation script closes immediately due to a system restriction, you can launch it using an interactive terminal shortcut. This keeps the window open so you and the instructor can inspect the text stream for path warnings.

### The Address Bar Terminal Shortcut:

1. Open the main `Workshop_bundle` folder in Windows File Explorer.
2. Click directly on an empty space inside the **Address Bar** at the top of your window (where the folder paths are displayed).
3. Type `cmd` over the path text and press **Enter**. A Command Prompt window will pop open, pre-targeted directly to your active folder directory!
4. Inside the black console window, use tab completion to run your module script safely. Type the first three letters of your module script:
   ```
   st1
   ```
5. Press the **Tab key** on your keyboard. Windows will automatically complete the rest of the file name for you:
   ```
   st1_run.bat
   ```
6. Press **Enter** to run the environment diagnostics interactively.

### Checking the core R Engine manually:

If you need to verify if the underlying 64-bit computation binary is responding independently of RStudio, execute this command within your opened console:

```
R-Portable\bin\x64\R.exe --version
```

A successful configuration will output a metadata block reading exactly:
`R version 4.5.1 (2025-06-13 ucrt) -- "Great Square Root"`.

## 📚 References and Further Reading

For detailed methodology, protocols, and scientific background, please refer to the following peer-reviewed literature:

- Schürz, C., Čerkasova, N., Farkas, C., Nemes, A., Plungė, S., Strauch, M., Szabó, B., Piniewski, M., 2022. **OPTAIN modelling protocols. Part 1: SWAT+ modelling protocol for the assessment of water and nutrient retention measures in small agricultural catchments** (Deliverable D4.2/a). EU Horizon 2020 OPTAIN Project, Grant Agreement No. 862756. <https://doi.org/10.5281/zenodo.7462415>.
- Szabó, B., Kassai, P., Plungė, S., Čerkasova, N., et al., 2024. **Addressing soil data needs and data gaps in catchment-scale environmental modelling: the European perspective**. SOIL 10 (2), 587–617. <https://doi.org/10.5194/soil-10-587-2024>.
- Plungė, S., Schürz, C., Čerkasova, N., Strauch, M., Piniewski, M., 2024a. **SWAT+ model setup verification tool: SWATdoctR**. Environ. Modell. Software 171. <https://doi.org/10.1016/j.envsoft.2023.105878>.
- Plungė, S., Szabó, B., Strauch, M., Čerkasova, N., Schürz, C., Piniewski, M., 2024b. **SWAT+ input data preparation in a scripted workflow: SWATprepR**. Environ. Sci. Eur. 36 (1). <https://doi.org/10.1186/s12302-024-00873-1>.
- Piniewski, M., Čerkasova, N., Plungė, S., Strauch, M., Schürz, C., et al., 2026. **Enhanced crop calibration for SWAT+: evaluating water, sediment and nutrient impacts across ten European catchments**. Environ. Model. Software 196, 106794. <https://doi.org/10.1016/j.envsoft.2025.106794>.
- Plungė, S., Schürz, C., Strauch, M., Piniewski, M., 2026. **SWATtunR: A transparent and reproducible workflow for scripted SWAT+ calibration in R**. Environ. Modell. Software 203, 107014. <https://doi.org/10.1016/j.envsoft.2026.107014>.
