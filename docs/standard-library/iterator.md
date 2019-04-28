---
title: '&lt;Iterator&gt;'
ms.date: 11/04/2016
f1_keywords:
- <iterator>
- iterator/std::<iterator>
helpviewer_keywords:
- iterator header
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
ms.openlocfilehash: 1b0d3282075246f3b217f0c8acac19ed8ece79cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224091"
---
# <a name="ltiteratorgt"></a>&lt;Iterator&gt;

反復子のプリミティブ、定義済みの反復子とストリーム反復子、およびサポート テンプレートをいくつか定義します。 定義済み反復子には、挿入アダプターとリバース アダプターが含まれます。 挿入反復子アダプターのクラスには、フロント、バック、汎用の 3 つがあります。 これには、コンテナーのメンバー関数の反復子が提供する上書きセマンティクスではなく、挿入セマンティクスが用意されています。

## <a name="syntax"></a>構文

```cpp
#include <iterator>
```

## <a name="remarks"></a>Remarks

反復子はポインターを一般化したもので、C++ プログラムが一貫した方法でさまざまなデータ構造を操作できるように要件が抽象化されています。 反復子は、コンテナーとジェネリックなアルゴリズムの仲介として機能します。 特定のデータ型を操作するのではなく、反復子の型で指定されている範囲を操作するようにアルゴリズムが定義されます。 そして、反復子の要件を満たすすべてのデータ構造をアルゴリズムで操作できます。 反復子には 5 つの種類またはカテゴリがあり、それぞれが独自の一連の要件と、結果として生じる機能を持ちます。

- 出力: 前方移動。値を格納できますが、取得できません。ostream および inserter によって指定されます。

- 入力: 前方移動。値を取得できますが、格納できません。istream によって指定されます。

- 前方: 前方移動。値を格納および取得できます。

- 双方向: 前方/後方移動。値を格納および取得できます。list、set、multiset、map、および multimap によって指定されます。

- ランダム アクセス: 任意の順序でアクセスされる要素。値を格納および取得できます。vector、deque、string、および array によって指定されます。

より多くの要件を持ち、より強力に要素にアクセスできる反復子が、要件の少ない反復子の代わりに使用される場合があります。 たとえば、前方反復子が呼び出された場合は、ランダム アクセス反復子が代わりに使用される可能性があります。

