# license-automator
Automate putting licenses into all your C++ headers and source files! 

This project will recursively go through directories looking for files with the ``.cpp`` or ``.hpp`` file endings, although more flexibility will be available in the future. 

Each file will be evaluated to see if it contains the old license (optional), and if found it will be replaced by the new license, else, if an old license is not specified, it will just append the new license to the beginning of the file.

This uses Python **3**

## Usage

### Step 1
Create a file with the license you want to put in all the files. A tip is to add the comment "operator" that you prefer to use, such as a ``//`` before each line.

**Put 2 extra lines at the bottom of the license file. Otherwise, it will not work and you will get errors.**

### Step 2
Run the Python script from the directory you are wanting to add licenses to the files from. Use the following command line arguments:

```
python3 licensor.py -c THE_FILE_THAT_YOUR_LICENSE_IS_IN
```

There are more command line parameters, such as directories that you would like to exclude, OR, the old license in most files that you would like to replace.

To use directory excludes, use the ``-e`` parameter as so:
```
python3 licensor.py -c THE_FILE_THAT_YOUR_LICENSE_IS_IN -e ./build ./third_party ./doNotPutLicensesInThisDirectory
```

To replace an old license in all sources with a new license, use:
```
python3 licensor.py -c THE_FILE_THAT_YOUR_LICENSE_IS_IN -o THE_FILE_THAT_YOUR_OLD_LICENSE_IS_IN
```
You can still add excludes to this combination of commands.
