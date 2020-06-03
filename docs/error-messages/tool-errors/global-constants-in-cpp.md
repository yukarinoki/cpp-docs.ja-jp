---
title: C++ のグローバル定数
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: cabe5e92a496181d60536d7274eca388aba5c068
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195475"
---
# <a name="global-constants-in-c"></a>C++ のグローバル定数

C++グローバル定数には静的なリンケージがあります。 これは、C とは異なります。でグローバル定数を複数のファイルで使用C++しようとすると、未解決の外部エラーが発生します。 コンパイラはグローバル定数を最適化し、変数に予約された領域を残します。

このエラーを解決する方法の1つとして、ヘッダーファイルに const 初期化を含め、必要に応じて CPP ファイルにそのヘッダーを含めることができます。これは、関数プロトタイプの場合と同様です。 別の方法として、変数を非定数にし、評価時に定数参照を使用することもできます。

次の例では、C2019 が生成されます。

```cpp
// global_constants.cpp
// LNK2019 expected
void test(void);
const int lnktest1 = 0;

int main() {
   test();
}
```

この場合、次のようになります。

```cpp
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>参照

[リンカー ツール エラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
