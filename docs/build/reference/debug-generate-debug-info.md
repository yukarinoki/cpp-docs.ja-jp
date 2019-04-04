---
title: /DEBUG (デバッグ情報の生成)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateDebugInformation
- /debug
helpviewer_keywords:
- DEBUG linker option
- /DEBUG linker option
- -DEBUG linker option
- PDB files
- debugging [C++], debug information files
- generate debug info linker option
- pdb files, generating debug info
- .pdb files, generating debug info
- debugging [C++], linker option
- program databases [C++]
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
ms.openlocfilehash: ca7ef5d1935ddea0441f49e387e35184c6fd1fc6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810199"
---
# <a name="debug-generate-debug-info"></a>/DEBUG (デバッグ情報の生成)

```
/DEBUG[:{FASTLINK|FULL|NONE}]
```

## <a name="remarks"></a>Remarks

**/Debug**オプションは、実行可能ファイルのデバッグ情報を作成します。

リンカーでは、プログラム データベース (PDB) ファイルにデバッグ情報が保存されます。 プログラムの後続のビルド時に pdb ファイルを更新します。

実行可能ファイル (.exe ファイルまたは DLL) デバッグ用に作成には、対応する pdb ファイルのパスと名前が含まれています。 デバッガーは、埋め込まれている名を読み取って、プログラムをデバッグするときに、PDB を使用します。 リンカーは、プログラムと拡張子 .pdb の基本名、プログラム データベースの名前を使用して、その作成元のパスを埋め込みます。 この既定をオーバーライドするには設定[/PDB](pdb-use-program-database.md)し、別のファイル名を指定します。

**/DEBUG:FASTLINK**オプションは、Visual Studio 2017 で利用可能な以降。 このオプションは、実行可能ファイルをビルドするために使用する個別のコンパイル製品でプライベート シンボル情報ができます。 オブジェクト ファイルと完全なコピーではなく、実行可能ファイルをビルドするために使用するライブラリのデバッグ情報にインデックスを作成する限られた PDB を生成します。 このオプションは、2 ~ 4 倍ほど高速完全な PDB の生成でリンクでき、ローカルでデバッグし、利用可能なビルド製品がある場合にお勧めします。 この制限付きの PDB は、必要なビルド製品はなど、別のコンピューターで実行可能ファイルをデプロイするときに、使用する場合のデバッグは使用できません。 開発者コマンド プロンプトでは、この限られた PDB から完全な PDB を生成するのに mspdbcmf.exe ツールを使用することができます。 Visual Studio で、完全な PDB ファイルを生成するためのプロジェクトまたはビルドのメニュー項目を使用して、プロジェクトまたはソリューションの完全な PDB を作成します。

**/DEBUG:FULL**オプション コンパイルの個々 の製品 (オブジェクト ファイルとライブラリ) から、1 つの PDB にプライベート シンボルのすべての情報を移動およびリンクの最も時間のかかる含めることができます。 ただし、完全な PDB を使用して、実行可能ファイルが配置されるときなど、使用可能なその他のビルド製品がない場合に、実行可能ファイルをデバッグできます。

**/Debug: NONE**オプションは、PDB を生成しません。

指定すると **/debug** 、リンカーは、追加オプションなしで **/DEBUG:FULL**コマンドラインとメイクファイル ビルドでは、リリース ビルドとデバッグとリリースの Visual Studio IDE でVisual Studio 2015 と以前のバージョンでビルドします。 Visual Studio 2017 以降では、IDE でビルド システム既定値は **/DEBUG:FASTLINK**を指定すると、 **/debug**オプションを使用しないデバッグ ビルドします。 旧バージョンとの互換性を維持するためには、他の既定値が変更されていません。

コンパイラの[C7 互換](z7-zi-zi-debug-information-format.md)(/Z7) オプションと、コンパイラ、.obj ファイルのデバッグ情報のままにします。 使用することも、[プログラム データベース](z7-zi-zi-debug-information-format.md).obj ファイルの pdb ファイルにデバッグ情報を格納する (/Zi) コンパイラ オプション。 リンカーの PDB のオブジェクトの最初に検索、.obj ファイルで記述された絶対パスと、.obj ファイルが使用されているディレクトリにします。 オブジェクトの PDB ファイル名または場所をリンカーに指定することはできません。

[/INCREMENTAL](incremental-link-incrementally.md) /DEBUG を指定した場合は、暗黙的に指定します。

/デバッグの既定値の変更、 [/opt](opt-optimizations.md)オプションを REF NOREF と ICF NOICF、ため、/OPT:REF または/OPT:ICF を指定する必要があります明示的に元の既定値を設定する場合。

.Exe または .dll を含むデバッグ情報を作成することはできません。 デバッグ情報は、常に、.obj や .pdb ファイルに配置します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**デバッグ**プロパティ ページ。

1. 変更、**デバッグ情報の生成**プロパティ PDB の生成を有効にします。 既定では Visual Studio 2017 での/DEBUG:FASTLINK を有効にします。

1. 変更、**プログラム データベース ファイルの完全な生成**/DEBUG:FULL をインクリメンタル ビルドのたびに完全な PDB の生成を有効にするプロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
