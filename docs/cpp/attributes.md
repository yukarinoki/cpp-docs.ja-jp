---
title: C++ 標準属性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/28/2017
ms.topic: language-reference
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: 7bd7fd4e01fb210069f4dbae42a671e4dd9c64c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416198"
---
# <a name="attributes-in-c"></a>C++ での属性

C++ 標準は、一連の属性を定義し、コンパイラ販売元 (、ベンダー固有名前空間内で)、独自の属性を定義することもできますが、標準で定義されている属性のみを認識するようにコンパイラが必要です。

場合によっては、標準的な属性はコンパイラ固有 declspec パラメーターと重複します。 Visual c で使用することができます、`[[deprecated]]`属性を使用せずに`declspec(deprecated)`属性は、準拠するコンパイラで認識されるとします。 すべての他の declspec パラメーター dllimport と dllexport などがないとしてまだ属性と同じのため declspec 構文を使用して続行する必要があります。 プログラムの意味を変更しないして属性、型システムには影響しません。 コンパイラは、認識されていない属性値を無視します。

**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 属性リストのスコープを 1 つのすべての名前、名前空間を指定できます`using`紹介子。

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C++ 標準属性

C++ 11 では、属性は、ベンダー固有ができない可能性がありますまたは可能性のある追加の情報を伴う C++ コンストラクト (クラス、関数、変数、およびブロックに限らずを含む) の注釈を設定する標準化された方法を提供します。 コンパイラは、この情報を使用して、情報メッセージを生成したり、属性のコードをコンパイルするときに、特別なロジックを適用することができます。 コンパイラは、認識されない属性を無視し、つまり、この構文を使用して、独自のカスタム属性を定義することはできません。 属性は、二重の角かっこで囲まれました。

```cpp
[[deprecated]]
void Foo(int);
```

#Pragma ディレクティブ、_ _declspec() (Visual C) などのベンダー固有の拡張機能に代わる、標準化された手段を表す属性または&#95;&#95;属性&#95;&#95; (GNU)。 ただし、ほとんどの場合は、ベンダー固有の構造体を使用する必要があります。 標準では、現在準拠コンパイラが認識する必要があります、次の属性を指定します。

- `[[noreturn]]` 関数決してを返すように指定します。つまり、例外が常にスローされます。 コンパイラのコンパイル ルールを調整できます`[[noreturn]]`エンティティです。

- `[[carries_dependency]]` 関数がデータ依存関係のスレッドの同期に関して順序を反映させることを指定します。 属性は、渡された引数が関数の本体に依存関係を持ち込むことを指定する、1 つまたは複数のパラメーターに適用できます。 属性は、関数の戻り値が関数からの依存関係を持ち込むことを指定する自体に適用できます。 コンパイラは、この情報を使用して、効率的なコードを生成することができます。

- `[[deprecated]]` **Visual Studio 2015 以降:** 指定関数が使用するものではありませんが存在しない将来のバージョンのライブラリ インターフェイスとします。 このコンパイラを使用してクライアント コードが、関数を呼び出すしようとしたときに、情報メッセージを生成します。 クラス、typedef 名、変数、非静的データ メンバー、関数、名前空間、列挙体、列挙子、またはテンプレートの特殊化の宣言に適用できます。  

- `[[fallthrough]]` **2017 およびそれ以降の visual Studio:** (で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md))、`[[fallthrough]]`のコンテキストで属性を使用できます[切り替える](switch-statement-cpp.md)コンパイラ (または読むすべてのユーザーへのヒントとしてステートメントコード) fallthrough が動作をすることです。 Visual C コンパイラ現在は警告 fallthrough が動作のため、この属性はコンパイラの動作の効果を持ちません。

- `[[nodiscard]]` **Visual Studio 2017 15.3 およびそれ以降のバージョン:** (で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)) 関数の戻り値が破棄されるものではありませんを指定します。 この例のように、C4834 の警告を発生させます。

   ```cpp
   [[nodiscard]]
   int foo(int i) { return i * i; }

   int main()
   {
       foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
       return 0;
   }
   ```

- `[[maybe_unused]]` **Visual Studio 2017 15.3 およびそれ以降のバージョン:** (で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)) 変数、関数、クラス、typedef、非静的データ メンバー、列挙型、またはテンプレートの特殊化は意図的に使用しないことを指定します。 エンティティがマークされている場合、コンパイラは警告しない`[[maybe_unused]]`は使用されません。 属性がない宣言されているエンティティは、属性およびその逆に後で再宣言することができます。 エンティティは、マークされている、最初の宣言を分析した後と、現在の翻訳単位の翻訳の残りの部分をマークされていると見なされます。

## <a name="microsoft-specific-attributes"></a>Microsoft 固有の属性

- `[[gsl::suppress(rules)]]` この Microsoft 固有の属性を強制するチェッカーからの警告を抑制するために使用される[ガイドライン サポート ライブラリ (GSL)](https://github.com/Microsoft/GSL)コード内のルール。 たとえば、次のコード スニペットがあるとします。

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

   - 26494 (型のルール 5: 常にオブジェクトを初期化します)。

   - 26485 (範囲のルール 3: ポインター減衰にない配列です)。

   - 26481 (境界規則 1: ポインター演算を使用しません。 スパン代わりに使用します。)

   最初の 2 つの警告は、インストールされアクティブ化 CppCoreCheck コード分析ツールを使用してこのコードをコンパイルするときに発生します。 属性のため、3 つ目の警告イベントは発生しません。 境界プロファイル全体を抑制するには、特定のルールの数を含めずに [gsl::suppress(bounds)] を作成します。 C++ の主要なガイドラインより、安全なコードを記述するために設計されています。 非表示属性しやすい必要ない場合に、警告をオフにします。
