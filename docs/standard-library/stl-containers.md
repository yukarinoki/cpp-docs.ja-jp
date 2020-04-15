---
title: C++ 標準ライブラリのコンテナー
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, class template containers
- containers, C++ Standard Library
ms.assetid: 8e915ca1-19ba-4f0d-93c8-e2c3bfd638eb
ms.openlocfilehash: 01be754dd7b418f64cf495d7563f65b323265df8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376699"
---
# <a name="c-standard-library-containers"></a>C++ 標準ライブラリのコンテナー

標準ライブラリには、関連するオブジェクトのコレクションを格納するさまざまなタイプ セーフ コンテナーが用意されています。 コンテナーはクラス テンプレートです。 コンテナー変数を宣言するときは、コンテナーが保持する要素の型を指定します。 コンテナーは、初期化子リストを使用して構築できます。 要素の追加と削除、およびその他の操作を行うためのメンバー関数があります。

[反復子](../standard-library/iterators.md)を使用して、コンテナー内の要素を反復処理し、個々の要素にアクセスします。 イテレータは、メンバー関数、演算子、グローバル関数を使用して明示的に使用できます。 また、range-for ループなどを使用して暗黙的に反復子を使用することもできます。 すべての C++ 標準ライブラリのコンテナーは共通のインターフェイスを持っていますが、各コンテナーには固有の特殊化された反復子が定義されます。

コンテナーは、シーケンス コンテナー、連想コンテナー、およびコンテナー アダプターの 3 種類に分けることができます。

## <a name="sequence-containers"></a><a name="sequence_containers"></a> シーケンス コンテナー

シーケンス コンテナーは、挿入された要素の、指定された順序を維持します。

`vector` コンテナーは配列のように動作しますが、必要に応じて自動的に拡張されます。 ランダム アクセスが可能で連続して格納され、長さに関しては高い柔軟性があります。 こうした理由などから、`vector` はほとんどのアプリケーションに推奨されるシーケンス コンテナーです。 使用するシーケンス コンテナーの種類が不明な場合は、ベクターを使用して開始します。 詳細については、「[vector クラス](../standard-library/vector-class.md)」をご覧ください。

コンテナー`array`には の長所`vector`がいくつかありますが、長さはそれほど柔軟ではありません。 詳細については、[array クラス](../standard-library/array-class-stl.md)に関する記事をご覧ください。

`deque` (両端キュー) コンテナーは、コンテナーの先頭と末尾で、すばやい挿入および削除を行うことができます。 ランダム アクセスと柔軟な長さの利点を`vector`共有しますが、連続していません。 詳細については、「[deque クラス](../standard-library/deque-class.md)」をご覧ください。

コンテナ`list`は双方向のリンクリストで、コンテナ内の任意の場所で双方向アクセス、高速挿入、および高速削除を可能にしますが、コンテナ内の要素にランダムにアクセスすることはできません。 詳細については、「[list クラス](../standard-library/list-class.md)」をご覧ください。

`forward_list` コンテナーはシングルリンク リストであり、`list` の前方アクセス バージョンです。 詳細については、「[forward_list クラス](../standard-library/forward-list-class.md)」をご覧ください。

## <a name="associative-containers"></a>連想コンテナー

連想コンテナーでは、要素は事前に定義された順序で挿入されます (たとえば、昇順に並べ替えられて)。 順序なしの連想コンテナーも使用できます。 連想コンテナーは、マップとセットという 2 つのサブセットに分類できます。

ディクショナリとも呼ばれる `map` は、キーと値のペアで構成されています。 キーはシーケンスを順序付けるために使用され、値はそのキーに関連付けられます。 たとえば、`map` には、テキスト内のすべての一意の単語を表すキーと、それに対応する、テキスト内で各単語が出現する回数を表す値が含まれる場合があります。 `map` の順序なしのバージョンは `unordered_map` です。 詳細については、「[map クラス](../standard-library/map-class.md)」および「[unordered_map クラス](../standard-library/unordered-map-class.md)」をご覧ください。

