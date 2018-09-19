---
title: リンカー ツールの警告 LNK4217 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4217
dev_langs:
- C++
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c650eddd8078419f63df48cc91705d2e86eb5c8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067983"
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