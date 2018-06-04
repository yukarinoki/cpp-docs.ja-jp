---
title: コンパイラの警告 (レベル 2) C4412 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4412
dev_langs:
- C++
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47659a9ba0469b8ee719dbc686ba611e876d32c1
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704014"
---
# <a name="compiler-warning-level-2-c4412"></a>コンパイラの警告 (レベル 2) C4412

> '*関数*': 関数のシグネチャには、型が含まれています'*型*';。C++ オブジェクトは、純粋なコードの間で受け渡すに安全でないと混合またはネイティブです。

## <a name="remarks"></a>コメント

**/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。 純粋である必要があるコードがある場合は、c# に移植することをお勧めします。

ランタイム エラーの原因になる可能性のある安全でない状況が検出されました: 呼び出しはから行われていますが、 **/clr: 純粋な**dllimport と関数のシグネチャを使用してインポートされている関数をコンパイル単位には、安全でない型が含まれています. メンバー関数を含むまたはデータ メンバーが安全でない型または安全でない型への間接参照がある場合、型は安全ではありません。

これは、既定の呼び出し規約と純粋なネイティブ コードの間の違いのための安全ではありません (またはネイティブおよびマネージの混合)。 インポートするときに (を介して`dllimport`) 関数を **/clr: 純粋な**コンパイル単位、署名の各型の宣言が (特にように注意しての関数をエクスポートするコンパイル単位内と同じであることを確認相違暗黙の呼び出し規約)。

仮想メンバー関数は、傾向が予期しない結果が得られます。  ただし、非仮想関数でもは正しい結果が得られるようにテストしてください。 正しい結果を取得している場合は、この警告は無視できます。

C4412 が既定では off です。 参照してください[コンパイラの警告無効になっている既定](../../preprocessor/compiler-warnings-that-are-off-by-default.md)と[dllexport、dllimport](../../cpp/dllexport-dllimport.md)詳細についてはします。

この警告を解決するには、型からのすべての関数を削除します。

## <a name="example"></a>例

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

## <a name="example"></a>例

次のサンプルは、次の 2 つの型を宣言するヘッダー ファイルです。 `Unsafe`メンバー関数があるために、型に安全ではありません。

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

## <a name="example"></a>例

このサンプルでは、ヘッダー ファイルで定義されている型と関数をエクスポートします。

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

## <a name="example"></a>例

既定呼び出し規約、 **/clr: 純粋な**コンパイルとは異なるネイティブ コンパイルします。  C4412.h が含まれる、`Test`の既定値は`__clrcall`します。 コンパイルして、このプログラムを実行する場合 (使用しない **/c**)、プログラムは例外をスローします。

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