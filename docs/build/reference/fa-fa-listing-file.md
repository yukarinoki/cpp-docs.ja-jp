---
title: /FA、/Fa (リスティング ファイル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
dev_langs:
- C++
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1840d2f2ff7d968fdcc19e2013a89af9cec32d24
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="fa-fa-listing-file"></a>/FA、/Fa (リスティング ファイル)
アセンブラー コードを含むリスティング ファイルを作成します。  
  
## <a name="syntax"></a>構文  
  
> **/FA**[**c**\][**s**\]**[u]**  
> **/Fa**_パス名_  
  
## <a name="remarks"></a>コメント  
`/FA`コンパイラ オプションは、コンパイル時に、通常、C または C++ ソース ファイルに対応する各翻訳単位のアセンブラー リスティング ファイルを生成します。 既定では ANSI としてエンコードされるリスティング ファイルのアセンブラーのみが含まれています。 省略可能な`c`、 `s`、および`u`引数`/FA`コントロールかどうかのコードをコンピューターまたはソース コードは、この一覧を表示するには、アセンブラーと共に出力と、一覧が utf-8 としてエンコードされているかどうか。  
  
既定では、各リスティング ファイルは、ソース ファイルと同じ基本名を取得し、.asm 拡張子を持ちます。 使用してマシン語コードが含まれている場合、`c`オプション、リスティング ファイル .cod 拡張子が付きます。 リスティング ファイルとそれが作成される場所を使用して、ディレクトリの拡張機能と名前を変更することができます、`/Fa`オプション。  

### <a name="fa-arguments"></a>/FA 引数  
none  
アセンブラー言語のみが一覧に含まれています。  
  
`c`  
任意。 一覧には、マシン語コードが含まれています。  
  
`s`  
任意。 一覧には、ソース コードが含まれています。  
  
`u` 省略可能。 Utf-8 形式でリスティング ファイルをエンコードし、バイト オーダー マーカーが含まれています。 既定では、ファイルは ANSI としてエンコードされます。 使用して`u`任意のシステムに正しく表示されるリスト ファイルを作成するコンパイラへの入力としてのソース コード ファイルのかどうかは、Unicode を使用していますか。  
  
両方`s`と`u`を指定し、ソース コード ファイルの場合、Unicode エンコードを使用し、utf-8、.asm ファイル内のコード行が正しく表示されない場合があります以外です。  
  
### <a name="fa-argument"></a>/Fa 引数  
none  
1 つ*ソース*.asm ファイルがコンパイル時にソース コード ファイルごとに作成します。  
  
*filename*という名前の一覧ファイル*filename*.asm は、現在のディレクトリに配置されます。 これは、1 つのソース コード ファイルをコンパイルするときにのみ有効です。  
  
*filename.extension*  
という名前の一覧ファイル*filename.extension*は、現在のディレクトリに配置されます。 これは、1 つのソース コード ファイルをコンパイルするときにのみ有効です。  
  
*ディレクトリ*\  
1 つ*source_file*.asm ファイルが作成され、指定した配置*ディレクトリ*内の各ソース コード ファイル、コンパイルします。 必要なバック スラッシュを注意してください。 現在のディスク上のパスのみが許可されます。  
  
*ディレクトリ*\\*ファイル名*という名前の一覧ファイル*filename*.asm が配置される、指定した*ディレクトリ*です。 これは、1 つのソース コード ファイルをコンパイルするときにのみ有効です。  
  
*ディレクトリ*\\*filename.extension*  
という名前の一覧ファイル*filename.extension*配置は、指定した*ディレクトリ*です。 これは、1 つのソース コード ファイルをコンパイルするときにのみ有効です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  開く、 **C/C++** フォルダーを選択、**出力ファイル**プロパティ ページ。  
  
3.  変更、**アセンブラーの出力**プロパティを設定、`/FAc`と`/FAs`アセンブラー、コンピューター、およびソース コードのオプションです。 変更、**アセンブラー リストを使用して Unicode**プロパティを設定、 `/FAu` ANSI または utf-8 の出力オプション。 変更、 **ASM リストの場所**を設定する、`/Fa`ファイルの名前と場所を一覧表示するためのオプションです。  
  
両方を設定**アセンブラーの出力**と**アセンブラー リストを使用して Unicode**プロパティ可能性があります[コマンドラインの警告 D9025](../../error-messages/tool-errors/command-line-warning-d9025.md)です。 IDE でこれらのオプションを組み合わせるを使用して、**追加オプション**フィールドで、**コマンド ライン**プロパティ ページの代わりにします。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   詳細については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A>」または「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>」を参照してください。 指定する`/FAu`を参照してください<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>です。  
  
## <a name="example"></a>例  
次のコマンドラインは、結合されたソースを生成し、マシン語コード リスティング ファイル hello.cod:  
  
```  
CL /FAcs HELLO.CPP  
```  
  
## <a name="see-also"></a>関連項目  
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)