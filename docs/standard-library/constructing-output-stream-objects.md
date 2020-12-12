---
description: 詳細については、「出力ストリームオブジェクトの構築」を参照してください。
title: 出力ストリーム オブジェクトのコンストラクト
ms.date: 11/04/2016
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
ms.openlocfilehash: e730e4cb675b216fa56b5624feb69fadcd61400a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233644"
---
# <a name="constructing-output-stream-objects"></a>出力ストリーム オブジェクトのコンストラクト

定義済みの `cout`、`cerr`、または `clog` オブジェクトのみを使う場合は、出力ストリームをコンストラクトする必要はありません。 次の場合はコンストラクターを使う必要があります。

- [出力ファイル ストリーム コンストラクター](#vclrfoutputfilestreamconstructorsanchor1)

- [出力文字列ストリームコンストラクター](#vclrfoutputstringstreamconstructorsanchor2)

## <a name="output-file-stream-constructors"></a><a name="vclrfoutputfilestreamconstructorsanchor1"></a> 出力ファイルストリームコンストラクター

2 つの方法のいずれかで、出力ファイル ストリームをコンストラクトできます。

- 既定のコンストラクターを使った後、`open` メンバー関数を呼び出します。

   ```cpp
   ofstream myFile; // Static or on the stack
   myFile.open("filename");

   ofstream* pmyFile = new ofstream; // On the heap
   pmyFile->open("filename");
   ```

- コンストラクターの呼び出しで、ファイル名とモード フラグを指定します。

   ```cpp
   ofstream myFile("filename", ios_base::out);
   ```

## <a name="output-string-stream-constructors"></a><a name="vclrfoutputstringstreamconstructorsanchor2"></a> 出力文字列ストリーム コンストラクター

出力文字列ストリームをコンストラクトするには、次のように `ostringstream` を使うことができます。

```cpp
using namespace std;
// ...
ostringstream myString;
myString << "this is a test" << ends;

string sp = myString.str(); // Obtain string
cout << sp << endl;
```

`ends` "マニピュレーター" は、必要な終端 null 文字を文字列に追加します。

## <a name="see-also"></a>関連項目

[出力ストリーム](../standard-library/output-streams.md)
