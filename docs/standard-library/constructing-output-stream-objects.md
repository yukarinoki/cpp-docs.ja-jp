---
title: 出力ストリーム オブジェクトのコンストラクト
ms.date: 11/04/2016
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
ms.openlocfilehash: 7da7d9dd0fae3ce3fa21ecd774f88643dca49c26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212002"
---
# <a name="constructing-output-stream-objects"></a>出力ストリーム オブジェクトのコンストラクト

定義済みの `cout`、`cerr`、または `clog` オブジェクトのみを使う場合は、出力ストリームをコンストラクトする必要はありません。 次の場合はコンストラクターを使う必要があります。

- [出力ファイル ストリーム コンストラクター](#vclrfoutputfilestreamconstructorsanchor1)

- [出力文字列ストリーム コンストラクター](#vclrfoutputstringstreamconstructorsanchor2)

## <a name="vclrfoutputfilestreamconstructorsanchor1"></a> 出力ファイル ストリーム コンストラクター

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

## <a name="vclrfoutputstringstreamconstructorsanchor2"></a> 出力文字列ストリーム コンストラクター

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

[出力ストリーム](../standard-library/output-streams.md)<br/>
