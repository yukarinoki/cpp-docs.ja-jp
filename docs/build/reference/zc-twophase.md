---
title: /Zc:twoPhase-(2 フェーズの名前参照を無効にする)
ms.date: 03/06/2018
f1_keywords:
- twoPhase
- /Zc:twoPhase
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
ms.openlocfilehash: 5f990181fd1e606cf9d7dd33242752bed33aa456
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315808"
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/Zc:twoPhase-(2 フェーズの名前参照を無効にする)

ときに、 **/Zc:twoPhase-** オプションを指定すると、コンパイラは、解析し、Visual Studio 2017 バージョン 15.3 の前に Visual Studio のバージョンと同じ非準拠の方法で、クラス テンプレートと関数テンプレートをインスタンス化します。

## <a name="syntax"></a>構文

> **/Zc:twoPhase-**

## <a name="remarks"></a>Remarks

Visual Studio 2017 バージョン 15.3 以降、既定では、コンパイラは、テンプレートの名前解決のため 2 フェーズの名前参照を使用します。 場合 **/Zc:twoPhase-** を指定すると、コンパイラの以前非準拠クラス テンプレートと関数テンプレート名解像度と置換の動作に戻ります。

**/Zc:twoPhase-** 非準拠の動作を有効にするオプションが既定で設定されていません。 [/Permissive -](permissive-standards-conformance.md)オプションは、2 フェーズ参照コンパイラの準拠の動作を暗黙的に設定しますを使用してオーバーライドできます **/Zc:twoPhase-** します。

準拠モードでは、バージョン 10.0.15063.0 (Creators Update またはレッドス トーン 2) と以前のバージョンの Windows SDK ヘッダー ファイルが正しく動作しない操作を行います。 使用する必要があります **/Zc:twoPhase-** Visual Studio 2017 バージョン 15.3 以降を使用すると、これらの SDK バージョンのコードをコンパイルします。 バージョン 10.0.15254.0 (レッドス トーン 3 または Fall Creators Update) 以降、Windows SDK のバージョンが準拠モードで正しく動作し、必要としない、 **/Zc:twoPhase-** オプション。

使用 **/Zc:twoPhase-** コードが正しくコンパイルする従来の動作が必要な場合。 厳密に標準に準拠するように、コードの更新を検討してください。

### <a name="compiler-behavior-under-zctwophase-"></a>/Zc:twoPhase-コンパイラの動作

バージョンの Visual Studio 2017 バージョン 15.3 では、前に、コンパイラとタイミング **/Zc:twoPhase-** 指定すると、コンパイラはこの動作を使用します。

- テンプレート宣言のみ、クラスの先頭および基底クラス リストを解析します。 テンプレートの本文は、トークンのストリームとしてキャプチャされます。 関数本体、初期化子、既定の引数、または noexcept 引数を解析しません。 クラス テンプレートは、クラス テンプレート内の宣言が正しいことを検証する一時的な型で擬似インスタンス化します。 このクラス テンプレートを検討してください。

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   テンプレートの宣言`template <typename T`>、クラスの先頭`class Derived`、および基底クラス リスト`public Base<T>`が解析、テンプレートの本文は、トークンのストリームとしてキャプチャされますが、します。

- 関数テンプレートを解析するときに、コンパイラは関数のシグネチャのみを解析します。 関数本体が解析されることはありません。 代わりに、トークンのストリームとしてキャプチャします。

その結果、テンプレートの本文に構文エラーがある、テンプレートがインスタンス化されない場合は、エラーは診断ことはありません。

この動作の別の効果は、オーバー ロードの解決です。 トークンのストリームがインスタンス化のサイトに展開されるため、テンプレートの宣言では表示されませんでしたシンボル可能性がありますをインスタンス化の時点で表示して、オーバー ロードの解決に関与します。 これは、標準とは異なり、テンプレートで定義されたときに表示されていないコードに基づいて動作を変更するテンプレートにつながります。

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

コンパイル時に **/Zc:twoPhase-**、「呼び出しが int 型に解決する」を出力します。 準拠モードで **/permissive -**、このプログラムは、2 つ目のオーバー ロードするため、「呼び出しが void * に解決する」を出力`func`コンパイラが検出すると、テンプレートは表示されません。

