---
title: '&lt;iterator&gt;'
ms.date: 11/04/2016
f1_keywords:
- <iterator>
- iterator/std::<iterator>
helpviewer_keywords:
- iterator header
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
ms.openlocfilehash: 08e2051db70ee1891c7b60860c7ea0b423855be5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841923"
---
# <a name="ltiteratorgt"></a>&lt;iterator&gt;

反復子のプリミティブ、定義済みの反復子とストリーム反復子、およびサポート テンプレートをいくつか定義します。 定義済み反復子には、挿入アダプターとリバース アダプターが含まれます。 挿入反復子アダプターのクラスには、フロント、バック、汎用の 3 つがあります。 これには、コンテナーのメンバー関数の反復子が提供する上書きセマンティクスではなく、挿入セマンティクスが用意されています。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<iterator>

**名前空間:** std

## <a name="remarks"></a>解説

反復子はポインターを一般化したもので、C++ プログラムが一貫した方法でさまざまなデータ構造を操作できるように要件が抽象化されています。 反復子は、コンテナーとジェネリックなアルゴリズムの仲介として機能します。 特定のデータ型を操作するのではなく、反復子の型で指定されている範囲を操作するようにアルゴリズムが定義されます。 そして、反復子の要件を満たすすべてのデータ構造をアルゴリズムで操作できます。 反復子には 5 つの種類またはカテゴリがあり、それぞれが独自の一連の要件と、結果として生じる機能を持ちます。

- 出力: 前方移動。値を格納できますが、取得できません。ostream および inserter によって指定されます。

- 入力: 前方移動。値を取得できますが、格納できません。istream によって指定されます。

- 前方: 前方移動。値を格納および取得できます。

- 双方向: 前方/後方移動。値を格納および取得できます。list、set、multiset、map、および multimap によって指定されます。

- ランダム アクセス: 任意の順序でアクセスされる要素。値を格納および取得できます。vector、deque、string、および array によって指定されます。

より多くの要件を持ち、より強力に要素にアクセスできる反復子が、要件の少ない反復子の代わりに使用される場合があります。 たとえば、前方反復子が呼び出された場合は、ランダム アクセス反復子が代わりに使用される可能性があります。

Visual Studio では、C++ 標準ライブラリの反復子に、チェックを行う反復子とチェックを行わない反復子のさまざまなデバッグ モードの状況をサポートする拡張機能が追加されました。 詳細については、「[安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)」をご覧ください。

## <a name="members"></a>メンバー

### <a name="functions"></a>Functions

