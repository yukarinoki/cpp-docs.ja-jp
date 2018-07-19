---
title: コンパイラ エラー C3272 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3272
dev_langs:
- C++
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39900d11e7f6be25e8c9b701a52ff726807a4828
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254158"
---
# <a name="compiler-error-c3272"></a>コンパイラ エラー C3272
'symbol': シンボルは、StructLayout(LayoutKind::Explicit) で定義された型パラメーターのメンバーであるため、このシンボルには FieldOffset が必要です  
  
ときに`StructLayout(LayoutKind::Explicit)`でフィールドをマークする必要がありますが有効で`FieldOffset`です。  
  
次の例では C3272 が生成されます。  
  
```  
// C3272_2.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Explicit)]  
ref struct X  
{  
   int data_;   // C3272  
   // try the following line instead  
   // [FieldOffset(0)] int data_;  
};  
```  
