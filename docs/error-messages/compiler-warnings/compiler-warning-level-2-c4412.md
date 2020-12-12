---
description: '詳細情報: コンパイラの警告 (レベル 2) C4412'
title: コンパイラの警告 (レベル 2) C4412
ms.date: 11/04/2016
f1_keywords:
- C4412
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
ms.openlocfilehash: 9b7ce857d5b0545ac620e94bda9655dde0f63489
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208633"
---
# <a name="compiler-warning-level-2-c4412"></a>コンパイラの警告 (レベル 2) C4412

> '*function*': 関数シグネチャに型 '*type*' が含まれています。C++ オブジェクトは、純粋なコードと混合またはネイティブの間で渡すことは安全ではありません。

## <a name="remarks"></a>解説

**/Clr: pure** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。 純粋にする必要があるコードがある場合は、それを C# に移植することをお勧めします。

コンパイラは、実行時エラーの原因となる可能性のある安全ではない状況を検出しました。これは、 **/clr: pure** コンパイル単位から dllimport を介してインポートされた関数への呼び出しが行われ、関数シグネチャに安全でない型が含まれています。 型にメンバー関数が含まれている場合、または unsafe 型または unsafe 型への間接参照であるデータメンバーがある場合、型は安全ではありません。

これは安全ではありません。これは、純粋なコードとネイティブコードの間 (またはネイティブとマネージの混合) の既定の呼び出し規約が異なるためです。 `dllimport`関数を **/clr: pure** コンパイル単位にインポートする場合は、シグネチャ内の各型の宣言が、関数をエクスポートするコンパイル単位の宣言と同じであることを確認してください (暗黙的な呼び出し規約の違いについては特に注意してください)。

仮想メンバー関数は、特に予期しない結果を招く可能性があります。  ただし、仮想ではない関数でも、正しい結果が得られるようにテストする必要があります。 正しい結果が得られることが確実な場合は、この警告を無視してもかまいません。

C4412 は既定ではオフになっています。 詳細については、「 [既定でオフになっているコンパイラの警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」および「 [dllimport」を](../../cpp/dllexport-dllimport.md) 参照してください。

この警告を解決するには、型からすべての関数を削除します。

## <a name="examples"></a>例

次の例では、C4412 が生成されます。

```cpp
// C4412.cpp
// compile with: /c /W2 /clr:pure
#pragma warning (default : 4412)

struct Unsafe {
   virtual void __cdecl Test();
};

struct Safe {
   int i;
};

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   Unsafe *pUnsafe = func();   // C4412
   // pUnsafe->Test();

   Safe *pSafe = func2();   // OK
}
```

次のサンプルは、2つの型を宣言するヘッダーファイルです。 `Unsafe`メンバー関数があるため、型は安全ではありません。

```cpp
// C4412.h
struct Unsafe {
   // will be __clrcall if #included in pure compilation
   // defaults to __cdecl in native or mixed mode compilation
   virtual void Test(int * pi);

   // try the following line instead
   // virtual void __cdecl Test(int * pi);
};

struct Safe {
   int i;
};
```

このサンプルでは、ヘッダーファイルで定義されている型を使用して関数をエクスポートします。

```cpp
// C4412_2.cpp
// compile with: /LD
#include "C4412.h"

void Unsafe::Test(int * pi) {
   *pi++;
}

__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }
```

**/Clr: pure** コンパイルの既定の呼び出し規約は、ネイティブコンパイルとは異なります。  C4412 が含まれている場合、は `Test` 既定でに設定され `__clrcall` ます。 このプログラムをコンパイルして実行すると ( **/c** を使用しない場合)、プログラムは例外をスローします。

次の例では、C4412 が生成されます。

```cpp
// C4412_3.cpp
// compile with: /W2 /clr:pure /c /link C4412_2.lib
#pragma warning (default : 4412)
#include "C4412.h"

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   int n = 7;
   Unsafe *pUnsafe = func();   // C4412
   pUnsafe->Test(&n);

   Safe *pSafe = func2();   // OK
}
```
