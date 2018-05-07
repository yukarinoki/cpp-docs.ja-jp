---
title: コンパイラ エラー C3155 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3155
dev_langs:
- C++
helpviewer_keywords:
- C3155
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 383727d6f1665544654c047f37f094a38d6b5309
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3155"></a>コンパイラ エラー C3155
属性はプロパティ インデクサーでは使用できません。  
  
インデックス付きプロパティの宣言が正しくありません。 詳細については、次を参照してください。[する方法: プロパティを使用して C + + CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)です。  
  
## <a name="example"></a>例  
次の例では、C3155 を生成します。  
  
```  
// C3155.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct R {  
   property int F[[ParamArray] int] {   // C3155  
   // try the following line instead  
   // property int F[ int] {   // OK  
      int get(int i) {   
         return 0;   
      }  
   }  
};  
```