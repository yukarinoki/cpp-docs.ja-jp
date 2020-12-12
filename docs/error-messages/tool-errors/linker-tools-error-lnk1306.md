---
description: 詳細については、「リンカツール Error LNK1306」を参照してください。
title: リンカ ツール エラー LNK1306
ms.date: 11/04/2016
f1_keywords:
- LNK1306
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
ms.openlocfilehash: aa6386da7c836eea8365d8a4ffde0bbd80d0fa81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193657"
---
# <a name="linker-tools-error-lnk1306"></a>リンカ ツール エラー LNK1306

> DLL エントリポイント関数を管理できません。ネイティブにコンパイル

`DllMain` を MSIL にコンパイルできません。ネイティブにコンパイルする必要があります。

この問題を解決するには、

- **/Clr** を指定せずにエントリポイントを含むファイルをコンパイルします。

- セクションにエントリポイントを配置し `#pragma unmanaged` ます。

詳細については、次を参照してください。

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)

- [マネージド、アンマネージド](../../preprocessor/managed-unmanaged.md)

- [混合アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)

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

この問題を解決するには、/clr オプションを使用してこのファイルをコンパイルしないようにするか、 `#pragma` 次の例に示すように、ディレクティブを使用してアンマネージセクションにエントリポイント定義を配置します。

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
