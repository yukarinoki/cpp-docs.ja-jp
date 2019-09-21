---
title: noexcept (C++)
ms.date: 01/12/2018
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: cf53aca918e36d18ab7f8aa14b01caaf0e55627c
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975901"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++ 11:** 関数が例外をスローするかどうかを指定します。

## <a name="syntax"></a>構文

> *noexcept-expression*: &nbsp;&nbsp;&nbsp;&nbsp;**noexcept** &nbsp;&nbsp;&nbsp;&nbsp;**noexcept(** *constant-expression* **)**

### <a name="parameters"></a>パラメーター

*constant-expression*<br/>
潜在的な例外の種類のセットが空かどうかを表す**ブール**型の定数式。 無条件バージョンは、と同じ`noexcept(true)`です。

## <a name="remarks"></a>Remarks

*Noexcept 式*は、例外*指定*の一種であり、関数を終了する例外の例外ハンドラーによって照合される可能性のある型のセットを表す関数宣言のサフィックスです。 `noexcept(` *Constant_expression*が**true**、無条件シノニム**noexcept**の単項条件演算子*constant_expression* `)`は、一連の潜在的な例外の種類を指定します。関数を終了できますが空です。 つまり、関数は例外をスローしないため、例外をスコープ外に反映することはできません。 演算子`noexcept(` *constant_expression* where constant_expression は false を生成します。または、(デストラクターまたは解放関数以外の) 例外の指定がない場合は、`)`関数を終了できる可能性のある例外のセットは、すべての型のセットです。

関数を**noexcept**としてマークします。この関数は、直接または間接的に呼び出したすべての関数が**noexcept**または**const**でもある場合に限ります。 コンパイラは、 **noexcept**関数にバブルアップする可能性のある例外のすべてのコードパスを必ずチェックするわけではありません。 例外によってマーク`noexcept`された関数の外側のスコープが終了した場合、 [std:: terminate](../standard-library/exception-functions.md#terminate)がすぐに呼び出され、スコープ内のオブジェクトのデストラクターが呼び出される保証はありません。 動的例外指定子`throw()`ではなく、 **noexcept**を使用します。これは標準で非推奨とされます。 例外がコールスタック`noexcept`の上位に伝達されることを許可しないすべての関数に適用することをお勧めします。 関数が**noexcept**として宣言されている場合、コンパイラは複数の異なるコンテキストでより効率的なコードを生成できます。 詳細については、「[例外の指定](exception-specifications-throw-cpp.md)」を参照してください。

## <a name="example"></a>例

引数をコピーするテンプレート関数は、コピーされるオブジェクトが plain old data type (POD) であるという条件に対して、 **noexcept**として宣言される場合があります。 このような関数は、次のように宣言することができます。

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
[例外の指定 (throw、noexcept)](exception-specifications-throw-cpp.md)