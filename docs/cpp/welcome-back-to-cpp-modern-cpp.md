---
title: C++ へようこそ - Modern C++
description: Modern C++ の新しいプログラミング イディオムとその根拠について説明します。
ms.date: 05/17/2020
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: f2b9159e74ba7ce37c7eab1513826da939a3be49
ms.sourcegitcommit: f1752bf90b4f869633a859ace85439ca19e208b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2020
ms.locfileid: "87232197"
---
# <a name="welcome-back-to-c---modern-c"></a>C++ へようこそ - Modern C++

C++ は、作成以来、世界で最も広く使用されているプログラミング言語の 1 つになりました。 適切に記述された C++ プログラムは、高速で効率的です。 この言語は他の言語よりも柔軟性に優れています。これは、最も高い抽象化のレベルでも、低いシリコンのレベルでも使用できます。 C++ によって、高度に最適化された標準ライブラリが提供されます。 これにより、低レベルのハードウェア機能にアクセスして、速度を最大化し、メモリ要件を最小限に抑えることができます。 C++ を使用すると、広範囲にわたるアプリを作成することができます。 ゲーム、デバイス ドライバー、ハイパフォーマンスの科学ソフトウェア。 埋め込みプログラム。 Windows クライアント アプリ。 他のプログラミング言語のライブラリやコンパイラさえも C++ で作成されます。

C++ の最初の要件の 1 つは、C 言語との下位互換性でした。 その結果、C++ を使用すると常に、生ポインター、配列、null で終了する文字列、その他の機能を使用して、C スタイルでプログラミングすることができます。 これらを使用すると、優れたパフォーマンスを実現できますが、バグや複雑さを引き起こす可能性もあります。 C++ は、その進化に伴って機能が強化され、C スタイルのイディオムを使用する必要性が大幅に低減されています。 古い C プログラミング機能は必要なときに利用できますが、Modern C++ コードでは、その必要性がますます少なくなっています。 Modern C++ コードは、よりシンプル化され、安全性が向上し、より洗練され、しかもこれまでにないほど高速です。

以下のセクションでは、Modern C++ の主な機能の概要について説明します。 特に明記されていない限り、ここに記載される機能は、C++ 11 以降で使用できます。 Microsoft C++ コンパイラでは、[`/std`](../build/reference/std-specify-language-standard-version.md) コンパイラ オプションを設定して、プロジェクトに使用する標準のバージョンを指定できます。

## <a name="resources-and-smart-pointers"></a>リソースとスマート ポインター

C スタイルのプログラミングでバグの主なクラスの 1 つは、"*メモリ リーク*" です。 多くの場合、リークは、 **`new`** で割り当てられたメモリに対する **`delete`** の呼び出しに失敗したことが原因で発生します。 Modern C++ では、"*リソース取得は初期化である*" (RAII) の原則が重視されています。 考え方はシンプルです。 リソース (ヒープ メモリ、ファイル ハンドル、ソケットなど) は、オブジェクトによって "*所有される*" 必要があります。 そのオブジェクトによって、そのコンストラクターで新たに割り当てられたリソースが作成または受け取られるか、デストラクターで削除されます。 RAII の原則により、所有しているオブジェクトが範囲外になったときにすべてのリソースがオペレーティング システムに返されることが保証されます。

RAII 原則を簡単に導入できるように、C++ 標準ライブラリには、3 つの種類のスマート ポインター ([`std::unique_ptr`](../standard-library/unique-ptr-class.md)、[`std::shared_ptr`](../standard-library/shared-ptr-class.md)、[`std::weak_ptr`](../standard-library/weak-ptr-class.md)) が用意されています。 スマート ポインターは、所有しているメモリの割り当てと削除を処理します。 次の例は、`make_unique()` の呼び出しでヒープに割り当てられる配列メンバーを持つクラスを示しています。 **`new`** と **`delete`** の呼び出しは、`unique_ptr` クラスによってカプセル化されます。 `widget` オブジェクトが範囲外になると、unique_ptr デストラクターが呼び出され、配列に割り当てられたメモリが解放されます。  

