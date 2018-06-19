---
title: コンパイラ エラー C2662 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2662
dev_langs:
- C++
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4e5f40fcc93739cabd2d5bd73bac6cce2332323
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235348"
---
# <a name="compiler-error-c2662"></a>コンパイラ エラー C2662
'function': 'type1' から 'type2' への 'this' ポインターを変換できません  
  
 コンパイラは変換できませんでした、`this`からポインター`type1`に`type2`です。  
  
 このエラーは、以外を呼び出すことによって発生することができます`const`メンバー関数を`const`オブジェクト。  考えられる解決策:  
  
-   削除、`const`オブジェクトの宣言からです。  
  
-   追加`const`メンバー関数をします。  
  
 次の例では、C2662 が生成されます。  
  
```  
// C2662.cpp  
class C {  
public:  
   void func1();  
   void func2() const{}  
} const c;  
  
int main() {  
   c.func1();   // C2662  
   c.func2();   // OK  
}  
```  
  
 コンパイルするときに **/clr**で関数を呼び出すことはできません、`const`または`volatile`マネージ型を修飾します。 Const マネージ オブジェクトでメソッドを呼び出すことはできませんのでマネージ クラスの const メンバー関数を宣言することはできません。  
  
```  
// C2662_b.cpp  
// compile with: /c /clr  
ref struct M {  
   property M^ Type {  
      M^ get() { return this; }  
   }  
  
   void operator=(const M %m) {  
      M ^ prop = m.Type;   // C2662  
   }  
};  
  
ref struct N {  
   property N^ Type {  
      N^ get() { return this; }  
   }  
  
   void operator=(N % n) {  
      N ^ prop = n.Type;   // OK  
   }  
};  
```  
  
 次の例では、C2662 が生成されます。  
  
```  
// C2662_c.cpp  
// compile with: /c  
// C2662 expected  
typedef int ISXVD;  
typedef unsigned char BYTE;  
  
class LXBASE {  
protected:  
    BYTE *m_rgb;  
};  
  
class LXISXVD:LXBASE {  
public:  
   // Delete the following line to resolve.  
   ISXVD *PMin() { return (ISXVD *)m_rgb; }  
  
   ISXVD *PMin2() const { return (ISXVD *)m_rgb; };   // OK  
};  
  
void F(const LXISXVD *plxisxvd, int iDim) {  
   ISXVD isxvd;  
   // Delete the following line to resolve.  
   isxvd = plxisxvd->PMin()[iDim];  
  
   isxvd = plxisxvd->PMin2()[iDim];    
}  
```