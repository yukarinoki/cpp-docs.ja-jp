---
description: 詳細については、「リンカツール Error LNK1107」を参照してください。
title: リンカ ツール エラー LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: 2a5ed9ba0bc4789a324d143b6287a08712299cdd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281393"
---
# <a name="linker-tools-error-lnk1107"></a>リンカ ツール エラー LNK1107

ファイルが無効であるか壊れています: 場所で読み取ることができません

ツールでファイルを読み取ることができませんでした。 ファイルを再作成します。

LNK1107 は、 [/clr: noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) または  [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)で作成されたモジュール (.dll または .netmodule 拡張子) をリンカーに渡そうとした場合にも発生する可能性があります。代わりに .obj ファイルを渡してください。

次のサンプルをコンパイルすると、次のようになります。

```cpp
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

次に、コマンドラインで [ **link LNK1107.dll** ] を指定すると、LNK1107 が表示されます。  このエラーを解決するには、代わりに **LINK LNK1107** を指定します。
