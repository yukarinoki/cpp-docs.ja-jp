---
title: リンカ ツール エラー LNK1306 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1306
dev_langs:
- C++
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cc007a4a594c8593d7820365377f1c811b1e23c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050568"
---
# <a name="linker-tools-error-lnk1306"></a>リンカ ツール エラー LNK1306

> DLL エントリ ポイント関数を管理することはできません。ネイティブにコンパイルされます。

`DllMain` MSIL にコンパイルすることはできませんこれは、ネイティブにコンパイルする必要があります。

この問題を解決するには

- エントリ ポイントなしを含むファイルをコンパイル **/clr**します。

- エントリ ポイントを`#pragma unmanaged`セクション。

詳細については次を参照してください:

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)

- [managed、unmanaged](../../preprocessor/managed-unmanaged.md)

- [混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)

- [DLL と Visual C++ ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)

## <a name="example"></a>例

次の例では、LNK1306 が生成されます。

```cpp
// LNK1306.cpp
// compile with: /clr /link /dll /entry:NewDllMain
// LNK1306 error expected
#include <windows.h>
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
```

この問題を解決するオプションを使用しない、/clr をこのファイルをコンパイルまたはを使用して、`#pragma`この例で示すように、非管理対象のセクションでは、エントリ ポイントの定義を配置するディレクティブ。

```cpp
// LNK1306fix.cpp
// compile with: /clr /link /dll /entry:NewDllMain
#include <windows.h>
#pragma managed(push, off)
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
#pragma managed(pop)
```
