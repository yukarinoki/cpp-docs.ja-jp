---
description: 詳細については、「リンカツール Error LNK1313」を参照してください。
title: リンカ ツール エラー LNK1313
ms.date: 11/04/2016
f1_keywords:
- LNK1313
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
ms.openlocfilehash: 1c10038def9a448645e80ae10fc47d4372769b58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310724"
---
# <a name="linker-tools-error-lnk1313"></a>リンカ ツール エラー LNK1313

> ijw/ネイティブ モジュールが検出されました。純粋なモジュールとリンクできません。

## <a name="remarks"></a>解説

現在のバージョンの Visual C++ は、 **/clr: pure** を使用してコンパイルされた .obj ファイルを使用したネイティブまたは混合マネージ/ネイティブ .obj ファイルのリンクをサポートしていません。

**/Clr: pure** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

## <a name="examples"></a>例

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

次の例では lnk1313 エラーが生成されます。

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```
