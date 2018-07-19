---
title: '&lt;functional&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <functional>
- functional/std::<functional>
- std::<functional>
dev_langs:
- C++
helpviewer_keywords:
- functors
- functional header
ms.assetid: 7dd463e8-a29f-49bc-aedd-8fa53b54bfbc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6528cb1f3aa4da429cd27d1123536ab694f60ac6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961237"
---
# <a name="ltfunctionalgt"></a>&lt;functional&gt;

*関数オブジェクト* (ファンクターとも呼ばれます) とそれらのバインダーの作成に役立つ C++ 標準ライブラリ関数を定義します。 関数オブジェクトは、`operator()` を定義するオブジェクトの種類です。 関数オブジェクトは関数ポインターとしても使用できますが、一般的に、関数オブジェクトは、関数呼び出しの実行中にアクセスできる追加情報を格納するために使用されます。

## <a name="syntax"></a>構文

```cpp
#include <functional>
```

## <a name="remarks"></a>Remarks

アルゴリズムでは、単項および二項という 2 種類の関数オブジェクトが使用されます。 単項関数オブジェクトは 1 つの引数を必要とし、二項関数オブジェクトは 2 つの引数を必要とします。 関数オブジェクトと関数ポインターは述語としてアルゴリズムに渡すことができますが、関数オブジェクトは適応性があり、C++ 標準ライブラリのスコープ、柔軟性、効率が向上します。 たとえば、値をアルゴリズムに渡す前に、その値を関数にバインドする必要がある場合は、関数ポインターを使用できないことがあります。 関数アダプターを利用すると、関数ポインターが、値にバインドできる適応性のある関数オブジェクトに変換されます。 ヘッダー \<functional> には、メンバー関数を適応性のある関数オブジェクトとして呼び出すことができるメンバー関数アダプターも含まれます。 関数が引数と戻り値の型を指定する入れ子になった型宣言を持っている場合、それらの関数は適応性があります。 C++ 標準では、すべての標準オブジェクト クラスで、unary_function 基底クラスや binary_function 基底クラスから継承することによって、この適応性を実装する必要があります。 関数オブジェクトとそのアダプターを使用すると、C++ 標準ライブラリで既存のアプリケーションをアップグレードでき、ライブラリと C++ プログラミング環境との統合に役立てることができます。

Visual C の実装内の関数オブジェクトの\<機能 > が含まれています*透過的な演算子のファンクター*標準の特殊化である関数オブジェクトとテンプレートのパラメーターを受け取らず、関数の引数の完全転送と結果の完全取得を実行します。 この機能は、C++14 ドラフト標準の仕様の一部です。 これらのテンプレートの特殊化では、算術演算子のファンクター、比較演算子のファンクター、論理演算子のファンクター、ビットごとの演算子のファンクターを呼び出すときに、引数の型を指定する必要はありません。 ユーザー独自の型または異なる種類の型の組み合わせに対して算術演算子、比較演算子、論理演算子、ビットごとの演算子をオーバーロードしてから、透過的な演算子のファンクターを関数の引数として使用できます。 たとえば、ユーザー独自の型 *MyType* が `operator<` を実装する場合、型 `sort(my_collection.begin(), my_collection.end(), less<MyType>())` を明示的に指定する代わりに、`sort(my_collection.begin(), my_collection.end(), less<>())` を呼び出すことができます。

## <a name="c11c14-implementation"></a>C++11/C++14 実装

C++11/C++14 の Visual C++ 実装では、次の機能が追加されます。

- *呼び出しシグネチャ*は、戻り値の型の名前の後に、かっこで囲まれたコンマ区切りのリスト (0 個以上の引数の型が含まれます) が続きます。

- *呼び出し可能型* は、関数へのポインター、メンバー関数へのポインター、メンバー データへのポインター、関数呼び出し演算子のすぐ左にオブジェクトを示すことができるクラス型のいずれかになります。

- *呼び出し可能オブジェクト*は、呼び出し可能型のオブジェクトです。

