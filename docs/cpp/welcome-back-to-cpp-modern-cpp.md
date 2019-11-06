---
title: C++ へようこそ (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: 1f59395001722244cb407ef07ed8a301f08df85b
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624760"
---
# <a name="welcome-back-to-c-modern-c"></a>C++ へようこそ (Modern C++)

C++ は世界で最も広く使用されているプログラミング言語の 1 つです。 適切に記述された C++ プログラムは、高速で効率的です。 この言語は、楽しめるゲームから、高性能な科学的ソフトウェア、デバイス ドライバー、埋め込みプログラム、さらに Windows クライアント アプリケーションに至るまで、幅広いアプリケーションの作成に使用でき、他の言語よりも柔軟性があります。 20 年以上にわたって、C++ はそれらをはじめとするさまざまなソリューション使用されてきました。 ますます多くの C++ プログラマが、旧来の C のプログラミング スタイルから卒業して、最新の C++ の手法を身に着けていることを、ご存知でない方もいるかもしれません。

C++ の最初の要件の 1 つは、C 言語との下位互換性でした。 それ以来、C++ はさまざまな進化をとげています。C 言語でのクラスの使用に始まり、最初の C++ 言語仕様が作成され、それに続く多くの拡張が行われてきました。 この経緯のため、C++ はマルチパラダイムのプログラミング言語と呼ばれることが多くあります。 C++ では、生のポインター、配列、null で終わる文字列、カスタム データ構造、その他の機能を使って、純粋な手続き型の C スタイルのプログラミングを行うことも可能です。これにより優れたパフォーマンスが可能となりますが、バグと複雑性も生じることになります。  C スタイルのプログラミングはそのようなリスクを抱えていたため、C++ の当初のねらいの 1 つは、タイプ セーフで、作成、拡張、保守の容易なプログラムを作成可能にすることでした。 C++ は、早い段階でオブジェクト指向プログラミングなどのプログラミング パラダイムを追加しました。 長年にわたり、十分に検証されたデータ構造やアルゴリズムの標準ライブラリと共に、さまざまな機能が言語に追加されました。 これらの拡張が最新の C++ のスタイルを可能にしています。

最新の C++ では下記のような点が強化されています。

- ヒープまたは静的なグローバル スコープではなく、スタック ベースのスコープ。

- 明示的な型名ではなく、自動型推論。

- 生のポインターではなく、スマート ポインター。

- `std::string` および `std::wstring` 型 ( [\<文字列 >](../standard-library/string.md)を参照) は、未加工の `char[]` 配列ではなく、を参照してください。

- 未加工の配列やカスタムコンテナーではなく、`vector`、`list`、`map` などの標準ライブラリコンテナー。 [ C++ ](../standard-library/cpp-standard-library-header-files.md) [\<vector >](../standard-library/vector.md)、 [\<リスト >](../standard-library/list.md)、および[\<マップ >](../standard-library/map.md)を参照してください。

- C++手動でコード化されたものではなく、標準ライブラリの[アルゴリズム](../standard-library/algorithm.md)。

- 例外はエラー状態の報告と処理のためだけに使用される。

- 他のスレッド間通信メカニズムではC++なく、標準ライブラリ `std::atomic<>` を使用したロック解放のスレッド間通信 ( [\<アトミック >](../standard-library/atomic.md)を参照)。

- 小さな関数ではなくインライン[ラムダ関数](../cpp/lambda-expressions-in-cpp.md)が個別に実装されています。

- 範囲ベースの for ループでは、配列、 C++標準ライブラリコンテナー、Windows ランタイムコレクションを操作するより堅牢なループを `for ( for-range-declaration : expression )`の形式で記述します。 これは、コア言語サポートの一部です。 詳細については、「[範囲ベースの ForC++ステートメント ()](../cpp/range-based-for-statement-cpp.md)」を参照してください。

C++ 言語自体も進化しました。 次の 2 つのコード スニペットを比較してみます。 このスニペットは以前の C++ を使ったものです。

```cpp
#include <vector>

void f()
{
    // Assume circle and shape are user-defined types
    circle* p = new circle( 42 );
    vector<shape*> v = load_shapes();

    for( vector<circle*>::iterator i = v.begin(); i != v.end(); ++i ) {
        if( *i && **i == *p )
            cout << **i << " is a match\n";
    }

    // CAUTION: If v's pointers own the objects, then you
    // must delete them all before v goes out of scope.
    // If v's pointers do not own the objects, and you delete
    // them here, any code that tries to dereference copies
    // of the pointers will cause null pointer exceptions.
    for( vector<circle*>::iterator i = v.begin();
            i != v.end(); ++i ) {
        delete *i; // not exception safe
    }

    // Don't forget to delete this, too.
    delete p;
} // end f()
```

このスニペットは最新の C++ で同じことを行うものです。

```cpp
#include <memory>
#include <vector>

void f()
{
    // ...
    auto p = make_shared<circle>( 42 );
    vector<shared_ptr<shape>> v = load_shapes();

    for( auto& s : v )
    {
        if( s && *s == *p )
        {
            cout << *s << " is a match\n";
        }
    }
}
```

最新の C++ では、スマート ポインターを使用できるため、新規/削除を使用したり、明示的な例外処理を使用する必要はありません。 **Auto**型推論と[ラムダ関数](../cpp/lambda-expressions-in-cpp.md)を使用すると、コードをより迅速に記述し、それを強化し、それを理解することができます。 また、範囲ベース**の for**ループは、C スタイル**の**for ループとは異なり、明確で使いやすく、意図しないエラーが発生しにくくなります。 スケルトン コードを使って、最小限のコードでアプリケーションを記述できます。 さらにそのコードを例外セーフでメモリ セーフにすることができ、割り当て/解放や、エラー コードを取り扱う必要はありません。

最新の C++ では、2 種類のポリモーフィズムが組み込まれています: コンパイル時にテンプレート経由によるもの、および実行時に継承と仮想化によるものです。 2 種類のポリモーフィズムを活用することにより、優れた効果を生じることができます。 標準C++ライブラリテンプレート `shared_ptr` は、内部の仮想メソッドを使用して、非常に簡単な型の消去を実現します。 ただし、テンプレートが最適な選択である場合には、ポリモーフィズムの仮想化を過度に使用しないでください。 テンプレートは非常に強力です。

他の言語から C++ に移ってきた方、特に型の大部分が参照型であり、値型が非常に少ない、他のマネージド言語から移ってきた方は、C++ のクラスは既定で値型であることに注意してください。 ただし、それらを参照型として指定して、オブジェクト指向プログラミングをサポートするポリモーフィックな動作を可能とすることもできます。 値型はメモリとレイアウト コントロールに関するものであり、参照型はポリモーフィズムをサポートする基底クラスと仮想関数に関するものであることを理解すると、役に立ちます。 既定では、値型はコピー可能で、それぞれにコピー コンストラクターとコピー代入演算子があります。 参照型を指定する場合は、コピー コンストラクターとコピー代入演算子を無効化して、クラスをコピー不可にし、ポリモーフィズムをサポートする仮想デストラクターを使用します。 また値型はコンテンツに関するものであり、コピーされるときに、それぞれ変更可能な 2 つの個別の値を持ちます。 一方、参照型はオブジェクトがどのようなものであるかについての識別に関するものであり、このためポリモーフィックな型として参照される場合もあります。

再びパワーが重要視されてきているため、C++ にとってのルネサンスが訪れています。 プログラマの生産性が重要である場合には Java や C# などの言語が適していますが、パワーとパフォーマンスがより重要である場合には、それらの言語には限界があります。 高い効率性とパワーに関しては、特に制限のあるハードウェアによるデバイスでは、最新の C++ に勝るものはありません。

言語が最新であるだけでなく、開発ツールも最新です。 Visual Studio を使用すると、開発サイクルのすべての部分が堅牢で効率的になります。 これにはアプリケーション ライフサイクル管理 (ALM) ツール、IntelliSense などの IDE の強化、XAML などのツールに適した方法、ビルド、デバッグ、および他のツールが含まれています。

ドキュメントのこの部分の記事は、最新の C++ プログラムを作成するために、最も重要な機能および技術に関する、高レベルのガイドラインとベスト プラクティスを提供します。

- [C++型システム](../cpp/cpp-type-system-modern-cpp.md)

- [均一な初期化とコンストラクターのデリゲート](../cpp/uniform-initialization-and-delegating-constructors.md)

- [オブジェクトの有効期間とリソース管理](../cpp/object-lifetime-and-resource-management-modern-cpp.md)

- [リソースを所有するオブジェクト (RAII)](../cpp/objects-own-resources-raii.md)

- [スマートポインター](../cpp/smart-pointers-modern-cpp.md)

- [コンパイル時のカプセル化の pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)

- [コンテナー](../cpp/containers-modern-cpp.md)

- [アルゴリズム](../cpp/algorithms-modern-cpp.md)

- [文字列および i/o の書式設定 (モダンC++)](../cpp/string-and-i-o-formatting-modern-cpp.md)

- [エラーと例外処理](../cpp/errors-and-exception-handling-modern-cpp.md)

- [ABI の境界での移植性](../cpp/portability-at-abi-boundaries-modern-cpp.md)

詳細については、 [c++ 11 でC++非推奨とされ](https://stackoverflow.com/questions/9299101/which-c-idioms-are-deprecated-in-c11)た Stack Overflow に関する記事を参照してください。

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[ラムダ式](../cpp/lambda-expressions-in-cpp.md)<br/>
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)<br/>
[Microsoft C++言語準拠テーブル](../overview/visual-cpp-language-conformance.md)