`set` は単に、一意の要素の昇順のコンテナーです。値がキーにもなっています。 `set` の順序なしのバージョンは `unordered_set` です。 詳細については、「[set クラス](../standard-library/set-class.md)」および「[unordered_set クラス](../standard-library/unordered-set-class.md)」をご覧ください。

`map` と `set` のどちらでも、キーまたは要素の 1 つのインスタンスだけをコンテナーに挿入できます。 要素の複数のインスタンスが必要な場合は、`multimap` または `multiset` を使用します。 順序なしのバージョンは `unordered_multimap` と `unordered_multiset` です。 詳細については、「[multimap クラス](../standard-library/multimap-class.md)」、「[unordered_multimap クラス](../standard-library/unordered-multimap-class.md)」、「[multiset クラス](../standard-library/multiset-class.md)」、および「[unordered_multiset クラス](../standard-library/unordered-multiset-class.md)」をご覧ください。

順序ありのマップおよびセットは双方向反復子をサポートしており、順序なしのバージョンは前方反復子をサポートしています。 詳細については、「[イテレータ](../standard-library/iterators.md)」を参照してください。

### <a name="heterogeneous-lookup-in-associative-containers-c14"></a>連想コンテナーの異種ルックアップ (C++14)

順序付けされた連想コンテナ (マップ、マルチマップ、セット、マルチセット) が異種検索を`find()`サポートするようになりました。 `lower_bound()` 代わりに、オーバーロードされた `operator<` が定義されてキーの型の比較が可能になっている任意の型を渡すことができます。

異種ルックアップは、次に示すように、コンテナー変数の宣言時に `std::less<>` または `std::greater<>` の "ダイヤモンド ファンクター" 比較子を指定した場合に、オプトインで有効化されます。

```cpp
std::set<BigObject, std::less<>> myNewSet;
```

既定の比較子を使用すると、コンテナーは c++ 11 以前と同じように正確に動作します。

次の例では、各オブジェクト`operator<`の`BigObject::id`メンバーと比較できる`std::set`小さな文字列を渡すだけで、a のユーザーがルックアップを実行できるようにするオーバーロード方法を示します。

```cpp
#include <set>
#include <string>
#include <iostream>
#include <functional>

using namespace std;

class BigObject
{
public:
    string id;
    explicit BigObject(const string& s) : id(s) {}
    bool operator< (const BigObject& other) const
    {
        return this->id < other.id;
    }

    // Other members....
};

inline bool operator<(const string& otherId, const BigObject& obj)
{
    return otherId < obj.id;
}

inline bool operator<(const BigObject& obj, const string& otherId)
{
    return obj.id < otherId;
}

int main()
{
    // Use C++14 brace-init syntax to invoke BigObject(string).
    // The s suffix invokes string ctor. It is a C++14 user-defined
    // literal defined in <string>
    BigObject b1{ "42F"s };
    BigObject b2{ "52F"s };
    BigObject b3{ "62F"s };
    set<BigObject, less<>> myNewSet; // C++14
    myNewSet.insert(b1);
    myNewSet.insert(b2);
    myNewSet.insert(b3);
    auto it = myNewSet.find(string("62F"));
    if (it != myNewSet.end())
        cout << "myNewSet element = " << it->id << endl;
    else
        cout << "element not found " << endl;

    // Keep console open in debug mode:
    cout << endl << "Press Enter to exit.";
    string s;
    getline(cin, s);
    return 0;
}

//Output: myNewSet element = 62F
```

マップ、マルチマップ、セット、およびマルチセットの次のメンバー関数は、異種検索をサポートするためにオーバーロードされています。

1. 検索

1. count

1. lower_bound

1. upper_bound

1. equal_range

## <a name="container-adapters"></a>コンテナー アダプター

コンテナー アダプターは、簡潔さと明確さのためにインターフェイスを制限する、シーケンスまたは連想コンテナーの変化形です。 コンテナー アダプターは反復子をサポートしていません。

`queue` コンテナーは FIFO (先入れ先出し) のセマンティクスに従います。 *プッシュ*された (つまり、キューに挿入された) 最初の要素は、最初に*ポップ*されます (つまり、キューから削除されます)。 詳細については、「[queue クラス](../standard-library/queue-class.md)」をご覧ください。

