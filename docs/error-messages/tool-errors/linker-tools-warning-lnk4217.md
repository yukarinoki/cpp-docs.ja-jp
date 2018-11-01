---
title: リンカー ツールの警告 LNK4217
ms.date: 11/04/2016
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: 12766241832d39f0b47ed85036c0ebeb0447fc75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448049"
---
# <a name="linker-tools-warning-lnk4217"></a>リンカー ツールの警告 LNK4217

ローカルで定義されたシンボル 'symbol' 関数 'function' のインポート

[_declspec](../../cpp/dllexport-dllimport.md)シンボルがローカルで定義されている場合でも、シンボルが指定されました。 削除、`__declspec`修飾子をこの警告を解決します。

`symbol` イメージ内で定義されているシンボルの名前です。 `function` シンボルをインポートする関数です。

オプションを使用してコンパイルするときに、この警告は表示されません[/clr](../../build/reference/clr-common-language-runtime-compilation.md)します。

LNK4217 は、最初のモジュールのインポート ライブラリと 2 番目のモジュールをコンパイルする代わりと同時に、2 つのモジュールをリンクしようとした場合にも発生します。

```
// LNK4217.cpp
// compile with: /LD
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

この場合、次のようになります。

```
// LNK4217b.cpp
// compile with: /c
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

これら 2 つのモジュールをリンクしようとして、LNK4217 が発生、解決するのには、最初のサンプルのインポート ライブラリを使用した 2 つ目のサンプルをコンパイルします。