---
title: コンパイラの警告 (レベル 1) C4747 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4747
dev_langs:
- C++
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 203943f3741d07e278652a7032a6dcdcb305a384
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285825"
---
# <a name="compiler-warning-level-1-c4747"></a>コンパイラの警告 (レベル 1) C4747
呼び出すマネージ 'entrypoint': マネージ コード DLL エントリ ポイントおよび DLL エントリ ポイントから到達した呼び出しを含むローダー ロック下で実行できません  
  
 コンパイラは、MSIL にコンパイルされる可能性がある) DLL エントリ ポイントを検出します。  エントリ ポイントが MSIL にコンパイル済み DLL を読み込むと潜在的な問題があるため MSIL に DLL エントリ ポイント関数のコンパイルを強くお勧めしています。  
  
 詳細については、次を参照してください。[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)と[リンカ ツール エラー LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md)です。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  モジュールをコンパイルできません **/clr**です。  
  
2.  エントリ ポイント関数をマーク`#pragma unmanaged`です。  
  
## <a name="example"></a>例  
 次の例では、C4747 を生成します。  
  
```  
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