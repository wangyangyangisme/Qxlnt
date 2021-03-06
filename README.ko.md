# Qxlnt

> *Read this in other languages: [English](README.md), :kr: [한국어](README.ko.md)*

<p align="center"><img src="https://github.com/j2doll/Qxlnt/raw/master/markdown-data/Concept-QXlnt.jpg"></p>

![](markdown-data/qxlnt-badge1.png)

- Qxlnt는 xlnt가 Qt에서 사용될 수있게 해주는 도우미 프로젝트입니다.
- xlnt는 C++14를 사용하는 xlsx 라이브러리입니다. 자세한 정보는 '라이센스 및 링크'를 참조하십시오.

## 왜 만들었는가?

- xlnt는 xlsx Excel 파일을 사용하기에 훌륭한 라이브러리입니다. :+1:
- 그래서 xlnt를 Qt에서 사용하기 쉬운 방법을 찾고 있었습니다. 물론 cmake는 Qt와 호환되지만 사용하기가 쉽지 않습니다. 그래서 Qxlnt를 만들었습니다.

## 헬로우 월드 (HelloQXlnt)

```cpp
#include <iostream>
#include <xlnt/xlnt.hpp>
#include <QCoreApplication>

int main(int argc, char **argv)
{     
    QCoreApplication a(argc, argv); // Qt 코드입니다.

    xlnt::workbook wb; // xlnt 코드입니다. 다같이 섞어서 쓰세요!
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

## 주의 :zap:

- C++14 이상 버전이 필요합니다.
	- gcc 4.x (4.8 이하)는 지원되지 않습니다. 현재 (2018) gcc 버전은 7.x입니다.
	- Visual C++를 사용하는 경우 VS 2017 이상의 버전을 사용하십시오.

## 테스트
- 현재 테스트 중입니다.
- [테스트 환경](BuildEnv.md)을 참조하세요.

## 할 일
- 다양한 Qt 환경에서 테스트 :cloud:
- 유니코드 테스트 (파일명, 경로명, 자료) :zap:

## 라이센스 및 링크

- ![](markdown-data/mit-license.png) Qxlnt는 MIT 라이센스입니다. (https://github.com/j2doll/Qxlnt)[https://github.com/j2doll/Qxlnt] 
- ![](markdown-data/mit-license.png) xlnt는 MIT 라이센스입니다. (https://github.com/tfussell/xlnt)[https://github.com/tfussell/xlnt] 
- ![](markdown-data/mit-license.png) libstudxml는 MIT 라이센스입니다. (https://www.codesynthesis.com/projects/libstudxml/)[https://www.codesynthesis.com/projects/libstudxml/]
- ![](markdown-data/boost-license.png) utfcpp는 Boost 소프트웨어 라이센스입니다. [http://utfcpp.sourceforge.net](http://utfcpp.sourceforge.net)

## :mailbox: 연락처
- 제게 이슈를 남겨주세요. [https://github.com/j2doll/Qxlnt/issues](https://github.com/j2doll/Qxlnt/issues)

## 진행중인 유사한 프로젝트

### :star: <b>QXlsx</b> [https://github.com/j2doll/QXlsx](https://github.com/j2doll/QXlsx)

<p align="center"><img src="https://github.com/j2doll/QXlsx/raw/master/markdown.data/QXlsx2.jpg"></p>

- QXlsx는 엑셀 파일(*.xlsx)을 읽고 쓰는 라이브러리입니다.
- QtXlsx가 더이상 지원되지 않기 때문에(2014), QtXlsx에 기반한 새로운 프로젝트를 만들었습니다. (2017-)
- QXlsx는 개발언어로 C++를 사용합니다. (Qt 5.x 사용)
- QXlsx는 정적 또는 동적 라이브러리를 사용하지 않아도 되도록 제작되었습니다.

### :star: <b>Qlibxlsxwriter</b> [https://github.com/j2doll/Qlibxlsxwriter](https://github.com/j2doll/Qlibxlsxwriter)

<p align="center"><img src="https://github.com/j2doll/Qlibxlsxwriter/raw/master/markdown.data/logo.png"></p>

- Qlibxlsxwriter는 libxlsxwriter를 Qt에서 사용할 수있는 도우미 프로젝트입니다.
- libxlsxwriter는 Excel XLSX 파일을 만들기위한 C 라이브러리 입니다.
