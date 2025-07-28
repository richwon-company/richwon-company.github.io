---
title: PDF 파일에서 명판 문구 추출 및 엑셀 파일 만들기
description: PDF 파일에서 명판 문구를 뽑아 엑셀 파일로 정리하는 방법을 쉽게 안내합니다.
sidebar_label: "1-2단계: PDF → 엑셀"
sidebar_position: 3
tags:
  - 명판자동화
  - 발주서
  - 엑셀
---

# 1단계: 캐드 파일에서 명판 문구 추출하여 파일 만들기

---

```mermaid
flowchart TD
    스캔PDF[스캔본 PDF]-- <a href='https://www.ilovepdf.com/ko/ocr-pdf' target="_blank" rel="noopener noreferrer">PDF OCR(글자 추출)</a> --> 일반PDF[글자 드래그 되는 PDF]
    일반PDF-- <a href='https://www.ilovepdf.com/ko/pdf_to_excel' target="_blank" rel="noopener noreferrer">PDF to excel</a> -->XLSX파일[엑셀 파일]
    XLSX파일-->자동화프로그램[R-edit]
    DXF템플릿파일[캐드 파일]-->자동화프로그램

    classDef main fill:#a3d0ff,stroke:#333,stroke-width:2px;
    class 스캔PDF,일반PDF,TXT2XLS,XLSX파일,자동화프로그램,DXF템플릿파일,DXF결과물파일,Type3,vnd파일,가공담당자 main;
```

- **R-edit**을 거쳐 **DXF 파일**을 만들고, **Type3 프로그램**에서 **vnd 파일**(출력용 결과물)을 생성하여 **가공 담당자**에게 전달합니다.

---

## 📝 준비물
- 고객이 보낸 **발주서 PDF**
- **Excel(엑셀) 프로그램**

---

## PDF 종류 파악하기

PDF는 스캔본 PDF와 컴퓨터로 작성한 문서 PDF가 있습니다. 스캔본은 단순한 이미지이기 때문에 PDF 문서 안에 글자 정보가 없습니다. 컴퓨터로 작성한 PDF 문서는 실제로 PDF 안에 글자 정보가 있기 때문에 글자에 드래그가 됩니다. 드래그 여부로 PDF 종류를 간단히 체크할 수 있습니다.

### 스캔본 PDF 일 경우

1. [PDF OCR](https://www.ilovepdf.com/ko/ocr-pdf)을 해주는 홈페이지에 들어갑니다.

   ![01 PDF OCR 홈페이지](/img/자동화%20프로그램/01%20PDF%20OCR%20홈페이지.png)

2. 글자를 추출하고자 하는 PDF 파일을 선택합니다.

   ![02 PDF 파일 선택](/img/자동화%20프로그램/02%20PDF%20파일%20선택.png)

3. OCR 옵션 화면입니다. 필요시 문서 언어를 한국어나 영어로 설정합니다.

   ![03 OCR 옵션 선택](/img/자동화%20프로그램/03%20OCR%20옵션%20선택.png)

4. OCR이 끝나면 **PDF 다운로드** 버튼을 눌러서 PDF 파일을 다운로드합니다.  
   다운로드 후 글자가 드래그 되는지 확인합니다.

   ![04 OCR 완료](/img/자동화%20프로그램/04%20OCR%20완료.png)

---

### 글자 드래그 되는 PDF 일 경우

1. [PDF을 Excel로 변환](https://www.ilovepdf.com/ko/pdf_to_excel)해주는 홈페이지에 들어갑니다.

   ![05 PDF에서 EXCEL로 변환 홈페이지](/img/자동화%20프로그램/05%20PDF에서%20EXCEL로%20변환%20홈페이지.png)

2. 엑셀로 변환하려는 PDF 파일을 선택합니다.

   ![06 PDF 파일 선택](/img/자동화%20프로그램/06%20PDF%20파일%20선택.png)

3. **OCR 없음** 기능이 무료입니다. **OCR 없음**을 선택합니다.  
   레이아웃은 원하는 것을 선택합니다.

   ![07 PDF Excel 변환 옵션 선택](/img/자동화%20프로그램/07%20PDF%20Excel%20변환%20옵션%20선택.png)

4. **OCR 없이 계속**을 선택합니다. **OCR 적용**은 유료 기능입니다.

   ![08 OCR 없이 계속](/img/자동화%20프로그램/08%20OCR%20없이%20계속.png)

5. 변환이 끝나면 **EXCEL 다운로드** 버튼을 눌러서 엑셀 파일을 다운로드합니다.  

   ![09 변환 완료 EXCEL 다운로드](/img/자동화%20프로그램/09%20변환%20완료%20EXCEL%20다운로드.png)

6. 변환이 완료된 엑셀 파일을 R-edit 프로그램에서 사용할 수 있는 형태로 직접 정리합니다.
   :::info
   ChatGPT 같은 AI한테 직접 정리해달라고 작성해도 됩니다.
   ```
   아래 원본 데이터를 다음과 같은 형태로 바꾸고 싶다. 엑셀에 붙여넣을 수 있도록 결과물을 만들어주세요.
   원하는 형태:
   텍스트1  텍스트2
   데이터1  데이터2

   원본 데이터:
   [엑셀 데이터를 전체 선택(ctrl+A) 후 복사해서 붙여넣기]
   ```
   :::

   ![10 EXCEL 파일 화면](/img/자동화%20프로그램/10%20EXCEL%20파일%20화면.png)

---

## ✅ 체크리스트
- [ ] OCR 이후 오타가 없는지 확인
- [ ] 똑같은 문구로 많은 수량을 요구한 사례가 있는지 확인

---