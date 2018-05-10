---
title: コンパイラの警告 (レベル 4) C4702 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4702
dev_langs:
- C++
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29c2d6b0328fd8dd4cd6f9a226253036b62d03ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4702"></a>コンパイラの警告 (レベル 4) C4702
到達できないコード  
  
 この警告は、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果: 制御が渡らないコードです。 C4702 が生成されます (バック エンド)、コンパイラは、到達できないコードを検出すると、レベル 4 の警告です。  
  
 Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C では有効では、コードの場合は、到達できないコードを削除するか、すべてのソース コードが実行のいくつかのフローに到達できることを保証します。  
  
## <a name="example"></a>例  
 次の例では、C4702 が生成されます。  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## <a name="example"></a>例  
 コンパイルするときに **/GX**、 **/EHc**、 **/EHsc**、または **/EHac**になり、extern C 関数を使用して、コードが到達できないため extern C関数をスローしないと見なされます、したがって、catch ブロックが到達可能ではありません。  この警告が無効である関数をスローすることができる場合、コンパイル時に **/EHa**または **/EHs**によってスローされる例外。  
  
 詳細については、次を参照してください。 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)詳細についてはします。  
  
 次の例では、C4702 が生成されます。  
  
```  
// C4702b.cpp  
// compile with: /W4 /EHsc  
#include <iostream>  
  
using namespace std;  
extern "C" __declspec(dllexport) void Function2(){}  
  
int main() {  
   try {  
      Function2();  
   }  
   catch (...) {  
      cout << "Exp: Function2!" << endl;   // C4702  
   }  
}  
```