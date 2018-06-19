---
title: コンパイラ エラー C3755 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3755
dev_langs:
- C++
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3602f78659e58de9dc394f6887901c46de8de60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267110"
---
# <a name="compiler-error-c3755"></a>コンパイラ エラー C3755
'delegate': デリゲートを定義することがない可能性があります  
  
 A [delegate (C++ コンポーネント拡張)](../../windows/delegate-cpp-component-extensions.md)宣言しますが、定義されていないことができます。  
  
## <a name="example"></a>例  
 次の例では、C3755 を生成します。  
  
```  
// C3755.cpp  
// compile with: /clr /c  
delegate void MyDel() {};   // C3755  
```  
  
## <a name="example"></a>例  
 C3755 は、デリゲートのテンプレートを作成しようとする場合にも発生することができます。 次の例では、C3755 を生成します。  
  
```  
// C3755_b.cpp  
// compile with: /clr /c  
ref struct R {  
   template<class T>  
   delegate void D(int) {}   // C3755  
};  
```