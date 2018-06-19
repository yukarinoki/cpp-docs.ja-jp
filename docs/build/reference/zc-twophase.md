---
title: /Zc:twoPhase-(2 フェーズの名前検索を無効にする) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- twoPhase
- /Zc:twoPhase
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5653959b25105f10ae98768217524dc0ff0cbe2a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389102"
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/Zc:twoPhase-(2 フェーズの名前検索を無効にする)

ときに、 **/Zc:twoPhase-** オプションを指定すると、コンパイラが解析し、非準拠と同様に Visual Studio 2017 15.3 のバージョンより前に、の Visual Studio のバージョンのクラス テンプレートと関数テンプレートのインスタンスを作成します。 

## <a name="syntax"></a>構文

> **/Zc:twoPhase-**

## <a name="remarks"></a>コメント

Visual Studio 2017 15.3 以降では、既定のバージョンでは、コンパイラは、テンプレート名の解決策の名前の 2 フェーズ参照を使用します。 場合 **/Zc:twoPhase-** を指定すると、コンパイラはその以前非準拠クラス テンプレートと関数テンプレート名の解決と代替の動作に戻ります。

**/Zc:twoPhase-** 非準拠の動作を有効にするオプションは既定では設定されません。 [寛容/-](permissive-standards-conformance.md)オプションは、暗黙的に準拠した 2 フェーズ参照コンパイラの動作を設定するがを使用してオーバーライドできます **/Zc:twoPhase-** です。

準拠モードでは、10.0.15063.0 (更新プログラムの作成者または Redstone 2) のバージョンと以前のバージョンの Windows SDK のヘッダー ファイルが正しく動作しないしないでください。 使用する必要があります **/Zc:twoPhase-** Visual Studio 2017 バージョン 15.3 およびそれ以降のバージョンを使用すると、その SDK のバージョンのコードをコンパイルします。 Version 10.0.15254.0 (Redstone 3 または秋作成者の更新プログラム) 以降を Windows SDK のバージョンが準拠モードで正しく動作し、必要としない、 **/Zc:twoPhase-** オプション。

使用して **/Zc:twoPhase-** 場合は、コードが正しくコンパイルする従来の動作が必要です。 標準に準拠するように、コードの更新を検討してください。

### <a name="compiler-behavior-under-zctwophase-"></a>/Zc:twoPhase-コンパイラの動作

Visual Studio 2017 バージョン 15.3、前に、コンパイラのバージョンでは、いつ **/Zc:twoPhase-** を指定すると、コンパイラはこの動作を使用します。

- テンプレートの宣言のみ、クラスの先頭で、および基本クラスの一覧を解析します。 テンプレート本体は、トークンのストリームとしてキャプチャされます。 関数本体、初期化子、既定の引数、または noexcept 引数は解析されません。 クラス テンプレートは、クラス テンプレートの宣言が正しいことを検証する仮の型で擬似インスタンス化です。 このクラス テンプレートを考えてみます。

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   テンプレート宣言`template <typename T`>、クラスの先頭で`class Derived`、および基底クラス リスト`public Base<T>`解析は、トークンのストリームとして、テンプレート本体がキャプチャされますが、します。

- 関数テンプレートを解析するときに、コンパイラは関数のシグネチャのみを解析します。 関数本体が解析されることはありません。 代わりに、トークンのストリームとしてキャプチャされることができます。

その結果、テンプレート本体に構文エラーがあり、ユーザーが、テンプレートがインスタンス化されることはありませんは、エラーは診断ことはありません。

この動作の他の影響は、オーバー ロードの解決です。 トークンのストリームがインスタンス化のサイトで展開されているため、テンプレートの宣言に表示されていなかったシンボル可能性がありますをインスタンス化時点で表示して、オーバー ロードの解決に関与します。 これは、テンプレートをテンプレートが定義されている場合、標準とは対照的に表示されていないコードに基づく動作を変更する可能性があります。

たとえば、次のコードについて考えます。

```cpp
#include <cstdio>

void func(void*) { std::puts("The call resolves to void*") ;}

template<typename T> void g(T x)
{
    func(0);
}

void func(int) { std::puts("The call resolves to int"); }

int main() 
{
    g(3.14);
}
```

コンパイル時に **/Zc:twoPhase-**、「呼び出しが int 型に解決」を出力します。 準拠モードで**寛容/-**、このプログラムは、2 番目のオーバー ロードのため「の呼び出しは、void * に解決される、」を出力`func`テンプレートが見つかった場合に表示されません。

