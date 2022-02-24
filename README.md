# QLed

[![PyPI version](https://badge.fury.io/py/QLed.svg)](https://badge.fury.io/py/QLed)

An LED Widget for the PySide2 Framework

![QLed Test Screenshot](https://raw.githubusercontent.com/jazzycamel/QLed/master/QLed_test_screenshot.png)

## Installation
### pip
`$ pip install QLed`

### setup.py
Download or clone this repository and then run

`$ python setup.py install`

## Usage
```python
from PySide2.QtWidgets import QApplication, QWidget, QVBoxLayout
from QLed import QLed

class Widget(QWidget):
    def __init__(self ,parent=None, **kwargs):
        super().__init__(parent, **kwargs)
        
        l=QVBoxLayout(self)
        self._led=QLed(self, onColour=QLed.Red, shape=QLed.Circle)
        self._led.value=True
        l.addWidget(self._led)
        
if __name__=="__main__":
    from sys import argv, exit
    
    a=QApplication(argv)
    w=Widget()
    w.show()
    exit(a.exec_())
```

The simple example above creates a single, circular LED that is red in colour when on.

The available shapes are:

* Circle
* Round
* Square
* Triangle

The available colours are:

* Red
* Green
* Yellow
* Grey
* Orange
* Purple
* Blue

The LED is switched on and off by settings the boolean `value` property (either directly or via the setter function `setValue(bool)`).

## Dependencies
* PySide2
* six

## Tested Platforms/Versions
This module has been tested (recently) with the following configurations

* Windows11, Python 3.8.8, PySide2 5.15.2
