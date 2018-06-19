---
title: コンパイラ エラー C3420 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3420
dev_langs:
- C++
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d7614d07cf98ae9fe857809bf9400d36a48ab0b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255059"
---
# <a name="compiler-error-c3420"></a>コンパイラ エラー C3420
'finalizer' : ファイナライザーを仮想にすることはできません  
  
 ファイナライザーは、それを囲む型から非仮想的にのみ呼び出すことができます。 したがって、仮想のファイナライザーを宣言すると、エラーになります。  
  
 詳細については、次を参照してください。[する方法のデストラクターおよびファイナライザー: を定義およびクラスと構造体を使用 (C + + CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)です。  
  
## <a name="example"></a>例  
 次の例では C3420 が生成されます。  
  
```  
// C3420.cpp  
// compile with: /clr /c  
ref class R {  
   virtual !R() {}   // C3420  
};  
```