*依存名*、テンプレート パラメーターに依存する名前でも検索動作がある **/Zc:twoPhase-** です。 準拠モードでは、依存名は、テンプレートの定義の時点でバインドされていません。 代わりに、テンプレートがインスタンス化されるときに、これらの名前参照します。 依存する関数名、関数呼び出しの名前は、上と、テンプレートの定義内の呼び出しの時点で表示されている関数のセットにバインドされます。 引数依存の検索からの他のオーバー ロードは、テンプレートの定義の時点と、テンプレートがインスタンス化のポイントの両方に追加されます。 2 フェーズ参照の 2 つのフェーズは非依存名の検索時のテンプレートの定義および参照の依存名のテンプレートのインスタンス化時にします。 **/Zc:twoPhase-** コンパイラは行わない引数依存の検索とは別に通常、非修飾参照を行う (つまり、実行される処理は 2 フェーズ参照)、ため、オーバー ロードの解決の結果が異なる場合があります。

別の例を次に示します。

```cpp
// zctwophase1.cpp
// Compile by using
// cl /EHsc /W4 /permissive- zctwophase1.cpp
// cl /EHsc /W4 /permissive- /Zc:twoPhase- zctwophase1.cpp

#include <cstdio>

void func(long) { std::puts("func(long)"); }

template <typename T> void tfunc(T t) {
    func(t);
}

void func(int) { std::puts("func(int)"); }

namespace NS {
    struct S {};
    void func(S) { std::puts("NS::func(NS::S)"); }
}

int main() {
    tfunc(1729);
    NS::S s;
    tfunc(s);
}
```

なしでコンパイルされるときに **/Zc:twoPhase-**、印刷

```Output
func(long)
NS::func(NS::S)
```

コンパイルしたときに **/Zc:twoPhase-**、印刷

```Output
func(int)
NS::func(NS::S)
```

準拠モードで**寛容/-**、呼び出し`tfunc(1729)`に解決される、`void func(long)`オーバー ロードできません`void func(int)`オーバー ロードの下にある、 **/Zc:twoPhase-** であるため修飾されていません。`func(int)`がテンプレートの定義の後に宣言され、引数依存の検索で検出されません。 しかし、 `void func(S)` 、オーバー ロードの呼び出しの設定に追加されるので、引数依存の検索に参加して`tfunc(s)`テンプレート関数の後に宣言されている場合でもです。

### <a name="update-your-code-for-two-phase-conformance"></a>2 フェーズの適合性、コードを更新します。

古いバージョンのコンパイラには、キーワードは不要`template`と`typename`everywhere、C++ 標準で必要なです。 いくつかの位置には、コンパイラが参照の最初のフェーズ中に依存している名前を解析する必要がある方法を区別するためにこれらのキーワードが必要です。 例えば:

`T::Foo<a || b>(c);`

準拠コンパイラ解析`Foo`のスコープ内の変数として`T`、つまり、このコードは、論理的- や式`T::foo < a`左のオペランドとしてと`b > (c)`右側のオペランドとして。 使用することを意味する場合`Foo`関数テンプレートとして追加することで、テンプレートであるを指定する必要があります、`template`キーワード。

`T::template Foo<a || b>(c);`

Visual Studio 2017 バージョン 15.3、以前のバージョンで、いつ **/Zc:twoPhase-** を指定すると、コンパイラがなくこのコードを使用できます、`template`キーワードの引数を持つ関数テンプレートへの呼び出しとして解釈`a || b`非常に限定された方法でテンプレートを解析しているため、します。 上記のコードは、最初のフェーズですべての解析はありません。 2 番目のフェーズは、ことを識別するための十分なコンテキスト`T::Foo`は変数ではなく、テンプレートをコンパイラが、キーワードの使用を強制していないためです。

この動作は、キーワードを排除することによっても確認できます`typename`関数テンプレート本体、初期化子、既定の引数、および noexcept 引数名の前にします。 例えば:

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

キーワードを使用しない場合`typename`関数本体でこのコードはコンパイル **/Zc:twoPhase-**、ではない**寛容/-** です。 `typename`キーワードがあることを示すために必要な`TYPE`が依存しています。 本文が下にある解析されないため **/Zc:twoPhase-** コンパイラが、キーワードを必要とします。 **寛容/-** 準拠モードでないコード、`typename`キーワードには、エラーが生成されます。 Visual Studio 2017 バージョン 15.3 にコードを移行し、挿入、`typename`キーワードが存在しません。

同様に、このサンプル コードについて考えてみます。

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

**/Zc:twoPhase-** 古いコンパイラでコンパイラだけが必要な`template`2 行目にキーワード。 既定と準拠モードでは、コンパイラ今すぐも必要です、`template`ことを示す 4 行目ではキーワード`T::X<T>`テンプレートです。 このキーワードが欠落しているコードを確認し、標準に準拠しているコードを作成することを指定します。

準拠の問題の詳細については、次を参照してください。 [Visual Studio での C++ 適合性の向上](../../cpp-conformance-improvements-2017.md)と[非標準動作](../../cpp/nonstandard-behavior.md)です。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:twoPhase-** を選択し**OK**です。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
