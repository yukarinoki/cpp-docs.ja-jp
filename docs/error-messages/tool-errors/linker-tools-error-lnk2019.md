---
title: リンカ ツール エラー LNK2019
ms.date: 12/15/2017
f1_keywords:
- LNK2019
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.openlocfilehash: 3c4e5578c7b0f496feb4d40933af624f462a31d2
ms.sourcegitcommit: 680a155cc44a38f88bb2b1c5a1ef6dcb7141c011
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72252624"
---
# <a name="linker-tools-error-lnk2019"></a>リンカ ツール エラー LNK2019

未解決の外部シンボル '*symbol*' が関数 '*function*' で参照されています

コンパイルされた*関数*のコードは、*シンボル*への参照または呼び出しを行いますが、そのシンボルは、リンカーに指定されたライブラリまたはオブジェクトファイルで定義されていません。

このエラーメッセージの後には、致命的なエラー [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)が続きます。 エラー LNK1120 を修正するには、すべての LNK2001 および LNK2019 エラーを修正する必要があります。

## <a name="possible-causes"></a>考えられる原因

このエラーを取得する方法は多数ありますが、そのすべてには、リンカーが*解決*できない関数または変数への参照、またはの定義を見つけるための参照が含まれています。 コンパイラは、シンボルが*宣言*されていないときに *、定義さ*れていない場合は、別のソースファイルまたはライブラリに存在する可能性があることを識別できます。 シンボルが参照されているが定義されていない場合、リンカーは未解決の外部シンボルエラーを生成します。

LNK2019 エラーが発生する一般的な問題には次のものがあります。

### <a name="the-object-file-or-library-that-contains-the-definition-of-the-symbol-is-not-linked"></a>シンボルの定義を含むオブジェクトファイルまたはライブラリがリンクされていません

Visual Studio で、定義を含むソースファイルがビルドされ、プロジェクトの一部としてリンクされていることを確認します。 コマンドラインで、定義を含むソースファイルがコンパイルされていること、および作成されたオブジェクトファイルがリンクするファイルの一覧に含まれていることを確認します。

### <a name="the-declaration-of-the-symbol-is-not-spelled-the-same-as-the-definition-of-the-symbol"></a>シンボルの宣言のスペルがシンボルの定義と同じではありません

宣言と定義の両方で正しいスペルと大文字小文字が使用されていること、およびシンボルが使用または呼び出されている場所が正しいことを確認します。

### <a name="a-function-is-used-but-the-type-or-number-of-the-parameters-do-not-match-the-function-definition"></a>関数が使用されていますが、パラメーターの型または数が関数の定義と一致しません

関数の宣言は、定義と一致している必要があります。 関数の呼び出しが宣言と一致することと、宣言が定義と一致することを確認します。 また、テンプレート関数を呼び出すコードでも、テンプレート関数の宣言を一致させ、定義と同じテンプレート パラメーターを組み込む必要があります。 テンプレート宣言の不一致の例については、「例」の「sample LNK2019e」を参照してください。

### <a name="a-function-or-variable-is-declared-but-not-defined"></a>関数または変数が宣言されていますが、定義されていません。

これは通常、ヘッダーファイルに宣言が存在するが、一致する定義が実装されていないことを意味します。 メンバー関数または静的データ メンバーの場合、実装にはクラス スコープ セレクターを含める必要があります。 例については、「 [Missing Function Body or Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md)」を参照してください。

### <a name="the-calling-convention-is-different-between-the-function-declaration-and-the-function-definition"></a>呼び出し規則が関数宣言と関数定義で異なっています。

呼び出し規則 ([__cdecl](../../cpp/cdecl.md)、 [__stdcall](../../cpp/stdcall.md)、 [__fastcall](../../cpp/fastcall.md)、または [__vectorcall](../../cpp/vectorcall.md)) は、装飾名の一部としてエンコードされます。 呼び出し規則が同じであることを確認します。

### <a name="a-symbol-is-defined-in-a-c-file-but-declared-without-using-extern-c-in-a-c-file"></a>シンボルは C ファイルで定義されていますが、 C++ファイルで Extern "C" を使用せずに宣言されています。

