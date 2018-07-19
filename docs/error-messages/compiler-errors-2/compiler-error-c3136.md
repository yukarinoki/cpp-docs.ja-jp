---
title: コンパイラ エラー C3136 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f892c7f3d1ca7bf2aebf3ecfe7574182b544fd01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248852"
---
# <a name="compiler-error-c3136"></a>コンパイラ エラー C3136
'interface': COM インターフェイスは、他の COM インターフェイスからのみ継承できます、'interface' は、COM インターフェイスではありません  
  
 適用されているインターフェイス、[インターフェイス属性](../../windows/interface-attributes.md)COM インターフェイスではないインターフェイスから継承します。 COM インターフェイスの最終的な継承`IUnknown`です。 インターフェイス属性に続く任意のインターフェイスは、COM インターフェイスです。  
  
 次の例では、C3136 が生成されます。  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```