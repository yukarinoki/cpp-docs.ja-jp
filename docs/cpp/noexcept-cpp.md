---
title: noexcept (C++)
ms.date: 11/19/2019
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: 2618c7e9b35e4ba50ad1bda20a8694dd829ec2d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223643"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++ 11:** 関数が例外をスローするかどうかを指定します。

## <a name="syntax"></a>構文

> *noexcept-式*: \
> &nbsp;&nbsp;&nbsp;&nbsp;**`noexcept`**\
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *定数式* **)**

### <a name="parameters"></a>パラメーター

*定数式*<br/>
**`bool`** 潜在的な例外の種類のセットが空かどうかを表す型の定数式。 無条件バージョンは、と同じです `noexcept(true)` 。

## <a name="remarks"></a>解説

*Noexcept 式*は、例外*指定*の一種であり、関数を終了する例外の例外ハンドラーによって照合される可能性のある型のセットを表す関数宣言のサフィックスです。 Constant_expression によって生成される単項条件演算子 `noexcept(` *constant_expression* `)` *constant_expression* **`true`** とその無条件シノニム **`noexcept`** は、関数を終了できる可能性のある例外の種類のセットが空であることを指定します。 つまり、関数は例外をスローしないため、例外をスコープ外に反映することはできません。 Constant_expression によって `noexcept(` *constant_expression* `)` 生成される演算子 constant_expression、 *constant_expression* **`false`** または (デストラクターまたは解放関数以外の) 例外の指定がない場合は、関数を終了できる可能性のある例外のセットがすべての型のセットであることを示します。

関数は、 **`noexcept`** 直接または間接的に呼び出すすべての関数もまたはである場合にのみ、としてマークし **`noexcept`** **`const`** ます。 コンパイラは、関数にバブルアップする可能性のある例外のすべてのコードパスを必ずチェックするわけではありません **`noexcept`** 。 例外によってマークされた関数の外側のスコープが終了した場合 **`noexcept`** 、 [std:: terminate](../standard-library/exception-functions.md#terminate)がすぐに呼び出され、スコープ内のオブジェクトのデストラクターが呼び出される保証はありません。 **`noexcept`** 動的例外指定子の代わりにを使用します `throw()` 。これは標準で非推奨とされます。 **`noexcept`** 例外がコールスタックの上位に伝達されることを許可しないすべての関数に適用することをお勧めします。 関数を宣言すると **`noexcept`** 、コンパイラはいくつかの異なるコンテキストでより効率的なコードを生成できます。 詳細については、「[例外の指定](exception-specifications-throw-cpp.md)」を参照してください。

## <a name="example"></a>例

引数をコピーするテンプレート関数 **`noexcept`** は、コピーされるオブジェクトが plain old data type (POD) であるという条件で宣言される場合があります。 このような関数は、次のように宣言することができます。

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
