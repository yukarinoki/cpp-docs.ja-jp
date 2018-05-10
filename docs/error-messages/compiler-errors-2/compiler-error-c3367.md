---
title: コンパイラ エラー C3367 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3367
dev_langs:
- C++
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2884e38d1ad1aecef8e7b0723674ebd9849d8f40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3367"></a>コンパイラ エラー C3367
'static_member_function': バインドされていないデリゲートを作成するために静的関数を使用することはできません  
  
バインドされていないデリゲートを呼び出す場合は、オブジェクトのインスタンスを渡す必要があります。 静的メンバー関数はクラス名によって呼び出されるので、バインドされていないデリゲートは、インスタンス メンバー関数でのみインスタンス化できます。  
  
バインドされていないデリゲートの詳細については、次を参照してください。[する方法: 定義および使用するデリゲート (C + + CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)です。  
  
## <a name="example"></a>例  
次の例では C3367 が生成されます。  
  
```cpp  
// C3367.cpp  
// compile with: /clr  
ref struct R {  
   void b() {}  
   static void f() {}  
};  
  
delegate void Del(R^);  
  
int main() {  
   Del ^ a = gcnew Del(&R::b);   // OK  
   Del ^ b = gcnew Del(&R::f);   // C3367  
}  
```