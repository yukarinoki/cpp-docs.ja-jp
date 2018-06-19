---
title: コンパイラ エラー C2158 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2158
dev_langs:
- C++
helpviewer_keywords:
- C2158
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b1a7151b58d02b582bf0c73fb4bb185f2b3c0ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171152"
---
# <a name="compiler-error-c2158"></a>コンパイラ エラー C2158
'type': #pragma make_public ディレクティブは、現在テンプレートでないネイティブの型にのみサポートされています  
  
 [make_public](../../preprocessor/make-public.md) プラグマは、ネイティブの非テンプレート型にのみ適用できます。  
  
## <a name="example"></a>例  
 次の例では C2158 が生成されます。  
  
```  
// C2158.cpp  
// compile with: /clr /c  
ref class A {};  
#pragma make_public(A)   // C2158  
  
template< typename T >  
class B {};  
#pragma make_public(B)   // C2158  
#pragma make_public(B<int>)   // C2158  
  
void C () {}  
#pragma make_public(C)   // C2158  
  
class D {};  
#pragma make_public(D)   // OK  
```