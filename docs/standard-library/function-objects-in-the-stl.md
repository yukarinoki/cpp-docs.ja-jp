---
title: C++ 標準ライブラリの関数オブジェクト
ms.date: 11/04/2016
helpviewer_keywords:
- functors
- C++ Standard Library, functors
- C++ Standard Library, function objects
- function objects
ms.assetid: 85f8a735-2c7b-4f10-9c4d-95c666ec4192
ms.openlocfilehash: 7af56f52b59b03dfed9e1233473239274a0dcbd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437120"
---
# <a name="function-objects-in-the-c-standard-library"></a>C++ 標準ライブラリの関数オブジェクト

*関数オブジェクト*、つまり *ファンクター*は、operator() を実装する任意の型です。 この演算子は *呼び出し演算子* と呼ばれます。 *適用演算子*と呼ばれることもあります。 C++ 標準ライブラリで、関数オブジェクトは、主にコンテナーの並べ替え条件として、およびアルゴリズム内で使用されます。

関数オブジェクトには、直接的な関数呼び出しに勝る 2 つの主な利点があります。 1 つ目に、関数オブジェクトには状態を含めることができます。 2 つ目に、関数オブジェクトは型であるため、テンプレート パラメーターとして使用できます。

## <a name="creating-a-function-object"></a>関数オブジェクトの作成

関数オブジェクトを作成するには、型を作成し、次のように operator() を実装します。

```cpp
class Functor
{
public:
    int operator()(int a, int b)
    {
        return a < b;
    }
};
```

`main` 関数の最後の行は関数オブジェクトを呼び出す方法を示しています。 これは関数呼び出しに見えますが、実際には Functor 型の operator() を呼び出しています。 関数オブジェクト呼び出しと関数の呼び出しが類似しているため、関数オブジェクトという用語が生じました。

## <a name="function-objects-and-containers"></a>関数オブジェクトとコンテナー

C++ 標準ライブラリでは、[\<functional>](../standard-library/functional.md) ヘッダー ファイルにいくつかの関数オブジェクトが含まれています。 これらの関数オブジェクトの用途の 1 つに、コンテナーの並べ替え条件としての使用があります。 たとえば、 `set` コンテナーは次のように宣言されます。

```cpp
template <class Key,
    class Traits=less<Key>,
    class Allocator=allocator<Key>>
class set
```

2 番目のテンプレート引数は、関数オブジェクト `less`です。 この関数オブジェクトを返します**true**以下は、最初のパラメーターが渡された場合、2 番目のパラメーターよりも渡されます。 一部のコンテナーはその要素を並べ替えるため、コンテナーには 2 つの要素を比較する方法が必要です。関数オブジェクトを使えば、これが可能になります。 関数オブジェクトを作成し、それをコンテナーのテンプレート リストに指定すると、独自の並べ替え条件を定義できます。

## <a name="function-objects-and-algorithms"></a>関数オブジェクトとアルゴリズム

関数オブジェクトのもう 1 つの用途は、アルゴリズム内での使用です。 たとえば、 `remove_if` アルゴリズムは次のように宣言されます。

```cpp
template <class ForwardIterator, class Predicate>
ForwardIterator remove_if(
    ForwardIterator first,
    ForwardIterator last,
    Predicate pred);
```

`remove_if` への最後の引数は、ブール値 ( *述語*) を返す関数オブジェクトです。 関数オブジェクトの結果は場合**true**、反復子がアクセスされているコンテナーから要素を削除し、`first`と`last`します。 引数 `pred` には、[\<functional>](../standard-library/functional.md) ヘッダー内で宣言したいずれかの関数オブジェクトを使用するか、独自の関数オブジェクトを作成できます。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
