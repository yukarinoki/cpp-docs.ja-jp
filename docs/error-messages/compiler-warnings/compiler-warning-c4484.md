---
title: コンパイラの警告 C4484 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4484
dev_langs:
- C++
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75531c207f0136f16109b4d69d689b883998aae2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4484"></a>コンパイラの警告 C4484
'override_function': 基本 ref クラス メソッド 'base_class_function' と一致しますが、'virtual'、'new' または 'override'; に設定されていません'new' (および 'virtual') と見なされます  
  
 コンパイルするときに **/clr**コンパイラが vtable の新しいスロットを取得する関数を意味、基本クラスの関数を暗黙的にオーバーライドされません。 解決するには、関数は、上書きするかどうかを明示的に指定します。  
  
 詳細については次を参照してください:  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [new (新しいスロット vtable の)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 は常に、エラーとして発行されます。 使用して、[警告](../../preprocessor/warning.md)を抑制する状況 C4484 プラグマ。  
  
## <a name="example"></a>例  
 次の例では、C4484 を生成します。  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```