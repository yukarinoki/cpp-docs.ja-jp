---
title: /P (プリプロセス出力のファイルへの書き込み)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
ms.openlocfilehash: 9b3d84d94ed75acd68011b895afbc4f190019673
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622241"
---
# <a name="p-preprocess-to-a-file"></a>/P (プリプロセス出力のファイルへの書き込み)

C および C++ ソース ファイルを前処理し、ファイルを前処理済みの出力を書き込みます。

## <a name="syntax"></a>構文

```
/P
```

## <a name="remarks"></a>Remarks

ファイル名は、ソース ファイルの基本名に .i 拡張機能を持ちます。 プロセスですべてのプリプロセッサ ディレクティブが実行されます、マクロの展開が実行されて、およびコメントを削除します。 前処理済みの出力内のコメントを保持するために使用して、 [(保持プリプロセス時のコメント)/C](../../build/reference/c-preserve-comments-during-preprocessing.md)オプションと共に **/P**します。

**/P**追加`#line`ディレクティブを先頭と末尾各インクルード ファイルの条件付きコンパイルのプリプロセッサ ディレクティブによって削除された行に出力します。 これらのディレクティブは、前処理済みファイルの行を再設定します。 その結果、処理の後のステージ中に生成されたエラーは、前処理済みファイル内の行ではなく、元のソース ファイルの行番号を参照してください。 生成を抑制する`#line`ディレクティブを使用して、 [/EP (#line ディレクティブなしの stdout に前処理する)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)だけでなく **/P**します。

**/P**オプションはコンパイルを中止します。 使用する場合でも、.obj ファイルは生成されません[/Fo (オブジェクト ファイル名)](../../build/reference/fo-object-file-name.md)します。 Compilation の前処理済みファイルを再送信する必要があります。 **/P**から出力ファイルも生成されません、 **/FA**、 **/Fa**、および **/Fm**オプション。 詳細については、次を参照してください。 [/FA、/Fa (リスティング ファイル)](../../build/reference/fa-fa-listing-file.md)と[/Fm (マップ ファイルの名前)](../../build/reference/fm-name-mapfile.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**プリプロセッサ**プロパティ ページ。

1. 変更、**前処理されたファイルの生成**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>

## <a name="example"></a>例

次のコマンドラインの前処理`ADD.C`、コメントを保持、追加`#line`ディレクティブをファイルに結果を書き出すと`ADD.I`:

```
CL /P /C ADD.C
```

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/Fi (出力ファイル名の前処理)](../../build/reference/fi-preprocess-output-file-name.md)