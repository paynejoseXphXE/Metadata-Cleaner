# Metadata Remover
python script to remove all EXIF metadata from image batch

To use this script, save it as clean_image_metadata.py and run it from the command line like this:

python clean_image_metadata.py /path/to/input/folder /path/to/output/folder

or

python clean_image_metadata.py /path/to/image/file.jpg /path/to/output/folder

If you don't specify an output folder, the cleaned files will be saved in a folder with the same name as the input folder or file, with the suffix "_cleaned" added.


The create_output_folder decorator takes a function as its argument, and returns a new function that first checks if the output_folder keyword argument is None. If it is, the decorator creates an output folder with the same name as the input folder, with the suffix "_cleaned" added. The new function then calls the original function with the same arguments and keyword arguments as before, but with the output_folder keyword argument set to the newly created output folder (if applicable).

In the clean_image_metadata function, we use the @create_output_folder decorator to add the functionality of creating the output folder if it doesn't exist. We also modify the function to take the output_folder keyword argument instead of generating it from the input folder, since the decorator will take care of that.

In the main block, we now pass the output_folder keyword argument to the clean_image_metadata function when cleaning all image files in a folder.
geeluwlq