---
title: コンパイラ エラー C3374 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3374
dev_langs:
- C++
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd06f0e63ab1c467b9359c38ad77056440535aba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253893"
---
# <a name="compiler-error-c3374"></a>コンパイラ エラー C3374
delegate インスタンスを作成する場合以外に、'関数' のアドレスを指定できません  
  
 delegate インスタンスを作成する以外のコンテキストで、関数のアドレスが取得されました。  
  
 次の例では警告 C3374 が生成されます。  
  
```  
// C3374.cpp  
// compile with: /clr  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      System::Console::WriteLine("in func1 {0}", i);  
   }  
};  
  
int main() {  
   &A::func1;   // C3374  
  
   // OK  
   A ^ a = gcnew A;  
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [方法: デリゲートを定義および使用する (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)