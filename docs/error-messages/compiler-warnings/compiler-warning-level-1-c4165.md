---
title: コンパイラの警告 (レベル 1) C4165 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4165
dev_langs:
- C++
helpviewer_keywords:
- C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39487999f2aa74a5600d84d71917712e03b2d626
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277567"
---
# <a name="compiler-warning-level-1-c4165"></a>コンパイラの警告 (レベル 1) C4165
'HRESULT' は 'bool'; に変換します。これは、目的ですか。  
  
HRESULT を使用する場合、[場合](../../cpp/if-else-statement-cpp.md)ステートメントでは、HRESULT に変換される、 [bool](../../cpp/bool-cpp.md) HRESULT として変数を明示的にテストする場合を除き、します。 既定では、この警告はオフに設定されています。  
  
## <a name="example"></a>例  
次の例には、C4165 が生成されます。  
  
```cpp  
// C4165.cpp  
// compile with: /W1  
#include <windows.h>  
#pragma warning(1:4165)  
  
extern HRESULT hr;  
int main() {  
   if (hr) {  
   // try either of the following ...  
   // if (FAILED(hr)) { // C4165 expected  
   // if (hr != S_OK) {  
   }  
}  
```