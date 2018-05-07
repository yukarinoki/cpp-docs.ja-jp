---
title: コンパイラ エラー C2059 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2059
dev_langs:
- C++
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69182e4b27b474cafe60b71b02594a244f65a09b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2059"></a>コンパイラ エラー C2059
構文エラー: 'token'  
  
 トークンには、構文エラーが発生しました。  
  
 次の例を宣言する行のエラー メッセージを生成する`j`です。  
  
```  
// C2059e.cpp  
// compile with: /c  
// C2143 expected  
// Error caused by the incorrect use of '*'.  
   int j*; // C2059   
```  
  
 エラーの原因を特定するには、エラー メッセージに記載されている行だけでなく、その上に行を確認します。 行を調べては増えませんに関する問題の手掛かりを場合は、エラー メッセージに記載されている行とその上におそらく複数の行をコメント アウトしてください。  
  
 直後にあるシンボルのエラー メッセージが発生したかどうか、`typedef`変数、変数が、ソース コードで定義されていることを確認します。  
  
 シンボルと評価された場合、何も発生する可能性が C2059 を取得することがありますと **/D** `symbol` **=** をコンパイルするために使用します。  
  
```  
// C2059a.cpp  
// compile with: /DTEST=  
#include <stdio.h>  
  
int main() {  
   #ifdef TEST  
      printf_s("\nTEST defined %d", TEST);   // C2059  
   #else  
      printf_s("\nTEST not defined");  
   #endif  
}  
```  
  
 C2059 エラーが発生することが別のケースは、関数の既定の引数で構造体を指定するアプリケーションをコンパイルする場合です。 引数の既定値は、式にする必要があります。 初期化子リスト — たとえば、いずれかの構造体の初期化に使用する — 式ではありません。  この問題を解決するには、必要な初期化を実行するコンス トラクターを定義します。  
  
 次の例では、C2059 が生成されます。  
  
```  
// C2059b.cpp  
// compile with: /c  
struct ag_type {  
   int a;  
   float b;  
   // Uncomment the following line to resolve.  
   // ag_type(int aa, float bb) : a(aa), b(bb) {}   
};  
  
void func(ag_type arg = {5, 7.0});   // C2059  
void func(ag_type arg = ag_type(5, 7.0));   // OK  
```  
  
 メンバーのテンプレート クラスまたはクラスの外側の関数を定義する場合にも、C2059 を取得できます。 詳細については、次を参照してください。[サポート技術情報の記事 241949](http://support.microsoft.com/kb/241949)です。  
  
 正しくない形式のキャストの C2059 に発生します。  
  
 次の例では、C2059 が生成されます。  
  
```  
// C2059c.cpp  
// compile with: /clr  
using namespace System;  
ref class From {};  
ref class To : public From {};  
  
int main() {  
   From^ refbase = gcnew To();  
   To^ refTo = safe_cast<To^>(From^);   // C2059  
   To^ refTo2 = safe_cast<To^>(refbase);   // OK  
}  
```  
  
 C2059 は、ピリオドを含む名前空間の名前を作成しようとする場合にも発生することができます。  
  
 次の例では、C2059 が生成されます。  
  
```  
// C2059d.cpp  
// compile with: /c  
namespace A.B {}   // C2059  
  
// OK  
namespace A  {  
   namespace B {}  
}  
```  
  
 C2059 は演算子名を修飾するときに発生する可能性が (`::`、 `->`、および`.`) キーワードが続かなければなりません`template`この例のように。  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::Rebind<X>::Other AX; // error C2059  
};  
  
```  
  
 既定では、C++ であると推定`AY::Rebind`; テンプレートではありません、次にそのため、`<`小として解釈されます-不等号です。  必要がありますコンパイラに通知する明示的にいる`Rebind`テンプレートは、山かっこを正しく解析することができるようにします。 このエラーを解決するには、`template`依存する型の名前を次に示すようにキーワード。  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::template Rebind<X>::Other AX; // correct  
};  
  
```