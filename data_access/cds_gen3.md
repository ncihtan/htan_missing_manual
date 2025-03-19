---
order: 993
---

HTAN files avaliable througn the NCI CRDC Cancer Data Service can be downloaded in the terminal using the [gen3-client](https://docs.gen3.org/gen3-resources/user-guide/). The gen3-client provides an easy-to-use, command-line interface for uploading and downloading data files to and from a Gen3 data commons from the terminal or command prompt, respectively.


## Step-by-step guide

### Step 1: Install the Gen3-client

- Follow the [Gen3-client install instructions](https://gen3.org/resources/user/gen3-client/#1-installation-instructions) for your operating system.

### Step 2: Obtain and Configure API Credentials

- Log in to the NCI Commons Framework at [nci-crdc.datacommons.io](https://nci-crdc.datacommons.io).
- Go to your profile settings, create a new API key, and download the credentials.json file.

### Step 3: Configure the gen3-client

- Configure a profile for the gen3-client that points towards your credentials and the NCI CRDC endpoint.

    ```
    gen3-client configure \
        --profile=<your-profile-name> \
        --cred=<path-to-your-credentials-json> \
        --apiendpoint=https://nci-crdc.datacommons.io
    ```


### Step 4: Select Files from the HTAN Data Portal

- Go to the HTAN Data Portal and filter the files based on your criteria (e.g., open access CDS files).
- Select the files you want to download.

### Step 5: Use the Gen3 Client to Download Files

- Select the "Download files" link and view the the gen client command for your selected files.
- Copy the Gen3-client command and run it in your terminal. Update the profile name and download location as needed. The command should look like this:

    ```
    gen3-client download-multiple \
        --profile=<your-profile-name> \
        --manifest=gen3_manifest.json \
        --download_path=<your-download-location>
    ```