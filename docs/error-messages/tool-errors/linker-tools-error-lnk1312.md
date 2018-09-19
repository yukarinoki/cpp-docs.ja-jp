---
title: リンカ ツール エラー LNK1312 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1312
dev_langs:
- C++
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 335a3976675f36e3da295bc23c8e17440a56a505
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088653"
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