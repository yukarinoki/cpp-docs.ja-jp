---
title: E (stdout に前処理) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /e
dev_langs:
- C++
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f9105c5c75bc4695d0b00debdff49acf78690b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376915"
---
# <a name="e-preprocess-to-stdout"></a>/E (プリプロセス出力の標準出力へのコピー)
C および C++ ソース ファイルを前処理され、前処理済みファイルを標準出力デバイスにコピーされます。  
  
## <a name="syntax"></a>構文  
  
```  
/E  
```  
  
## <a name="remarks"></a>コメント  
 このプロセスですべてのプリプロセッサ ディレクティブが実行されます。、マクロの展開が実行されて、およびコメントが削除されます。 プリプロセス済みの出力内のコメントを保持するために使用して、 [(保持コメント中に前処理)/C](../../build/reference/c-preserve-comments-during-preprocessing.md)コンパイラ オプションもします。  
  
 **/E**追加`#line`ディレクティブを先頭と末尾各インクルード ファイルの条件付きコンパイル用のプリプロセッサ ディレクティブによって削除された行に出力します。 これらのディレクティブは、前処理済みファイルの行を再設定します。 その結果、処理の後のステージ中に生成されたエラーは、前処理済みファイル内の行ではなく、元のソース ファイルの行番号を参照してください。  
  
 **/E**オプションには、コンパイルが行われません。 コンパイルのプリプロセス済みのファイルを再送信する必要があります。 **/E**も抑制の出力ファイル、 **/FA**、 **/Fa**、および **/Fm**オプション。 詳細については、次を参照してください。 [/FA、/Fa (ファイルを一覧表示する)](../../build/reference/fa-fa-listing-file.md)と[/Fm (マップ ファイルの名前)](../../build/reference/fm-name-mapfile.md)です。  
  
 非表示にする`#line`、ディレクティブを使用して、 [/EP (#line ディレクティブしない stdout へのプリプロセス)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)オプションを代わりにします。  
  
 プリプロセス済みの出力ではなくファイルを送信する`stdout`を使用して、 [/P (プリプロセス出力ファイルへの)](../../build/reference/p-preprocess-to-a-file.md)オプションを代わりにします。  
  
 非表示にする`#line`ディレクティブと送信ファイルをプリプロセス済みの出力を使用して **/P**と **/EP**一緒にします。  
  
 プリコンパイル済みヘッダーを使用することはできません、 **/E**オプション。  
  
 別のファイルをプリプロセス時にスペースが出力されませんトークンの後に注意してください。 これで不正なプログラムまたはできなくなる可能性が意図しない副作用です。 次のプログラムが正常にコンパイルされます。  
  
```  
#define m(x) x  
m(int)main( )  
{  
   return 0;  
}  
```  
  
 ただし、使用してコンパイルする場合。  
  
```  
cl -E test.cpp > test2.cpp  
```  
  
 `int main` test2.cpp は正しくできません`intmain`です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  コンパイラ オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコマンドラインを前処理`ADD.C`、コメントを保持、追加`#line`ディレクティブは、標準出力デバイスに結果を表示します。  
  
```  
CL /E /C ADD.C  
```  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)