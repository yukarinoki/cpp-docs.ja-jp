---
description: '詳細情報: コンパイラの警告 (レベル 1) C4747'
title: コンパイラの警告 (レベル 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: e182f4fc6a270917bb0b7e348000a0f084183ba6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332204"
---
# <a name="compiler-warning-level-1-c4747"></a>コンパイラの警告 (レベル 1) C4747

マネージド ' entrypoint ' を呼び出しています: マネージドコードは、DLL エントリポイントおよび DLL エントリポイントから到達した呼び出しを含むローダーロック下では実行できません

コンパイラにより、MSIL にコンパイルされた (可能性のある) DLL エントリポイントが見つかりました。  エントリポイントが MSIL にコンパイルされている DLL の読み込みで問題が発生する可能性があるため、DLL エントリポイント関数を MSIL にコンパイルしないことを強くお勧めします。

詳細については、「 [混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md) 」および「 [リンカーツールのエラー LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md)」を参照してください。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. **/Clr** を使用してモジュールをコンパイルしないでください。

1. エントリポイント関数をとしてマーク `#pragma unmanaged` します。

## <a name="example"></a>例

次の例では、C4747 が生成されます。

```cpp
// C4747.cpp
// compile with: /clr /c /W1
// C4747 expected
#include <windows.h>

// Uncomment the following line to resolve.
// #pragma unmanaged

BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {
   return TRUE;
};
```
