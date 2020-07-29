---
title: C++ Core ガイドライン チェッカーの使用
ms.date: 08/14/2018
ms.topic: conceptual
dev_langs:
- CPP
ms.openlocfilehash: 9c36c17e819e954d66833f059fe794ac14898e75
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227726"
---
# <a name="use-the-c-core-guidelines-checkers"></a>C++ Core ガイドライン チェッカーの使用

C++ Core Guidelines は、C++ の専門家とデザイナーによって作成された C++ のコーディングに関するガイドライン、規則、およびベストプラクティスの移植可能なセットです。 現在、Visual Studio では、C++ 用のコード分析ツールの一部として、これらのルールのサブセットをサポートしています。 コアガイドラインチェッカーは、visual Studio 2017 および Visual Studio 2019 に既定でインストールされ、 [Visual studio 2015 の NuGet パッケージとして入手でき](#vs2015_corecheck)ます。

## <a name="the-c-core-guidelines-project"></a>C++ Core Guidelines プロジェクト

Bjarne Stroustrup などによって作成された C++ Core Guidelines は、最新の C++ を安全かつ効果的に使用するためのガイドです。 このガイドラインでは、静的なタイプセーフとリソースの安全性を重視しています。 これらの例では、言語のエラーが発生しやすい部分を排除または最小化する方法を示し、信頼性の高い方法でコードをより簡単かつ効率的にする方法を提案します。 これらのガイドラインは、標準 C++ Foundation によって管理されています。 詳細については、ドキュメントを参照し、 [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)して、 [GitHub](https://github.com/isocpp/CppCoreGuidelines)の C++ Core Guidelines ドキュメントプロジェクトファイルにアクセスしてください。

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>コード分析での C++ Core Check ガイドラインの有効化

プロジェクトのコード分析を有効にするには、プロジェクトの [**プロパティページ**] ダイアログの [**コード分析**] セクションで [**ビルド時にコード分析を有効にする**] チェックボックスをオンにします。

![コード分析の全般設定のプロパティページ](media/cppcorecheck_codeanalysis_general.png)

コード分析を有効にしたときに既定で実行される Microsoft ネイティブ推奨規則セットには、C++ Core Check の規則のサブセットが含まれています。 追加のコアチェック規則を有効にするには、ドロップダウンをクリックし、含める規則セットを選択します。

![追加の C++ Core Check ルールセットのドロップダウン](media/cppcorecheck_codeanalysis_extensions.png)

## <a name="examples"></a>例

C++ Core Check の規則によって検出される可能性のあるいくつかの問題の例を次に示します。

```cpp
// CoreCheckExample.cpp
// Add CppCoreCheck package and enable code analysis in build for warnings.

int main()
{
    int arr[10];           // warning C26494
    int* p = arr;          // warning C26485

    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
    {
        int* q = p + 1;    // warning C26481 (suppressed)
        p = q++;           // warning C26481 (suppressed)
    }

    return 0;
}
```

この例では、C++ Core Check の規則で検出できる警告のいくつかを示します。

- C26494 は rule 型です。 5: 常にオブジェクトを初期化します。

- C26485 はルールの境界です。 3: 配列からポインターへの減衰がありません。

- C26481 は rule Bounds です。 1: ポインター演算は使用しないでください。 代わりに `span` を使用してください

このコードをコンパイルするときに C++ Core Check コード分析のルールセットがインストールされ、有効になっている場合、最初の2つの警告が出力されますが、3番目の警告は抑制されます。 コード例のビルド出力を次に示します。

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C++ Core Guidelines は、より適切で安全なコードを記述するのに役立ちます。 ただし、ルールまたはプロファイルを適用できないインスタンスがある場合は、コード内で直接非表示にするのが簡単です。 属性を使用すると、 `gsl::suppress` 次のコードブロックの規則違反を検出して報告することが C++ Core Check によって防止されます。 個々のステートメントをマークして、特定のルールを抑制することができます。 `[[gsl::suppress(bounds)]]`特定の規則番号を含めずに、境界プロファイル全体を作成して抑制することもできます。

## <a name="supported-rule-sets"></a>サポートされている規則セット

新しいルールが C++ Core Guidelines チェッカーに追加されると、既存のコードに対して生成される警告の数が増加する可能性があります。 定義済みの規則セットを使用して、有効にする規則の種類をフィルター処理できます。
ほとんどの規則のリファレンストピックは、「 [Visual Studio C++ Core Check リファレンス](code-analysis-for-cpp-corecheck.md)」にあります。

Visual Studio 2017 バージョン15.3 の場合、サポートされている規則セットは次のとおりです。

- **所有者ポインター**の規則[ \<T> は、C++ Core Guidelines の所有者に関連するリソース管理のチェック](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)を適用します。

- **Const ルール**[は、C++ Core Guidelines から定数に関連したチェックを](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)適用します。

- **生のポインターの規則**[は、C++ Core Guidelines からの生のポインターに関連するリソース管理のチェックを](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)適用します。

- **一意のポインター規則**[は、C++ Core Guidelines から一意のポインターセマンティクスを持つ型に関連するリソース管理チェックを](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)適用します。

- **境界ルール**により[、C++ Core Guidelines の境界プロファイル](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)が適用されます。

- **型ルール**に[よって、C++ Core Guidelines の種類のプロファイル](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)が適用されます。

**Visual Studio 2017 バージョン 15.5**:

- **クラスの規則**特殊なメンバー関数と仮想仕様の適切な使用に焦点を当てるいくつかのルール。 これは、[クラスおよびクラス階層](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class)で推奨されるチェックのサブセットです。
- **同時実行ルール**1つの規則。正しく宣言されていないガードオブジェクトをキャッチします。 詳細については、「[同時実行に関するガイドライン](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency)」を参照してください。
- **宣言の規則**グローバル変数の宣言方法に焦点を当てた、[インターフェイスガイドライン](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces)のいくつかの規則。
- **関数の規則**指定子の導入に役立つ2つのチェック **`noexcept`** 。 これは、[関数の設計と実装を明確](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions)にするためのガイドラインの一部です。
- **共有ポインターの規則**[リソース管理](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource)ガイドラインの適用の一環として、共有ポインターが関数に渡されるかローカルで使用される方法に固有のいくつかの規則が追加されました。
- **スタイルルール**1つの単純だが重要なチェック。 [goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto)の使用を禁止します。 これは、C++ でコーディングスタイルと式およびステートメントの使用を改善するための最初の手順です。

**Visual Studio 2017 バージョン 15.6**:

- **算術ルール**算術[オーバーフロー](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow)、[署名符号なし操作](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned)、および[ビット操作](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative)を検出するルール。

警告を1つまたは複数のグループに制限することを選択できます。 **ネイティブの最小**および**ネイティブで推奨される**規則セットには、他の PREfast チェックに加えて、C++ Core Check の規則が含まれています。 使用可能な規則セットを表示するには、[プロジェクトのプロパティ] ダイアログボックスを開き、[**コード分析**] を選択し、[**規則セット**] コンボボックスでドロップダウンを開き、 **[複数の規則セットを選択**します] を選択します。 Visual Studio での規則セットの使用の詳細については、「[規則セットを使用して実行する C++ 規則を指定する](using-rule-sets-to-specify-the-cpp-rules-to-run.md)」を参照してください。

## <a name="macros"></a>[マクロ]

C++ Core Guidelines チェッカーには、コード内の警告のカテゴリ全体を簡単に抑制できるようにするマクロを定義するヘッダーファイルが付属しています。

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

これらのマクロは、ルールセットに対応し、警告番号のスペース区切りの一覧に展開されます。 適切なプラグマコンストラクトを使用すると、プロジェクトまたはコードのセクションにとって興味深いルールの有効なセットを構成できます。 次の例では、コード分析によって、不足している定数修飾子のみが警告されます。

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>属性

Microsoft C++ コンパイラでは、GSL 抑制属性が制限付きでサポートされています。 関数内の expression ステートメントおよび block ステートメントの警告を抑制するために使用できます。

```cpp
// Suppress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Suppress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{
    new int;
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```

## <a name="suppress-analysis-by-using-command-line-options"></a>コマンドラインオプションを使用した分析の抑制

#Pragmas の代わりに、ファイルの [プロパティ] ページのコマンドラインオプションを使用して、プロジェクトまたは1つのファイルの警告を非表示にすることができます。 たとえば、ファイルの警告 C26400 を無効にするには、次のようにします。

1. でファイルを右クリックし**ソリューションエクスプローラー**

1. [プロパティ] を選択します。 **C/C + + |コマンドライン**

1. [**追加オプション**] ウィンドウで、を追加 `/wd26400` します。

コマンドラインオプションを使用すると、を指定することによって、ファイルのすべてのコード分析を一時的に無効にすることができ `/analyze-` ます。 これ*により、'/analyze ' を '/analyze e-' でオーバーライド*する警告 D9025 が生成されます。これにより、後でコード分析を再度有効にするように通知されます。

## <a name="enable-the-c-core-guidelines-checker-on-specific-project-files"></a><a name="corecheck_per_file"></a>特定のプロジェクトファイルで C++ Core Guidelines チェックを有効にする

場合によっては、フォーカスのあるコード分析を行っても、Visual Studio IDE を使用すると便利な場合があります。 次のサンプルシナリオは、大規模なプロジェクトでビルド時間を節約し、結果を簡単にフィルター処理できるようにするために使用できます。

1. コマンドシェルで、 `esp.extension` `esp.annotationbuildlevel` 環境変数と環境変数を設定します。
1. これらの変数を継承するには、コマンドシェルから Visual Studio を開きます。
1. プロジェクトを読み込み、そのプロパティを開きます。
1. コード分析を有効にし、適切な規則セットを選択します。ただし、コード分析の拡張機能は有効にしません。
1. C++ Core Guidelines チェッカーを使用して分析するファイルにアクセスし、そのプロパティを開きます。
1. [ **C/c + +] \ (コマンドラインオプション \** ) を選択して追加`/analyze:plugin EspXEngine.dll`
1. プリコンパイル済みヘッダーの使用を無効にします (**C/c + + プリコンパイル済みヘッダー**)。 この操作が必要になるのは、拡張エンジンがプリコンパイル済みヘッダー (PCH) から内部情報を読み取ろうとする可能性があるためです。PCH が既定のプロジェクトオプションでコンパイルされた場合は、互換性がありません。
1. プロジェクトをリビルドします。 共通の PREFast チェックはすべてのファイルで実行する必要があります。 C++ Core Guidelines チェッカーは既定では有効になっていないため、このチェックを使用するように構成されているファイルでのみ実行する必要があります。

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>Visual Studio の外部で C++ Core Guidelines チェッカーを使用する方法

自動ビルドの C++ Core Guidelines チェックを使用できます。

### <a name="msbuild"></a>MSBuild

ネイティブコード分析チェッカー (PREfast) は、カスタムターゲットファイルによって MSBuild 環境に統合されています。 プロジェクトのプロパティを使用して有効にし、C++ Core Guidelines チェッカー (PREfast に基づく) を追加することができます。

```xml
  <PropertyGroup>
    <EnableCppCoreCheck>true</EnableCppCoreCheck>
    <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>
    <RunCodeAnalysis>true</RunCodeAnalysis>
  </PropertyGroup>
```

これらのプロパティは、必ず、Microsoft .Cpp. .targets ファイルをインポートする前に追加してください。 特定の規則セットを選択するか、カスタム規則セットを作成するか、他の PREfast チェックを含む既定の規則セットを使用することができます。

[前に説明](#corecheck_per_file)したのと同じ方法を使用して、指定したファイルに対してのみ C++ Core Checker を実行できますが、MSBuild ファイルを使用します。 環境変数は、次の項目を使用して設定でき `BuildMacro` ます。

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>CppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

プロジェクトファイルを変更しない場合は、コマンドラインで次のようにプロパティを渡すことができます。

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>MSBuild 以外のプロジェクト

MSBuild に依存しないビルドシステムを使用する場合でも、このチェックを実行できますが、コード分析エンジンの構成の一部について理解しておく必要があります。 これらの内部構造は、今後サポートされるとは限りません。

いくつかの環境変数を設定し、コンパイラに適切なコマンドラインオプションを使用する必要があります。 "ネイティブツールコマンドプロンプト" 環境で作業することをお勧めします。これにより、コンパイラの特定のパス、インクルードディレクトリなどを検索する必要がなくなります。

- **環境変数**
  - `set esp.extensions=cppcorecheck.dll`これは、C++ Core Guidelines モジュールを読み込むようにエンジンに指示します。
  - `set esp.annotationbuildlevel=ignore`これにより、SAL 注釈を処理するロジックが無効になります。 注釈は C++ Core Guidelines チェッカーのコード分析には影響しませんが、処理には時間がかかります (時間がかかることがあります)。 この設定は省略可能ですが、強くお勧めします。
  - `set caexcludepath=%include%`標準ヘッダーで起動する警告を無効にすることを強くお勧めします。 ここでは、プロジェクトの共通ヘッダーへのパスなど、さらにパスを追加できます。

- **コマンドラインオプション**
  - `/analyze`コード分析を有効にします (/analyze: only と/analyze: quiet も使用することを検討してください)。
  - `/analyze:plugin EspXEngine.dll`このオプションは、PREfast にコード分析拡張エンジンを読み込みます。 次に、このエンジンは C++ Core Guidelines チェッカーを読み込みます。

## <a name="use-the-guideline-support-library"></a>ガイドラインサポートライブラリを使用する

ガイドラインサポートライブラリは、主要なガイドラインに従うことができるように設計されています。 GSL には、エラーが発生しやすい構造を代替として置き換えることができる定義が含まれています。 たとえば、 `T*, length` パラメーターのペアを型に置き換えることができ `span<T>` ます。 GSL はで入手でき [http://www.nuget.org/packages/Microsoft.Gsl](https://www.nuget.org/packages/Microsoft.Gsl) ます。 ライブラリはオープンソースであるため、ソースの表示、コメントの作成、または投稿を行うことができます。 プロジェクトはにあり [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) ます。

## <a name="use-the-c-core-check-guidelines-in-visual-studio-2015-projects"></a><a name="vs2015_corecheck"></a>Visual Studio 2015 プロジェクトの C++ Core Check ガイドラインを使用する

Visual Studio 2015 を使用する場合、C++ Core Check コード分析規則セットは既定ではインストールされません。 Visual Studio 2015 の C++ Core Check コード分析ツールを有効にするには、いくつかの追加の手順を実行する必要があります。 Microsoft では、Nuget パッケージを使用して Visual Studio 2015 プロジェクトのサポートを提供しています。 パッケージは CppCoreCheck という名前で、で入手でき [http://www.nuget.org/packages/Microsoft.CppCoreCheck](https://www.nuget.org/packages/Microsoft.CppCoreCheck) ます。 このパッケージには、少なくとも Visual Studio 2015 with Update 1 がインストールされている必要があります。

また、パッケージは、ヘッダーのみのガイドラインサポートライブラリ (GSL) である依存関係として別のパッケージをインストールします。 GSL は、GitHub のでも参照でき [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) ます。

コード分析規則の読み込み方法によっては、Visual Studio 2015 内で確認する各 C++ プロジェクトに CppCoreCheck NuGet パッケージをインストールする必要があります。

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Visual Studio 2015 でプロジェクトに CppCoreCheck パッケージを追加するには

1. **ソリューションエクスプローラー**で、右クリックして、パッケージを追加するソリューション内のプロジェクトのコンテキストメニューを開きます。 [ **Nuget**パッケージの管理] を選択して、 **nuget パッケージマネージャー**を開きます。

1. [ **NuGet パッケージマネージャー** ] ウィンドウで、CppCoreCheck を検索します。

    ![Nuget パッケージマネージャーウィンドウに CppCoreCheck パッケージが表示されます](../code-quality/media/cppcorecheck_nuget_window.png)

1. CppCoreCheck パッケージを選択し、[**インストール**] をクリックして、プロジェクトに規則を追加します。

   NuGet パッケージは、プロジェクトに対してコード分析を有効にしたときに呼び出される追加の MSBuild *. .targets*ファイルをプロジェクトに追加します。 この *.targets*ファイルは、Visual Studio コード分析ツールに追加の拡張機能として C++ Core Check 規則を追加します。 パッケージがインストールされている場合は、[プロパティページ] ダイアログボックスを使用して、リリースおよび試験的な規則を有効または無効にすることができます。

## <a name="see-also"></a>関連項目

- [Visual Studio C++ Core Check リファレンス](code-analysis-for-cpp-corecheck.md)
