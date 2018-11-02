---
title: リンカ ツール エラー LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: 49fa7e7963d6bb561e1602b58fe1f26c5f3d54bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436232"
---
# <a name="linker-tools-error-lnk1312"></a>リンカ ツール エラー LNK1312

無効または壊れたファイル: アセンブリをインポートできません。

アセンブリ、モジュールまたはアセンブリでコンパイルされた以外のファイルを作成するときに **/clr**に渡された、 **/ASSEMBLYMODULE**リンカー オプション。  オブジェクト ファイルが渡された場合 **/ASSEMBLYMODULE**、のみ、オブジェクトに直接渡す、リンカーの代わりを **/ASSEMBLYMODULE**します。

## <a name="example"></a>例

次の例では、.obj ファイルを作成します。

```
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

## <a name="example"></a>例

次の例では、LNK1312 が生成されます。

```
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```