Visual Studio では、C++ 標準ライブラリの反復子に、チェックを行う反復子とチェックを行わない反復子のさまざまなデバッグ モードの状況をサポートする拡張機能が追加されました。 詳細については、次を参照してください。[安全なライブラリ。C++標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)します。

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[advance](../standard-library/iterator-functions.md#advance)|指定された位置の番号によって反復子をインクリメントします。|
|[back_inserter](../standard-library/iterator-functions.md#back_inserter)|指定されたコンテナーの後ろに要素を挿入できる反復子を作成します。|
|[begin](../standard-library/iterator-functions.md#begin)|指定されたコンテナーの最初の要素への反復子を取得します。|
|[cbegin](../standard-library/iterator-functions.md#cbegin)|指定されたコンテナーの最初の要素への定数反復子を取得します。|
|[cend](../standard-library/iterator-functions.md#cend)|指定されたコンテナーの最後の要素の後ろにある要素への定数反復子を取得します。|
|[distance](../standard-library/iterator-functions.md#distance)|2 つの反復子によってアドレス指定された位置の間のインクリメント数を決定します。|
|[end](../standard-library/iterator-functions.md#end)|指定されたコンテナーの最後の要素の後ろにある要素への反復子を取得します。|
|[front_inserter](../standard-library/iterator-functions.md#front_inserter)|指定されたコンテナーの前に要素を挿入できる反復子を作成します。|
|[inserter](../standard-library/iterator-functions.md#inserter)|指定された挿入ポイントにあるコンテナーに新しい要素を追加する反復子アダプター。|
|[make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)|他のアルゴリズムで使用できる [checked_array_iterator](../standard-library/checked-array-iterator-class.md) を作成します。 **注:** この関数は、標準 C++ ライブラリの Microsoft 拡張機能です。 この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C++ 標準ビルド環境には移植できません。|
|[make_move_iterator](../standard-library/iterator-functions.md#make_move_iterator)|提供された反復子を含む移動反復子を、格納された基本反復子としてを返します。|
|[make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)|他のアルゴリズムで使用できる [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md) を作成します。 **注:** この関数は、標準 C++ ライブラリの Microsoft 拡張機能です。 この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C++ 標準ビルド環境には移植できません。|
|[next](../standard-library/iterator-functions.md#next)|指定された回数を繰り返し、新しい反復子の位置を返します。|
|[prev](../standard-library/iterator-functions.md#prev)|指定された回数を逆方向に繰り返し、新しい反復子の位置を返します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](../standard-library/iterator-operators.md#op_neq)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトと等しくないかどうかを調べます。|
|[operator==](../standard-library/iterator-operators.md#op_eq_eq)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトと等しいかどうかを調べます。|
|[operator<](../standard-library/iterator-operators.md#op_lt)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/iterator-operators.md#op_gt_eq)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクト以下かどうかを調べます。|
|[operator>](../standard-library/iterator-operators.md#op_gt)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/iterator-operators.md#op_gt_eq)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクト以上かどうかを調べます。|
|[operator+](../standard-library/iterator-operators.md#op_add)|反復子にオフセットを追加し、新しいオフセット位置に挿入された要素をアドレス指定する新しい `reverse_iterator` アドレスを返します。|
|[operator-](../standard-library/iterator-operators.md#operator-)|ある反復子を別の反復子から減算し、その差異を返します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[back_insert_iterator](../standard-library/back-insert-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。 型のコンテナーに要素を挿入`Container`、を介して、保護されたアクセスを`pointer`格納オブジェクトがコンテナーと呼ばれます。|
|[bidirectional_iterator_tag](../standard-library/bidirectional-iterator-tag-struct.md)|戻り値の型を提供するクラス、`iterator_category`双方向反復子を表す関数。|
|[checked_array_iterator](../standard-library/checked-array-iterator-class.md)|チェックを行うランダム アクセス反復子を使用して配列にアクセスするクラス。 **注:** このクラスは、標準 C++ ライブラリの Microsoft 拡張機能です。 この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C++ 標準ビルド環境には移植できません。|
|[forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)|戻り値の型を提供するクラス、`iterator_category`前方反復子を表す関数。|
|[front_insert_iterator](../standard-library/front-insert-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。 型のコンテナーに要素を挿入`Container`、を介して、保護されたアクセスを`pointer`格納オブジェクトがコンテナーと呼ばれます。|
|[input_iterator_tag](../standard-library/input-iterator-tag-struct.md)|戻り値の型を提供するクラス、`iterator_category`入力反復子を表す関数。|
|[insert_iterator](../standard-library/insert-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。 型のコンテナーに要素を挿入`Container`、を介して、保護されたアクセスを`pointer`格納オブジェクトがコンテナーと呼ばれます。 格納、保護された`iterator`クラスのオブジェクト、`Container::iterator`という`iter`します。|
|[istream_iterator](../standard-library/istream-iterator-class.md)|このテンプレート クラスは、入力反復子オブジェクトを表します。 クラスのオブジェクトを抽出します`Ty`へのポインター型の格納されたオブジェクトを介してアクセスする、入力ストリームから`basic_istream` \< **Elem**、 **Tr**>。|
|[istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)|このテンプレート クラスは、入力反復子オブジェクトを表します。 クラスの要素を挿入`Elem`、出力ストリーム バッファーにアクセスされたオブジェクトを介してその型の格納、`pointer`に`basic_streambuf` \< **Elem**、 **Tr**>。|
|[Iterator](../standard-library/iterator-struct.md)|このテンプレート クラスは、すべての反復子の基本型として使用されます。|
|[iterator_traits](../standard-library/iterator-traits-struct.md)|同じ方法で参照できるように、別の反復子の型に関連付けられているクリティカルな型を指定するテンプレート ヘルパー クラス。|
|[move_iterator](../standard-library/move-iterator-class.md)|`move_iterator` オブジェクトには、型 `RandomIterator` のランダム アクセス反復子が格納されています。 これは、逆参照された場合を除いて、ランダム アクセス反復子と同じように動作します。 `operator*` の結果は `value_type&&:` に暗黙的にキャストされ、`rvalue reference` が作成されます。|
|[ostream_iterator](../standard-library/ostream-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。 クラスのオブジェクトを挿入`Type`、出力ストリームにアクセスされたオブジェクトを介してその型の格納、`pointer`に`basic_ostream` \< **Elem**、 **Tr**>。|
|[ostreambuf_iterator クラス](../standard-library/ostreambuf-iterator-class.md)|このテンプレート クラスは、出力反復子オブジェクトを表します。 クラスの要素を挿入`Elem`へのポインター型の格納されたオブジェクトを介してアクセス、出力ストリーム バッファーに`basic_streambuf` \< **Elem**、 **Tr**>。|
|[output_iterator_tag](../standard-library/output-iterator-tag-struct.md)|戻り値の型を提供するクラス`iterator_category`出力反復子を表す関数。|
|[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)|戻り値の型を提供するクラス`iterator_category`ランダム アクセス反復子を表す関数。|
|[reverse_iterator](../standard-library/reverse-iterator-class.md)|このテンプレート クラスは、逆方向でのみランダム アクセス反復子のように動作するオブジェクトを表します。|
|[unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md)|チェックを行わないランダム アクセス反復子を使用して配列にアクセスするクラス。 **注:** このクラスは、標準 C++ ライブラリの Microsoft 拡張機能です。 この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C++ 標準ビルド環境には移植できません。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
