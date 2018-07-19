---
title: コンパイラ エラー C3908 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3908
dev_langs:
- C++
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f971ec355c3f1c3772b2a0cd4059cf0a8abd630
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275279"
---
# <a name="compiler-error-c3908"></a>コンパイラ エラー C3908
'construct' より少ない制限の厳しいアクセス レベル  
  
 プロパティ アクセサー メソッド (get または set) は、プロパティ自体に指定されたアクセスよりも制限の緩いアクセスにはできません。  同様に、イベントのアクセサー メソッドの  
  
 詳細については、次を参照してください。[プロパティ](../../windows/property-cpp-component-extensions.md)と[イベント](../../windows/event-cpp-component-extensions.md)です。  
  
 次の例では、C3908 が生成されます。  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```