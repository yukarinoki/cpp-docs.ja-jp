---
title: コンパイラの警告 (レベル 1) C4376 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4376
dev_langs:
- C++
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 615faaaa586e60a32ce670cd554a8b0b1c157a25
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4376"></a>コンパイラの警告 (レベル 1) C4376
アクセス指定子 'old_specifier:' はサポートされていません。'new_specifier:' を使用してください  
  
 メタデータの型とメンバーのアクセシビリティを指定する方法の詳細については、次を参照してください[可視性を入力](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)と[メンバーの可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)で[する方法: を定義すると消費クラスと構造体 (C + + CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)。  
  
## <a name="example"></a>例  
 次の例では、C4376 を生成します。  
  
```  
// C4376.cpp  
// compile with: /clr /W1 /c  
public ref class G {  
public public:   // C4376  
   void m2();  
};  
  
public ref class H {  
public:   // OK  
   void m2();  
};  
```