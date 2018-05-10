---
title: コンパイラの警告 (レベル 1) C4383 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4383
dev_langs:
- C++
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b78209cf4e3e320cca8b161a4e6c99eaca6d771c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4383"></a>コンパイラの警告 (レベル 1) C4383
'instance_dereference_operator': ユーザー定義の 'operator' 演算子が存在するときに、ハンドルの逆参照の意味を変更できますオペランドに対して明示的に指定する静的関数として、演算子を書き込んでください。  
  
 マネージ型に逆参照演算子のインスタンスのユーザー定義の上書きを追加すると、ハンドルのオブジェクトを取得する型の逆参照演算子の機能を無効可能性があります。 検討逆参照演算子を静的なユーザー定義を記述します。  
  
 詳細については、次を参照してください。[オブジェクト演算子 (^) へのハンドル](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md)と[参照演算子の追跡](../../windows/tracking-reference-operator-cpp-component-extensions.md)です。  
  
 また、インスタンス演算子では、参照されたメタデータを使用して他の言語コンパイラを使用できません。 詳細については、次を参照してください。[ユーザー定義の演算子 (C + + CLI)](../../dotnet/user-defined-operators-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 次の例では、C4383 を生成します。  
  
```  
// C4383.cpp  
// compile with: /clr /W1  
  
ref struct S {  
   int operator*() { return 0; }   // C4383  
};  
  
ref struct T {  
   static int operator*(T%) { return 0; }  
};   
  
int main() {  
   S s;  
   S^ pS = %s;  
  
   T t;  
   T^ pT = %t;  
   T% rT = *pT;  
}  
```