---
title: C++ Core ガイドライン チェッカーの使用
description: C++ Core Guidelines 用に Microsoft C++ コード分析規則を設定して使用する方法。
ms.date: 12/16/2020
ms.topic: conceptual
dev_langs:
- CPP
ms.openlocfilehash: 93b69839bc9e5ffd45a08da12e84028eea10aef4
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645164"
---
# <a name="use-the-c-core-guidelines-checkers"></a>C++ Core ガイドライン チェッカーの使用

C++ Core Guidelines は、C++ の専門家とデザイナーによって作成された C++ のコーディングに関するガイドライン、規則、およびベストプラクティスの移植可能なセットです。 現在、Visual Studio では、C++ 用のコード分析ツールの一部として、これらのルールのサブセットをサポートしています。 コアガイドラインチェッカーは、Visual Studio 2017 および Visual Studio 2019 に既定でインストールされます。 これら [は、Visual Studio 2015 の NuGet パッケージとして提供](#vs2015_corecheck)されています。

## <a name="the-c-core-guidelines-project"></a>C++ Core Guidelines プロジェクト

Bjarne Stroustrup などによって作成された C++ Core Guidelines は、最新の C++ を安全かつ効果的に使用するためのガイドです。 このガイドラインでは、静的なタイプセーフとリソースの安全性を重視しています。 これらは、言語のエラーが発生しやすい部分を排除または最小化する方法を識別します。 また、コードを単純化し、信頼性が高く、パフォーマンスを向上させる方法についても説明します。 これらのガイドラインは、標準 C++ Foundation によって管理されています。 詳細については、ドキュメントを参照し、 [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)して、 [GitHub](https://github.com/isocpp/CppCoreGuidelines)の C++ Core Guidelines ドキュメントプロジェクトファイルにアクセスしてください。

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>コード分析での C++ Core Check ガイドラインの有効化

::: moniker range="<=msvc-150"

Microsoft ネイティブ推奨規則セットには、C++ Core Check の規則のサブセットが含まれています。 これは、コード分析が有効になっている場合に既定で実行されるルールセットです。

### <a name="to-enable-code-analysis-on-your-project"></a>プロジェクトでコード分析を有効にするには

1. プロジェクトの [  **プロパティページ** ] ダイアログを開きます。

1. [ **構成プロパティ**] [ > **コード分析** ] プロパティページを選択します。

1. [ **ビルド時にコード分析を有効にする** ] チェックボックスをオンにします。

![コード分析の全般設定のプロパティページ](media/cppcorecheck_codeanalysis_general.png)

追加のコアチェック規則を有効にするには、ドロップダウンリストを開き、含める規則セットを選択します。

![追加の C++ Core Check ルールセットのドロップダウン](media/cppcorecheck_codeanalysis_extensions.png)

::: moniker-end
::: moniker range=">=msvc-160"

Microsoft ネイティブ推奨規則セットには、C++ Core Check の規則のサブセットが含まれています。 Microsoft コード分析が有効になっている場合、既定で実行されるルールセットです。

### <a name="to-enable-code-analysis-on-your-project"></a>プロジェクトでコード分析を有効にするには、次のようにします。

1. プロジェクトの [  **プロパティページ** ] ダイアログを開きます。

1. [ **構成プロパティ**] [ > **コード分析** ] プロパティページを選択します。

1. **[ビルドのためのコード分析を有効** にし、 **Microsoft コード分析** のプロパティを有効にする] を設定します。

また、サポートされているすべての C++ Core Check 規則を実行するか、独自のサブセットを選択して実行することもできます。

### <a name="to-enable-additional-core-check-rules"></a>追加のコアチェックルールを有効にするには

1. プロジェクトの [  **プロパティページ** ] ダイアログを開きます。

1. [ **構成プロパティ**] [ > **コード分析**] [ > **Microsoft** プロパティ] ページを選択します。

1. [ **アクティブな規則** ] ドロップダウンリストを開き、[ **複数の規則セットを選択** する] を選択します。

1. [ **規則セットの追加または削除** ] ダイアログで、含める規則セットを選択します。

::: moniker-end

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

- C26481 は rule Bounds です。 1: ポインター演算は使用しないでください。 代わりに、`span` を使用してください。

C++ Core Check コード分析のルールセットをインストールして有効にし、このコードをコンパイルします。 コード分析では、最初の2つの警告が出力され、3番目の警告は表示されません。 Visual Studio 2015 のコード例のビルド出力を次に示します。

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C++ Core Guidelines は、より適切で安全なコードを記述するのに役立ちます。 ただし、ルールまたはプロファイルを適用できないインスタンスが見つかる場合があります。 コード内で直接非表示にするのは簡単です。 属性を使用すると、 `[[gsl::suppress]]` 次のコードブロックの規則違反を検出して報告することが C++ Core Check によって防止されます。 個々のステートメントをマークして、特定のルールを抑制することができます。 `[[gsl::suppress(bounds)]]`特定の規則番号を含めずに、境界プロファイル全体を作成して抑制することもできます。

## <a name="supported-rule-sets"></a>サポートされている規則セット

新しいルールが C++ Core Guidelines チェッカーに追加されると、既存のコードに対して生成される警告の数が増加する可能性があります。 定義済みの規則セットを使用して、有効にする規則の種類をフィルター処理できます。 ほとんどのルールのリファレンス記事については、「 [Visual Studio C++ Core Check リファレンス](code-analysis-for-cpp-corecheck.md)」を参照してください。

- **算術ルール**: 算術 [オーバーフロー](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow)、署名されていない [操作](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned)、および [ビット操作](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative)を検出するルール。<sup>15.6</sup>

- **境界ルール**: [C++ Core Guidelines の境界プロファイル](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)を適用します。<sup>15.3</sup>

- **クラスの規則**: 特殊なメンバー関数と仮想仕様の適切な使用に焦点を当てるいくつかの規則。 これらは、 [クラスおよびクラス階層](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class)で推奨されているチェックのサブセットです。<sup>15.5</sup>

- **同時実行規則**: 無効なガードオブジェクトの宣言をキャッチする単一の規則。 詳細については、「 [同時実行に関するガイドライン](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency)」を参照してください。<sup>15.5</sup>

- **Const Rules**: [C++ Core Guidelines から const 関連のチェックを](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)適用します。<sup>15.3</sup>

- **宣言規則**: グローバル変数の宣言方法に重点を置いた、 [インターフェイスガイドライン](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces) のいくつかの規則。<sup>15.5</sup>

- **列挙規則**: これらの規則は [、C++ Core Guidelines からの列挙型関連のチェックを](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-enum)適用します。<sup>16.3</sup>

- **試験** 的な規則これらは試験的な C++ Core Check ルールであり、日常的に使用するのに便利ですが、準備はできません。 試してみて、フィードバックをお [寄せ](https://aka.ms/feedback/suggest?space=62)ください。<sup>16.0</sup>

- **関数の規則**: 指定子の導入に役立つ2つのチェックを行い **`noexcept`** ます。 これらは、 [関数の設計と実装を明確](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions)にするためのガイドラインに含まれています。<sup>15.5</sup>

- **Gsl ルール**: これらのルールは [、C++ Core Guidelines のガイドラインサポートライブラリ](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-gsl)に関連するチェックを適用します。<sup>15.7</sup>

- **有効期間ルール**: これらのルールにより [、C++ Core Guidelines の有効期間プロファイル](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prolifetime-lifetime-safety-profile)が適用されます。<sup>15.7</sup>

- **所有者ポインターの規則**: [ \<T> C++ Core Guidelines の所有者に関連するリソース管理のチェック](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)を適用します。<sup>15.3</sup>

- **生のポインターの規則**: [C++ Core Guidelines からの生のポインターに関連するリソース管理のチェックを](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)適用します。<sup>15.3</sup>

- **共有ポインターの規則**: [リソース管理](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource) ガイドラインの適用の一部です。<sup>15.5</sup> 共有ポインターを関数に渡す方法またはローカルで使用する方法に固有の規則をいくつか追加しました。

- **Stl 規則**: これらの規則は [、C++ Core Guidelines からの C++ 標準ライブラリ (STL)](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-stdlib)に関連するチェックを適用します。<sup>15.7</sup>

- **スタイルルール**: 1 つの単純ですが重要なチェックで、 [goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto)は使用できません。<sup>15.5</sup> C++ でのコーディングスタイルと式およびステートメントの使用を改善するための最初の手順です。

- **型ルール**: [C++ Core Guidelines の型プロファイル](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)を適用します。<sup>15.3</sup>

- **一意のポインターの規則**: [C++ Core Guidelines からの一意のポインターセマンティクスを持つ型に関連するリソース管理チェックを](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)適用します。<sup>15.3</sup>

- **C++ Core Check の規則**: この規則セットは、試験的な規則を除き、 [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c-core-guidelines)から現在実装されているすべてのチェックを含みます。

<sup>15.3</sup> Visual Studio 2017 バージョン 15.3 \ でこれらのルールが最初に表示される
<sup>15.5</sup> Visual Studio 2017 バージョン 15.5 \ でこれらのルールが最初に表示される
<sup>15.6</sup> Visual Studio 2017 バージョン 15.6 \ でこれらのルールが最初に表示される
<sup>15.7</sup> Visual Studio 2017 バージョン 15.7 \ でこれらのルールが最初に表示される
<sup>16.0</sup> Visual Studio 2019 バージョン 16.0 \ でこれらのルールが最初に表示される
<sup>16.3</sup> Visual Studio 2019 バージョン16.3 でこれらのルールが最初に表示される

警告を1つまたは複数のグループに制限することを選択できます。 **ネイティブの最小** および **ネイティブで推奨される** 規則セットには C++ Core Check 規則やその他の PREfast チェックが含まれます。

::: moniker range="<=msvc-150"

使用可能な規則セットを表示するには、[ **プロジェクトのプロパティ** ] ダイアログを開きます。 [**プロパティページ**] ダイアログボックスで、[**構成プロパティ**] [  >  **コード分析**]  >  **[全般**] プロパティページを選択します。 次に、[ **ルールセット** ] コンボボックスのドロップダウンを開いて、使用可能なルールセットを表示します。 規則セットのカスタム組み合わせを作成するには、[ **複数の規則セットを選択** する] を選択します。 [ **規則セットの追加または削除** ] ダイアログボックスには、選択できる規則が一覧表示されます。 Visual Studio での規則セットの使用の詳細については、「 [規則セットを使用して実行する C++ 規則を指定する](using-rule-sets-to-specify-the-cpp-rules-to-run.md)」を参照してください。

::: moniker-end
::: moniker range=">=msvc-160"

使用可能な規則セットを表示するには、[ **プロジェクトのプロパティ** ] ダイアログを開きます。 [**プロパティページ**] ダイアログボックスで、[**構成プロパティ**] [  >  **コード分析**] [  >  **Microsoft** ] プロパティページを選択します。 次に、[ **アクティブな規則** ] コンボボックスのドロップダウンを開いて、使用可能な規則セットを表示します。 規則セットのカスタム組み合わせを作成するには、[ **複数の規則セットを選択** する] を選択します。 [ **規則セットの追加または削除** ] ダイアログボックスには、選択できる規則が一覧表示されます。 Visual Studio での規則セットの使用の詳細については、「 [規則セットを使用して実行する C++ 規則を指定する](using-rule-sets-to-specify-the-cpp-rules-to-run.md)」を参照してください。

::: moniker-end

## <a name="macros"></a>マクロ

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

Microsoft C++ コンパイラでは、属性のサポートが制限されてい `[[gsl::suppress]]` ます。 関数内の expression ステートメントおよび block ステートメントの警告を抑制するために使用できます。

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

1. **ソリューションエクスプローラー** でファイルを右クリックし、[**プロパティ**] を選択します。

1. [**プロパティページ**] ダイアログボックスで、[**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **追加オプション** ] の [追加] を選択 *`/wd26400`* します。

コマンドラインオプションを使用すると、を指定することによって、ファイルのすべてのコード分析を一時的に無効にすることができ **`/analyze-`** ます。 " */Analyze" を '/analyze e-' にオーバーライド* する警告 D9025 が表示されます。これにより、後でコード分析を再度有効にするように通知されます。

## <a name="enable-the-c-core-guidelines-checker-on-specific-project-files"></a><a name="corecheck_per_file"></a> 特定のプロジェクトファイルで C++ Core Guidelines チェックを有効にする

場合によっては、フォーカスのあるコード分析を行っても、Visual Studio IDE を使用すると便利です。 大規模なプロジェクトでは、次のサンプルシナリオを試してみてください。 ビルド時間を節約し、結果のフィルター処理を簡単に行うことができます。

1. コマンドシェルで、 `esp.extension` `esp.annotationbuildlevel` 環境変数と環境変数を設定します。

1. これらの変数を継承するには、コマンドシェルから Visual Studio を開きます。

1. プロジェクトを読み込み、そのプロパティを開きます。

1. コード分析を有効にし、適切な規則セットを選択しますが、コード分析拡張を有効にしないでください。

1. C++ Core Guidelines チェッカーを使用して分析するファイルにアクセスし、そのプロパティを開きます。

1. [**構成プロパティ**]、[  >  **c/c + +**]、[追加オプション] の順に選択  >    >  して追加します。*`/analyze:plugin EspXEngine.dll`*

1. プリコンパイル済みヘッダーの使用を無効にします (**構成プロパティ**  >  **C/c + +**  >  **プリコンパイル済みヘッダー**)。 拡張エンジンがプリコンパイル済みヘッダー (PCH) から内部情報を読み取ろうとする可能性があるため、これが必要になります。 PCH が既定のプロジェクトオプションを使用してコンパイルされた場合は、互換性がありません。

1. プロジェクトをリビルドします。 共通の PREFast チェックはすべてのファイルで実行する必要があります。 C++ Core Guidelines チェッカーは既定では有効になっていないため、これを使用するように構成されているファイルでのみ実行する必要があります。

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

ファイルをインポートする前に、これらのプロパティを必ず追加してください *`Microsoft.Cpp.targets`* 。 特定の規則セットを選択するか、カスタム規則セットを作成することができます。 または、他の PREfast チェックを含む既定の規則セットを使用します。

C++ Core Checker は、指定したファイルに対してのみ実行できます。 [前に説明](#corecheck_per_file)したのと同じアプローチを使用しますが、MSBuild ファイルを使用します。 環境変数は、次の項目を使用して設定でき `BuildMacro` ます。

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

MSBuild に依存しないビルドシステムを使用する場合でも、チェックを実行できます。 これを使用するには、コード分析エンジンの構成の一部について理解しておく必要があります。 今後のバージョンの Visual Studio では、これらの内部構造のサポートは保証されません。

コード分析には、いくつかの環境変数とコンパイラのコマンドラインオプションが必要です。 **ネイティブツールのコマンドプロンプト** 環境を使用することをお勧めします。これにより、コンパイラの特定のパスを検索したり、ディレクトリを含めたりする必要がなくなります。

- **環境変数**
  - `set esp.extensions=cppcorecheck.dll` これは、C++ Core Guidelines モジュールを読み込むようにエンジンに指示します。
  - `set esp.annotationbuildlevel=ignore` これにより、SAL 注釈を処理するロジックが無効になります。 注釈は C++ Core Guidelines チェッカーのコード分析には影響しませんが、処理には時間がかかります (時間がかかることがあります)。 この設定は省略可能ですが、強くお勧めします。
  - `set caexcludepath=%include%` 標準ヘッダーで発生する警告を無効にすることを強くお勧めします。 ここでは、プロジェクトの共通ヘッダーへのパスなど、さらにパスを追加できます。

- **コマンド ライン オプション**
  - **`/analyze`**  コード分析を有効にします (とも使用することを検討してください **`/analyze:only`** **`/analyze:quiet`** )。
  - **`/analyze:plugin EspXEngine.dll`** このオプションは、PREfast にコード分析拡張エンジンを読み込みます。 次に、このエンジンは C++ Core Guidelines チェッカーを読み込みます。

## <a name="use-the-guideline-support-library"></a>ガイドラインサポートライブラリを使用する

ガイドラインサポートライブラリ (GSL) は、中核となるガイドラインに従うように設計されています。 GSL には、エラーが発生しやすい構造を代替として置き換えることができる定義が含まれています。 たとえば、 `T*, length` パラメーターのペアを型に置き換えることができ `span<T>` ます。 GSL プロジェクトは、GitHub ので入手でき [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) ます。 ライブラリはオープンソースであるため、ソースの表示、コメントの作成、または投稿を行うことができます。 [Vcpkg](../build/vcpkg.md) package manager を使用して、ライブラリをローカルにダウンロードしてインストールすることもできます。

::: moniker range="msvc-140"

## <a name="use-the-c-core-check-guidelines-in-visual-studio-2015-projects"></a><a name="vs2015_corecheck"></a> Visual Studio 2015 プロジェクトの C++ Core Check ガイドラインを使用する

Visual Studio 2015 を使用する場合、C++ Core Check コード分析規則セットは既定ではインストールされません。 Visual Studio 2015 で C++ Core Check コード分析ツールを有効にするには、追加の手順が必要です。 Microsoft では、NuGet パッケージを使用して Visual Studio 2015 プロジェクトのサポートを提供しています。 パッケージは CppCoreCheck という名前で、で入手でき [http://www.nuget.org/packages/Microsoft.CppCoreCheck](https://www.nuget.org/packages/Microsoft.CppCoreCheck) ます。 このパッケージには、少なくとも Visual Studio 2015 with Update 1 がインストールされている必要があります。

パッケージでは、別のパッケージも依存関係として、ヘッダーのみのガイドラインサポートライブラリ (GSL) としてインストールされます。 GSL は、GitHub のでも参照でき [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) ます。

コード分析規則が Visual Studio 2015 内で読み込まれる方法により、 `Microsoft.CppCoreCheck` 確認する各 C++ プロジェクトに NuGet パッケージをインストールする必要があります。

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Visual Studio 2015 でプロジェクトに CppCoreCheck パッケージを追加するには

1. **ソリューションエクスプローラー** で、右クリックして、パッケージを追加するソリューション内のプロジェクトのコンテキストメニューを開きます。 [ **Nuget** パッケージの管理] を選択して、 **nuget パッケージマネージャー** を開きます。

1. [ **NuGet パッケージマネージャー** ] ウィンドウで、CppCoreCheck を検索します。

    ![Nuget パッケージマネージャーウィンドウに CppCoreCheck パッケージが表示されます](../code-quality/media/cppcorecheck_nuget_window.png)

1. CppCoreCheck パッケージを選択し、[ **インストール** ] をクリックして、プロジェクトに規則を追加します。

   NuGet パッケージは、 *`.targets`* プロジェクトに対してコード分析を有効にしたときに呼び出される追加の MSBuild ファイルをプロジェクトに追加します。 このファイルにより、 *`.targets`* C++ Core Check の規則が Visual Studio コード分析ツールに追加の拡張機能として追加されます。 パッケージがインストールされている場合は、[プロパティページ] ダイアログボックスを使用して、リリースおよび試験的な規則を有効または無効にすることができます。

::: moniker-end

## <a name="see-also"></a>関連項目

- [Visual Studio C++ Core Check リファレンス](code-analysis-for-cpp-corecheck.md)
