---
description: 詳細については、「/Yc (プリコンパイル済みヘッダーファイルの作成)」を参照してください。
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
ms.openlocfilehash: eba045c3148d0caceee3ca6f9d5352ea61726757
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243650"
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (プリコンパイル済みヘッダー ファイルの作成)

特定の時点でのコンパイルの状態を表すプリコンパイル済みヘッダー (.pch) ファイルを作成するようにコンパイラに指示します。

## <a name="syntax"></a>構文

> __/Yc__\
> __/Yc__*ファイル名*

## <a name="arguments"></a>引数

*filename*<br/>
ヘッダー (.h) ファイルを指定します。 この引数を使用すると、コンパイラは .h ファイルまでのすべてのコードをコンパイルします。

## <a name="remarks"></a>解説

引数を指定せずに **/yc** を指定すると、コンパイラは、基本ソースファイルの最後まで、または [hdrstop](../../preprocessor/hdrstop.md) ディレクティブが発生したベースファイル内のポイントまで、すべてのコードをコンパイルします。 **Hdrstop** プラグマまたは **/fp** オプションを使用して別のファイル名を指定しない限り、生成される .pch ファイルの基本名は基本のソースファイルと同じになります。

プリコンパイル済みコードは、 **/yc** オプションと .pch 拡張子を使用して指定されたファイルの基本名から作成された名前のファイルに保存されます。 /Fp (名前を使用することもでき [ます。Pch ファイル)](fp-name-dot-pch-file.md) オプション。プリコンパイル済みヘッダーファイルの名前を指定します。

__/Yc__*filename* を使用すると、コンパイラは、指定されたファイルまでのすべてのコードをコンパイルし、その後、 [/Yu (プリコンパイル済みヘッダーファイルを使用)](yu-use-precompiled-header-file.md)オプションを使用します。

__/Yc__*filename と* __/yu__*filename* オプションが同じコマンドラインで実行され、同じファイル名を指定している場合は、 __/yc__*filename* が優先されます。 この機能により、メイク文書の記述が簡単になります。

プリコンパイル済みヘッダーの詳細については、以下を参照してください。

- [/Y (プリコンパイル済みヘッダー)](y-precompiled-headers.md)

- [プリコンパイル済みヘッダーファイル](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. .Cpp ファイルを選択します。 .Cpp ファイルは、プリコンパイル済みヘッダー情報が含まれている .h ファイルを #include 必要があります。 プロジェクトの **/yc** 設定は、ファイルレベルでオーバーライドできます。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成プロパティ**]、[ **c/c + +**]、[ **プリコンパイル済みヘッダー** ] の各プロパティページを開きます。

1. **プリコンパイル済みヘッダー** プロパティを変更します。

1. ファイル名を設定するには、 **プリコンパイル済みヘッダーファイル** のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> と <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A> を参照してください。

## <a name="example"></a>例

次のコードについて考えてみます。

```cpp
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
// ...
```

このコードがコマンドでコンパイルされると `CL /YcMYAPP.H PROG.CPP` 、コンパイラは、afxwin.h、resource.h、および myapp のすべての前処理を、myapp という名前のプリコンパイル済みヘッダーファイルに保存します。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[プリコンパイル済みヘッダーファイル](../creating-precompiled-header-files.md)