```cpp
#include <memory>
class widget
{
private:
    std::unique_ptr<int> data;
public:
    widget(const int size) { data = std::make_unique<int>(size); }
    void do_something() {}
};

void functionUsingWidget() {
    widget w(1000000);   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.data gadget member
    // ...
    w.do_something();
    // ...
} // automatic destruction and deallocation for w and w.data

```

ヒープ メモリを割り当てる場合は、可能な限り、スマート ポインターを使用します。 new および delete 演算子を明示的に使用する必要がある場合は、RAII の原則に従ってください。 詳細については、「[オブジェクトの有効期間とリソースの管理 (RAII)](object-lifetime-and-resource-management-modern-cpp.md)」を参照してください。

## <a name="stdstring-and-stdstring_view"></a>`std::string` および `std::string_view`

C スタイルの文字列は、バグのもう 1 つの主な原因です。 [`std::string` および `std::wstring`](../standard-library/basic-string-class.md) を使用すると、C スタイルの文字列に関連するほとんどすべてのエラーを取り除くことができます。 また、検索、追加、先頭への追加などのメンバー関数の利点も得られます。 どちらも速度について高度に最適化されています。 読み取り専用アクセスのみが必要とされる関数に文字列を渡す場合、C++ 17 では、[`std::string_view`](../standard-library/basic-string-view-class.md) を使用して、パフォーマンスをさらに向上させることができます。

## <a name="stdvector-and-other-standard-library-containers"></a>`std::vector` およびその他の標準ライブラリのコンテナー

標準ライブラリのコンテナーはすべて、RAII の原則に従います。 これらは、要素を安全に走査するための反復子を提供します。 さらに、これらは、パフォーマンスについて高度に最適化されており、正確性について徹底的にテストされています。 これらのコンテナーを使用すると、カスタム データ構造で発生する可能性のあるバグや非効率性が排除されます。 C++ では、生の配列の代わりに [`vector`](../standard-library/vector-class.md) をシーケンシャル コンテナーとして使用します。

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

既定の連想コンテナーとしては、(`unordered_map` ではなく) [`map`](../standard-library/map-class.md) を使用します。 縮退および複数ケースには、[`set`](../standard-library/set-class.md)、[`multimap`](../standard-library/multimap-class.md)、[`multiset`](../standard-library/multiset-class.md) を使用します。

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

パフォーマンスの最適化が必要な場合は、次の使用を検討します。

- [`array`](../standard-library/array-class-stl.md) 型 (埋め込みが重要な場合、たとえば、クラス メンバーとして使用する)。

- 順序指定されていない連想コンテナー (例: [`unordered_map`](../standard-library/unordered-map-class.md))。 これらの、要素ごとのオーバーヘッドが軽減され、一定時間ルックアップを使用できますが、正確かつ効率的に使用するのは困難な場合があります。

- 並べ替えられた `vector`。 詳細については、「[アルゴリズム](../cpp/algorithms-modern-cpp.md)」をご覧ください。

C スタイルの配列を使用しないでください。 データへの直接アクセスを必要とする古い API については、代わりに、`f(vec.data(), vec.size());` などのアクセサー メソッドを使用します。 コンテナーの詳細については、「[C++ 標準ライブラリのコンテナー](../standard-library/stl-containers.md)」を参照してください。

## <a name="standard-library-algorithms"></a>標準ライブラリのアルゴリズム

プログラムのカスタム アルゴリズムを記述する必要があると思う前に、まず、C++ 標準ライブラリの[アルゴリズム](../standard-library/algorithm.md)を確認してください。 標準ライブラリには、検索、並べ替え、フィルター処理、ランダム化などの多くの一般的な操作のためのさまざまなアルゴリズムが含まれており、その数は増え続けています。 数値演算ライブラリは広範囲にわたります。 C++ 17 以降、多くのアルゴリズムの並列バージョンが提供されています。

