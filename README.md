# Qt UI file sorter

When loading, editing and saving a Qt UI file with Qt Designer, Qt designer will not respect the order of xml items. Instead the order will change seemingly at random.

This behavior is unfriendly to version control.

Currently the tool supports:
- Sort the children of QGridLayout by row-column order
- Remove stdset="0" attributes
- Remove native="true" attributes

Problem is discussed further here:

https://stackoverflow.com/questions/65463217/qt-ui-file-xml-order-qgridlayout-row-order-leads-to-large-commit-differences/65778726?noredirect=1#comment116324573_65778726


Installation:
```sh
git clone git@github.com:davidosterberg/Qt-UI-file-sorter.git
```

Usage:
```sh
sort_ui [-h] [-o outfile] [--no-sort-qgridlayout] [--no-remove-stdset] [--no-remove-native] filename
```

Example:
```sh
sort_ui examples/TaskHoleParameters.ui
```
will sort the supplied unsorted ui file overwriting the original.

## Usage on Windows

1. Create the file sort_ui.bat with this content
```sh
set PATH=C:\Projects\FreeCADLibs_12.1.3_x64_VC15\bin;%PATH%

cd C:\Projects\sort_ui
python.exe sort_ui "%~f1"
```

2. Adjust the paths to your setup.
3. The lxml module can be fetched from here: https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml
whl is a compressed format (probably zip) that can be opened with 7-zip. Drag and drop the content to the directory of sort_ui.bat


Now just drag and drop a ui file to the sort_ui.bat file.