|名前|説明|
|-|-|
|[切り替わる](../standard-library/iterator-functions.md#advance)|指定された位置の番号によって反復子をインクリメントします。|
|[back_inserter](../standard-library/iterator-functions.md#back_inserter)|指定されたコンテナーの後ろに要素を挿入できる反復子を作成します。|
|[初め](../standard-library/iterator-functions.md#begin)|指定されたコンテナーの最初の要素への反復子を取得します。|
|[cbegin](../standard-library/iterator-functions.md#cbegin)|指定されたコンテナーの最初の要素への定数反復子を取得します。|
|[cend](../standard-library/iterator-functions.md#cend)|指定されたコンテナーの最後の要素の後ろにある要素への定数反復子を取得します。|
|[crbegin](../standard-library/iterator-functions.md#crbegin)||
|[crend](../standard-library/iterator-functions.md#crend)||
|[data](../standard-library/iterator-functions.md#data)||
|[distance](../standard-library/iterator-functions.md#distance)|2 つの反復子によってアドレス指定された位置の間のインクリメント数を決定します。|
|[end](../standard-library/iterator-functions.md#end)|指定されたコンテナーの最後の要素の後ろにある要素への反復子を取得します。|
|[empty](../standard-library/iterator-functions.md#empty)||
|[front_inserter](../standard-library/iterator-functions.md#front_inserter)|指定されたコンテナーの前に要素を挿入できる反復子を作成します。|
|[インサーター](../standard-library/iterator-functions.md#inserter)|指定された挿入ポイントにあるコンテナーに新しい要素を追加する反復子アダプター。|
|[make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)|他のアルゴリズムで使用できる [checked_array_iterator](../standard-library/checked-array-iterator-class.md) を作成します。 **注:** この関数は、標準 C++ ライブラリの Microsoft 拡張機能です。 この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C++ 標準ビルド環境には移植できません。|
|[make_move_iterator](../standard-library/iterator-functions.md#make_move_iterator)|提供された反復子を含む移動反復子を、格納された基本反復子としてを返します。|
|[make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)|他のアルゴリズムで使用できる [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md) を作成します。 **注:** この関数は、標準 C++ ライブラリの Microsoft 拡張機能です。 この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C++ 標準ビルド環境には移植できません。|
|[次へ](../standard-library/iterator-functions.md#next)|指定された回数を繰り返し、新しい反復子の位置を返します。|
|[prev](../standard-library/iterator-functions.md#prev)|指定された回数を逆方向に繰り返し、新しい反復子の位置を返します。|
|[rbegin](../standard-library/iterator-functions.md#rbegin)||
|[rend](../standard-library/iterator-functions.md#rend)||
|[size](../standard-library/iterator-functions.md#size)||

### <a name="operators"></a>演算子

|名前|説明|
|-|-|
|[operator! =](../standard-library/iterator-operators.md#op_neq)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトと等しくないかどうかを調べます。|
|[operator = =](../standard-library/iterator-operators.md#op_eq_eq)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトと等しいかどうかを調べます。|
|[<演算子 ](../standard-library/iterator-operators.md#op_lt)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/iterator-operators.md#op_gt_eq)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクト以下かどうかを調べます。|
|[>演算子 ](../standard-library/iterator-operators.md#op_gt)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/iterator-operators.md#op_gt_eq)|演算子の左側の反復子オブジェクトが右側の反復子オブジェクト以上かどうかを調べます。|
|[演算子 +](../standard-library/iterator-operators.md#op_add)|反復子にオフセットを追加し、新しいオフセット位置に挿入された要素をアドレス指定する新しい `reverse_iterator` アドレスを返します。|
|[operator](../standard-library/iterator-operators.md#operator-)|ある反復子を別の反復子から減算し、その差異を返します。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[back_insert_iterator](../standard-library/back-insert-iterator-class.md)|クラステンプレートは、出力反復子オブジェクトを記述します。 このメソッドは、要素を型のコンテナーに挿入します。このコンテナーは、 `Container` コンテナーと呼ばれる保護されたオブジェクトを介してアクセスし `pointer` ます。|
|[bidirectional_iterator_tag](../standard-library/bidirectional-iterator-tag-struct.md)|`iterator_category`双方向反復子を表す関数の戻り値の型を提供するクラス。|
|[checked_array_iterator](../standard-library/checked-array-iterator-class.md)|チェックを行うランダム アクセス反復子を使用して配列にアクセスするクラス。 **注:** このクラスは、標準 C++ ライブラリの Microsoft 拡張機能です。 この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C++ 標準ビルド環境には移植できません。|
|[forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)|前方反復子を表す関数の戻り値の型を提供するクラス `iterator_category` 。|
|[front_insert_iterator](../standard-library/front-insert-iterator-class.md)|クラステンプレートは、出力反復子オブジェクトを記述します。 このメソッドは、要素を型のコンテナーに挿入します。このコンテナーは、 `Container` コンテナーと呼ばれる保護されたオブジェクトを介してアクセスし `pointer` ます。|
|[input_iterator_tag](../standard-library/input-iterator-tag-struct.md)|入力反復子を表す関数の戻り値の型を提供するクラス `iterator_category` 。|
|[insert_iterator](../standard-library/insert-iterator-class.md)|クラステンプレートは、出力反復子オブジェクトを記述します。 このメソッドは、要素を型のコンテナーに挿入します。このコンテナーは、 `Container` コンテナーと呼ばれる保護されたオブジェクトを介してアクセスし `pointer` ます。 また、というクラスの保護されたオブジェクトも格納し `iterator` `Container::iterator` `iter` ます。|
|[istream_iterator](../standard-library/istream-iterator-class.md)|クラステンプレートは、入力反復子オブジェクトを表します。 このクラスは、入力ストリームからクラスのオブジェクトを抽出 `Ty` します。これには、へのポインター型の、格納されているオブジェクトを介してアクセス `basic_istream` \<**Elem**, **Tr**> します。|
|[istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)|クラステンプレートは、入力反復子オブジェクトを表します。 このクラスは、出力ストリームバッファーにクラスの要素を挿入します。このバッファーは、格納されている `Elem` オブジェクトを介して、型 `pointer` にアクセス `basic_streambuf` \<**Elem**, **Tr**> します。|
|[反](../standard-library/iterator-struct.md)|クラステンプレートは、すべての反復子の基本型として使用されます。|
|[iterator_traits](../standard-library/iterator-traits-struct.md)|同じ方法で参照できるように、別の反復子の型に関連付けられているクリティカルな型を指定するテンプレート ヘルパー クラス。|
|[move_iterator](../standard-library/move-iterator-class.md)|`move_iterator` オブジェクトには、型 `RandomIterator` のランダム アクセス反復子が格納されています。 これは、逆参照された場合を除いて、ランダム アクセス反復子と同じように動作します。 `operator*` の結果は `value_type&&:` に暗黙的にキャストされ、`rvalue reference` が作成されます。|
|[ostream_iterator](../standard-library/ostream-iterator-class.md)|クラステンプレートは、出力反復子オブジェクトを記述します。 クラスのオブジェクトを `Type` 出力ストリームに挿入します。このストリームは、格納されているオブジェクトを介して `pointer` にアクセス `basic_ostream` \<**Elem**, **Tr**> します。|
|[ostreambuf_iterator クラス](../standard-library/ostreambuf-iterator-class.md)|クラステンプレートは、出力反復子オブジェクトを記述します。 このクラスは、出力ストリームバッファーにクラスの要素を挿入します。これには、 `Elem` へのポインター型の、格納されているオブジェクトを介してアクセス `basic_streambuf` \<**Elem**, **Tr**> します。|
|[output_iterator_tag](../standard-library/output-iterator-tag-struct.md)|`iterator_category`出力反復子を表す関数の戻り値の型を提供するクラス。|
|[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)|`iterator_category`ランダムアクセス反復子を表す関数の戻り値の型を提供するクラス。|
|[reverse_iterator](../standard-library/reverse-iterator-class.md)|クラステンプレートは、逆方向でのみランダムアクセス反復子のように動作するオブジェクトを表します。|
|[unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md)|チェックを行わないランダム アクセス反復子を使用して配列にアクセスするクラス。 **注:** このクラスは、標準 C++ ライブラリの Microsoft 拡張機能です。 この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C++ 標準ビルド環境には移植できません。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
