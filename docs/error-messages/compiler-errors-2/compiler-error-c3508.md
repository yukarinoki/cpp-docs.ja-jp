---
title: コンパイラ エラー C3508 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3508
dev_langs:
- C++
helpviewer_keywords:
- C3508
ms.assetid: 16d08f89-2f32-44eb-9421-68acecddf49b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5930bbc365a3fb9eeae720c8c5355444ac18d879
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258040"
---
# <a name="compiler-error-c3508"></a>コンパイラ エラー C3508
'type': 有効な Automation 型ではありません  
  
 無効な型が指定されました。  
  
## <a name="example"></a>例  
 次の例では、C3508 が生成されます。  
  
```  
// C3508.cpp  
#define _ATL_DEBUG_QI  
  
#define WIN32_LEAN_AND_MEAN  
#define STRICT  
#ifndef _WIN32_WINNT  
#define _WIN32_WINNT 0x0400  
#endif  
  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
extern CComModule _Module;  
#include <atlcom.h>  
#include <atlctl.h>  
#include <atlstr.h>  
  
extern "C" int printf_s(const char*, ...);  
  
[module(name=oso)];  
  
union U  
// try the following two lines instead  
// [export]  
// struct U  
{  
   int i, j;  
};  
  
[dispinterface]  
__interface I  
{  
   [id(1)] HRESULT func(U* u);  
};  
  
[coclass]  
struct C : I  
{  
   HRESULT func(U*)   // C3508  
   {  
      return E_FAIL;  
   }  
};  
  
int main()  
{  
}  
```