`priority_queue` コンテナーは、最高の値を持つ要素が常にキューの先頭になるように編成されます。 詳細については、「[priority_queue クラス](../standard-library/priority-queue-class.md)」をご覧ください。

`stack` コンテナーは、LIFO (後入れ先出し) のセマンティクスに従います。 スタックに最後にプッシュされた要素が最初にポップされます。 詳細については、「[stack Class (stack クラス)](../standard-library/stack-class.md)」をご覧ください。

コンテナー アダプターは反復子をサポートしていないため、C++ 標準ライブラリ アルゴリズムでは使用できません。 詳細については、「[アルゴリズム](../standard-library/algorithms.md)」をご覧ください。

## <a name="requirements-for-container-elements"></a>コンテナー要素の要件

一般に、C++ 標準ライブラリ コンテナーに挿入される要素は、コピー可能なものであれば、ほぼどのオブジェクト型でもかまいません。 移動のみ可能な要素 (たとえば、`vector<unique_ptr<T>>` を使用して作成される `unique_ptr<>` など) は、要素をコピーしようとするメンバー関数を呼び出さなければ正常に動作します。

デストラクターは例外をスローできません。

この記事の前の方で説明した順序ありの連想コンテナーでは、パブリックな比較演算子が定義されている必要があります。 既定では、演算子は `operator<` ですが、`operator<` とでは動作しない型もサポートされます。

コンテナーに対する一部の操作では、パブリックな既定のコンストラクターとパブリックな等価演算子も必要となる場合があります。 たとえば、順序なしの連想コンテナーでは、等値とハッシュのサポートが必要です。

## <a name="accessing-container-elements"></a>コンテナー要素へのアクセス

コンテナーの要素には、反復子を使用してアクセスします。 詳細については、「[イテレータ](../standard-library/iterators.md)」を参照してください。

> [!NOTE]
> また、C++ 標準ライブラリ コレクションに対する反復処理には[範囲ベースの for ループ](../cpp/range-based-for-statement-cpp.md)を使用できます。

## <a name="comparing-containers"></a>コンテナーの比較

すべてのコンテナーは、同じ要素型を含み、型が同じである 2 つのコンテナーを比較するために、演算子 == をオーバーロードします。 ==\<を使用すると、ベクトル文字列>を別のベクトル\<文字列>と比較できますが、それを使用して、ベクター\<文字列>をリスト\<文字列>またはベクトル char*>\<と>ベクトル\<文字列と比較することはできません。  C++98/03 では[、std::equal](algorithm-functions.md#equal)または[std:mismatch](algorithm-functions.md#mismatch)を使用して、異なるコンテナー型や要素型を比較できます。 C++ 11 では[、std::is_permutation](algorithm-functions.md#is_permutation)を使用することもできます。 しかし、これらのすべての場合において、関数はコンテナが同じ長さであると仮定します。 2 つ目の範囲が 1 つ目の範囲より短いと、未定義の動作が発生します。 また、2 番目の範囲が長い場合も、比較は 1 つ目の範囲の末尾を越えて続行されないため、不正確になる可能性があります。

### <a name="comparing-dissimilar-containers-c14"></a>異なるコンテナーの比較 (C++ 14)

C++14 以降では、2 つの完全な範囲を使用する`std::equal`、、または関数のオーバーロードのいずれかを使用して、`std::mismatch`異なるコンテナー`std::is_permutation`や異なる要素の型を比較できます。 これらのオーバーロードを使用すると、長さが異なるコンテナーを比較できます。 これらのオーバーロードは、ユーザー エラーの影響を受けにくく、長さが異なるコンテナーを比較しているときに一定の時間で false を返すように最適化されています。 したがって、明確な理由がない場合、または二重範囲の最適化の恩恵を受けないように[std::list](../standard-library/list-class.md)コンテナーを使用している場合を除き、これらのオーバーロードを使用することをお勧めします。

## <a name="see-also"></a>関連項目

[並列コンテナ](../parallel/concrt/parallel-containers-and-objects.md)\
[\<サンプルコンテナー>](../standard-library/sample-container.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
