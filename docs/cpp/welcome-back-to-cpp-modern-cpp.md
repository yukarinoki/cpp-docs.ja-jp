---
title: C++ - モダン C++ へようこそ
description: Modern C++ の新しいプログラミングイディオムとその根拠について説明します。
ms.date: 01/10/2020
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: 7d0fcb623162713b845107bbf00669af7ae5ca98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369502"
---
# <a name="welcome-back-to-c---modern-c"></a>C++ - モダン C++ へようこそ

C++ は、その作成以来、世界で最も広く使用されているプログラミング言語の 1 つとなっています。 適切に記述された C++ プログラムは、高速で効率的です。 言語は他の言語よりも柔軟です:それは最高レベルの抽象化で動作し、シリコンのレベルでダウンすることができます。 C++ には、高度に最適化された標準ライブラリが用意されています。 低レベルのハードウェア機能にアクセスできるため、速度を最大化し、メモリ要件を最小限に抑えることができます。 C++ を使用すると、さまざまなアプリを作成できます。 ゲーム、デバイス ドライバー、および高性能の科学ソフトウェア。 組み込みプログラム。 Windows クライアント アプリ。 他のプログラミング言語のライブラリやコンパイラも C++ で書かれています。

C++ の最初の要件の 1 つは、C 言語との下位互換性でした。 その結果、C++ では、生のポインター、配列、null で終わる文字列、およびその他の機能を使用して、C スタイルのプログラミングが常に許可されています。 優れたパフォーマンスを実現できるだけでなく、バグや複雑さが生じることもあります。 C++ の進化は、C スタイルのイディオムを使用する必要性を大幅に減らす機能を強調してきました。 古い C プログラミング機能は必要なときに存在しますが、最新の C++ コードでは、必要な機能は少なくなっています。 最新の C++ コードは、よりシンプルで、より安全で、よりエレガントで、これまでと同じくらい速く提供されています。

