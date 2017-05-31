# WSSTestHandler
A test web handler for the IRIS Web Service Shell.

The program by default produces a set of random values (default=50) in a specified
format type of either text (default), xml, or a zip of text files with 
up to 10 random values in each file. The number of values 
returned is defined by the num_values parameter.

Various handler exit sequences can be manually triggered
via the command line handler.

Example error sequences:
------------------------
force a *runtime* error with a stack trace 3 levels deep

```.../irisws/wsstest/1/query?force_error=runtime&runtime_error_level=3&nodata=404```

force an exception with exit code 1 *before* writing data to std-out

```.../irisws/wsstest/1/query?force_error=before&force_exit_code=1&nodata=404```

force an exception with exit code 3 *after* writing data to std-out

```.../irisws/wsstest/1/query?force_error=after&force_exit_code=3&nodata=404```

sleep for 5 seconds and force an exception with exit code 1 *before* writing data to std-out

```.../irisws/wsstest/1/query?force_sleep=5&force_error=before&force_exit_code=3&nodata=404```

force an exception with exit code 1 *before* writing data to std-out and write a cutom error message to std-error

```.../irisws/wsstest/1/query?force_error=before&force_exit_code=1&error_msg='my custom error message'&nodata=404```
