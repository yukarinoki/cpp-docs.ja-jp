---
title: トークン連結演算子 (##)
ms.date: 11/04/2016
f1_keywords:
- '##'
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
ms.openlocfilehash: dab4da5fd65fc280d2061256a580a015917d24b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179595"
---
# <a name="token-pasting-operator-"></a>トークン連結演算子 (##)

二重シャープ記号または"トークン連結演算子 (**##**)、両方のオブジェクトのような関数に似たマクロで使用されて、「マージ」演算子と呼ばれることがあります。 この演算子を使用すると、別々のトークンを 1 つのトークンに結合できます。そのため、これをマクロ定義の最初または最後のトークンにすることはできません。

マクロ定義の仮パラメーターの前または後ろにトークン連結演算子がある場合、仮パラメーターは展開されていない実引数に即座に置き換えられます。 引数に対するマクロ展開が置換の前に行われることはありません。

次に、出現するたびにトークン連結演算子*トークン文字列*が削除され、前と後にトークンが連結されます。 結果のトークンは有効なトークンである必要があります。 有効であれば、トークンがスキャンされ、マクロ名を表す場合は置換が可能かどうかが確認されます。 この識別子は、置換前のプログラム内で連結されたトークンを認識するための名前になります。 各トークンは、他のどこか、つまり、プログラム内またはコンパイラのコマンド ラインで定義された特定のトークンを表します。 演算子の前または後の空白は、省略可能です。

この例は、プログラムの出力を指定するときの、文字列化演算子とトークン連結演算子の両方の使用方法を示しています。

```cpp
#define paster( n ) printf_s( "token" #n " = %d", token##n )
int token9 = 9;
```

マクロが次のような数値引数で呼び出された場合、

```cpp
paster( 9 );
```

このマクロは次のようになり、

```cpp
printf_s( "token" "9" " = %d", token9 );
```

さらに、次のようになります。

```cpp
printf_s( "token9 = %d", token9 );
```

## <a name="example"></a>例

```cpp
// preprocessor_token_pasting.cpp
#include <stdio.h>
#define paster( n ) printf_s( "token" #n " = %d", token##n )
int token9 = 9;

int main()
{
   paster(9);
}
```

```Output
token9 = 9
```

## <a name="see-also"></a>関連項目

[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)