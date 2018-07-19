---
title: コンパイラの警告 (レベル 3) C4738 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50b94cde2f8809b8ce56dc599804d11b8d058166
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291142"
---
# <a name="compiler-warning-level-3-c4738"></a>コンパイラの警告 (レベル 3) C4738
メモリに 32 ビットの浮動結果を格納します。パフォーマンスが低下する可能性があります  
  
 C4738 は、キャスト、代入式の結果に渡された引数、またはその他の操作の丸めが必要になることや、操作がレジスタ不足しています (に書き込むときに) メモリを使用するために必要なことを警告します。 その場合、パフォーマンスが低下します。  
  
 この警告を解決し、丸め処理を避けるため、コンパイル時に[/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md)使用または`double`の代わりに`float`です。  
  
 この警告を解決し、レジスタの不足を回避する、計算の順序を変更しの使用を変更インライン展開  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C4738 が生成されます。  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```