---
title: リンカ ツール エラー LNK2011 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2011
dev_langs:
- C++
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18562a21886508ff0766641f95ac2e15b76fd424
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095392"
---
# <a name="linker-tools-error-lnk2011"></a>リンカ ツール エラー LNK2011

プリコンパイル済みのオブジェクトがリンクされていません。イメージは動作しない可能性があります。

プリコンパイル済みヘッダーを使用する場合は、すべてのオブジェクト ファイルがプリコンパイル済みヘッダーを作成する必要がありますでリンクするようにリンクが必要です。 他のソース ファイルを使用するためのプリコンパイル済みヘッダーを生成するために使用するソース ファイルがあれば、オブジェクト ファイルも含める必要があります。

たとえば、他のソース ファイルを使用するためのプリコンパイル済みヘッダーを作成する STUB.cpp という名前のファイルをコンパイルする場合 stub.obj も一緒にリンクする必要があります。 またはこのエラーが表示されます。 次のコマンド行では、1 つの行は、COMMON.pch PROG1.cpp と PROG2.cpp 2 と 3 行で使用される、プリコンパイル済みヘッダーを作成に使用されます。 STUB.cpp のみを含むファイル`#include`行 (同じ`#include`PROG1.cpp PROG2.cpp と見なされた行) と、プリコンパイル済みヘッダーの生成にのみ使用されます。 最後の行で LNK2011 を回避するために stub.obj も一緒にリンクする必要があります。

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```