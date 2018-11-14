---
title: コンパイラ エラー C2059
ms.date: 11/04/2016
f1_keywords:
- C2059
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
ms.openlocfilehash: dec5f7a9eb91603b129cfb589352b6ee2579e553
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521792"
---
# <a name="compiler-error-c2059"></a>コンパイラ エラー C2059

構文エラー: 'token'

トークンには、構文エラーが発生しました。

次の例には、宣言している行のエラー メッセージが生成されます。`j`します。

```
// C2059e.cpp
// compile with: /c
// C2143 expected
// Error caused by the incorrect use of '*'.
   int j*; // C2059
```

エラーの原因を判断するには、というエラー メッセージに記載されている行だけでなく、その上の行を確認します。 行を調べても、問題に関する手がかりは生成されない場合、は、エラー メッセージに記載されている行とおそらく上に複数の行をコメント アウトしてください。

シンボルの直後にエラー メッセージが発生したかどうか、`typedef`変数、変数がソース コードで定義されていることを確認します。

シンボルと評価された場合、何も発生する可能性が C2059 してしまう場合 **/D** `symbol` **=** をコンパイルするために使用します。

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

C2059 が発生することが別のケースでは、関数の既定の引数で構造体を指定するアプリケーションをコンパイルする場合です。 引数の既定値は、式を指定する必要があります。 初期化子リスト: 構造体の初期化に使用されるものなど、式ではありません。  この問題を解決するには、必要な初期化を実行するコンス トラクターを定義します。

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

C2059 は正しくない形式のキャストは発生します。

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

ピリオドを含む名前空間の名前を作成しようとした場合も、C2059 が発生します。

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

演算子名を修飾することができる C2059 が発生する可能性が (`::`、`->`と`.`)、キーワードの後に`template`この例のように。

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

C++ では既定では、想定される`AY::Rebind`; テンプレートではありません、次にそのため、`<`小として解釈されます-記号。  必要がありますをコンパイラに指示明示的にいる`Rebind`テンプレートは、山かっして正しく解析できるようにします。 このエラーを修正するには、使用、`template`依存の型の名前を次に示すようにキーワード。

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