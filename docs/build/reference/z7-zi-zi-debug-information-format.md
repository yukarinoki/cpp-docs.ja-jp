---
title: -Z7、-zi、ZI (デバッグ情報の形式) |Microsoft ドキュメント
ms.custom: ''
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /ZI
- /Zi
- /Z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a86605b8fd47c0febedfc9ab022dfc2c2728822a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379082"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7、/Zi、/ZI (デバッグ情報の形式)

オブジェクト ファイルまたはプログラム データベース (PDB) ファイルにこの情報を保持するかどうか、プログラム用に作成されたデバッグ情報の種類を指定します。

## <a name="syntax"></a>構文

> **/Z**{**7**|**i**|**I**}  

## <a name="remarks"></a>コメント

コードがコンパイルされ、デバッグ モードでビルドされたときに、コンパイラは関数と、および変数の型については、デバッガーで使用するための行番号の場所のシンボル名を生成します。 このシンボリック デバッグ情報をコンパイラによって生成されたオブジェクト ファイル (.obj ファイル) または実行可能ファイルの別の PDB ファイル (.pdb ファイル) に含まれることはできます。  デバッグ情報の形式オプションは、次のセクションで説明します。  
  
### <a name="none"></a>なし

既定では、デバッグ情報の形式のオプションが指定されていない場合、コンパイラありませんデバッグ情報を生成、コンパイルが高速なためです。  
  
### <a name="z7"></a>/Z7

**/Z7**オプションは、デバッガーでは、使用するための詳細なシンボリック デバッグ情報も含まれているオブジェクト ファイルを生成します。 これらのオブジェクト ファイルとビルドの実行可能ファイルは、デバッグ情報を持たないファイルよりも大きいできます。 シンボリック デバッグ情報には、変数や関数の名前と型、および行番号が含まれます。 PDB ファイルは生成されません。

サード パーティ製のライブラリのデバッグ バージョンのディストリビューターの場合、PDB ファイルを持たないことによる利点があります。 ただし、プリコンパイル済みヘッダーのオブジェクト ファイルは、フェーズ中に、ライブラリのリンク、およびデバッグするために必要です。 型情報だけ (コードを含まない) .pch オブジェクト ファイルの場合は、使用する必要ありますも、 [/Yl (挿入 PCH 参照デバッグ ライブラリの)](../../build/reference/yl-inject-pch-reference-for-debug-library.md)オプションは、ライブラリをビルドするときに、既定では、有効にします。

[/Gm (簡易リビルドの有効)](../../build/reference/gm-enable-minimal-rebuild.md)場合オプションは使用できません **/Z7**を指定します。

### <a name="zi"></a>/ZI

**/Zi**オプションはすべて、シンボリック デバッグ情報を格納用デバッガーでは、別の PDB ファイルを生成します。 オブジェクト ファイルにデバッグ情報が含まれていないか、実行可能ファイルであるために大幅に小さくなります。

使用 **/Zi**の最適化には影響しません。 ただし、 **/Zi**わけでは **/debug**; を参照してください[/DEBUG (デバッグ情報の生成)](../../build/reference/debug-generate-debug-info.md)詳細についてはします。


両方を指定すると **/Zi**と **/clr**、<xref:System.Diagnostics.DebuggableAttribute>属性がアセンブリのメタデータに保存されていません。 場合は、ソース コードで指定する必要があります。 この属性は、アプリケーションの実行時パフォーマンスに影響します。 方法の詳細については**Debuggable**属性がパフォーマンスに影響し、パフォーマンスに与える影響を変更する方法を参照してください[デバッグするイメージの簡略化を行う](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug)です。

PDB ファイルの名前、コンパイラ*プロジェクト*.pdb です。 プロジェクトの外側でファイルをコンパイルする場合、コンパイラが VC をという名前の PDB ファイルを作成*x*.pdb、場所*x*コンパイラのバージョンを使用中のメジャーおよびマイナー バージョン番号を連結します。 コンパイラは、このオプションは、デバッガーが指すシンボリックと行番号情報の場所を使用して作成された各オブジェクト ファイル内の名前、PDB と識別のタイムスタンプの署名を埋め込みます。 名と PDB ファイル内の署名は、デバッガーで読み込まれるシンボルの実行可能ファイルと一致する必要があります。 使用して、WinDBG デバッガーが一致しないシンボルを読み込むことができます、`.symopt+0x40`コマンド。 Visual Studio には、一致しないシンボルを読み込むためのようなオプションはありません。

使用してコンパイルされたオブジェクトからライブラリを作成するかどうかは **/Zi**ライブラリがプログラムにリンクされている場合に、関連付けられた .pdb ファイルが使用可能なにする必要があります。 したがって、ライブラリを配布する場合はまたに PDB ファイルを配布する必要があります。 PDB ファイルを使用せずにデバッグ情報を含むライブラリを作成する必要がありますを選択する、 **/Z7**オプション。 プリコンパイル済みヘッダー オプションを使用する場合、PDB ファイルには、プリコンパイル済みヘッダーと、ソース コードの残りの部分の両方のデバッグ情報が配置されます。

### <a name="zi"></a>/ZI

**/ZI**オプションはのような **/Zi**をサポートする形式に PDB ファイルが生成されますが、[エディット コンティニュ](/visualstudio/debugger/edit-and-continue-visual-cpp)機能します。 エディット コンティニュのデバッグ機能を使用するのには、このオプションを使用する必要があります。 エディット コンティニュ機能は開発者の生産性、便利ですが、コードのサイズ、パフォーマンス、およびコンパイラ準拠の問題が発生することができます。 ほとんどの最適化にエディット コンティニュと互換性がないために使用 **/ZI**も無効になります`#pragma optimize`コードのステートメント。 **/ZI**オプションも互換性がありませんを使用した、 [ &#95;&#95;行&#95;&#95;定義済みマクロ](../../preprocessor/predefined-macros.md); コードでコンパイルされた **/ZI** を使用することはできません **&#95;&#95;行&#95;&#95;** 非型テンプレート引数としてが **&#95;&#95;行&#95;&#95;** マクロの展開で使用できます。

**/ZI**オプションを指定する両方、 [/Gy (関数レベルのリンクを有効にする)](../../build/reference/gy-enable-function-level-linking.md)と[/FC (完全パスのソース コード ファイルで診断)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)コンパイル時に使用するオプションです。

**/ZI**と互換性がありません[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)です。

> [!NOTE]
> **/ZI**オプションは、x86 および x64 プロセッサを対象とすると、コンパイラで使用できるのみです。 このコンパイラ オプションは ARM プロセッサを対象とするコンパイラでは使用されません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 開く、**構成プロパティ** > **C/C++** > **全般**プロパティ ページ。

1. 変更、**デバッグ情報の形式**プロパティです。 選択**OK**して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  

