---
title: noexcept (C++)
ms.date: 11/19/2019
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: efb5ad272c8857e7a0dbd2c75885b826f2b8b9f8
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825365"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++ 11:** 関数が例外をスローするかどうかを指定します。

## <a name="syntax"></a>構文

> *noexcept-式*: \
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept**\
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *定数式* **)**

### <a name="parameters"></a>パラメーター

*定数式*<br/>
潜在的な例外の種類のセットが空かどうかを表す**ブール**型の定数式。 無条件バージョンは、と同じ`noexcept(true)`です。

## <a name="remarks"></a>解説

*Noexcept 式*は、例外*指定*の一種であり、関数を終了する例外の例外ハンドラーによって照合される可能性のある型のセットを表す関数宣言のサフィックスです。 単項条件`noexcept(`演算子*constant_expression* `)` *constant_expression*が**true**を生成し、その無条件シノニム**noexcept**では、関数を終了できる可能性のある例外の種類のセットが空であることを指定します。 つまり、関数は例外をスローしないため、例外をスコープ外に反映することはできません。 `noexcept(` *constant_expression* Constant_expression`)`演算子は、 *constant_expression*が**false**を生成した場合、または (デストラクターまたは解放関数以外の) 例外の指定がない場合、関数を終了できる可能性のある例外のセットがすべての型のセットであることを示します。

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

[例外とエラー処理に関する最新の C++ のベストプラクティス](errors-and-exception-handling-modern-cpp.md)<br/>
[例外の指定 (throw、noexcept)](exception-specifications-throw-cpp.md)
