---
description: 詳細については、「リンカツール Error LNK2011」を参照してください。
title: リンカ ツール エラー LNK2011
ms.date: 11/04/2016
f1_keywords:
- LNK2011
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
ms.openlocfilehash: f149324a61d34333e8f29f70bf5fee4cd952ba8b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338469"
---
# <a name="linker-tools-error-lnk2011"></a>リンカ ツール エラー LNK2011

プリコンパイル済みオブジェクトがリンクされていません。イメージは実行されない可能性があります

プリコンパイル済みヘッダーを使用する場合、リンクを使用するには、プリコンパイル済みヘッダーを使用して作成されたすべてのオブジェクトファイルをリンクする必要があります。 他のソースファイルで使用するプリコンパイル済みヘッダーを生成するために使用するソースファイルがある場合は、プリコンパイル済みヘッダーと共に作成されたオブジェクトファイルを含める必要があります。

たとえば、スタブという名前のファイルをコンパイルして、他のソースファイルで使用するプリコンパイル済みヘッダーを作成する場合は、スタブとリンクする必要があります。これを行わないと、このエラーが発生します。 次のコマンドラインでは、1行目を使用してプリコンパイル済みヘッダーの PROG1 を作成します。これは、2行目と3行目の PROG2 と共に使用されます。 ファイル PROG1 には、 `#include` 行 (および PROG2 と同じ行) のみが含まれて `#include` おり、プリコンパイル済みヘッダーを生成するためにのみ使用されます。 最後の行では、LNK2011 を回避するために、スタブ .obj をリンクする必要があります。

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```
