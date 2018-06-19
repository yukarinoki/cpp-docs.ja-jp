---
title: コンパイラ エラー C3914 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3914
dev_langs:
- C++
helpviewer_keywords:
- C3914
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3818c54f3720bdff92280e04a4750ed1b4f238c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270701"
---
# <a name="compiler-error-c3914"></a>コンパイラ エラー C3914
既定のプロパティを静的にすることはできません。  
  
既定のプロパティの宣言が正しくありません。  詳細については、次を参照してください。[する方法: プロパティを使用して C + + CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)です。  
  
## <a name="example"></a>例  
次の例では、C3914 を生成し、その修正方法を示しています。  
  
```  
// C3914.cpp  
// compile with: /clr /c  
ref struct X {  
   static property int default[int] {   // C3914  
   // try the following line instead  
   // property int default[int] {  
      int get(int) { return 0; }  
      void set(int, int) {}  
   }  
};  
```