.. _faq:


FAQ
===


Are all VISA attributes and methods implemented?
------------------------------------------------

No. We have implemented those attributes and methods that are most commonly
needed. We would like to reach feature parity. If there is something that you
need, let us know.


Why are you developing this?
----------------------------

The `National Instruments's VISA`_ is a proprietary library that only works on
certain systems. We wanted to provide a compatible alternative.


Why not using LibreVISA?
------------------------

LibreVISA_ is still young. However, you can already use it with the NI backend
as it has the same API. We think that PyVISA-py is easier to hack and we can
quickly reach feature parity with NI-VISA for message-based instruments.


Why putting PyVISA in the middle?
---------------------------------

Because it allows you to change the backend easily without changing your application.
In other projects, we implemented classes to call USBTMC devices without PyVISA.
But this leads to code duplication or an adapter class in your code.
By using PyVISA as a frontend to many backends, we abstract these things
from higher level applications.

Pyinstaller can’t find Pyvisa-py, how can I create a standalone executable for distribution to other users?
-----------------------------------------------------------------------------------------------------------

Pyvisa-py is not technically a valid package name.  Therefore, if you try to import it or if you try to use hiddenimports = [‘pyvisa.py’] in Pyinstaller the executable won’t run. 
The workaround is to change the name of your local installation of Pyvisa-py to Pyvisa_py.  
For example you would change your  
somepath\PythonXX_YY\Lib\site-packages\pyvisa-py 
to 
somepath\PythonXX_YY\Lib\site-packages\pyvisa_py.  
In your project you can then import pyvisa_py and run Pyinstaller as normal and you should get a working executable.



.. _PySerial: https://pythonhosted.org/pyserial/
.. _PyVISA: http://pyvisa.readthedocs.org/
.. _PyUSB: https://github.com/pyusb/pyusb
.. _PyPI: https://pypi.python.org/pypi/PyVISA-py
.. _GitHub: https://github.com/pyvisa/pyvisa-py
.. _`National Instruments's VISA`: http://ni.com/visa/
.. _`LibreVISA`: http://www.librevisa.org/
.. _`issue tracker`: https://github.com/pyvisa/pyvisa-py/issues
.. _`linux-gpib`: http://linux-gpib.sourceforge.net/
.. _`gpib-ctypes`: https://pypi.org/project/gpib-ctypes/
