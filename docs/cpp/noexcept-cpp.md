---
title: noexcept (C++)
ms.date: 01/12/2018
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: c314b554abb6c10e62b143f554777af50267e4e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620533"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++ 11:** 関数が例外をスローするかどうかを指定します。

## <a name="syntax"></a>構文

> *noexcept 式*: &nbsp; &nbsp; &nbsp; &nbsp; **noexcept** &nbsp; &nbsp; &nbsp; &nbsp; **noexcept(** *定数式* **)**

### <a name="parameters"></a>パラメーター

*constant-expression*<br/>
型の定数式**bool**潜在的な例外の種類のセットが空かどうかを表します。 無条件のバージョンは等価`noexcept(true)`します。

## <a name="remarks"></a>Remarks

A *noexcept 式*は一種の*例外仕様*関数の宣言に存在するすべての例外の例外ハンドラーによって照合される可能性がありますの種類のセットを表すためのサフィックスを関数。 単項条件演算子`noexcept(` *constant_expression* `)`場所*constant_expression* yeilds **true**、およびその無条件のシノニム**noexcept**関数を終了できる潜在的な例外の種類のセットが空であるかを指定します。 関数は例外をスローしませんし、そのスコープ外に伝達する例外を許可しません。 演算子`noexcept(` *constant_expression* `)`場所*constant_expression* yeilds **false**例外の指定の有無(以外の場合、デストラクター、または割り当て解除関数の) は、関数を終了できる潜在的な例外のセットが一連のすべての種類であることを示します。

関数としてマーク**noexcept**も、直接または間接的に、呼び出されるすべての関数の場合にのみ**noexcept**または**const**します。 コンパイラが必ずしもすべてのコード パスの最大のバブルが例外をチェックする**noexcept**関数。 例外でマークされた関数の外側のスコープは終了かどうか`noexcept`、 [std::terminate](../standard-library/exception-functions.md#terminate)がすぐに、呼び出されると、任意のスコープ内のオブジェクトのデストラクターが呼び出される保証はありません。 使用**noexcept**動的例外指定子ではなく`throw()`、するは、標準で推奨されなくなりました。 適用することをお勧めします。`noexcept`コール スタックに伝播する例外を許可しないすべての関数。 関数が宣言されている場合**noexcept**、複数の異なるコンテキストでより効率的なコードを生成するコンパイラが有効にします。 詳細については、次を参照してください。[例外仕様](exception-specifications-throw-cpp.md)します。

## <a name="example"></a>例

引数をコピーするテンプレート関数を宣言することがあります**noexcept**ことを条件にコピーされるオブジェクトは、プレーンな古いデータ型 (POD)。 このような関数は、次のように宣言することができます。

```cpp
#include <type_traits>

template <typename T>
T copy_object(const T& obj) noexcept(std::is_pod<T>)
{
   // ...
}
```

## <a name="see-also"></a>関連項目

[C++ 例外処理](cpp-exception-handling.md)<br/>
[例外の仕様 (スロー、noexcept)](exception-specifications-throw-cpp.md)