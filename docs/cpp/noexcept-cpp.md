---
title: noexcept (C++)
ms.date: 11/19/2019
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: cc669a43ff9acbb98ce970c21cba5ac9cdc5b732
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161049"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++ 11:** 関数が例外をスローするかどうかを指定します。

## <a name="syntax"></a>構文

> *noexcept-式*: &nbsp;&nbsp;&nbsp;&nbsp;**noexcept** &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *定数式* **)**

### <a name="parameters"></a>パラメーター

*定数式*<br/>
潜在的な例外の種類のセットが空かどうかを表す**ブール**型の定数式。 無条件バージョンは `noexcept(true)`に相当します。

## <a name="remarks"></a>解説

*Noexcept 式*は、例外*指定*の一種であり、関数を終了する例外の例外ハンドラーによって照合される可能性のある型のセットを表す関数宣言のサフィックスです。 単項条件演算子は、 *constant_expression*が**true**を生成し、無条件シノニム**noexcept**で、関数を終了する可能性のある例外の種類のセットが空であることを指定する `noexcept(`*constant_expression*`)` ます。 つまり、関数は例外をスローしないため、例外をスコープ外に反映することはできません。 演算子は、 *constant_expression*が**false**を返すか、または (デストラクターまたは解放関数以外の) 例外の指定がない場合に、関数を終了できる可能性のある例外のセットがすべての型のセットであることを示す`)` *constant_expression* `noexcept(`ます。

関数を**noexcept**としてマークします。この関数は、直接または間接的に呼び出したすべての関数が**noexcept**または**const**でもある場合に限ります。 コンパイラは、 **noexcept**関数にバブルアップする可能性のある例外のすべてのコードパスを必ずチェックするわけではありません。 例外によって `noexcept`マークされた関数の外側のスコープが終了した場合、 [std:: terminate](../standard-library/exception-functions.md#terminate)が直ちに呼び出され、スコープ内のオブジェクトのデストラクターが呼び出される保証はありません。 動的例外指定子 `throw()`ではなく、 **noexcept**を使用します。これは標準では非推奨となりました。 例外がコールスタックの上位に伝達されないようにする関数に `noexcept` を適用することをお勧めします。 関数が**noexcept**として宣言されている場合、コンパイラは複数の異なるコンテキストでより効率的なコードを生成できます。 詳細については、「[例外の指定](exception-specifications-throw-cpp.md)」を参照してください。

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

## <a name="see-also"></a>参照

[例外C++とエラー処理に関する最新のベストプラクティス](errors-and-exception-handling-modern-cpp.md)<br/>
[例外の指定 (throw、noexcept)](exception-specifications-throw-cpp.md)
