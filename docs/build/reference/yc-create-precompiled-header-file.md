---
title: /Yc (プリコンパイル済みヘッダー ファイルの作成)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
ms.openlocfilehash: bda384152962bc59ab37b1aae138091aa6f4514c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536841"
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (プリコンパイル済みヘッダー ファイルの作成)

コンパイラで特定の時点のコンパイルの状態を表すプリコンパイル済みヘッダー (.pch) ファイルを作成するように指示します。

## <a name="syntax"></a>構文

> __/Yc__<br/>
> __/Yc__*ファイル名*

## <a name="arguments"></a>引数

*ファイル名*<br/>
ヘッダー (.h) ファイルを指定します。 この引数を使用すると、コンパイラは、.h ファイルを含むすべてのコードをコンパイルします。

## <a name="remarks"></a>Remarks

ときに **/Yc**なしで指定された引数、またはベースのファイル内のポイントに、ベースのソース ファイルの最後までのすべてのコードをコンパイルしている、 [hdrstop](../../preprocessor/hdrstop.md)ディレクティブに発生します。 使用して別のファイル名を指定しない限り .pch ファイルの結果として得られるが、ベースのソース ファイルと同じ基本名を持つ、 **hdrstop**プラグマまたは **/Fp**オプション。

指定したファイルのベース名から作成された名前のプリコンパイルされたコードをファイルに保存、 **/Yc**オプションと拡張子 .pch をします。 使用することも、 [/Fp (名前です。Pch ファイル)](../../build/reference/fp-name-dot-pch-file.md)プリコンパイル済みヘッダー ファイルの名前を指定するオプション。

使用する場合 __/Yc__*filename*でその後使用するため、指定したファイルを含むすべてのコードをコンパイルして、 [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)オプション。

場合、オプション __/Yc__*filename*と __/Yu__*filename*同じコマンド行で発生し、両方の参照、または、同じファイル名を意味します。__/Yc__*filename*が優先されます。 この機能は、メイクファイルの記述を簡略化します。

プリコンパイル済みヘッダーの詳細についてを参照してください。

- [/Y (プリコンパイル済みヘッダー)](../../build/reference/y-precompiled-headers.md)

- [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. .Cpp ファイルを選択します。 .Cpp ファイルである必要があります #include プリコンパイル済みヘッダーの情報を含む .h ファイル。 プロジェクトの **/Yc**ファイル レベルで設定をオーバーライドできます。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 開く、**構成プロパティ**、 **C/C++**、**プリコンパイル済みヘッダー**プロパティ ページ。

1. 変更、**プリコンパイル済みヘッダーの**プロパティ。

1. ファイル名を設定するには、変更、**プリコンパイル済みヘッダー ファイル**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> 」および「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>」を参照してください。

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

コマンドを使用してこのコードをコンパイルするときに`CL /YcMYAPP.H PROG.CPP`コンパイラは、AFXWIN.h、RESOURCE.h のすべての前処理を保存し、プリコンパイル済みヘッダー ファイルで MYAPP.h というされます。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)