---
title: リンカ ツール エラー LNK2019 |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2019
dev_langs:
- C++
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4323e5f8357da046db7a9403d7c575dfdde566b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2019"></a>リンカ ツール エラー LNK2019

未解決の外部シンボル '*シンボル*'関数で参照されている'*関数*'

コンパイル済みコード*関数*参照またはへの呼び出しは*シンボル*が、そのシンボルがリンカーに指定されたオブジェクト ファイル、ライブラリのいずれかで定義されていません。

このエラー メッセージの致命的なエラーが続く[LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)です。 エラー LNK1120 を修正するすべての LNK2001 および LNK2019 エラーを修正する必要があります。

## <a name="possible-causes"></a>考えられる原因

このエラーが発生するさまざまな方法がありますが、関数またはリンカーできません変数への参照を含むすべての*解決*定義を見つけられないか。 コンパイラがシンボルがない場合に特定できます*宣言*がない場合ではありません*定義*定義が別のソース ファイルまたはライブラリ内であるので、します。 シンボルが参照されるが、定義されていることはない場合、リンカーは未解決の外部シンボル エラーを生成します。

LNK2019 エラーが発生する一般的な問題には次のものがあります。

### <a name="the-object-file-or-library-that-contains-the-definition-of-the-symbol-is-not-linked"></a>オブジェクト ファイルまたはシンボルの定義が含まれているライブラリがリンクされていません。

Visual Studio での定義を含むソース ファイルが構築およびプロジェクトの一部としてリンクされていることを確認します。 コマンド ライン定義を含むソース ファイルがコンパイルされると、リンクするファイルの一覧で、結果として得られるオブジェクト ファイルが含まれることを確認します。

### <a name="the-declaration-of-the-symbol-is-not-spelled-the-same-as-the-definition-of-the-symbol"></a>シンボルの宣言では、シンボルの定義と同じスペルがありません。

正しいスペルおよび大文字と小文字が、定義と宣言の両方で使用して、シンボルの使用方法またはと呼ばれる任意の場所を確認します。

### <a name="a-function-is-used-but-the-type-or-number-of-the-parameters-do-not-match-the-function-definition"></a>関数が使用されるが、型またはパラメーターの数が、関数定義と一致しません。

関数の宣言は、定義と一致している必要があります。 関数の呼び出しが宣言と一致することと、宣言が定義と一致することを確認します。 また、テンプレート関数を呼び出すコードでも、テンプレート関数の宣言を一致させ、定義と同じテンプレート パラメーターを組み込む必要があります。 テンプレート宣言の不一致の例は、サンプル LNK2019e.cpp「例」を参照してください。

### <a name="a-function-or-variable-is-declared-but-not-defined"></a>関数または変数の宣言が定義されていません

これは通常、ヘッダー ファイルで宣言が存在しますが、対応する定義が実装されていないことを意味します。 メンバー関数または静的データ メンバーの場合、実装にはクラス スコープ セレクターを含める必要があります。 例については、「 [Missing Function Body or Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md)」を参照してください。

### <a name="the-calling-convention-is-different-between-the-function-declaration-and-the-function-definition"></a>呼び出し規則が関数宣言と関数定義で異なる

呼び出し規則 ([__cdecl](../../cpp/cdecl.md)、 [__stdcall](../../cpp/stdcall.md)、 [__fastcall](../../cpp/fastcall.md)、または [__vectorcall](../../cpp/vectorcall.md)) は、装飾名の一部としてエンコードされます。 呼び出し規則が同じであることを確認します。

### <a name="a-symbol-is-defined-in-a-c-file-but-declared-without-using-extern-c-in-a-c-file"></a>シンボルは C ファイルで定義されているが、C++ ファイルで extern"C"を使用せずに宣言されました。

C としてコンパイルされたファイルで定義されるシンボルは、C++ ファイルで [extern "C"](../../cpp/using-extern-to-specify-linkage.md) 修飾子を使用せずに宣言されたシンボルと装飾名が異なります。 シンボルごとに宣言がコンパイル リンケージと一致することを確認してください。 同様に、C++ ファイルで定義されているシンボルを C プログラムで使用する場合にも、定義の中で `extern "C"` を使用します。

### <a name="a-symbol-is-defined-as-static-and-then-later-referenced-outside-the-file"></a>シンボルが static として定義されているし、後で、ファイルの外部参照

