---
description: 詳細については、「入力ストリームオブジェクトの構築」を参照してください。
title: 入力ストリーム オブジェクトのコンストラクト
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
ms.openlocfilehash: 2ee1e0bb310c608b53a79afd101aaeafb3cb6645
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324920"
---
# <a name="constructing-input-stream-objects"></a>入力ストリーム オブジェクトのコンストラクト

`cin` オブジェクトのみを使う場合は、入力ストリームをコンストラクトする必要はありません。 次のものを使う場合は、入力ストリームをコンストラクトする必要があります。

- [入力ファイルストリームコンストラクター](#vclrfinputfilestreamconstructorsanchor8)

- [入力文字列ストリームコンストラクター](#vclrfinputstringstreamconstructorsanchor9)

## <a name="input-file-stream-constructors"></a><a name="vclrfinputfilestreamconstructorsanchor8"></a> 入力ファイル ストリーム コンストラクター

入力ファイル ストリームは、2 つの方法で作成できます。

- **`void`** 引数コンストラクターを使用して、 `open` メンバー関数を呼び出します。

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- コンストラクターの呼び出しでファイル名とモード フラグを指定し、それによってコンストラクション プロセスの間にファイルを開きます。

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="input-string-stream-constructors"></a><a name="vclrfinputstringstreamconstructorsanchor9"></a> 入力文字列ストリーム コンストラクター

入力文字列ストリーム コンストラクターには、事前に割り当てられて初期化された記憶域のアドレスが必要です。

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)
