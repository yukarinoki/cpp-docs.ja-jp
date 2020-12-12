---
description: 詳細については、「入出力ストリーム」を参照してください。
title: Input-Output ストリーム
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
ms.openlocfilehash: fd261bfdac5b9ce95b04430e9d77c6bd1df56c7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231642"
---
# <a name="inputoutput-streams"></a>入出力ストリーム

`basic_iostream`は、ヘッダーファイルで定義されてい \<istream> ます。これは、入力と出力の両方の文字ベース i/o ストリームを処理するオブジェクトのクラステンプレートです。

との文字固有の特殊化を定義する typedef が2つあり `basic_iostream` ます。 `iostream` (ヘッダーファイルと混同しないでください \<iostream> ) は、に基づく i/o ストリームです。 `basic_iostream<char>` `wiostream` は、に基づく `basic_iostream<wchar_t>` i/o ストリームですが、はに基づいています。

詳細については、「[basic_iostream クラス](../standard-library/basic-iostream-class.md)」、「[iostream](../standard-library/basic-iostream-class.md)」、および「[wiostream](../standard-library/basic-iostream-class.md)」を参照してください。

`basic_iostream` からはクラス テンプレート `basic_fstream` が派生され、これ、ファイルとの間で文字データをストリーミングするのに使用されます。

`basic_fstream` の文字に固有の特殊化を提供する typedef もあります。 これらは、に `fstream` 基づくファイル i/o ストリームであり、 **`char`** `wfstream` に基づくファイル i/o ストリームです。これは、に基づいてい **`wchar_t`** ます。 詳細については、「[basic_fstream クラス](../standard-library/basic-fstream-class.md)」、「[fstream](../standard-library/basic-fstream-class.md)」、および「[wfstream](../standard-library/basic-fstream-class.md)」を参照してください。 これらの typedef を使用するには、ヘッダーファイルをインクルードする必要があり \<fstream> ます。

> [!NOTE]
> `basic_fstream` オブジェクトを使用してファイル I/O を実行する場合、基になるバッファーに、個別に指定された読み取りと書き込みの位置が含まれていても、現在の入力位置と現在の出力位置が一緒に関連付けられるため、一部のデータを読み取ると、出力位置が移動します。

クラス テンプレート `basic_stringstream` とその一般的な特殊化 `stringstream` は、通常、I/O ストリーム オブジェクトで使用して、文字データを挿入および抽出します。 詳細については、「[basic_stringstream クラス](../standard-library/basic-stringstream-class.md)」を参照してください。

## <a name="see-also"></a>関連項目

[stringstream](../standard-library/basic-stringstream-class.md)\
[basic_stringstream クラス](../standard-library/basic-stringstream-class.md)\
[\<sstream>](../standard-library/sstream.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
