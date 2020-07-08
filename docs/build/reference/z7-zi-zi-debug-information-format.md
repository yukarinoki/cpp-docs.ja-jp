---
title: /Z7、/Zi、/ZI (デバッグ情報の形式)
ms.date: 07/06/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /ZI
- /Zi
- /Z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
helpviewer_keywords:
- C7 compatible compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
ms.openlocfilehash: bc3fd9c065219a128e29290084b1e1fb51fc773e
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058595"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7、/Zi、/ZI (デバッグ情報の形式)

**`/Z7`**、 **`/Zi`** 、およびコンパイラオプションでは、 **`/ZI`** プログラムに対して作成されるデバッグ情報の種類、およびこの情報をオブジェクトファイルとプログラムデータベース (PDB) ファイルのどちらに保存するかを指定します。

## <a name="syntax"></a>構文

> **`/Z7`**\
> **`/Zi`**\
> **`/ZI`**

## <a name="remarks"></a>Remarks

デバッグオプションを指定すると、コンパイラによって、デバッガーで使用する関数と変数、型情報、および行の場所のシンボル名が生成されます。 このシンボリックデバッグ情報は、コンパイラによって生成されたオブジェクトファイル ( *`.obj`* ファイル)、または実行可能ファイルの別の PDB ファイル (ファイル) に含めることができ *`.pdb`* ます。 デバッグ情報の形式のオプションについては、次のセクションで説明します。

### <a name="none"></a>なし

既定では、デバッグ情報フォーマットオプションが指定されていない場合、コンパイラはデバッグ情報を生成しないため、コンパイルが高速になります。

### <a name="z7"></a>/Z7

オプションを指定すると、 **`/Z7`** デバッガーで使用する完全なシンボリックデバッグ情報も含むオブジェクトファイルが生成されます。 これらのオブジェクトファイルと、それらから構築されたライブラリは、デバッグ情報のないファイルよりもかなり大きくなる可能性があります。 シンボリックデバッグ情報には、変数、関数、および行番号の名前と型が含まれています。 コンパイラによって生成される PDB ファイルはありません。 ただし、リンカーにオプションが渡された場合でも、これらのオブジェクトファイルまたはライブラリから PDB ファイルを生成することはでき **`/DEBUG`** ます。

サードパーティライブラリのデバッグバージョンのディストリビューターの場合、PDB ファイルがないという利点があります。 ただし、プリコンパイル済みヘッダーのオブジェクトファイルは、ライブラリリンクフェーズ中、およびデバッグのために必要です。 オブジェクトファイルに型情報のみがある (コードがない) 場合は *`.pch`* 、ライブラリをビルドするときに、既定で有効になっている[ `/Yl` (デバッグライブラリの PCH 参照の挿入)](yl-inject-pch-reference-for-debug-library.md)オプションも使用する必要があります。

が指定されている場合、非推奨の [ [ `/Gm` 最小リビルドを有効にする](gm-enable-minimal-rebuild.md)] オプションは使用できません **`/Z7`** 。

### <a name="zi"></a>/ZI

オプションを指定すると、 **`/Zi`** デバッガーで使用するすべてのシンボリックデバッグ情報を含む個別の PDB ファイルが生成されます。 デバッグ情報がオブジェクトファイルまたは実行可能ファイルに含まれていないため、はるかに小さくなります。

の使用は、 **`/Zi`** 最適化には影響しません。 ただし、 **`/Zi`** はを意味 **`/debug`** します。 詳細については、「 [ `/DEBUG` (デバッグ情報の生成)](debug-generate-debug-info.md)」を参照してください。

との両方を指定すると **`/Zi`** **`/clr`** 、 <xref:System.Diagnostics.DebuggableAttribute> 属性はアセンブリメタデータに配置されません。 必要に応じて、ソースコードで指定する必要があります。 この属性は、アプリケーションの実行時パフォーマンスに影響します。 属性がパフォーマンスに与える影響と、パフォーマンスへの影響を変更する方法の詳細については `Debuggable` 、「[イメージを簡単にデバッグ](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug)できるようにする」を参照してください。

コンパイラは PDB ファイルに名前 *`<project>.pdb`* を指定します。ここで、 *`<project>`* はプロジェクトの名前です。 プロジェクトの外部でファイルをコンパイルすると、コンパイラはという名前の PDB ファイルを作成し *`VC<x>.pdb`* *`<x>`* ます。は、使用されているコンパイラバージョンのメジャーバージョン番号とマイナーバージョン番号を連結したものです。 コンパイラは、このオプションを使用して作成された各オブジェクトファイルに、PDB の名前とタイムスタンプ付き署名を埋め込みます。 この名前とシグネチャは、シンボル情報と行番号情報の場所にデバッガーをポイントします。 PDB ファイルの名前と署名は、デバッガーに読み込まれるシンボルの実行可能ファイルと一致している必要があります。 WinDBG デバッガーでは、コマンドを使用して、一致しないシンボルを読み込むことができ **`.symopt+0x40`** ます。 Visual Studio には、一致しないシンボルを読み込むためのオプションはありません。

を使用してコンパイルされたオブジェクトからライブラリを作成する場合は、 **`/Zi`** ライブラリがプログラムにリンクされているときに、関連付けられている PDB ファイルが使用可能である必要があります。 つまり、ライブラリを配布する場合は、PDB ファイルも配布する必要があります。 PDB ファイルを使用せずにデバッグ情報が含まれているライブラリを作成するには、オプションを選択する必要があり **`/Z7`** ます。 プリコンパイル済みヘッダーのオプションを使用すると、プリコンパイル済みヘッダーとその他のソースコードの両方のデバッグ情報が PDB ファイルに配置されます。

### <a name="zi"></a>/ZI

**`/ZI`** オプションはに似てい **`/Zi`** ますが、[エディットコンティニュ](/visualstudio/debugger/edit-and-continue-visual-cpp)機能をサポートする形式で PDB ファイルが生成されます。 エディットコンティニュのデバッグ機能を使用するには、このオプションを使用する必要があります。 エディットコンティニュ機能は、開発者の生産性向上に役立ちますが、コードのサイズ、パフォーマンス、およびコンパイラの準拠に関する問題が発生する可能性があります。 ほとんどの最適化はエディットコンティニュと互換性がないため、を使用すると、 **`/ZI`** `#pragma optimize` コード内のステートメントが無効になります。 この **`/ZI`** オプションは、 [ `__LINE__` 定義済みのマクロ](../../preprocessor/predefined-macros.md)の使用と互換性がありません。を使用してコンパイルされたコードは **`/ZI`** `__LINE__` 、マクロの展開で使用できますが、非型テンプレート引数としてを使用することはできません `__LINE__` 。

**`/ZI`** オプションは、コンパイルで使用される[ `/Gy` (関数レベルのリンクの有効化)](gy-enable-function-level-linking.md)オプションと[ `/FC` (診断でのソースコードファイルの完全パス](fc-full-path-of-source-code-file-in-diagnostics.md)) オプションの両方を強制します。

**`/ZI`** はと互換性がありません[ `/clr` (共通言語ランタイムのコンパイル)](clr-common-language-runtime-compilation.md)。

> [!NOTE]
> この **`/ZI`** オプションは、x86 および x64 プロセッサを対象とするコンパイラでのみ使用できます。 このコンパイラオプションは、ARM プロセッサを対象とするコンパイラでは使用できません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **構成プロパティ**の  >  [**C/c + +**  >  **全般**] プロパティページを開きます。

1. "**デバッグ情報の形式**" プロパティを変更します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