- *呼び出しラッパーの型*は、呼び出し可能オブジェクトを保持する型であり、オブジェクトに転送される呼び出し操作をサポートします。

- *呼び出しラッパー*は、呼び出しラッパーの型のオブジェクトです。

- *ターゲット オブジェクト*は、呼び出しラッパー オブジェクトによって保持される呼び出し可能オブジェクトです。

擬似関数 `INVOKE(f, t1, t2, ..., tN)` は、次のいずれかを意味します。

- `(t1.*f)(t2, ..., tN)`。`f` がクラス `T` のメンバー関数へのポインターであり、`t1` が型 `T` のオブジェクト、型 `T` のオブジェクトへの参照、`T` から派生した型のオブジェクトへの参照のいずれかである場合。

- `((*t1).*f)(t2, ..., tN)`。`f` がクラス `T` のメンバー関数へのポインターであり、`t1` が上で説明した以外の型のオブジェクトである場合。

- `t1.*f`。N == 1 で、`f` がクラス `T` のメンバー データへのポインターであり、`t1` が型 `T` のオブジェクト、型 `T` のオブジェクトへの参照、`T` から派生した型のオブジェクトへの参照のいずれかである場合。

- `(*t1).*f`。N == 1 で、`f` がクラス `T` のメンバー データへのポインターであり、`t1` が上で説明した以外の型のオブジェクトである場合。

- `f(t1, t2, ..., tN)`。上記のいずれのケースにも該当しない場合。

擬似関数 `INVOKE(f, t1, t2, ..., tN, R)` は、暗黙的に `INVOKE(f, t1, t2, ..., tN)` に変換される `R` を意味します。

呼び出しラッパーに*弱い結果型*が含まれている場合は、そのメンバー型 `result_type` の種類は、ラッパーのターゲット オブジェクトの型 `T` に基づいて次のようなります。

- `T` が関数へのポインターである場合、`result_type` は 戻り値の型 `T` のシノニムになります。

- `T` がメンバー関数へのポインターである場合、`result_type` は 戻り値の型 `T` のシノニムになります。

- `T` がメンバー型 `result_type` を持つクラス型である場合、`result_type` は `T::result_type` のシノニムになります。

- それ以外の場合は、メンバー `result_type` は存在しません。

