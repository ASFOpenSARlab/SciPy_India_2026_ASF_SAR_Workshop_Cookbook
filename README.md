# SciPy India 2026: Alaska Satellite Facility NISAR Workshop 

<img src="assets/ASF_logo.svg" alt="thumbnail" width="300"/>

[![nightly-build](https://github.com/ASFOpenSARlab/ASF_Cookbook_Template/actions/workflows/nightly-build.yaml/badge.svg)](https://github.com/ASFOpenSARlab/ASF_Cookbook_Template/actions/workflows/nightly-build.yaml)

## Motivation

Session 2 of this workshop introduces NISAR and walks participants through real-world applications with various NISAR products. 
## Authors

Alex Lewandowski, Julia White 

### Contributors

<a href="https://github.com/ASFOpenSARlab/ASF_Cookbook_Template/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=ASFOpenSARlab/ASF_Cookbook_Template" />
</a>

### I: The NISAR Mission 

- NISAR mission overview
- Overview of NISAR products
- Useful resources for accessing and using NISAR data 

### II: Using NISAR GCOV Data 
- What is NISAR GCOV data?
- What is in a NISAR GCOV file?
- What are the applications for GCOV data? - this might be covered in section 1: useful resources for NISAR data 

### III: Using NISAR GUNWs 

(Add content for this section, e.g., "Example workflows include ... ")

## Running the Notebooks

### Running in a Jupyter Hub

If you are working in a Jupyter Hub that allows you to build Pixi environments, such as [OpenSARLab](https://opensarlab-docs.asf.alaska.edu/user-guides/opensarlab/), use the following steps to run the notebooks in this cookbook.

1. Clone the repository:

   ```bash
    git clone https://github.com/your_account/your_cookbook.git
   ```

1. Run the `notebooks/software_environment.ipynb` notebook.

### Running on Your Own Machine

If you are interested in running this material locally on your computer, you will need to follow this workflow:

(Replace "your_account/your_cookbook" with the GitHub org or user name and title of your cookbook repository)

1. Create a copy of this Cookbook template repository, by clicking the `Use this template button` and selecting the `Create a new repository` option on this [repository's GitHub page](). 

1. Clone the new repository:

   ```bash
    git clone https://github.com/your_account/your_cookbook.git
   ```

1. Move into the `your_cookbook` directory
   ```bash
   cd your_cookbook
   ```
1. Launch in Jupyter Lab with the included Pixi environment
    ```bash
    pix run lab
    ```
