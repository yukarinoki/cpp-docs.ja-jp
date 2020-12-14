---
description: 詳細については、「C++ のグローバル定数」を参照してください。
title: C++ のグローバル定数
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: 8e960e7e10942fc231fcdeafef6e8d755694c460
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261659"
---
# <a name="global-constants-in-c"></a>C++ のグローバル定数

C++ グローバル定数には静的なリンケージがあります。 これは、C とは異なります。C++ でグローバル定数を複数のファイルで使用しようとすると、未解決の外部エラーが発生します。 コンパイラはグローバル定数を最適化し、変数に予約された領域を残します。

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

## <a name="see-also"></a>関連項目

[リンカツールエラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