すべての呼び出しラッパーには、移動コンストラクターとコピー コンストラクターが含まれています。 *単純な呼び出しラッパー*とは、代入演算子を含んでおり、そのコピー コンストラクター、移動コンストラクター、代入演算子が例外をスローしない呼び出しラッパーです。 *転送呼び出しラッパー*とは、任意の引数リストを使用して呼び出すことができ、ラップされた呼び出し可能オブジェクトに引数を参照として渡す呼び出しラッパーです。 すべての右辺値引数は右辺値参照として渡され、左辺値引数は左辺値参照として渡されます。

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[bad_function_call](../standard-library/bad-function-call-class.md)|[function](../standard-library/function-class.md) オブジェクトが空であるために、そのオブジェクトでの `operator()` の呼び出しが失敗したことを示す場合にスローされる例外を記述するクラス。|
|[binary_negate](../standard-library/binary-negate-class.md)|指定した二項関数の戻り値を否定するメンバー関数を提供するテンプレート クラス。|
|[binder1st](../standard-library/binder1st-class.md)|指定した値に二項関数の 1 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するコンストラクターを提供するテンプレート クラス。|
|[binder2nd](../standard-library/binder2nd-class.md)|指定した値に二項関数の 2 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するコンストラクターを提供するテンプレート クラス。|
|[const_mem_fun_ref_t](../standard-library/const-mem-fun-ref-t-class.md)|参照引数による初期化を行うときに、引数を使用しない const メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。|
|[const_mem_fun_t](../standard-library/const-mem-fun-t-class.md)|ポインター引数による初期化を行うときに、引数を使用しない const メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。|
|[const_mem_fun1_ref_t](../standard-library/const-mem-fun1-ref-t-class.md)|参照引数による初期化を行うときに、1 つの引数を使用する const メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。|
|[const_mem_fun1_t](../standard-library/const-mem-fun1-t-class.md)|ポインター引数による初期化を行うときに、1 つの引数を使用する const メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。|
|[function](../standard-library/function-class.md)|呼び出し可能オブジェクトをラップするクラス。|
|[hash](../standard-library/hash-class.md)|値のハッシュ コードを計算するクラス。|
|[is_bind_expression](../standard-library/is-bind-expression-class.md)|`bind` を呼び出すことによって特定の型が生成されるかどうかをテストするクラス。|
|[is_placeholder](../standard-library/is-placeholder-class.md)|特定の型がプレースホルダーであるかどうかをテストするクラス。|
|[mem_fun_ref_t](../standard-library/mem-fun-ref-t-class.md)|使用するアダプター クラスを`non_const`参照引数による初期化時に、単項関数オブジェクトとして呼び出せるようにする引数を受け取らないメンバー関数。|
|[mem_fun_t](../standard-library/mem-fun-t-class.md)|使用するアダプター クラスを`non_const`ポインター引数による初期化時に、単項関数オブジェクトとして呼び出せるようにする引数を受け取らないメンバー関数。|
|[mem_fun1_ref_t](../standard-library/mem-fun1-ref-t-class.md)|使用するアダプター クラスを`non_const`メンバー関数を 1 つの引数の参照引数による初期化時に、二項関数オブジェクトとして呼び出せるようにします。|
|[mem_fun1_t](../standard-library/mem-fun1-t-class.md)|使用するアダプター クラスを`non_const`メンバー関数を 1 つの引数のポインター引数による初期化時に、二項関数オブジェクトとして呼び出せるようにします。|
|[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md)|二項関数ポインターを適応性のある二項関数に変換します。|
|[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)|単項関数ポインターを適応性のある単項関数に変換します。|
|[reference_wrapper](../standard-library/reference-wrapper-class.md)|参照をラップするクラス。|
|[unary_negate](../standard-library/unary-negate-class.md)|指定した単項関数の戻り値を否定するメンバー関数を提供するテンプレート クラス。|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[bind](../standard-library/functional-functions.md#bind)|呼び出し可能オブジェクトに引数をバインドします。|
|[bind1st](../standard-library/functional-functions.md#bind1st)|指定した値に二項関数の 1 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するアダプターを作成するヘルパー テンプレート関数。|
|[bind2nd](../standard-library/functional-functions.md#bind2nd)|指定した値に二項関数の 2 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するアダプターを作成するヘルパー テンプレート関数。|
|[bit_and](../standard-library/functional-functions.md#bit_and)|2 つのパラメーターのビットごとの論理 AND (二項演算子 &) を返します。|
|[bit_not](../standard-library/functional-functions.md#bit_not)|パラメーターのビットごとの論理補数 (演算子 ~) を返します。|
|[bit_or](../standard-library/functional-functions.md#bit_or)|2 つのパラメーターのビットごとの論理 OR (演算子&#124;) を返します。|
|[bit_xor](../standard-library/functional-functions.md#bit_xor)|2 つのパラメーターのビットごとの論理 XOR (演算子 ^) を返します。|
|[cref](../standard-library/functional-functions.md#cref)|引数から const の `reference_wrapper` を構築します。|
|[mem_fn](../standard-library/functional-functions.md#mem_fn)|単純な呼び出しラッパーを生成します。|
|[mem_fun](../standard-library/functional-functions.md#mem_fun)|ポインター引数による初期化を行うときに、メンバー関数の関数オブジェクト アダプターを作成するために使用されるヘルパー テンプレート関数。|
|[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)|参照引数による初期化を行うときに、メンバー関数の関数オブジェクト アダプターを作成するために使用されるヘルパー テンプレート関数。|
|[not1](../standard-library/functional-functions.md#not1)|単項述語の補数を返します。|
|[not2](../standard-library/functional-functions.md#not2)|二項述語の補数を返します。|
|[ptr_fun](../standard-library/functional-functions.md#ptr_fun)|単項関数ポインターと二項関数ポインターをそれぞれ適応性のある単項関数および二項関数に変換するために使用されるヘルパー テンプレート関数。|
|[ref](../standard-library/functional-functions.md#ref)|引数から `reference_wrapper` を構築します。|
|[swap](../standard-library/functional-functions.md#swap)|2 つの `function` オブジェクトを交換します。|

### <a name="structs"></a>構造体

|||
|-|-|
|[binary_function](../standard-library/binary-function-struct.md)|二項関数オブジェクトを提供する派生クラスによって継承される可能性がある型を定義する空の基底クラス。|
|[divides](../standard-library/divides-struct.md)|クラスには、指定した値型の要素に対して算術演算 (除算) を実行する定義済みの関数オブジェクトが用意されています。|
|[equal_to](../standard-library/equal-to-struct.md)|指定した型の値がその型の他の値と等しいかどうかをテストする二項述語。|
|[greater](../standard-library/greater-struct.md)|指定した型の値がその型の他の値よりも大きいかどうかをテストする二項述語。|
|[greater_equal](../standard-library/greater-equal-struct.md)|指定した型の値がその型の他の値以上であるかどうかをテストする二項述語。|
|[less](../standard-library/less-struct.md)|指定した型の値がその型の他の値よりも小さいかどうかをテストする二項述語。|
|[less_equal](../standard-library/less-equal-struct.md)|指定した型の値がその型の他の値以下であるかどうかをテストする二項述語。|
|[logical_and](../standard-library/logical-and-struct.md)|クラスには、指定した値型の要素に対して論理積演算を実行する定義済みの関数オブジェクトが用意されており、結果の真偽をテストします。|
|[logical_not](../standard-library/logical-not-struct.md)|クラスには、指定した値型の要素に対して論理否定演算を実行する定義済みの関数オブジェクトが用意されており、結果の真偽をテストします。|
|[logical_or](../standard-library/logical-or-struct.md)|クラスには、指定した値型の要素に対して論理和演算を実行する定義済みの関数オブジェクトが用意されており、結果の真偽をテストします。|
|[minus](../standard-library/minus-struct.md)|クラスには、指定した値型の要素に対して算術演算 (減算) を実行する定義済みの関数オブジェクトが用意されています。|
|[modulus](../standard-library/modulus-struct.md)|クラスには、指定した値型の要素に対して算術演算 (剰余) を実行する定義済みの関数オブジェクトが用意されています。|
|[multiplies](../standard-library/multiplies-struct.md)|クラスには、指定した値型の要素に対して算術演算 (乗算) を実行する定義済みの関数オブジェクトが用意されています。|
|[negate](../standard-library/negate-struct.md)|クラスには、要素の値の負数を返す定義済みの関数オブジェクトが用意されています。|
|[not_equal_to](../standard-library/not-equal-to-struct.md)|指定した型の値がその型の他の値と等しくないかどうかをテストする二項述語。|
|[plus](../standard-library/plus-struct.md)|クラスには、指定した値型の要素に対して算術演算 (加算) を実行する定義済みの関数オブジェクトが用意されています。|
|[unary_function](../standard-library/unary-function-struct.md)|単項関数オブジェクトを提供する派生クラスによって継承される可能性がある型を定義する空の基底クラス。|

### <a name="objects"></a>オブジェクト

|||
|-|-|
|[_1.._M](../standard-library/1-object.md)|置き換え可能な引数のプレースホルダーです。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator==](../standard-library/functional-operators.md#op_eq_eq)|呼び出し可能オブジェクトの等価比較を否定します。|
|[operator!=](../standard-library/functional-operators.md#op_neq)|呼び出し可能オブジェクトの非等価比較を否定します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
