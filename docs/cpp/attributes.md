---
title: C++ での属性
ms.date: 05/06/2019
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: bc92e5f3e279edc6fbea7f99d52c469f9fdf04f8
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222304"
---
# <a name="attributes-in-c"></a>C++ での属性

C++ 標準は一連の属性を定義し、コンパイラ ベンダー (製造元固有名前空間に) 内で、独自の属性を定義することができますが、コンパイラが標準で定義されている属性のみを認識する必要があります。

場合によっては、標準属性は、コンパイラ固有の declspec パラメーターと重複します。 Visual C で使用することができます、`[[deprecated]]`属性を使用してではなく`declspec(deprecated)`属性が任意に準拠するコンパイラで認識されるとします。 すべての他の declspec パラメーター dllimport と dllexport などにはありませんとしてまだ属性と同じので declspec 構文を使用し続ける必要があります。 属性、型システムには影響しませんし、プログラムの意味を変更しません。 コンパイラは、認識されていない属性値を無視します。

**Visual Studio 2017 バージョン 15.3 以降**(で使用可能な[/std:c++17](../build/reference/std-specify-language-standard-version.md))。1 つのすべての名前を名前空間を指定する属性リストのスコープで**using**導入。

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C++ 標準の属性

C++ 11 では、属性は、標準化された追加情報は、ベンダー固有ができない可能性がありますを伴う C++ コンストラクト (クラス、関数、変数、およびブロックに限らずを含む) の注釈を付ける方法を提供します。 情報メッセージを生成したり、属性のコードをコンパイルするときに、特別なロジックを適用する、コンパイラはこの情報を使用できます。 コンパイラは、認識されない属性を無視し、つまり、この構文を使用して、独自のカスタム属性を定義することはできません。 属性は、二重の角かっこで囲まれています。

```cpp
[[deprecated]]
void Foo(int);
```

属性は標準化されたことを #pragma ディレクティブなどのベンダー固有拡張機能を表す __declspec() (Visual C++)、または&#95;&#95;属性&#95;&#95; (GNU)。 ただし、したが、ほとんどの場合、ベンダー固有の構造を使用する必要があります。 標準では、現在準拠コンパイラが認識する必要があります、次の属性を指定します。

- `[[noreturn]]` 関数が返すことはありません。 を指定します。つまり常に例外がスローされます。 コンパイラの場合は、そのコンパイル ルールを調整できます`[[noreturn]]`エンティティ。

- `[[carries_dependency]]` 関数がスレッドの同期に対して順序付けデータの依存関係を伝達を指定します。 属性は、渡された引数が関数本体に依存関係を実行するかを指定する、1 つまたは複数のパラメーターに適用できます。 属性は、関数、戻り値が、関数からの依存関係を実行して、自体に適用できます。 コンパイラより効率的なコードを生成するのに、この情報を使用できます。

- `[[deprecated]]` **Visual Studio 2015 以降:** 関数を使用するありませんを指定し、将来のバージョンのライブラリ インターフェイスは存在可能性があります。 コンパイラは、これを使用すると、クライアント コードが、関数を呼び出すしようとしたときに、情報メッセージを生成できます。 クラス、typedef 名、変数、非静的データ メンバー、関数、名前空間、列挙体、列挙子、またはテンプレートの特殊化の宣言に適用できます。

- `[[fallthrough]]` **Visual Studio 2017 以降:** (で使用可能な[/std:c++17](../build/reference/std-specify-language-standard-version.md))、`[[fallthrough]]`のコンテキストで属性を使用できる[スイッチ](switch-statement-cpp.md)コンパイラ (または読むすべてのユーザーへのヒントとしてステートメントコード)、fallthrough 動作が想定されています。 MicrosoftC++コンパイラ現在は、警告、fallthrough 動作のため、この属性には、コンパイラの動作の効果はありません。

- `[[nodiscard]]` **Visual Studio 2017 バージョン 15.3 以降:** (で使用可能な[/std:c++17](../build/reference/std-specify-language-standard-version.md)) 関数の戻り値が破棄されますを意図しないことを指定します。 この例で示すように、C4834 の警告を発生させます。

    ```cpp
    [[nodiscard]]
    int foo(int i) { return i * i; }

    int main()
    {
        foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
        return 0;
    }
    ```

- `[[maybe_unused]]` **Visual Studio 2017 バージョン 15.3 以降:** (で使用可能な[/std:c++ 17](../build/reference/std-specify-language-standard-version.md)) 変数、関数、クラス、typedef、非静的データ メンバー、列挙型、またはテンプレートの特殊化が意図的に使用しないことを指定します。 エンティティがマークされている場合、コンパイラは警告されません`[[maybe_unused]]`は使用されません。 属性を持つ、またはその逆の属性がない宣言されているエンティティ後で再宣言することができます。 エンティティは、マークされている最初の宣言を分析すると、および現在の翻訳単位の翻訳の残りの部分がマークされていると見なされます。

## <a name="microsoft-specific-attributes"></a>Microsoft 固有の属性

- `[[gsl::suppress(rules)]]` この Microsoft 固有の属性が適用チェッカーからの警告を抑制するために使用される[ガイドライン サポート ライブラリ (GSL)](https://github.com/Microsoft/GSL)コード内のルール。 たとえば、次のコード スニペットがあるとします。

    ```cpp
    void main()
    {
        int arr[10]; // GSL warning 26494 will be fired
        int* p = arr; // GSL warning 26485 will be fired
        [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
        {
            int* q = p + 1; // GSL warning 26481 suppressed
            p = q--; // GSL warning 26481 suppressed
        }
    }
    ```

  この例では、これらの警告が発生します。

  - 26494 (ルール 5 を入力します。常にオブジェクトを初期化します。)

  - 26485 (ルール 3 の範囲。配列からなしポインターへの減退。)

  - 26481 (ルール 1 の範囲。ポインターの算術演算を使用しないでください。 スパン代わりに使用します。)

  最初の 2 つの警告は、インストールし、アクティブ化 CppCoreCheck コード分析ツールを使用してこのコードをコンパイルするときに発生します。 ただし、属性により、3 番目の警告イベントは発生しません。 全体の bounds プロファイルを抑制するには、特定のルールの数を含めずに [gsl::suppress(bounds)] を作成します。 安全なコードを記述するため、C++ Core Guidelines のものです。 非表示属性を簡単に必要ない場合、警告をオフにします。