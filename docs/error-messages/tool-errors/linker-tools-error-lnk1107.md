---
title: リンカ ツール エラー LNK1107 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1107
dev_langs:
- C++
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73a1643d10ea9adc6ac6979eb2de023593ba8d01
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060708"
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