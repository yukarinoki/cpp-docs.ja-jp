---
title: コンパイラ エラー C2711 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2711
dev_langs:
- C++
helpviewer_keywords:
- C2711
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb2e5c904d7f6d865b94ea4fb4ba65be4c974f8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234276"
---
# <a name="compiler-error-c2711"></a>コンパイラ エラー C2711
'function': この関数にすることはできませんマネージとしてコンパイルする場合は、#pragma unmanaged を使用する検討してください  
  
 一部の命令すると、コンパイラが、外側の関数の MSIL を生成できなくなります。  
  
 次の例では、C2711 が生成されます。  
  
```  
// C2711.cpp  
// compile with: /clr  
// processor: x86  
using namespace System;  
value struct V {  
   static const t = 10;  
};  
  
void bar() {  
   V::t;  
   __asm int 3   // C2711 inline asm can't be compiled managed  
}  
```