*依存名*、テンプレート パラメーターに依存する名前でも検索動作がある **/Zc:twoPhase-** します。 準拠モードでは、依存名は、テンプレートの定義の時点でバインドされていません。 代わりに、テンプレートがインスタンス化されるときに、これらの名前を検索します。 依存する関数の名前は、関数の呼び出しの名前は、上記のテンプレートの定義での呼び出しの時点に表示されている関数のセットにバインドされます。 引数依存の検索から追加のオーバー ロードは、テンプレート定義のポイントとテンプレートがインスタンスのポイントの両方に追加されます。 2 フェーズ参照の 2 つのフェーズでは、依存名のテンプレートのインスタンス化時にテンプレートの定義、およびルックアップの時に非依存名のルックアップが。 **/Zc:twoPhase-** コンパイラは行いません引数依存の検索とは別に通常、非修飾参照 (つまり、実行される処理は 2 フェーズ参照)、ため、オーバー ロードの解決の結果が異なる場合があります。

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

なしのコンパイル時に **/Zc:twoPhase-**、印刷

```Output
func(long)
NS::func(NS::S)
```

コンパイルされたときに **/Zc:twoPhase-**、印刷

```Output
func(int)
NS::func(NS::S)
```

準拠モードで **/permissive -**、呼び出し`tfunc(1729)`に解決される、`void func(long)`オーバー ロードしない`void func(int)`オーバー ロードの下に **/Zc:twoPhase-** のため、修飾されていません。`func(int)`がテンプレートの定義の後に宣言され、引数依存の検索で見つかりませんでした。 `void func(S)`ため、オーバー ロードの呼び出しの設定に追加されますが、引数依存の検索に参加`tfunc(s)`テンプレート関数の後に宣言されている場合でもです。

### <a name="update-your-code-for-two-phase-conformance"></a>2 フェーズに準拠するため、コードを更新します。

以前のバージョンのコンパイラには、キーワードは不要`template`と`typename`C++ 標準でに、すべての場所。 コンパイラが参照の最初のフェーズ中に依存する名前を解析する必要がある方法を明確に区別する、いくつかの位置にこれらのキーワードが必要です。 例:

`T::Foo<a || b>(c);`

準拠コンパイラ解析`Foo`のスコープ内の変数として`T`、つまり、このコードは、論理的-、または式`T::foo < a`左のオペランドとしてと`b > (c)`右側のオペランドとして。 使用することを意味する場合`Foo`関数テンプレートとして追加することで、テンプレートであるを指定する必要があります、`template`キーワード。

`T::template Foo<a || b>(c);`

Visual Studio 2017 バージョン 15.3 では、以前のバージョンでいつ **/Zc:twoPhase-** を指定すると、コンパイラがなく、このコードを使用できます、`template`キーワードとの引数を持つ関数テンプレートへの呼び出しと解釈します。`a || b`非常に限定された方法でテンプレートを解析するため、します。 上記のコードは、最初のフェーズでまったく解析されません。 2 番目のフェーズは、ことを識別するための十分なコンテキスト`T::Foo`変数ではなく、テンプレートは、コンパイラがキーワードの使用を強制しないようにします。

この動作は、キーワードを排除することによっても表示されます`typename`関数テンプレート本体、初期化子、既定の引数、および noexcept 引数名の前にします。 例:

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

キーワードを使用しない場合`typename`関数本体内のこのコードはコンパイル **/Zc:twoPhase-** がない **/permissive -** します。 `typename`キーワードがあることを示す必要な`TYPE`は依存しています。 本文は、下は解析されないため、 **/Zc:twoPhase-** コンパイラは、キーワードを必要とします。 **/Permissive -** 準拠モードでは、コードなし、`typename`キーワードがエラーを生成します。 コードに移行する Visual Studio 2017 バージョン 15.3 以降、挿入、`typename`キーワードが存在しません。

同様に、このコード サンプルを検討してください。

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

**/Zc:twoPhase-** 以前のコンパイラでコンパイラのみが必要です、 `template` 2 行目にキーワード。 既定では、および準拠モードでは、コンパイラもが必要になりました、`template`キーワードがあることを示す 4 行`T::X<T>`はテンプレートです。 このキーワードが不足しているコードを確認し、標準に準拠しているコードを作成することを指定します。

準拠の問題の詳細については、次を参照してください。 [Visual Studio での C++ 準拠の強化](../../overview/cpp-conformance-improvements.md)と[非標準動作](../../cpp/nonstandard-behavior.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:twoPhase-** 選び、 **OK**します。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)<br/>
