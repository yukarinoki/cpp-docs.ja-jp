---
title: リンカ ツール エラー LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: 68048d9f824283d002a4ea8b64d88f37bbeefc48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255393"
---
# <a name="linker-tools-error-lnk1107"></a>リンカ ツール エラー LNK1107

無効または壊れたファイル: の場所で読み取ることができません

このツールは、ファイルを読み取れませんでした。 ファイルを再作成します。

モジュールに渡すしようとした場合にも LNK1107 (.dll または .netmodule の拡張機能で作成された[/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md)または[/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)) リンカー;、.obj ファイルを代わりに渡します。

次の例: コンパイルする場合

```
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

指定**リンク LNK1107.dll**コマンドラインで LNK1107 が表示されます。  エラーを解決するには、次のように指定します。**リンク LNK1107.obj**代わりにします。