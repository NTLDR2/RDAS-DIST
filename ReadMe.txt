Lzip7z

http://www.tc4shell.com/en/7zip/lzip/
Copyright (C) 2017 Dec Software.

Lzip7z is a small plugin for the popular 7-Zip archiver. You can use Lzip7z to
open, modify, or create .lz archives that are widely used on Unix-like systems.

INSTALLATION

To install the plugin into the 7-Zip installation folder, you need to create the
"Formats" subfolder. After that, copy Lzip.64.dll or Lzip.32.dll (depending on
your 7-Zip edition) and Lzip.ini to that subfolder. If you do that, each time
you launch 7-Zip, it will automatically find Lzip7z and use it when opening
.lz files.

USING

Unpacking

An .lz archive can contain only one file, which is typically a .tar file
("tarball"). Unix systems traditionally use the .tar format to pack multiple
files. To access an arbitrary file contained in the .tar file, 7-Zip extracts
its entire contents to a temporary directory.

In some cases an .lz file may consist of multiple independently decompressible
data sections (a "multimember archive"). If that is the case, 7-Zip can access
an arbitrary file in the .tar file without creating a temporary file. Lzip7z
inherently supports that mode. You can disable the support for that mode by
modifying the .ini file in the plugin directory. By default, the .ini file
contains the following strings:

[lzip] 
StreamSupport=1
MaxMemberSize=67108864

If you change the value of the StreamSupport parameter to 0, 7zip will always
create temporary files. The MaxMemberSize parameter sets the maximum allowed
size of an unpacked data section in bytes for accessing the contents of the .tar
file without creating a temporary file.

Packing

If you want to pack a single file to an .lz archive, select the "lzip" option in
the "Archive format" drop-down list. If you need to pack multiple files to a
single .lz archive, first pack all of them to a container file (for example,
.tar), and then pack that file to an .lz archive.
 
You can also enter additional parameters into the Parameters text input field.

The parameter d sets the dictionary size in bytes. The minimum allowed size is 4
KB, and the maximum allowed size is 512 MB.

The parameter fb sets the number of fast bytes. The minimum is 5, and the
maximum is 273.

The parameter s sets the size of an unpacked independently decompressible data
section in bytes.