C としてコンパイルされたファイルで定義されるシンボルは、C++ ファイルで [extern "C"](../../cpp/using-extern-to-specify-linkage.md) 修飾子を使用せずに宣言されたシンボルと装飾名が異なります。 シンボルごとに宣言がコンパイル リンケージと一致することを確認してください。 同様に、C++ ファイルで定義されているシンボルを C プログラムで使用する場合にも、定義の中で `extern "C"` を使用します。

### <a name="a-symbol-is-defined-as-static-and-then-later-referenced-outside-the-file"></a>シンボルは static として定義され、後でファイルの外部で参照されます。

C++ では、C とは異なり、 [グローバル定数](../../error-messages/tool-errors/global-constants-in-cpp.md) は `static` リンケージを持ちます。 この制限を回避するには、 `const` 初期化をヘッダー ファイルに組み込み、そのヘッダーを .cpp ファイルにインクルードします。あるいは、変数を非定数にし、定数参照を使用してそれにアクセスすることもできます。

### <a name="a-static-member-of-a-class-is-not-defined"></a>クラスの静的メンバーが定義されていません

静的クラス メンバーは一意に定義する必要があります。そうしないと、単一定義規則に違反します。 インラインで定義できない静的クラス メンバーは、完全修飾名を使用して 1 つのソース ファイル内で定義する必要があります。 それがまったく定義されていない場合、リンカーは LNK2019 を生成します。

### <a name="a-build-dependency-is-only-defined-as-a-project-dependency-in-the-solution"></a>ビルドの依存関係は、ソリューション内のプロジェクトの依存関係としてのみ定義されます

以前のバージョンの Visual Studio では、このレベルの依存関係で十分でした。 ただし、visual Studio 2010 以降では、Visual Studio でプロジェクト[間参照](/visualstudio/ide/managing-references-in-a-project)が必要になります。 プロジェクトにプロジェクト間の参照がない場合は、このリンカー エラーが発生することがあります。 この問題を修正するには、プロジェクト間参照を追加します。

### <a name="an-entry-point-is-not-defined"></a>エントリポイントが定義されていません

