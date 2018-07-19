---
title: -Yc (プリコンパイル済みヘッダー ファイルの作成) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
dev_langs:
- C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f26121c80378f4317d02f51582ad67033972765
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378663"
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (プリコンパイル済みヘッダー ファイルの作成)
特定の時点でのコンパイルの状態を表すプリコンパイル済みヘッダー (.pch) ファイルを作成するようにコンパイラに指示します。  
  
## <a name="syntax"></a>構文  
  
> __/Yc__
>  __/Yc__*ファイル名*  
  
  
## <a name="arguments"></a>引数  
*ファイル名*  
 ヘッダー (.h) ファイルを指定します。 この引数を使用すると、コンパイラは、.h ファイルを含むすべてのコードをコンパイルします。  
  
## <a name="remarks"></a>コメント  
 ときに **/Yc**なしで指定された引数またはベース ファイル内の点を基本ソース ファイルの最後までのすべてのコードをコンパイルしている、 [hdrstop](../../preprocessor/hdrstop.md)ディレクティブがします。 結果として得られる .pch ファイルは、同じ基本名と、基本ソース ファイルを使用して別のファイル名を指定していない限り、 **hdrstop**プラグマ、または **/Fp**オプション。  
  
 プリコンパイルされたコードがで指定されたファイルのベース名から作成された名前のファイルに保存、 **/Yc**オプションと拡張子を .pch です。 使用することも、 [/Fp (名前です。Pch ファイル)](../../build/reference/fp-name-dot-pch-file.md)プリコンパイル済みヘッダー ファイルの名前を指定するにはオプションです。  
  
 使用する場合 __/Yc__*filename*、以降での使用の指定したファイルを含むすべてのコードをコンパイルして、 [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)オプション。  
  
 場合オプション __/Yc__*filename*と __/Yu__*filename*同じコマンドラインで発生し、両方を参照しているか、同じファイル名を意味します。__/Yc__*filename*が優先されます。 この機能は、メイクファイルの記述を簡略化します。  
  
 プリコンパイル済みヘッダーの詳細についてを参照してください。  
  
-   [/Y (プリコンパイル済みヘッダー)](../../build/reference/y-precompiled-headers.md)  
  
-   [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  .Cpp ファイルを選択します。 .Cpp ファイルである必要があります #include プリコンパイル済みヘッダーの情報を含む .h ファイルです。 プロジェクトの **/Yc**ファイル レベルで設定をオーバーライドできます。  
  
2.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
3.  開く、**構成プロパティ**、 **C/C++**、**プリコンパイル済みヘッダー**プロパティ ページ。  
  
4.  変更、**プリコンパイル済みヘッダーの**プロパティです。  
  
5.  ファイル名を設定するには、変更、**プリコンパイル済みヘッダー ファイル**プロパティです。
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコードがあるとします。  
  
```cpp  
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
// ...  
```  
  
コマンドを使用してこのコードをコンパイルするときに`CL /YcMYAPP.H PROG.CPP`コンパイラは、AFXWIN.h、RESOURCE.h のすべての前処理を保存、およびプリコンパイル済みヘッダー ファイルで MYAPP.h というされます。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)[プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)