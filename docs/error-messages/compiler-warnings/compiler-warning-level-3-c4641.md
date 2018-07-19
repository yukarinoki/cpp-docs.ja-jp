---
title: コンパイラの警告 (レベル 3) C4641 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4641
dev_langs:
- C++
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea8413971353e7ffbe6579412d0eed9c735b91b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291438"
---
# <a name="compiler-warning-level-3-c4641"></a>コンパイラの警告 (レベル 3) C4641
XML ドキュメント コメントはあいまいな相互参照  
  
 コンパイラは、明確に参照を解決できませんでした。 この警告を解決するのには、参照があいまいでないために必要なパラメーター情報を指定します。  
  
 詳細については、「 [XML Documentation](../../ide/xml-documentation-visual-cpp.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C4641 を生成します。  
  
```  
// C4641.cpp  
// compile with: /W3 /doc /clr /c  
  
/// <see cref="f" />   // C4641  
// try the following line instead  
// /// <see cref="f(int)" />  
public ref class GR {  
public:  
   void f( int ) {}  
   void f( char ) {}  
};  
```