アプリケーションコードでは、適切なエントリポイントを定義する必要があります。 `main` またはコンソールアプリケーションの場合は `wmain`、Windows アプリケーションの場合は `WinMain` または @no__t。 詳細については、次を参照してください [main:プログラムのスタートアップ @ no__t または[WinMain 関数](/windows/win32/api/winbase/nf-winbase-winmain)。 カスタムエントリポイントを使用するには、 [/entry (エントリポイントシンボル)](../../build/reference/entry-entry-point-symbol.md)リンカーオプションを指定します。 

### <a name="you-build-a-console-application-by-using-settings-for-a-windows-application"></a>Windows アプリケーションの設定を使用してコンソールアプリケーションを作成する

エラーメッセージが、関数*function_name*で参照されている**未解決の外部シンボル WinMain**に似ている場合は、 **/SUBSYSTEM: WINDOWS**ではなく **/SUBSYSTEM: CONSOLE**を使用してリンクします。 この設定の詳細と、Visual Studio でこのプロパティを設定する手順の詳細については、「 [/SUBSYSTEM (Specify Subsystem)](../../build/reference/subsystem-specify-subsystem.md)」を参照してください。

### <a name="you-attempt-to-link-64-bit-libraries-to-32-bit-code-or-32-bit-libraries-to-64-bit-code"></a>64ビットライブラリを32ビットコードに、または32ビットライブラリを64ビットコードにリンクしようとしています

コードにリンクされているライブラリとオブジェクトファイルは、コードと同じアーキテクチャ用にコンパイルする必要があります。 プロジェクトが参照するライブラリが、プロジェクトと同じアーキテクチャ用にコンパイルされていることを確認します。 リンカーによって使用される[/libpath](../../build/reference/libpath-additional-libpath.md)または**追加ライブラリディレクトリ**のパスオプションが、正しいアーキテクチャ用に構築されたライブラリを指していることを確認してください。

### <a name="you-use-different-compiler-options-for-function-inlining-in-different-source-files"></a>異なるソースファイルでの関数のインライン展開に異なるコンパイラオプションを使用しています

.cpp ファイルで定義されている関数のインライン展開を使用している場合に、異なるソース ファイルで関数のインライン展開のコンパイラ オプションが混在していると、LNK2019 が発生することがあります。 詳細については、「 [Function Inlining Problems](../../error-messages/tool-errors/function-inlining-problems.md)」を参照してください。

### <a name="you-use-automatic-variables-outside-their-scope"></a>スコープ外で自動変数を使用する

自動変数 (関数スコープ) は、その関数のスコープ内でのみ使用できます。 これらの変数を `extern` として宣言して他のソース ファイルで使用することはできません。 例については、「 [Automatic (Function Scope) Variables](../../error-messages/tool-errors/automatic-function-scope-variables.md)」を参照してください。

### <a name="you-call-instrinsic-functions-or-pass-argument-types-to-intrinsic-functions-that-are-not-supported-on-your-target-architecture"></a>ているか関数を呼び出すか、またはターゲットアーキテクチャでサポートされていない組み込み関数に引数の型を渡す

たとえば、組み込関数 AVX2 を使用している場合に、 [/ARCH:AVX2](../../build/reference/arch-x86.md) コンパイラ オプションを指定しないと、コンパイラはこの組み込みを外部関数であると想定します。 コンパイラは、インライン命令を生成するのではなく、組み込みと同じ名前で外部シンボルへの呼び出しを生成します。 リンカーは、欠落しているこの関数の定義を検索しようとして、LNK2019 を生成します。 ターゲット アーキテクチャでサポートされている組み込み関数と型のみを使用していることを確認してください。

### <a name="you-mix-code-that-uses-native-wchar_t-with-code-that-doesnt"></a>ネイティブの wchar @ no__t-0t を使用するコードと、

C++Visual Studio 2005 で実行された言語準拠作業は、既定で-1 @no__t ネイティブ型になりました。 以前のバージョンの Visual Studio を使用してコンパイルされたライブラリファイルおよびオブジェクトファイルと互換性のあるコードを生成するには、 [/zc: wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)コンパイラオプションを使用する必要があります。 すべてのファイルが同じ **/zc: wchar @ no__t-1t**設定を使用してコンパイルされていない場合、型参照は互換性のある型に解決されない可能性があります。 すべてのライブラリ ファイルとオブジェクト ファイル内の `wchar_t` の型に互換性があることを検証し、使用する型を更新するか、コンパイル時に使用する **/Zc:wchar_t** の設定を一貫させるようにしてください。

## <a name="third-party-library-issues-and-vcpkg"></a>サードパーティライブラリの問題と Vcpkg

ビルドの一部としてサードパーティのライブラリを構成しようとしているときにこのエラーが表示される場合は、 C++ [Vcpkg](../../vcpkg.md)(Visual Package Manager) を使用してライブラリをインストールし、ビルドすることを検討してください。 Vcpkg は、多数[のサードパーティ製ライブラリ](https://github.com/Microsoft/vcpkg/tree/master/ports)をサポートしており、プロジェクトの一部として成功したビルドに必要なすべての構成プロパティと依存関係を設定します。 詳細については、関連[するC++ビジュアルのブログ](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/)投稿を参照してください。

## <a name="diagnosis-tools"></a>診断ツール

リンカーが特定のシンボル定義を見つけられない理由を調べるのは難しい問題になることがあります。 多くの場合、問題は、ビルドに定義を含むコードを含めていないこと、またはビルドオプションによって外部シンボルに対して異なる装飾名が作成されていることです。 LNK2019 エラーを診断するために役立ついくつかのツールとオプションを紹介します。

- [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) リンカー オプションを使用すると、リンカーがどのファイルを参照しているかを判断できます。 これは、シンボルの定義の入ったファイルがビルドに含まれているかどうかを確認するために役立ちます。

- **DUMPBIN**ユーティリティの [ [/エクスポート](../../build/reference/dash-exports.md)] オプションと [ [/記号](../../build/reference/symbols.md)] オプションを使用すると、.dll ファイルとオブジェクトファイルまたはライブラリファイルで定義されているシンボルを見つけることができます。 エクスポートされた装飾名が、リンカーが検索する装飾名と一致することを確認してください。

- **Undname**ユーティリティを使用すると、装飾名に対応する、装飾されていない外部シンボルを表示できます。

## <a name="examples"></a>使用例

ここでは、LNK2019 エラーが発生するコードの例を、そのエラーを修正する方法に関する情報と一緒に紹介します。

### <a name="a-symbol-is-declared-but-not-defined"></a>シンボルが宣言されているが、定義されていない

この例では、外部変数が宣言されていますが、定義されていません。

```cpp
// LNK2019.cpp
// Compile by using: cl /EHsc /W4 LNK2019.cpp
// LNK2019 expected
extern char B[100];   // B is not available to the linker
int main() {
   B[0] = ' ';   // LNK2019
}
```

変数と関数が @no__t 0 として宣言されていますが、定義が指定されていない別の例を次に示します。

```cpp
// LNK2019c.cpp
// Compile by using: cl /EHsc LNK2019c.cpp
// LNK2019 expected
extern int i;
extern void g();
void f() {
   i++;
   g();
}
int main() {}
```

@No__t-0 と `g` がビルドに含まれているいずれかのファイルで定義されていない場合、リンカーは LNK2019 を生成します。 このエラーを修正するには、定義を含むソース コード ファイルをコンパイルの一部に組み込みます。 または、定義を含む .obj ファイルまたは .lib ファイルをリンカーに渡すこともできます。

### <a name="a-static-data-member-is-declared-but-not-defined"></a>静的データ メンバーが宣言されているが、定義されていない

LNK2019 は、静的データ メンバーが宣言されているものの定義がなされていない場合に発生することもあります。 次の例は LNK2019 を生成します。その修正方法も示しています。

```cpp
// LNK2019b.cpp
// Compile by using: cl /EHsc LNK2019b.cpp
// LNK2019 expected
struct C {
   static int s;
};

// Uncomment the following line to fix the error.
// int C::s;

int main() {
   C c;
   C::s = 1;
}
```

### <a name="declaration-parameters-do-not-match-definition"></a>パラメーターの宣言が定義と一致しない

テンプレート関数を呼び出すコードには、対応するテンプレート関数宣言が必要です。 宣言には、定義と同じテンプレート パラメーターを含める必要があります。 次の例では、ユーザー定義の演算子で LNK2019 が発生します。その修正方法も示しています。

```cpp
// LNK2019e.cpp
// compile by using: cl /EHsc LNK2019e.cpp
// LNK2019 expected
#include <iostream>
using namespace std;

template<class T> class
Test {
   // The operator<< declaration does not match the definition below:
   friend ostream& operator<<(ostream&, Test&);
   // To fix, replace the line above with the following:
   // template<typename T> friend ostream& operator<<(ostream&, Test<T>&);
};

template<typename T>
ostream& operator<<(ostream& os, Test<T>& tt) {
   return os;
}

int main() {
   Test<int> t;
   cout << "Test: " << t << endl;   // LNK2019 unresolved external
}
```

### <a name="inconsistent-wchar_t-type-definitions"></a>一貫性のない wchar_t 型の定義

このサンプルでは、`wchar_t` に解決される `WCHAR` を使用するエクスポートを含む DLL を作成します。

```cpp
// LNK2019g.cpp
// compile with: cl /EHsc /LD LNK2019g.cpp
#include "windows.h"
// WCHAR resolves to wchar_t
__declspec(dllexport) void func(WCHAR*) {}
```

次のサンプルでは、前のサンプルの DLL を使用して、型 unsigned short * と WCHAR @ no__t-0 が同じではないため、LNK2019 を生成します。

```cpp
// LNK2019h.cpp
// compile by using: cl /EHsc LNK2019h LNK2019g.lib
// LNK2019 expected
__declspec(dllimport) void func(unsigned short*);

int main() {
   func(0);
}
```

このエラーを修正するには、`unsigned short` を `wchar_t` または `WCHAR` に変更するか、 **/zc: wchar_t-** を使用して lnk2019g.cpp をコンパイルします。

## <a name="additional-resources"></a>その他の技術情報

LNK2001 の考えられる原因と解決方法の詳細については、「Stack Overflow の質問」を参照してください。[未定義の参照/未解決の外部シンボルエラーとその解決方法](https://stackoverflow.com/q/12573816/2002113)について説明します。

