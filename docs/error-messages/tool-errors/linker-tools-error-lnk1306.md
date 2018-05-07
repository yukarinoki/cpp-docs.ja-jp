---
title: リンカ ツール エラー LNK1306 |Microsoft ドキュメント
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
ms.openlocfilehash: bb340a4c28f94f18e0c4b65bea8749394e002bd3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1306"></a>リンカ ツール エラー LNK1306  
  
> DLL エントリ ポイント関数を管理することはできません。ネイティブにコンパイルします。  
  
`DllMain` MSIL にコンパイルすることはできませんこれは、ネイティブにコンパイルする必要があります。  
  
この問題を解決するのには  
  
-   せずエントリ ポイントが含まれているファイルをコンパイル **/clr**です。  
  
-   エントリ ポイントを配置する、`#pragma unmanaged`セクションです。  
  
詳細については次を参照してください:  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [managed、unmanaged](../../preprocessor/managed-unmanaged.md)  
  
-   [混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [DLL と Visual C++ ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)  
  
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
  
この問題を解決するオプションを使用しない、/clr を使用したり、このファイルをコンパイル、`#pragma`この例で示すように、アンマネージのセクションにエントリ ポイントの定義を記述するディレクティブ。  
  
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
