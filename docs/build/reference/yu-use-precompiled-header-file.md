---
description: '詳細情報: `/Yu` (プリコンパイル済みヘッダーファイルの使用)'
title: /Yu (プリコンパイル済みヘッダー ファイルの使用)
ms.date: 07/31/2020
f1_keywords:
- /Yu
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
ms.openlocfilehash: 7076a3a4dd9183a3a0072fa6211acbb0b95a4865
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229964"
---
# <a name="yu-use-precompiled-header-file"></a>`/Yu` (プリコンパイル済みヘッダーファイルを使用)

現在のコンパイルで既存のプリコンパイル済みヘッダー () ファイルを使用するようにコンパイラに指示し *`.pch`* ます。

## <a name="syntax"></a>構文

> **`/Yu`**\[*ファイル名*]

## <a name="arguments"></a>引数

*filename*<br/>
プリプロセッサディレクティブを使用してソースファイルに含まれるヘッダーファイルの名前 `#include` 。

## <a name="remarks"></a>解説

インクルードファイルの名前は、 **`/Yc`** プリコンパイル済みヘッダーを作成するオプションと、 **`/Yu`** プリコンパイル済みヘッダーの使用を示す後続のオプションの両方で同じである必要があります。

では **`/Yc`** 、 *ファイル名* によって、プリコンパイルが停止するポイントが指定されます。コンパイラは、すべてのコード *ファイル* 名をプリコンパイルします。また、インクルードファイルの基本名との拡張子を使用して、生成されたプリコンパイル済みヘッダーに名前を指定し *`.pch`* ます。

ファイルは、 *`.pch`* を使用して作成されている必要があり **`/Yc`** ます。

コンパイラは、.h ファイルの前に発生したすべてのコードをプリコンパイル済みとして扱います。 `#include`ファイルに関連付けられているディレクティブを超えてスキップし *`.h`* 、ファイルに含まれるコードを使用して、ファイル *`.pch`* *名* の後にすべてのコードをコンパイルします。

コマンドラインで、と filename の間にスペースを使用することはできません **`/Yu`** 。 

**`/Yu`** ファイル名を指定せずにオプションを指定する場合、ソースプログラムには [`#pragma hdrstop`](../../preprocessor/hdrstop.md) プリコンパイル済みヘッダーファイルのファイル名を指定するプラグマが含まれている必要があり *`.pch`* ます。 この場合、コンパイラは、によって指定されたプリコンパイル済みヘッダー ( *`.pch`* ファイル) を使用 [`/Fp (Name .pch file)`](fp-name-dot-pch-file.md) します。 コンパイラは、そのプラグマの位置をスキップし、指定されたプリコンパイル済みヘッダーファイルからコンパイル済みの状態を復元します。 次に、プラグマの後のコードのみがコンパイルされます。 `#pragma hdrstop`でファイル名が指定されていない場合、コンパイラは、ソースファイルのベース名から派生した拡張子を持つファイルを検索し *`.pch`* ます。 オプションを使用して **`/Fp`** 別のファイルを指定することもでき *`.pch`* ます。

ファイル名を指定せずにオプションを指定し、プラグマを指定しなかった場合は、 **`/Yu`** `hdrstop` エラーメッセージが生成され、コンパイルは失敗します。

**`/Yc`** _Filename_ オプションと **`/Yu`** _filename_ オプションが同じコマンドラインで実行され、両方とも同じファイル名を参照している場合は、 **`/Yc`** _filename_ が優先され、名前付きファイルまでのすべてのコードがプリコンパイルされます。 この機能により、メイク文書の記述が簡単になります。

ファイルには、 *`.pch`* プログラムに関するコンピューター環境とメモリアドレスに関する情報が含まれているため、 *`.pch`* ファイルを作成したコンピューター上のファイルのみを使用してください。

プリコンパイル済みヘッダーの詳細については、以下を参照してください。

- [`/Y` (プリコンパイル済みヘッダー)](y-precompiled-headers.md)

- [プリコンパイル済みヘッダー ファイル](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの .cpp ファイルで[ `/Yc` (プリコンパイル済みヘッダーファイルの作成)](yc-create-precompiled-header-file.md)を指定します。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **プリコンパイル済みヘッダー** ] プロパティページを選択します。

1. **プリコンパイル済みヘッダー** プロパティ、"ファイルを使用した **PCH の作成/使用**" プロパティ、または "**プリコンパイル済みヘッダーの作成/使用**" プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> と <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A> を参照してください。

## <a name="example"></a>例

次のコードがあるとします。

```cpp
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
...
```

はコマンドラインを使用してコンパイルされますが、 `CL /YuMYAPP.H PROG.CPP` コンパイラは3つの include ステートメントを処理しません。 代わりに、のプリコンパイル済みコードを使用し *`MYAPP.pch`* ます。これにより、3つすべてのファイル (および含まれるすべてのファイル) の前処理にかかる時間が短縮されます。

オプションをオプションと共に使用すると、 [`/Fp (Name .pch file)`](fp-name-dot-pch-file.md) **`/Yu`** 次の *`.pch`* 例に示すように、ファイル名がの *filename* 引数 **`/Yc`** またはソースファイルのベース名のいずれかと異なる場合に、ファイル名を指定できます。

```cmd
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP
```

このコマンドは、という名前のプリコンパイル済みヘッダーファイルを指定し *`MYPCH.pch`* ます。 コンパイラはその内容を使用して、すべてのヘッダーファイルのプリコンパイル済み状態を復元し *`MYAPP.h`* ます。 次に、コンパイラは * ディレクティブの後に出現するコードをコンパイルし `#include "MYAPP.h"` ます。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
