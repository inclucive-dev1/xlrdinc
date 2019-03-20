[![Build Status](https://travis-ci.org/python-excel/xlrd.svg?branch=master)](https://travis-ci.org/python-excel/xlrd)
[![Coverage Status](https://coveralls.io/repos/github/python-excel/xlrd/badge.svg?branch=master)](https://coveralls.io/github/python-excel/xlrd?branch=master)
[![Documentation Status](https://readthedocs.org/projects/xlrd/badge/?version=latest)](http://xlrd.readthedocs.io/en/latest/?badge=latest)
[![PyPI version](https://badge.fury.io/py/xlrd.svg)](https://badge.fury.io/py/xlrd)

# Fork of PyPI package `xlrd`

Name of new package: `xlrdinc`

We are currently using a lot of Python-UNO stuff, but have found the original libraries a little unmaintained (or at least slow in responding to bug reports). We do ask that you file issues directly on this repo instead of the original repo we forked from; we have no control over that original repo, and don't foresee timely response from the maintainers of that repo.

---

# Original README...

### xlrd

Please read this before using this library: https://groups.google.com/d/msg/python-excel/P6TjJgFVjMI/g8d0eWxTBQAJ

**Purpose**: Provide a library for developers to use to extract data from Microsoft Excel (tm) spreadsheet files. It is not an end-user tool.

**Author**: Inclucive (forked from John Machin's work)

**Licence**: BSD-style (see licences.py)

**Versions of Python supported**: 2.7, 3.4+.

**External modules required**:

The package itself is pure Python with no dependencies on modules or packages outside the standard Python distribution.

**Outside the current scope**: xlrd will safely and reliably ignore any of these if present in the file:

*   Charts, Macros, Pictures, any other embedded object. WARNING: currently this includes embedded worksheets.
*   VBA modules
*   Formulas (results of formula calculations are extracted, of course).
*   Comments
*   Hyperlinks
*   Autofilters, advanced filters, pivot tables, conditional formatting, data validation

**Unlikely to be done**:

*   Handling password-protected (encrypted) files.

**Particular emphasis (refer docs for details)**:

*   Operability across OS, regions, platforms
*   Handling Excel's date problems, including the Windows / Macintosh four-year differential.
*   Providing access to named constants and named groups of cells (from version 0.6.0)
*   Providing access to "visual" information: font, "number format", background, border, alignment and protection for cells, height/width etc for rows/columns (from version 0.6.1)

**Quick start**:

```python
import xlrd
book = xlrd.open_workbook("myfile.xls")
print("The number of worksheets is {0}".format(book.nsheets))
print("Worksheet name(s): {0}".format(book.sheet_names()))
sh = book.sheet_by_index(0)
print("{0} {1} {2}".format(sh.name, sh.nrows, sh.ncols))
print("Cell D30 is {0}".format(sh.cell_value(rowx=29, colx=3)))
for rx in range(sh.nrows):
    print(sh.row(rx))
```

**Another quick start**: This will show the first, second and last rows of each sheet in each file:

    python PYDIR/scripts/runxlrd.py 3rows *blah*.xls

**Installation**:

*   On Windows: use the installer.
*   Any OS: Unzip the .zip file into a suitable directory, chdir to that directory, then do "python setup.py install".
*   If PYDIR is your Python installation directory: the main files are in PYDIR/Lib/site-packages/xlrd the docs are in the doc subdirectory, and there's a sample script: PYDIR/Scripts/runxlrd.py
*   If os.sep != "/": make the appropriate adjustments.

**Acknowledgements**:

*   This package started life as a translation from C into Python of parts of a utility called "xlreader" developed by David Giffin. "This product includes software developed by David Giffin <david@giffin.org>."
*   OpenOffice.org has truly excellent documentation of the Microsoft Excel file formats and Compound Document file format, authored by Daniel Rentz. See http://sc.openoffice.org
*   U+5F20 U+654F: over a decade of inspiration, support, and interesting decoding opportunities.
*   Ksenia Marasanova: sample Macintosh and non-Latin1 files, alpha testing
*   Backporting to Python 2.1 was partially funded by Journyx - provider of timesheet and project accounting solutions (http://journyx.com/).
*   Provision of formatting information in version 0.6.1 was funded by Simplistix Ltd (http://www.simplistix.co.uk/)

---

# Help Us In Open-Source?

Please help us by alerting us to any related slow projects we should be forking actively.

We are an atypical Singaporean company with a very large pool of engineers we trained for cutting-edge software work. (Singaporean culture completely eschews technical skills in favor of supervisory/managerial jobs; we would argue "non-job" instead.) Our founders are linguists, which was how we trained (and were trained by, believe it or not) non-English engineers in East Asian regions.

Owing to our rapidly expanding knowledge bases (in multiple human languages), we have a cost-efficiency of "*third-world prices for Silicon Valley quality*" (with all due respect to the world's engineers for that "*Silicon Valley*" pop culture reference). We're cost-efficient; we don't run sweatshops.

We will put in substantial engineering effort to maintain and refine any abandoned (and useful) open-source projects, transparently and competently.

# Our Background, Our Gaps

Our main aim is to stem the relentless hacking of our Singaporean systems by weaning from our reliance on outsource vendors (who often are backed by foreign actors with a myriad of unanticipated intents). Our IT expenditure is skyrocketing as we purchase product after product, only to come back and find those products misconfigured by unskilled managers (who hired unskilled engineers).

We have a background in being outsourced vendors ourselves. We are the outsourced R&D arm for several technologically active countries. We are also desperately looking to learn how we can outsource safely. We do admit we had warped our Business Process Outsourcing (BPO) into Business Responsibility Outsourcing over decades.

Talent retention is also something we are dying to learn. We are having problems motivating our students to learn engineering skills (newly minted engineers spend office hours reading books on "*How to be a good CEO*"). Those who do learn competently get enticed to foreign countries. We're literally being hollowed out of technological capabilities.

Help us. And we will help you in return.
