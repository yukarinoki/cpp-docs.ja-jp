---
title: コンパイラ エラー C3379 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3379
dev_langs:
- C++
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ded7ebfba6ab9f9120ebfa48c1942209a74e704
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258284"
---
# <a name="compiler-error-c3379"></a>コンパイラ エラー C3379
'class': 入れ子になったクラスは、その宣言の一部としてアセンブリ アクセス指定子を持つことはできません  
  
 クラスまたは構造体などのマネージ型に適用すると、[パブリック](../../cpp/public-cpp.md)と[プライベート](../../cpp/private-cpp.md)キーワードは、クラスがアセンブリ メタデータを通じて公開されるかどうかを示します。 `public` または`private`外側のクラスのアセンブリのアクセスを継承しますが、入れ子になったクラスには適用できません。  
  
 使用すると[/clr](../../build/reference/clr-common-language-runtime-compilation.md)、`ref`と`value`キーワードは、クラスが管理されていることを示します (を参照してください[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md))。  
  
 次の例では、C3379 が生成されます。  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  
