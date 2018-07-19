---
title: -Yu (プリコンパイル済みヘッダー ファイルの使用) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yu
dev_langs:
- C++
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d115017e843e7f03455e1eef2b384b3475a1b798
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378718"
---
# <a name="yu-use-precompiled-header-file"></a>/Yu (プリコンパイル済みヘッダー ファイルの使用)
現在のコンパイルで既存のプリコンパイル済みヘッダー (.pch) ファイルを使用して、コンパイラに指示します。  
  
## <a name="syntax"></a>構文  
  
```  
/Yu[filename]  
```  
  
## <a name="arguments"></a>引数  
 *ファイル名*  
 ソース ファイルを使用して、含まれているヘッダー ファイルの名前、 **#include**プリプロセッサ ディレクティブです。  
  
## <a name="remarks"></a>コメント  
 インクルード ファイルの名前はの両方で同じである必要があります、 **/Yc**およびプリコンパイル済みヘッダーを作成するオプション後続 **/Yu**プリコンパイル済みヘッダーの使用を示すオプション。  
  
 **/Yc**、`filename`位置を指定するプリコンパイルが停止しますつまり、コンパイラがすべてのコードをプリコンパイル`filename`しインクルード ファイルと拡張機能の基本名を使用して生成されたプリコンパイル済みヘッダーの名前.pch です。  
  
 .Pch ファイル作成があります。 を使用して **/Yc**です。  
  
 コンパイラは、プリコンパイル済みと .h ファイルの前に発生しているすべてのコードを扱います。 以降も同様にスキップ、 **#include** .h ファイルに関連付けられているディレクティブが .pch ファイルに含まれるコードを使用し、後のすべてのコードをコンパイル`filename`です。  
  
 コマンド ラインでスペースは入れません間 **/Yu**と`filename`です。  
  
 指定すると、 **/Yu**ファイル名、ソース プログラムのないオプションを指定する必要があります、 [#pragma hdrstop](../../preprocessor/hdrstop.md)プラグマはプリコンパイル済みヘッダーの .pch ファイルのファイル名を指定します。 コンパイラが付けたプリコンパイル済みヘッダー (.pch ファイル) を使用するこの例では、 [/Fp (名前です。Pch ファイル)](../../build/reference/fp-name-dot-pch-file.md)です。 コンパイラはプラグマの位置にスキップ、プラグマで指定されたプリコンパイル済みヘッダー ファイルからコンパイル済みの状態を復元およびプラグマを次のコードだけをコンパイルします。 場合 **#pragma hdrstop**拡張子 .pch を持つソース ファイルのベース名から派生した名前のファイルのコンパイラ検索、ファイル名を指定しません。 使用することも、 **/Fp**別の .pch ファイルを指定するオプションです。  
  
 指定した場合、 **/Yu**ファイル名のないオプションを選択しを指定しない、 **hdrstop**プラグマによって、エラー メッセージが生成およびコンパイルが成功します。  
  
 場合、 **/Yc** `filename`と **/Yu** `filename`同じコマンドラインでオプションが発生して、同じファイル名を参照両方 **/Yc** `filename`は優先順位、までのすべてのコードをプリコンパイルし、名前付きのファイルをインクルードします。 この機能は、メイクファイルの記述を簡略化します。  
  
 .Pch ファイルがコンピューター環境についての情報だけでなく、プログラムのメモリ アドレス情報を含めるためにのみが作成されたコンピューター上の pch ファイルを使用する必要があります。  
  
 プリコンパイル済みヘッダーの詳細についてを参照してください。  
  
-   [/Y (プリコンパイル済みヘッダー)](../../build/reference/y-precompiled-headers.md)  
  
-   [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  指定[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)プロジェクト内の .cpp ファイルにします。  
  
2.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
3.  **[C/C++]** フォルダーをクリックします。  
  
4.  クリックして、**プリコンパイル済みヘッダー**プロパティ ページ。  
  
5.  変更、**ファイルを作成/使用 PCH**プロパティまたは**プリコンパイル済みヘッダーの作成/使用**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>」を参照してください。  
  
## <a name="examples"></a>使用例  
 場合、次のコード。  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 コマンドラインでコンパイルされた`CL /YuMYAPP.H PROG.CPP`コンパイラは、3 つを処理しません含めるステートメントがされます、プリコンパイル済み使用コードこれにより、ファイル (および、ファイルが含まれている可能性があります) の 3 つすべての前処理に関係する時間を節約します。  
  
 使用することができます、 [/Fp (名前です。Pch ファイル)](../../build/reference/fp-name-dot-pch-file.md)オプションは、 **/Yu**名がいずれか、ファイル名引数と異なる場合は、.pch ファイルの名前を指定するオプション **/Yc**またはに示すように、ソース ファイルの基本名、次の。  
  
```  
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP  
```  
  
 このコマンドでは、MYPCH.pch をという名前のプリコンパイル済みヘッダー ファイルを指定します。 コンパイラは、すべてのヘッダー ファイルの MYAPP.h のプリコンパイル済みの状態を復元するのに内容を使用します。 コンパイラが、MYAPP.h 後に発生するコードをコンパイルし、**含める**ステートメントです。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)