---
title: /Zc:twoPhase- (2 フェーズの名前参照の無効化)
description: '/Permissive-が指定されている場合に、/Zc: twoPhase が2フェーズの名前参照を無効にする方法について説明します。'
ms.date: 12/03/2019
f1_keywords:
- twoPhase
- /Zc:twoPhase
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
ms.openlocfilehash: 712503d08221d29a61323946008f2f36a467cb31
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234329"
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/Zc:twoPhase- (2 フェーズの名前参照の無効化)

**/Permissive-** の下にある **/zc: twoPhase**は、元の準拠していない Microsoft C++ コンパイラ動作を使用して、クラステンプレートと関数テンプレートを解析およびインスタンス化するようコンパイラに指示します。

## <a name="syntax"></a>構文

> **/Zc: twoPhase-**

## <a name="remarks"></a>解説

Visual Studio 2017 バージョン15.3 以降: [/permissive-](permissive-standards-conformance.md)では、コンパイラはテンプレート名の解決に2フェーズの名前参照を使用します。 また、 **/zc: twoPhase**を指定した場合、コンパイラは、以前の非準拠クラステンプレートと関数テンプレートの名前解決および置換動作に戻ります。 **/Permissive-** が指定されていない場合、非準拠の動作が既定値になります。

バージョン 10.0.15063.0 (作成者 Update または RS2) 以前の Windows SDK ヘッダーファイルは、準拠モードでは動作しません。 **/Zc: twoPhase-** **/permissive-** を使用するときに、これらの SDK バージョンのコードをコンパイルするために必要です。 バージョン 10.0.15254.0 (RS3) 以降のバージョンの Windows SDK は、準拠モードで正しく動作します。 **/Zc: twoPhase**は必要ありません。

**/Zc: twoPhase**を使用します。コードで古い動作が正しくコンパイルされる必要がある場合に使用します。 標準に準拠するようにコードを更新することを強くお勧めします。

### <a name="compiler-behavior-under-zctwophase-"></a>/Zc: twoPhase の下のコンパイラ動作

既定では、Visual Studio 2017 バージョン15.3 以降では、 **/permissive-** と **/zc: twoPhase**の両方を指定すると、コンパイラは次の動作を使用します。

- テンプレート宣言、クラスの先頭、および基底クラスのリストのみを解析します。 テンプレート本文は、トークンストリームとしてキャプチャされます。 関数本体、初期化子、既定の引数、または noexcept の引数は解析されません。 クラステンプレートは、クラステンプレート内の宣言が正しいことを検証するために、仮設型で擬似インスタンス化されます。 次のクラステンプレートを考えてみましょう。

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   テンプレート宣言、 `template <typename T>` 、クラス head、 `class Derived` および基底クラスリストは `public Base<T>` 解析されますが、テンプレート本体はトークンストリームとしてキャプチャされます。

- 関数テンプレートを解析するとき、コンパイラは関数のシグネチャのみを解析します。 関数本体が解析されることはありません。 代わりに、トークンストリームとしてキャプチャされます。

その結果、テンプレートの本文に構文エラーがあるにもかかわらず、テンプレートがインスタンス化されない場合、コンパイラはエラーを診断しません。

この動作のもう1つの影響は、オーバーロードの解決です。 非標準動作は、インスタンス化のサイトでトークンストリームが拡張される方法によって発生します。 テンプレート宣言で参照できないシンボルは、インスタンス化の時点で表示される場合があります。 これは、オーバーロードの解決に参加できることを意味します。 テンプレート定義に表示されていないコードに基づいて、テンプレートの動作が変更される場合があります (標準とは異なります)。

たとえば、次のコードを検討してみましょう。

```cpp
// zctwophase.cpp
// To test options, compile by using
// cl /EHsc /nologo /W4 zctwophase.cpp
// cl /EHsc /nologo /W4 /permissive- zctwophase.cpp
// cl /EHsc /nologo /W4 /permissive- /Zc:twoPhase- zctwophase.cpp

#include <cstdio>

void func(long) { std::puts("Standard two-phase") ;}

template<typename T> void g(T x)
{
    func(0);
}

void func(int) { std::puts("Microsoft one-phase"); }

int main()
{
    g(6174);
}
```

**/Zc: twoPhase**オプションで既定のモード、準拠モード、および準拠モードを使用する場合の出力を次に示します。

```cmd
C:\Temp>cl /EHsc /nologo /W4 zctwophase.cpp && zctwophase
zctwophase.cpp
Microsoft one-phase

C:\Temp>cl /EHsc /nologo /W4 /permissive- zctwophase.cpp && zctwophase
zctwophase.cpp
Standard two-phase

C:\Temp>cl /EHsc /nologo /W4 /permissive- /Zc:twoPhase- zctwophase.cpp && zctwophase
zctwophase.cpp
Microsoft one-phase
```

**/Permissive-** の下で準拠モードでコンパイルされると、このプログラムは " `Standard two-phase` " を出力します。これは、 `func` コンパイラがテンプレートに到達したときにの2番目のオーバーロードが表示されないためです。 **/Zc: twoPhase-** を追加すると、プログラムは "" を出力し `Microsoft one-phase` ます。 出力は、 **/permissive-** を指定しない場合と同じです。

