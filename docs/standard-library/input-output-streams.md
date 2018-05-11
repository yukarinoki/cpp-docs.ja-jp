---
title: 入出力ストリーム | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51a7a9aff4f77444bbec46a9739fae91cac3c104
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="inputoutput-streams"></a>入出力ストリーム

ヘッダー ファイル \<istream> で定義される `basic_iostream` は、入力および出力の両方の文字ベースの I/O ストリームを処理するオブジェクトのクラス テンプレートです。

`basic_iostream` の文字に固有の特殊化を定義し、コードを読みやすくするのに役立つ 2 つの typedef があります。`iostream` (ヘッダー ファイル \<iostream> と混同しないでください) は、`basic_iostream<char>` に基づいている I/O ストリームです。`wiostream` は、`basic_iostream<wchar_t>` に基づいている I/O ストリームです。

詳細については、「[basic_iostream クラス](../standard-library/basic-iostream-class.md)」、「[iostream](../standard-library/basic-iostream-class.md)」、および「[wiostream](../standard-library/basic-iostream-class.md)」を参照してください。

`basic_iostream` からはクラス テンプレート `basic_fstream` が派生され、これ、ファイルとの間で文字データをストリーミングするのに使用されます。

`basic_fstream` の文字に固有の特殊化を提供する typedef もあります。 `char` に基づくファイルの I/O ストリームである `fstream`、および `wchar_t` に基づくファイルの I/O ストリームである `wfstream` があります。 詳細については、「[basic_fstream クラス](../standard-library/basic-fstream-class.md)」、「[fstream](../standard-library/basic-fstream-class.md)」、および「[wfstream](../standard-library/basic-fstream-class.md)」を参照してください。 これらの typedef を使用するには、ヘッダー ファイル \<fstream> を含める必要があります。

> [!NOTE]
> `basic_fstream` オブジェクトを使用してファイル I/O を実行する場合、基になるバッファーに、個別に指定された読み取りと書き込みの位置が含まれていても、現在の入力位置と現在の出力位置が一緒に関連付けられるため、一部のデータを読み取ると、出力位置が移動します。

クラス テンプレート `basic_stringstream` とその一般的な特殊化 `stringstream` は、通常、I/O ストリーム オブジェクトで使用して、文字データを挿入および抽出します。 詳細については、「[basic_stringstream クラス](../standard-library/basic-stringstream-class.md)」を参照してください。

## <a name="see-also"></a>関連項目

[stringstream](../standard-library/basic-stringstream-class.md)<br/>
[basic_stringstream クラス](../standard-library/basic-stringstream-class.md)<br/>
[\<sstream>](../standard-library/sstream.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)<br/>
