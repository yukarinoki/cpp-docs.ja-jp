---
title: リンカ ツール エラー LNK2011
ms.date: 11/04/2016
f1_keywords:
- LNK2011
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
ms.openlocfilehash: e08f068099af68375523eae0f0cc4d63960f3261
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194812"
---
# <a name="linker-tools-error-lnk2011"></a>リンカ ツール エラー LNK2011

プリコンパイル済みオブジェクトがリンクされていません。イメージは実行されない可能性があります

プリコンパイル済みヘッダーを使用する場合、リンクを使用するには、プリコンパイル済みヘッダーを使用して作成されたすべてのオブジェクトファイルをリンクする必要があります。 他のソースファイルで使用するプリコンパイル済みヘッダーを生成するために使用するソースファイルがある場合は、プリコンパイル済みヘッダーと共に作成されたオブジェクトファイルを含める必要があります。

たとえば、スタブという名前のファイルをコンパイルして、他のソースファイルで使用するプリコンパイル済みヘッダーを作成する場合は、スタブとリンクする必要があります。これを行わないと、このエラーが発生します。 次のコマンドラインでは、1行目を使用してプリコンパイル済みヘッダーの PROG1 を作成します。これは、2行目と3行目の PROG2 と共に使用されます。 ファイル PROG1 には、`#include` の行 (および PROG2 と同じ `#include` 行) のみが含まれており、プリコンパイル済みヘッダーを生成するためにのみ使用されます。 最後の行では、LNK2011 を回避するために、スタブ .obj をリンクする必要があります。

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```
