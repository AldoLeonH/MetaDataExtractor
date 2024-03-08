# MetaDataExtractor
The inability to view DLL files, EXE files, or any applicable content within our compliance tool called BlackDuckHub posed a challenge. As a solution, a script was developed to facilitate the visualization of metadata for each binary file contained within a folder. This implies that the script must be recursive to access all the information.

**This script only works on Windows environment**

## Installation

```bash
git clone https://github.com/AldoLeonH/MetaDataExtractor.git
```

## Usage


This Python script facilitates the extraction of metadata from binary files within a specified directory. To use the script, execute it from the directory to be scanned, providing the following flags:

### Flags

**-p or --name**: The project name.

**-v or --version**: The project version.

**--output** (optional): The output folder for the results. If not specified, the script creates an "OutputBinariesMetadata" directory in the script's location.

The script recursively processes binary files, runs a PowerShell command on each file, and saves the results in a text file. It skips files without Product and ProductVersion metadata. The script provides a summary of processed files and their extensions at the beginning of the output file.

### **Important Note**
**Caution: Do not execute this command from your home directory.** The script constructs commands based on the location where it is executed. Running it from the home directory may result in unintentional metadata extracting of all directories and cause errors. Always navigate to the desired directory before using the script.

Remember to include the BA in the Project Name

```bash
python3 onlyBinaries.py -p [project_name] -v [project_version] --output [output_folder]

```
### Example

```bash
python3 onlyBinaries.py -p [AM_HLA403TH35] -v [MS11_12.0.3] --output [C:/Users/uig12345/Documents/OutputBinariesExtract]
```


## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

## License

[MIT](https://choosealicense.com/licenses/mit/)
