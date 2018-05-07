---
title: コンパイラ エラー C2979 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2979
dev_langs:
- C++
helpviewer_keywords:
- C2979
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07a28faaf7452a96759879b001cb9b078dd86f88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2979"></a>コンパイラ エラー C2979
明示的な特殊化はジェネリックではサポートされていません  
  
 ジェネリック クラスの宣言が正しくありません。  参照してください[ジェネリック](../../windows/generics-cpp-component-extensions.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C2979 が生成されます。  
  
```  
// C2979.cpp  
// compile with: /clr /c  
generic <>   
ref class Utils {};   // C2979 error  
  
generic <class T>  
ref class Utils2 {};   // OK  
```