C++ では、C とは異なり、 [グローバル定数](../../error-messages/tool-errors/global-constants-in-cpp.md) は `static` リンケージを持ちます。 この制限を回避するには、 `const` 初期化をヘッダー ファイルに組み込み、そのヘッダーを .cpp ファイルにインクルードします。あるいは、変数を非定数にし、定数参照を使用してそれにアクセスすることもできます。

### <a name="a-static-member-of-a-class-is-not-defined"></a>クラスの静的メンバーが定義されていません

静的クラス メンバーは一意に定義する必要があります。そうしないと、単一定義規則に違反します。 インラインで定義できない静的クラス メンバーは、完全修飾名を使用して 1 つのソース ファイル内で定義する必要があります。 それがまったく定義されていない場合、リンカーは LNK2019 を生成します。

### <a name="a-build-dependency-is-only-defined-as-a-project-dependency-in-the-solution"></a>ビルドの依存関係がソリューションにプロジェクトの依存関係としてのみ定義されています。

Visual Studio の以前のバージョンでは、このレベルの依存関係で十分でした。 ただし、Visual Studio 2010 以降では、Visual Studio が必要な[プロジェクト間参照](/visualstudio/ide/managing-references-in-a-project)です。 プロジェクトにプロジェクト間の参照がない場合は、このリンカー エラーが発生することがあります。 この問題を修正するには、プロジェクト間参照を追加します。

### <a name="you-build-a-console-application-by-using-settings-for-a-windows-application"></a>Windows アプリケーションの設定を使用して、コンソール アプリケーションをビルドします。

エラー メッセージがような場合**WinMain が関数で参照されている未解決の外部シンボル** *function_name*を使用してリンク **/SUBSYSTEM:CONSOLE** ではなく **/SUBSYSTEM:WINDOWS**です。 この設定の詳細と、Visual Studio でこのプロパティを設定する手順の詳細については、「 [/SUBSYSTEM (Specify Subsystem)](../../build/reference/subsystem-specify-subsystem.md)」を参照してください。

### <a name="you-attempt-to-link-64-bit-libraries-to-32-bit-code-or-32-bit-libraries-to-64-bit-code"></a>64 ビット ライブラリを 32 ビット コード、または 64 ビット コードを 32 ビット ライブラリにリンクしようとしています。

ライブラリと、コードにリンクされているオブジェクト ファイルは、コードと同じアーキテクチャをコンパイルする必要があります。 いることを確認、プロジェクトと同じアーキテクチャ向けのプロジェクト参照にコンパイルされたライブラリです。 確認、 [/LIBPATH](../../build/reference/libpath-additional-libpath.md)または**追加のライブラリ ディレクトリ**path オプションが適切なアーキテクチャ用に作成されたライブラリをリンカー ポイントによって使用されます。

### <a name="you-use-different-compiler-options-for-function-inlining-in-different-source-files"></a>異なるソース ファイルで関数のインライン展開を別のコンパイラ オプションを使用します。

.cpp ファイルで定義されている関数のインライン展開を使用している場合に、異なるソース ファイルで関数のインライン展開のコンパイラ オプションが混在していると、LNK2019 が発生することがあります。 詳細については、「 [Function Inlining Problems](../../error-messages/tool-errors/function-inlining-problems.md)」を参照してください。

### <a name="you-use-automatic-variables-outside-their-scope"></a>自動変数を使用して、そのスコープ外

自動変数 (関数スコープ) は、その関数のスコープ内でのみ使用できます。 これらの変数を `extern` として宣言して他のソース ファイルで使用することはできません。 例については、「 [Automatic (Function Scope) Variables](../../error-messages/tool-errors/automatic-function-scope-variables.md)」を参照してください。

### <a name="you-call-instrinsic-functions-or-pass-argument-types-to-intrinsic-functions-that-are-not-supported-on-your-target-architecture"></a>呼び出しているか、ターゲット アーキテクチャでサポートされていない組み込み関数に引数の型を渡す

たとえば、組み込関数 AVX2 を使用している場合に、 [/ARCH:AVX2](../../build/reference/arch-x86.md) コンパイラ オプションを指定しないと、コンパイラはこの組み込みを外部関数であると想定します。 コンパイラは、インライン命令を生成するのではなく、組み込みと同じ名前で外部シンボルへの呼び出しを生成します。 リンカーは、欠落しているこの関数の定義を検索しようとして、LNK2019 を生成します。 ターゲット アーキテクチャでサポートされている組み込み関数と型のみを使用していることを確認してください。

