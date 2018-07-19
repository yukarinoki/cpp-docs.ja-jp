---
title: -デバッグ (デバッグ情報の生成) |Microsoft ドキュメント
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
ms.openlocfilehash: f93c47a0f96cf0b75b453bcea97212d4ab2fd6d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375728"
---
# <a name="debug-generate-debug-info"></a>/DEBUG (デバッグ情報の生成)
```  
/DEBUG[:{FASTLINK|FULL|NONE}]  
```  
  
## <a name="remarks"></a>コメント  

**/Debug**オプションは、実行可能ファイルのデバッグ情報を作成します。    
  
リンカーは、プログラム データベース (PDB) ファイルにデバッグ情報を渡します。 プログラムの後続のビルド中に pdb ファイルを更新します。  
  
実行可能ファイル (.exe ファイルまたは DLL) デバッグ用に作成には、対応する pdb ファイルのパスと名前が含まれています。 デバッガーは、埋め込みの名前を読み込んで、pdb ファイルを使用して、プログラムをデバッグするときにします。 リンカーは、プログラム データベースの名前に、プログラムおよび拡張子 .pdb のベース名を使用し、その作成元のパスを埋め込みます。 この既定をオーバーライドするには設定[/PDB](../../build/reference/pdb-use-program-database.md)し、別のファイル名を指定します。  

**/DEBUG:FASTLINK**オプションは、実行可能ファイルをビルドするために使用する個々 のコンパイル製品のプライベート シンボル情報がします。 オブジェクト ファイルと完全なコピーを作成せずに実行可能ファイルをビルドするために使用するライブラリのデバッグ情報にインデックスを作成する限られた PDB を生成します。 このオプションは、2 ~ 4 倍ほど高速で、完全な PDB 生成をリンクしはローカルでのデバッグと、利用可能なビルドの製品がある場合に推奨します。 この制限付きの PDB は、必要なビルドの製品が実行可能ファイルが別のコンピューターに展開される場合など、使用できなくなったときにデバッグするため使用できません。 開発者コマンド プロンプトで、この制限付きの PDB から完全な PDB を生成するのに mspdbcmf.exe ツールを使用することができます。 Visual Studio には、プロジェクトまたはソリューションの完全な PDB を作成するのに、完全な PDB ファイルを生成するためのプロジェクトまたはビルド メニュー項目を使用します。  
  
**/DEBUG:FULL**オプションが 1 つの PDB に個々 のコンパイル製品 (オブジェクト ファイルとライブラリ) からプライベート シンボル情報をすべてを移動して、リンクの最も時間のかかる含めることができます。 ただし、他のビルドの製品がない場合、実行可能ファイルが展開される場合など、実行可能ファイルをデバッグする、完全な PDB を使用できます。  
  
**/Debug: NONE**オプションは、PDB を生成しません。  
  
指定すると **/debug** 、他のオプションとリンカーの既定値は **/DEBUG:FULL**コマンドラインとメイクファイル ビルド、リリース ビルドの Visual Studio IDE、およびデバッグとリリースの両方Visual Studio 2015 および以前のバージョンでビルドします。 Visual Studio 2017 以降は、IDE でビルド システム既定値は **/DEBUG:FASTLINK**を指定すると、 **/debug**オプション、デバッグ ビルドをします。 旧バージョンとの互換性を維持するためには、他の既定値が変更されていません。  
  
コンパイラの[C7 互換](../../build/reference/z7-zi-zi-debug-information-format.md)(/Z7) オプションは、コンパイラ、.obj ファイルにデバッグ情報のままにします。 使用することも、[プログラム データベース](../../build/reference/z7-zi-zi-debug-information-format.md)(/Zi) コンパイラ オプションを .obj ファイルの PDB 内でデバッグ情報を格納します。 .Obj ファイルで記述された絶対パスに最初、リンカーが検索、オブジェクトの PDB をし、.obj ファイルが使用されているディレクトリにします。 オブジェクトの PDB ファイル名またはディレクトリをリンカーを指定することはできません。  
  
[/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) /DEBUG が指定されている場合は暗黙的に指定します。  
  
/デバッグの既定値を変更する、 [/opt](../../build/reference/opt-optimizations.md) REF からをオプションを NOREF ICF から NOICF、するため、/opt:ref によるまたは/OPT:ICF を指定する必要があります明示的に元の既定値を設定する場合。  
  
.Exe または .dll デバッグ情報を含むを作成することはできません。 デバッグ情報は常に、.obj または .pdb ファイルに配置します。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**デバッグ**プロパティ ページ。  
  
4.  変更、**デバッグ情報の生成**プロパティ PDB 生成を有効にします。 これにより、既定では、Visual Studio 2017/DEBUG:FASTLINK です。  
  
4.  変更、**完全プログラム データベース ファイルの生成**/DEBUG:FULL をインクリメンタル ビルドするたびに完全な PDB の生成を有効にするプロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
