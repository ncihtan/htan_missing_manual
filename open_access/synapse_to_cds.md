
---
order: 993
---

# Guide: Transferring Uncontrolled Data from the HTAN Data Portal to the Cancer Genomics Cloud (CGC)

## Screen Recording Walkthrough
**[HTAN Data Jamboree Tutorial: Getting Uncontrolled Data from the HTAN Portal to SB-CGC](#)**

<div style="position: relative; width: 100%; height: 0; padding-bottom: 56.25%;">
    <iframe src="https://us02web.zoom.us/clips/embed/JNSyNG3rPRoWVYjWrYNiV-Z9Tv-TYIKdb54YLB6pk6CRhhnEQ0g14a4-2hItZXGOYXq3CzcSVjgNTL7HMhHjUm72.cd78QzhYRY4j02Mw" 
            frameborder="0" allowfullscreen="allowfullscreen" 
            style="position: absolute; width: 100%; height: 100%; top: 0; left: 0;">
    </iframe>
</div>

---

## Useful Links

- [SevenBridges CGC](https://cancergenomicscloud.org)
- [Synapse](https://synapse.org)
- [HTAN Data Portal](https://data.humantumoratlas.org)
- [Synapse Python/CLI Client Documentation](https://python-docs.synapse.org)

---

## Step-by-Step Guide

### 1. Start a Data Studio Instance
1. Go to [CancerGenomicsCloud.org](https://cancergenomicscloud.org).
2. Log in and launch a Data Studio instance with JupyterLab.

### 2. Install and Configure Synapse Client
1. Open the Terminal in JupyterLab.
2. Install the Synapse client (if not already installed) by typing:
   ```bash
   pip install synapseclient
   ```
3. Obtain a Personal Access Token:
   - Log into [Synapse.org](https://synapse.org).
   - Go to Account Settings > Personal Access Tokens.
   - Create a new token with “View and Download” permissions and copy the token.
4. Configure Synapse client with the Token:
   - In the JupyterLab Terminal, type:
     ```bash
     synapse config
     ```
   - When prompted, enter your Synapse username (optional) and paste the token.

### 3. Select Files from the HTAN Data Portal
1. Visit the [HTAN Data Portal](https://data.humantumoratlas.org) and find the data files you need (e.g., single-cell RNA-seq data in H5AD format).
2. Click the purple “Download selected files” button for the chosen files.
3. Copy the download commands (e.g., `synapse get syn1234`).

### 4. Download Files into the Data Studio Instance
1. Paste the copied download commands into the JupyterLab Terminal.
2. Verify that the files are in the workspace directory. You can now use these files within notebooks in the Data Studio instance.

### 5. Move Files to Output Folder
- Move files to the `output-files` directory to ensure they sync with your CGC project:
  ```bash
  cp <filename> ../output-files
  ```

### 6. Stop Data Studio Instance
1. Stop the Data Studio instance to trigger synchronization.
2. Check your project files on CGC; the downloaded files should now be available for further use.
