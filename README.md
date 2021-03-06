# Qxlnt

> *Read this in other languages: [English](README.md), :kr: [한국어](README.ko.md)*

<p align="center"><img src="https://github.com/j2doll/Qxlnt/raw/master/markdown-data/Concept-QXlnt.jpg"></p>

![](markdown-data/qxlnt-badge1.png)

- Qxlnt is a helper project that allows xlnt to be used in Qt.
- xlnt is xlsx library that using C++14. See 'License and links' for more information.

## Why did you make it?

- xlnt is a excellent library for using xlsx Excel files. :+1:
- I was looking for a way to make it easy to use in Qt. Of course, cmake is compatible with Qt, but it is not convenient to use. So I created Qxlnt.

## Hello World (HelloQXlnt)

```cpp
#include <iostream>
#include <xlnt/xlnt.hpp>
#include <QCoreApplication>

int main(int argc, char **argv)
{     
    QCoreApplication a(argc, argv); // It is a Qt code.

    xlnt::workbook wb; // It is a xlnt code. Mix it together!
    xlnt::worksheet ws = wb.active_sheet();
    ws.cell("A1").value(5);
    ws.cell("B2").value("string data");
    ws.cell("C3").formula("=RAND()");
    ws.merge_cells("C3:C4");
    ws.freeze_panes("B2");
    wb.save("example.xlsx");

    return 0;
}
```

## Notice :zap:

- C++14 or higher version is required.
	- gcc 4.x(4.8 or below) is not supported. Current(2018) gcc version is 7.x.
	- If you use Visual C++, then use VS 2017 or higher version.

## Test
- Currently in testing now.
- See [Tested Environments](BuildEnv.md)

## To Do
- Testing in various Qt environments. :cloud:
- Unicode Test (filename, file path, data value) :umbrella:

## License and links
- ![](markdown-data/mit-license.png) Qxlnt is under MIT License. [https://github.com/j2doll/Qxlnt](https://github.com/j2doll/Qxlnt)
- ![](markdown-data/mit-license.png) xlnt is under MIT License. [https://github.com/tfussell/xlnt](https://github.com/tfussell/xlnt) 
- ![](markdown-data/mit-license.png) libstudxml is under MIT License. [https://www.codesynthesis.com/projects/libstudxml/](https://www.codesynthesis.com/projects/libstudxml/)
- ![](markdown-data/boost-license.png) utfcpp is under Boost Software License. [http://utfcpp.sourceforge.net](http://utfcpp.sourceforge.net)

## :mailbox: Contact
- Please leave an issue to me. [https://github.com/j2doll/Qxlnt/issues](https://github.com/j2doll/Qxlnt/issues) 
- Hi! I'm j2doll (aka Jay Two). My native language is not English and my English is not fluent. Please, use EASY English. :-)

## Similar projects going on

### :star: <b>QXlsx</b> [https://github.com/j2doll/QXlsx](https://github.com/j2doll/QXlsx)

<p align="center"><img src="https://github.com/j2doll/QXlsx/raw/master/markdown.data/QXlsx2.jpg"></p>

- QXlsx is excel file(*.xlsx) reader/writer library.
- Because QtXlsx is no longer supported(2014), I created a new project that is based on QtXlsx. (2017-)
- Development language of QXlsx is C++. (with Qt 5.x)
- You don't need to use static library or dynamic shared object using QXlsx.

### :star: <b>Qlibxlsxwriter</b> [https://github.com/j2doll/Qlibxlsxwriter](https://github.com/j2doll/Qlibxlsxwriter)

<p align="center"><img src="https://github.com/j2doll/Qlibxlsxwriter/raw/master/markdown.data/logo.png"></p>

- Qlibxlsxwriter is a helper project that allows libxlsxwriter to be used in Qt.
- libxlsxwriter is a C library for creating Excel XLSX files.
