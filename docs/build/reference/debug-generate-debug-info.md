---
title: -DEBUG (デバッグ情報の生成) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateDebugInformation
- /debug
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11b3799447e160a56d73441b60215f1dfcb3e227
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132136"
---
# <a name="debug-generate-debug-info"></a>/DEBUG (デバッグ情報の生成)
```  
/DEBUG[:{FASTLINK|FULL|NONE}]  
```  
  
## <a name="remarks"></a>Remarks  

**/Debug**オプションは、実行可能ファイルのデバッグ情報を作成します。    
  
リンカーでは、プログラム データベース (PDB) ファイルにデバッグ情報が保存されます。 プログラムの後続のビルド時に pdb ファイルを更新します。  
  
実行可能ファイル (.exe ファイルまたは DLL) デバッグ用に作成には、対応する pdb ファイルのパスと名前が含まれています。 デバッガーは、埋め込まれている名を読み取って、プログラムをデバッグするときに、PDB を使用します。 リンカーは、プログラムと拡張子 .pdb の基本名、プログラム データベースの名前を使用して、その作成元のパスを埋め込みます。 この既定をオーバーライドするには設定[/PDB](../../build/reference/pdb-use-program-database.md)し、別のファイル名を指定します。  

**/DEBUG:FASTLINK**オプションは、Visual Studio 2017 で利用可能な以降。 このオプションは、実行可能ファイルをビルドするために使用する個別のコンパイル製品でプライベート シンボル情報ができます。 オブジェクト ファイルと完全なコピーではなく、実行可能ファイルをビルドするために使用するライブラリのデバッグ情報にインデックスを作成する限られた PDB を生成します。 このオプションは、2 ~ 4 倍ほど高速完全な PDB の生成でリンクでき、ローカルでデバッグし、利用可能なビルド製品がある場合にお勧めします。 この制限付きの PDB は、必要なビルド製品はなど、別のコンピューターで実行可能ファイルをデプロイするときに、使用する場合のデバッグは使用できません。 開発者コマンド プロンプトでは、この限られた PDB から完全な PDB を生成するのに mspdbcmf.exe ツールを使用することができます。 Visual Studio で、完全な PDB ファイルを生成するためのプロジェクトまたはビルドのメニュー項目を使用して、プロジェクトまたはソリューションの完全な PDB を作成します。  
  
**/DEBUG:FULL**オプション コンパイルの個々 の製品 (オブジェクト ファイルとライブラリ) から、1 つの PDB にプライベート シンボルのすべての情報を移動およびリンクの最も時間のかかる含めることができます。 ただし、完全な PDB を使用して、実行可能ファイルが配置されるときなど、使用可能なその他のビルド製品がない場合に、実行可能ファイルをデバッグできます。  
  
**/Debug: NONE**オプションは、PDB を生成しません。  
  
指定すると **/debug** 、リンカーは、追加オプションなしで **/DEBUG:FULL**コマンドラインとメイクファイル ビルドでは、リリース ビルドとデバッグとリリースの Visual Studio IDE でVisual Studio 2015 と以前のバージョンでビルドします。 Visual Studio 2017 以降では、IDE でビルド システム既定値は **/DEBUG:FASTLINK**を指定すると、 **/debug**オプションを使用しないデバッグ ビルドします。 旧バージョンとの互換性を維持するためには、他の既定値が変更されていません。  
  
コンパイラの[C7 互換](../../build/reference/z7-zi-zi-debug-information-format.md)(/Z7) オプションと、コンパイラ、.obj ファイルのデバッグ情報のままにします。 使用することも、[プログラム データベース](../../build/reference/z7-zi-zi-debug-information-format.md).obj ファイルの pdb ファイルにデバッグ情報を格納する (/Zi) コンパイラ オプション。 リンカーの PDB のオブジェクトの最初に検索、.obj ファイルで記述された絶対パスと、.obj ファイルが使用されているディレクトリにします。 オブジェクトの PDB ファイル名または場所をリンカーに指定することはできません。  
  
[/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) /DEBUG を指定した場合は、暗黙的に指定します。  
  
/デバッグの既定値の変更、 [/opt](../../build/reference/opt-optimizations.md)オプションを REF NOREF と ICF NOICF、ため、/OPT:REF または/OPT:ICF を指定する必要があります明示的に元の既定値を設定する場合。  
  
.Exe または .dll を含むデバッグ情報を作成することはできません。 デバッグ情報は、常に、.obj や .pdb ファイルに配置します。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。  
  
2.  をクリックして、**リンカー**フォルダー。  
  
3.  をクリックして、**デバッグ**プロパティ ページ。  
  
4.  変更、**デバッグ情報の生成**プロパティ PDB の生成を有効にします。 既定では Visual Studio 2017 での/DEBUG:FASTLINK を有効にします。  
  
4.  変更、**プログラム データベース ファイルの完全な生成**/DEBUG:FULL をインクリメンタル ビルドのたびに完全な PDB の生成を有効にするプロパティ。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