次に重要な例を示します。

- `for_each`: 既定の走査アルゴリズム (範囲ベースの `for` ループと共に)。

- `transform`: コンテナー要素の非インプレース変更用

- `find_if`: 既定の検索アルゴリズム。

- `sort`、`lower_bound`、その他の既定の並べ替えおよび検索アルゴリズム。

比較演算子を記述するには、厳格な **`<`** を使用し、可能な場合は、"*名前付きラムダ式*" を使用します。

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="auto-instead-of-explicit-type-names"></a>明示的な型名の代わりとなる `auto`

C++ 11 に、変数、関数、テンプレート宣言で使用するための [`auto`](auto-cpp.md) キーワードが導入されました。 **`auto`** を使用して、オブジェクトの型を推測するようにコンパイラに指示します。これにより、型を明示的に入力する必要がなくなります。 **`auto`** は、推測された型が入れ子になったテンプレートである場合に特に役立ちます。

```cpp
map<int,list<string>>::iterator i = m.begin(); // C-style
auto i = m.begin(); // modern C++
```

## <a name="range-based-for-loops"></a>範囲ベースの `for` ループ

C スタイルによる配列およびコンテナーの反復処理では、インデックス処理エラーが発生しやすく、入力も面倒です。 このようなエラーを排除し、コードを読みやすくするには、標準ライブラリのコンテナーと生の配列の両方で範囲ベースの **`for`** ループを使用します。 詳細については、「[範囲ベースの `for` ステートメント](../cpp/range-based-for-statement-cpp.md)」を参照してください。

```cpp
#include <iostream>
#include <vector>

int main()
{
    std::vector<int> v {1,2,3};

    // C-style
    for(int i = 0; i < v.size(); ++i)
    {
        std::cout << v[i];
    }

    // Modern C++:
    for(auto& num : v)
    {
        std::cout << num;
    }
}
```

## <a name="constexpr-expressions-instead-of-macros"></a>マクロの代わりとなる `constexpr` 式

C および C++ のマクロは、コンパイルの前にプリプロセッサによって処理されるトークンです。 マクロ トークンの各インスタンスは、ファイルがコンパイルされる前に、定義された値または式に置き換えられます。 C スタイルのプログラミングによって、マクロは、コンパイル時定数値を定義するために一般的に使用されます。 しかし、マクロはエラーが発生しやすく、デバッグが困難です。 Modern C++ では、コンパイル時定数に [`constexpr`](constexpr-cpp.md) 変数を使用することをお勧めします。

```cpp
#define SIZE 10 // C-style
constexpr int size = 10; // modern C++
```

### <a name="uniform-initialization"></a>一様初期化

Modern C++ では、どの型に対しても中かっこ初期化を使用できます。 この形式の初期化は、配列、ベクター、またはその他のコンテナーを初期化する場合に特に便利です。 次の例では、`v2` が `S` の 3 つのインスタンスで初期化されます。 `v3` は、中かっこを使用して自身が初期化される `S` の 3 つのインスタンスで初期化されます。 コンパイラは、`v3` の宣言された型に基づいて各要素の型を推測します。

```cpp
#include <vector>

struct S
{
    std::string name;
    float num;
    S(std::string s, float f) : name(s), num(f) {}
};

int main()
{
    // C-style initialization
    std::vector<S> v;
    S s1("Norah", 2.7);
    S s2("Frank", 3.5);
    S s3("Jeri", 85.9);

    v.push_back(s1);
    v.push_back(s2);
    v.push_back(s3);

    // Modern C++:
    std::vector<S> v2 {s1, s2, s3};

    // or...
    std::vector<S> v3{ {"Norah", 2.7}, {"Frank", 3.5}, {"Jeri", 85.9} };

}
```

詳細については、「[かっこ初期化](initializing-classes-and-structs-without-constructors-cpp.md)」を参照してください。