*依存名*は、テンプレートパラメーターに依存する名前です。 これらの名前の参照動作は、 **/zc: twoPhase-** の下でも異なります。 準拠モードでは、依存名がテンプレートの定義の時点でバインドされていません。 代わりに、テンプレートをインスタンス化するときに、コンパイラによって検索されます。 依存する関数名を持つ関数呼び出しの場合、名前は、テンプレート定義の呼び出しサイトで表示される関数にバインドされます。 引数依存の参照からの追加のオーバーロードは、テンプレート定義の時点でも、テンプレートのインスタンス化の時点でも追加されます。

2フェーズ参照は、テンプレート定義時の非依存名の参照と、テンプレートのインスタンス化時の依存名の参照という2つの部分で構成されます。 **/Zc: twoPhase の**下では、コンパイラは非修飾参照とは別に、引数依存の参照を実行しません。 つまり、2フェーズ参照が行われないため、オーバーロード解決の結果が異なる場合があります。

別の例:

```cpp
// zctwophase1.cpp
// To test options, compile by using
// cl /EHsc /W4 zctwophase1.cpp
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

**/Permissive-** なしでコンパイルすると、次のコードが出力されます。

```Output
func(int)
NS::func(NS::S)
```

**/Permissive-** を使用してコンパイルしたときに **/zc: twoPhase-** を指定しないと、次のコードが出力されます。

```Output
func(long)
NS::func(NS::S)
```

**/Permissive-** と **/zc: twoPhase**の両方を使用してコンパイルすると、次のコードが出力されます。

```Output
func(int)
NS::func(NS::S)
```

**/Permissive-** の下の準拠モードでは、呼び出しは `tfunc(1729)` オーバーロードに解決され `void func(long)` ます。 `void func(int)` **/Zc: twoPhase-** のように、オーバーロードには解決されません。 これは、非修飾 `func(int)` がテンプレートの定義の後で宣言され、引数依存の参照によって見つからないためです。 ただし、 `void func(S)` は引数依存の参照に参加するため、 `tfunc(s)` テンプレート関数の後に宣言されている場合でも、呼び出し用に設定されたオーバーロードに追加されます。

### <a name="update-your-code-for-two-phase-conformance"></a>2段階に準拠するようにコードを更新する

以前のバージョンのコンパイラでは、キーワード、 **`template`** および **`typename`** C++ 標準で必要とされるすべての場所を必要としません。 これらのキーワードは、参照の最初のフェーズでコンパイラが依存名を解析する方法を明確にするために、いくつかの位置で必要になります。 次に例を示します。

`T::Foo<a || b>(c);`

準拠するコンパイラは、 `Foo` のスコープ内で変数として解析し `T` ます。つまり、このコードは、左側のオペランドとして、右のオペランドとしてを持つ論理 or 式です `T::foo < a` `b > (c)` 。 関数テンプレートとしてを使用する場合は、キーワードを追加すること `Foo` で、それがテンプレートであることを示す必要があり **`template`** ます。

`T::template Foo<a || b>(c);`

Visual Studio 2017 バージョン15.3 以降のバージョンでは、 **/permissive-** と **/zc: twoPhase**が指定されている場合、コンパイラはキーワードを使用せずにこのコードを許可し **`template`** ます。 このコードは、限定された方法でテンプレートを解析するだけなので、引数を持つ関数テンプレートへの呼び出しとして解釈され `a || b` ます。 上記のコードは、最初のフェーズでは解析されません。 2番目のフェーズでは、が変数ではなくテンプレートであることを示すのに十分なコンテキストがある `T::Foo` ため、コンパイラはキーワードの使用を強制しません。

この動作は、 **`typename`** 関数テンプレート本体、初期化子、既定の引数、および noexcept 引数の名前の前にキーワードを削除することによっても確認できます。 次に例を示します。

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

関数本体でキーワードを使用しない場合 **`typename`** 、このコードは **/permissive-/Zc: twoPhase**でコンパイルされますが、 **/permissive-** だけではコンパイルされません。 **`typename`** キーワードは、が依存していることを示すために必要です `TYPE` 。 **/Zc: twoPhase の**下では本文が解析されないため、コンパイラはキーワードを必要としません。 **/Permissive-** 準拠モードでは、キーワードのないコードが **`typename`** エラーを生成します。 Visual Studio 2017 バージョン15.3 以降の準拠にコードを移行するには、 **`typename`** キーワードが欠落している場所に挿入します。

同様に、次のコードサンプルを考えてみます。

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

**/Permissive-/zc: twoPhase-** 以前のコンパイラでは、コンパイラは **`template`** 2 行目のキーワードのみを必要とします。 準拠モードでは、コンパイラは、がテンプレートであること **`template`** を示すために、4行目のキーワードも必要になりました `T::X<T>` 。 このキーワードが欠落しているコードを探し、コードが標準に準拠するように指定します。

準拠に関する問題の詳細については、「 [Visual Studio での C++ 準拠の機能強化](../../overview/cpp-conformance-improvements.md)」と「[非標準動作](../../cpp/nonstandard-behavior.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **/Zc: twoPhase**を含めるように "**追加オプション**" プロパティを変更し、[ **OK]** を選択します。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)