次のセクションでは、最新の C++ の主な機能の概要を説明します。 特に記載がない限り、ここに示されている機能は C++11 以降で使用できます。 Microsoft C++ コンパイラでは[、/std](../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを設定して、プロジェクトに使用する標準のバージョンを指定できます。

## <a name="resources-and-smart-pointers"></a>リソースとスマート ポインター

Cスタイルプログラミングのバグの主要なクラスの1つは *、メモリリーク*です。 リークは、**新しい**. **delete** 最新の C++ では、*リソース取得の原則は初期化*(RAII) を強調しています。 アイデアは簡単です。 リソース (ヒープ メモリ、ファイル ハンドル、ソケットなど) はオブジェクトによって*所有*されている必要があります。 そのオブジェクトは、コンストラクター内で新しく割り当てられたリソースを作成または受け取り、デストラクターで削除します。 RAII の原則は、所有オブジェクトがスコープ外に出たときに、すべてのリソースがオペレーティング システムに適切に戻されることを保証します。

RAII の原則の容易な採用をサポートするために、C++ 標準ライブラリには、3 つのスマート ポインター型が用意されています: [std::unique_ptr](../standard-library/unique-ptr-class.md) [、std::shared_ptr](../standard-library/shared-ptr-class.md)、および[std::weak_ptr](../standard-library/weak-ptr-class.md)。 スマート ポインターは、所有するメモリの割り当てと削除を処理します。 次の例は、 への呼び出しでヒープに割り当てられた配列メンバーを`make_unique()`持つクラスを示しています。 **new**および**delete**の呼び出し`unique_ptr`は、クラスによってカプセル化されます。 オブジェクトが`widget`スコープ外に出ると、unique_ptrデストラクタが呼び出され、配列に割り当てられたメモリが解放されます。  

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

可能な限り、ヒープ メモリを割り当てるときにスマート ポインターを使用します。 new 演算子および delete 演算子を明示的に使用する必要がある場合は、RAII の原則に従ってください。 詳細については、「[オブジェクトの有効期間とリソース管理 (RAII)」](object-lifetime-and-resource-management-modern-cpp.md)を参照してください。

## <a name="stdstring-and-stdstring_view"></a>std::文字列と std::string_view

C スタイルの文字列は、もう 1 つのバグの主要な原因です。 [std::string と std::wstring](../standard-library/basic-string-class.md)を使用すると、C スタイルの文字列に関連するほとんどすべてのエラーを排除できます。 また、検索、追加、前置きなどのメンバー関数の利点も得られます。 どちらも速度に合わせて高度に最適化されています。 読み取り専用アクセスのみを必要とする関数に文字列を渡す場合、C++17 では[std::string_view](../standard-library/basic-string-view-class.md)を使用してパフォーマンスをさらに高めることができます。

## <a name="stdvector-and-other-standard-library-containers"></a>std::vector およびその他の標準ライブラリコンテナ

標準ライブラリコンテナはすべて RAII の原則に従います。 要素の安全な移動にイテレータを提供します。 また、パフォーマンスに合わせて高度に最適化されており、正確性を十分にテストしています。 これらのコンテナを使用することで、カスタム データ構造に導入されるバグや非効率性の可能性を排除できます。 生の配列の代わりに、C++ のシーケンシャル コンテナーとして[ベクター](../standard-library/vector-class.md)を使用します。

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

デフォルト[map](../standard-library/map-class.md)の連想`unordered_map`コンテナとしてマップ (ではなく) を使用します。 退化およびマルチケースには、[セット](../standard-library/set-class.md)、[マルチマップ](../standard-library/multimap-class.md)、[およびマルチセット](../standard-library/multiset-class.md)を使用します。

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

パフォーマンスの最適化が必要な場合は、次の使用を検討します。

- 埋め込み時の[配列](../standard-library/array-class-stl.md)型は、たとえばクラス メンバーとして重要です。

- [unordered_map](../standard-library/unordered-map-class.md)などの順序付けされていない連想コンテナー。 これらの値は、要素ごとのオーバーヘッドと定数時間のルックアップが少なくなりますが、正しく効率的に使用するのが難しい場合があります。

- 並`vector`べ替え済み . 詳細については、「[アルゴリズム](../cpp/algorithms-modern-cpp.md)」をご覧ください。

C スタイルの配列は使用しないでください。 データに直接アクセスする必要がある古い API の場合は、代`f(vec.data(), vec.size());`わりにアクセサー メソッドを使用します。 コンテナーの詳細については、「 [C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。

## <a name="standard-library-algorithms"></a>標準ライブラリアルゴリズム

プログラムのカスタム アルゴリズムを作成する必要があると仮定する前に、まず C++ 標準ライブラリ[アルゴリズムを](../standard-library/algorithm.md)確認します。 標準ライブラリには、検索、並べ替え、フィルター処理、ランダム化など、多くの一般的な操作に対応するさまざまなアルゴリズムが含まれています。 数学ライブラリは広範囲に及びます。 C++17 以降では、多くのアルゴリズムの並列バージョンが提供されます。

次に重要な例を示します。

- **for_each、** デフォルトのトラバーサル アルゴリズムです (範囲ベースの for ループと共に)。

- **変換**、 コンテナ要素のインプレース変更

- **find_if、** 既定の検索アルゴリズムです。

- **並べ替え****、lower_bound、** およびその他の既定の並べ替えと検索アルゴリズムを使用します。

コンパレータを記述するには、厳密な**<** ラムダを使用し、可能な場合*はラムダを使用*します。

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="auto-instead-of-explicit-type-names"></a>明示的な型名の代わりに auto

C++11 では、変数、関数、およびテンプレートの宣言で使用する[auto](auto-cpp.md)キーワードが導入されました。 **auto**は、明示的に入力する必要がないように、オブジェクトの型を推測するようにコンパイラに指示します。 **auto**は、推定される型が入れ子になったテンプレートである場合に特に便利です。

```cpp
map<int,list<string>>::iterator i = m.begin(); // C-style
auto i = m.begin(); // modern C++
```

## <a name="range-based-for-loops"></a>範囲ベースの for ループ

配列とコンテナーに対する C スタイルの反復処理では、インデックスエラーが発生しやすく、型を入力するのも面倒です。 これらのエラーを排除し、コードを読みやすくするには、標準ライブラリのコンテナと生の配列の両方で範囲ベースの for ループを使用します。 詳細については、「[範囲ベースの for ステートメント](../cpp/range-based-for-statement-cpp.md)」を参照してください。

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

## <a name="constexpr-expressions-instead-of-macros"></a>マクロの代わりに constexpr 式

C および C++ のマクロは、コンパイル前にプリプロセッサによって処理されるトークンです。 マクロ トークンの各インスタンスは、ファイルがコンパイルされる前に、定義された値または式に置き換えられます。 マクロは、コンパイル時の定数値を定義するために、C スタイルのプログラミングで一般的に使用されます。 ただし、マクロはエラーを起こしやすく、デバッグが困難です。 現代の C++ では、コンパイル時定数に[constexpr](constexpr-cpp.md)変数を使用する必要があります。

```cpp
#define SIZE 10 // C-style
constexpr int size = 10; // modern C++
```

### <a name="uniform-initialization"></a>均一な初期化

現代の C++ では、任意の型に対してかっこの初期化を使用できます。 この初期化形式は、配列、ベクトル、またはその他のコンテナーを初期化する場合に特に便利です。 次の例では、 `v2` `S`の 3 つのインスタンスで初期化されます。 `v3`は、それ自体が中かっこ`S`を使用して初期化される 3 つのインスタンスで初期化されます。 コンパイラは、宣言された型に基づいて各要素の型を推測`v3`します。

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

詳細については、「[ブレースの初期化](initializing-classes-and-structs-without-constructors-cpp.md)」を参照してください。

## <a name="move-semantics"></a>セマンティクスの移動

最新の C++ では、不要なメモリ コピーを排除できる*移動セマンティクス*が用意されています。 以前のバージョンの言語では、特定の状況ではコピーが不可避でした。 *移動*操作は、コピーを作成せずに、あるオブジェクトから次のオブジェクトにリソースの所有権を転送します。 リソース (ヒープ メモリ、ファイル ハンドルなど) を所有するクラスを実装する場合は、*移動コンストラクター*を定義し、割*り当て演算子を移動*できます。 コンパイラは、コピーが必要ない状況で、オーバーロードの解決時にこれらの特殊なメンバーを選択します。 標準ライブラリ コンテナ型は、オブジェクトが定義されている場合、オブジェクトの移動コンストラクタを呼び出します。 詳細については、「[コンストラクターの移動」および「 割り当て演算子の移動 (C++)」](move-constructors-and-move-assignment-operators-cpp.md)を参照してください。

## <a name="lambda-expressions"></a>ラムダ式

C スタイルのプログラミングでは、関数ポインター を使用して関数を別の*関数*に渡すことができます。 関数ポインタは、維持および理解するには不便です。 参照する関数は、ソースコードの他の場所で、呼び出されるポイントから遠く離れた場所で定義できます。 また、タイプセーフではありません。 モダン C++ には *、関数オブジェクト* [、()](function-call-operator-parens.md)演算子をオーバーライドするクラスが用意されており、関数のように呼び出すことができます。 関数オブジェクトを作成する最も便利な方法は、インライン[ラムダ式](../cpp/lambda-expressions-in-cpp.md)を使用することです。 次の例は、ラムダ式を使用して関数オブジェクトを渡す方法を`for_each`示しています。

```cpp
    std::vector<int> v {1,2,3,4,5};
    int x = 2;
    int y = 4;
    auto result = find_if(begin(v), end(v), [=](int i) { return i > x && i < y; });
```

ラムダ式`[=](int i) { return i > x && i < y; }`は、"型`int`の引数を 1 つだけ受け取り、引数が大き`x`いか小さいかを示すブール値`y`を返す関数 " として読み取ることができます。 変数と`y`周囲の`x`コンテキストからラムダで使用できることに注意してください。 これらの`[=]`変数が値によって*キャプチャ*されることを指定します。つまり、ラムダ式には、これらの値の独自のコピーがあります。

## <a name="exceptions"></a>例外

最新の C++ では、エラー状態を報告および処理する最善の方法として、エラー コードではなく例外が強調されています。 詳細については、「[例外とエラー処理に関する最新の C++ のベスト プラクティス](errors-and-exception-handling-modern-cpp.md)」を参照してください。

## <a name="stdatomic"></a>std::アトミック

C++ 標準ライブラリ[std::アトミック](../standard-library/atomic-structure.md)構造体と関連する型を使用して、スレッド間通信メカニズムを使用します。

## <a name="stdvariant-c17"></a>std::バリアント (C++17)

共用体は、C スタイルのプログラミングで一般的に使用され、異なる型のメンバーが同じメモリ位置を占有できるようにすることでメモリを節約します。 ただし、共用体はタイプ セーフではなく、プログラミング エラーが発生しやすい可能性があります。 C++17 では、共用体に代わる堅牢で安全な代替として[、std::variant](../standard-library/variant-class.md)クラスが導入されています。 [std::visit](../standard-library/variant-functions.md#visit)関数を使用すると、型の安全な`variant`方法で型のメンバーにアクセスできます。

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)\
[ラムダ式](../cpp/lambda-expressions-in-cpp.md)\
[C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)\
[Microsoft C++ 言語の準拠表](../overview/visual-cpp-language-conformance.md)