## <a name="move-semantics"></a>移動セマンティクス

Modern C++ によって、"*移動セマンティクス*" が提供されるため、不要なメモリのコピーを排除することができます。 この言語の以前のバージョンでは、特定の状況下で、コピーを避けることができませんでした。 "*移動*" 操作により、コピーを作成することなく、リソースの所有権はあるオブジェクトから次のオブジェクトに転送されます。 一部のクラスは、ヒープ メモリ、ファイル ハンドルなどのリソースを所有します。 リソースを所有するクラスを実装すると、その "*移動コンストラクター*" と "*移動代入演算子*" を定義できます。 コピーが不要な場合、コンパイラによって、オーバーロード解決時に、これらの特殊なメンバーが選択されます。 標準ライブラリのコンテナー型では、移動コンストラクターが定義されている場合、オブジェクトのそれが呼び出されます。 詳細については、「[移動コンストラクターと移動代入演算子 (C++)](move-constructors-and-move-assignment-operators-cpp.md)」を参照してください。

## <a name="lambda-expressions"></a>ラムダ式

C スタイルのプログラミングでは、"*関数ポインター*" を使用して関数を別の関数に渡すことができます。 関数ポインターは、保守や解釈には不便です。 それらが参照する関数は、呼び出される位置から遠く離れた、ソース コードの他の場所で定義されている可能性があります。 また、それらは、タイプセーフではありません。 Modern C++ によって、"*関数オブジェクト*" が提供されます。これは、[`operator()`](function-call-operator-parens.md) 演算子をオーバーライドするクラスであり、関数と同様に呼び出すことができます。 関数オブジェクトを作成する最も便利な方法は、インライン [ラムダ式](../cpp/lambda-expressions-in-cpp.md)を使用することです。 次の例は、ラムダ式を使用して関数オブジェクトを渡して、ベクター内の各要素で `for_each` 関数を呼び出す方法を示しています。

```cpp
    std::vector<int> v {1,2,3,4,5};
    int x = 2;
    int y = 4;
    auto result = find_if(begin(v), end(v), [=](int i) { return i > x && i < y; });
```

ラムダ式 `[=](int i) { return i > x && i < y; }` は、"型 **`int`** の単一の引数を受け取り、その引数が `x` より大きく、`y` より小さいかどうかを示すブール式を返す関数" として読み取ることができます。 ラムダ式では、周囲のコンテキストから変数 `x` と `y` を使用できることにご注意ください。 `[=]` は、それらの変数が値によって "*キャプチャされる*" ことを指定します。つまり、ラムダ式には、それらの値の独自のコピーが含まれます。

## <a name="exceptions"></a>例外

Modern C++ では、エラー状況を報告および処理する最善の方法として、エラー コードよりも例外を重視しています。 詳細については、「[例外とエラー処理に関する最新の C++ のベストプラクティス](errors-and-exception-handling-modern-cpp.md)」を参照してください。

## `std::atomic`

スレッド間の通信メカニズムには、C++ 標準ライブラリの[`std::atomic`](../standard-library/atomic-structure.md) 構造体とそれに関連する型を使用します。

## <a name="stdvariant-c17"></a>`std::variant` (C++ 17)

C スタイルのプログラミングでは、一般的に、共用体を使用して、さまざまな型のメンバーが同じメモリ位置を専有できるようにして、メモリを節約します。 しかし、共用体はタイプセーフではなく、プログラミング エラーも発生しやすくなります。 C++ 17 では、共用体に代わる、より堅牢で安全な方法として、[`std::variant`](../standard-library/variant-class.md) クラスが導入されています。 [`std::visit`](../standard-library/variant-functions.md#visit) 関数を使用すると、タイプセーフな方法で、`variant` 型のメンバーにアクセスできます。

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)\
[ラムダ式](../cpp/lambda-expressions-in-cpp.md)\
[C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)\
[Microsoft C++ 言語の準拠表](../overview/visual-cpp-language-conformance.md)
