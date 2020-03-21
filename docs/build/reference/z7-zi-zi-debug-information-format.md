---
title: /Z7、/Zi、/ZI (デバッグ情報の形式)
ms.date: 04/08/2019
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
ms.openlocfilehash: aeaf435874b6d6b9dbc8a3d12ec06d38bf33aaae
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078263"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7、/Zi、/ZI (デバッグ情報の形式)

プログラムに対して作成されるデバッグ情報の種類、およびこの情報をオブジェクトファイルとプログラムデータベース (PDB) ファイルのどちらに保存するかを指定します。

## <a name="syntax"></a>構文

> **/Z**{**7**|**i**|**i**}

## <a name="remarks"></a>解説

コードをコンパイルしてデバッグモードでビルドすると、コンパイラによって、デバッガーで使用する関数と変数、型情報、および行番号の場所のシンボル名が生成されます。 このシンボリックデバッグ情報は、コンパイラによって生成されたオブジェクトファイル (.obj ファイル)、または実行可能ファイルの別の PDB ファイル (.pdb ファイル) に含めることができます。  デバッグ情報の形式のオプションについては、次のセクションで説明します。

### <a name="none"></a>なし

既定では、デバッグ情報フォーマットオプションが指定されていない場合、コンパイラはデバッグ情報を生成しないため、コンパイルが高速になります。

### <a name="z7"></a>/Z7

**/Z7**オプションを指定すると、デバッガーで使用する完全なシンボリックデバッグ情報も含むオブジェクトファイルが生成されます。 これらのオブジェクトファイルとビルドされた実行可能ファイルは、デバッグ情報のないファイルよりもかなり大きくなる可能性があります。 シンボリック デバッグ情報には、変数や関数の名前と型、および行番号が含まれます。 PDB ファイルは生成されません。

サードパーティ製ライブラリのデバッグバージョンのディストリビューターの場合、PDB ファイルがないという利点があります。 ただし、プリコンパイル済みヘッダーのオブジェクトファイルは、ライブラリリンクフェーズ中、およびデバッグのために必要です。 .Pch オブジェクトファイルに型情報のみが含まれている (コードがない) 場合は、ライブラリをビルドするときに、既定で有効になっている[/Yl (デバッグライブラリの Pch 参照の挿入)](yl-inject-pch-reference-for-debug-library.md)オプションも使用する必要があります。

**/Z7**が指定されている場合、非推奨の[/Gm (簡易リビルドの有効化)](gm-enable-minimal-rebuild.md)オプションは使用できません。

### <a name="zi"></a>/ZI

**/Zi**オプションを指定すると、デバッガーで使用するすべてのシンボリックデバッグ情報を含む個別の PDB ファイルが生成されます。 デバッグ情報はオブジェクトファイルまたは実行可能ファイルに含まれないため、はるかに小さくなります。

**/Zi**を使用しても、最適化には影響しません。 ただし、 **/zi**は **/debug**を意味します。詳細については、「 [/debug (デバッグ情報の生成)](debug-generate-debug-info.md) 」を参照してください。

**/Zi**と **/clr**の両方を指定した場合、<xref:System.Diagnostics.DebuggableAttribute> 属性はアセンブリメタデータに配置されません。 必要に応じて、ソースコードで指定する必要があります。 この属性は、アプリケーションの実行時パフォーマンスに影響します。 デバッグ可能な属性がパフォーマンスに与える影響と、パフォーマンスへの影響を変更する方法の詳細につい**ては、** 「[イメージを簡単にデバッグ](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug)できるようにする」を参照してください。

コンパイラは、 *pdb ファイルに*.pdb という名前を付いています。 プロジェクトの外部でファイルをコンパイルすると、コンパイラは VC*x*.pdb という名前の pdb ファイルを作成します。ここで*x*は、使用されているコンパイラバージョンのメジャーバージョン番号とマイナーバージョン番号を連結したものです。 コンパイラは、このオプションを使用して作成された各オブジェクトファイルに、PDB の名前とタイムスタンプ付き署名を埋め込みます。これにより、デバッガーがシンボル情報と行番号情報の場所を参照します。 PDB ファイルの名前と署名は、デバッガーに読み込まれるシンボルの実行可能ファイルと一致している必要があります。 WinDBG デバッガーでは、`.symopt+0x40` コマンドを使用して、一致しないシンボルを読み込むことができます。 Visual Studio には、一致しないシンボルを読み込むためのオプションはありません。

**/Zi**を使用してコンパイルされたオブジェクトからライブラリを作成する場合は、ライブラリがプログラムにリンクされているときに、関連付けられた .pdb ファイルが使用可能である必要があります。 したがって、ライブラリを配布する場合は、PDB ファイルも配布する必要があります。 PDB ファイルを使用せずにデバッグ情報が含まれているライブラリを作成するには、 **/Z7**オプションを選択する必要があります。 プリコンパイル済みヘッダーのオプションを使用すると、プリコンパイル済みヘッダーとその他のソースコードの両方のデバッグ情報が PDB ファイルに配置されます。

### <a name="zi"></a>/ZI

**/Zi**オプションは **/zi**に似ていますが、[エディットコンティニュ](/visualstudio/debugger/edit-and-continue-visual-cpp)機能をサポートする形式で PDB ファイルを生成します。 エディットコンティニュのデバッグ機能を使用するには、このオプションを使用する必要があります。 エディットコンティニュ機能は、開発者の生産性向上に役立ちますが、コードのサイズ、パフォーマンス、およびコンパイラの準拠に関する問題が発生する可能性があります。 ほとんどの最適化はエディットコンティニュと互換性がないため、 **/zi**を使用すると、コード内の `#pragma optimize` ステートメントが無効になります。 **/Zi**オプションは、 [ &#95; &#95;行&#95; &#95;の定義済みマクロ](../../preprocessor/predefined-macros.md)を使用することと互換性がありません。 **/zi**を使用してコンパイルされたコードでは、行を非型テンプレート引数と **&#95; &#95;し&#95;て使用**することはできません。ただし **&#95; &#95;、行&#95;** はマクロの展開で使用できます。

**/Zi**オプションでは、コンパイル時に、 [/Gy (関数レベルのリンクの有効化)](gy-enable-function-level-linking.md)オプションと[/Fc (診断でソースコードファイルの完全パス](fc-full-path-of-source-code-file-in-diagnostics.md)) オプションの両方が強制されます。

**/Zi**は[/Clr (共通言語ランタイムのコンパイル)](clr-common-language-runtime-compilation.md)と互換性がありません。

> [!NOTE]
> **/Zi**オプションは、x86 および x64 プロセッサを対象とするコンパイラでのみ使用できます。このコンパイラオプションは、ARM プロセッサを対象とするコンパイラでは使用できません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関する記事を参照してください。

1. **構成プロパティ** > **C/C++**  > **全般** プロパティページを開きます。

1. "**デバッグ情報の形式**" プロパティを変更します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>) をご覧ください。

## <a name="see-also"></a>参照

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