### <a name="you-mix-code-that-uses-native-wchart-with-code-that-doesnt"></a>ネイティブ wchar を使用するコードが混在する\_しないコードと t

Visual C++ 2005 で行われた C++ 言語への準拠作業により、 `wchar_t` は既定でネイティブ型になりました。 それより前のバージョンの Visual C++ を使用してコンパイルされたライブラリ ファイルおよびオブジェクト ファイルと互換性のあるコードを生成するには、 [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) コンパイラ オプションを使用する必要があります。 すべてのファイルは、同じを使用してコンパイルされている場合 **/Zc:wchar\_t**設定、型の参照が互換性のある型に解決されない場合があります。 すべてのライブラリ ファイルとオブジェクト ファイル内の `wchar_t` の型に互換性があることを検証し、使用する型を更新するか、コンパイル時に使用する **/Zc:wchar_t** の設定を一貫させるようにしてください。

## <a name="third-party-library-issues-and-vcpkg"></a>サード パーティ製のライブラリの問題と Vcpkg

ビルドの一部として、サード パーティ製ライブラリを構成しようとしているときにこのエラーが発生する場合は、使用を検討して[Vcpkg](../../vcpkg.md)Visual C のパッケージ マネージャーをインストールしてから、ライブラリを作成します。 Vcpkg サポートされている大規模なおよび成長[サード パーティ製のライブラリの一覧](https://github.com/Microsoft/vcpkg/tree/master/ports)、およびすべての構成プロパティと、プロジェクトの一部として、成功したビルドの必要な依存関係を設定します。 詳細については、関連するを参照してください[Visual C ブログ](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/)を投稿します。

## <a name="diagnosis-tools"></a>診断ツール

リンカーが特定のシンボル定義を見つけられない理由を調べるのは難しい問題になることがあります。 多くの場合、問題は、ビルド定義を含むコードが含まれていない、またはビルド オプションを別に作成した装飾の外部シンボル名のことです。 LNK2019 エラーを診断するために役立ついくつかのツールとオプションを紹介します。

- [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) リンカー オプションを使用すると、リンカーがどのファイルを参照しているかを判断できます。 これは、シンボルの定義の入ったファイルがビルドに含まれているかどうかを確認するために役立ちます。

- [/Exports](../../build/reference/dash-exports.md)と[/symbols](../../build/reference/symbols.md)のオプション、 **DUMPBIN**ユーティリティを使用して、どのシンボルが、.dll やオブジェクト ファイルまたはライブラリ ファイルで定義されているを発見できます。 エクスポートされた装飾名が、リンカーが検索する装飾名と一致することを確認してください。

- **UNDNAME**ユーティリティことができますが、同等装飾されていない外部シンボルを表示、装飾名です。

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

ここでは、別の例として、変数と関数が宣言されている`extern`定義が指定されていません。

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

しない限り、`i`と`g`定義はビルドに含まれるファイルの 1 つは、リンカーは LNK2019 を生成します。 このエラーを修正するには、定義を含むソース コード ファイルをコンパイルの一部に組み込みます。 また、.obj ファイルまたは .lib ファイルをリンカーに定義が含まれているを渡すことができます。

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

### <a name="inconsistent-wchart-type-definitions"></a>一貫性のない wchar_t 型の定義

このサンプルを使用しているエクスポートを持つ DLL の作成`WCHAR`に解決されます`wchar_t`です。

```cpp
// LNK2019g.cpp
// compile with: cl /EHsc /LD LNK2019g.cpp
#include "windows.h"
// WCHAR resolves to wchar_t
__declspec(dllexport) void func(WCHAR*) {}
```

次の例は、前の例で、DLL を使用し、型 unsigned short * と WCHAR ために、LNK2019 を生成\*が一致しません。

```cpp
// LNK2019h.cpp
// compile by using: cl /EHsc LNK2019h LNK2019g.lib
// LNK2019 expected
__declspec(dllimport) void func(unsigned short*);

int main() {
   func(0);
}
```

 このエラーを解決するには、次のように変更します。`unsigned short`に`wchar_t`または`WCHAR`、を使用して、LNK2019g.cpp をコンパイルまたは **/Zc:wchar_t-** です。

## <a name="additional-resources"></a>その他の技術情報

LNK2001 の考えられる原因および解決方法に関する詳細については、スタック オーバーフローの質問を参照してください。 [、未定義の参照/未解決外部シンボルというエラーと、その修正方法?](http://stackoverflow.com/q/12573816/2002113)です。

