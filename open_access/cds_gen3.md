---
order: 993
---

HTAN files avaliable througn the NCI CRDC Cancer Data Service can be downloaded in the terminal using the gen3 commend line client.

## Video walkthrough

<div style="position: relative; width: 75%; height: 0; padding-bottom: 56.25%;"><iframe src="https://us02web.zoom.us/clips/embed/Qkzr91sZyUvEHQL9DPVcpyS-0snpuI1-2TmAvroBqUk6UWvoxm2qlQl8xXWFEyKA6lUSJ2rQ5_u1mWxvsobpC90k.XD-nLVM2nku3XLvB" frameborder="0" allowfullscreen="allowfullscreen" style="position: absolute; width: 100%; height: 100%; top: 0; left: 0; "></iframe></div>

## Step-by-step guide



### Step 1: Set Up Your Environment

- Open your terminal and create a clean Conda environment (or environment of your choice) with Python 3.11.  
*Note: Python 3.12 is not compatible with the current version of the Gen3 client.*

    ```
    conda create -n gen3_env python=3.11
    conda activate gen3_env
    ```

- Install the Gen3 client by running:

    ```
    pip install gen3
    ```

3.	Verify the Gen3 client installation:

    ```
    gen3 --help
    ```
If help options are displayed, the installation was successful.

### Step 2: Obtain and Configure API Credentials

- Log in to the NCI Commons Framework at [nci-crdc.datacommons.io](https://nci-crdc.datacommons.io).
- Go to your profile settings, create a new API key, and download the credentials.json file.
- In the terminal, create the `.gen3` directory in your home folder if it doesn’t alreadyexist:- 
    ```
    mkdir ~/.gen3
    ```

- Move the credentials.json file to the `~/.gen3/` directory:

    ```
    mv path/to/credentials.json ~/.gen3/credentials.json
    ```


### Step 3: Select Files from the HTAN Data Portal

- Go to the HTAN Data Portal and filter the files based on your criteria (e.g., open access CDS files).
- Select the files you want to download

### Step 4: Use the Gen3 Client to Download Files

- Select the "Download files" link and view the the gen client command for your selected files.
- Copy the Gen3 command and run it in your terminal. The command should look like this:

    ```
    gen3-client download-multiple --profile=nci-crdc --object-ids <GUID1> <GUID2>
    ```

- **Run the command.** This may take a moment. You might see a warning initially, which is typically harmless and does not impact the download process.
- **Verify the Download.** Once the download completes, you should see the files in your directory. You’ll also receive a report showing successful downloads and any failed attempts (if any). For example:
    ```
    (gen3) ataylor@ajt-mbp gen3-test % gen3 --endpoint=nci-crdc.datacommons.io/ drs-pull objects dg.4DFC/6221caa8-7e68-11ee-a468-172bb8261521 dg.4DFC/621d8a38-7e68-11ee-82bd-ef84a2cd1f8d
    [2024-11-01 13:52:21,391][WARNING] Unable to process WTS response. Likely no WTS service running on this commons. Certain commands might fail.
    {"succeeded": ["dg.4DFC/6221caa8-7e68-11ee-a468-172bb8261521", "dg.4DFC/621d8a38-7e68-11ee-82bd-ef84a2cd1f8d"], "failed": []}

    (gen3) ataylor@ajt-mbp gen3-test % ls
    MIBITIFF_MBC_Point17_combined.ome.tiff	MIBITIFF_MBC_Point21_combined.ome.tiff
    ```