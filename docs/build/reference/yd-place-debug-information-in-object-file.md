---
description: 詳細については、「/Yd (デバッグ情報をオブジェクトファイルに配置する)」を参照してください。
title: /Yd (デバッグ情報のオブジェクト ファイルへの取り込み)
ms.date: 11/04/2016
f1_keywords:
- /yd
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
ms.openlocfilehash: 7716d5ca1893faefac9186f97e2f7439a3887343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243589"
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd (デバッグ情報のオブジェクト ファイルへの取り込み)

性能は、 [/yc](yc-create-precompiled-header-file.md) オプションと [/Z7](z7-zi-zi-debug-information-format.md) オプションと共に使用すると、プリコンパイル済みヘッダー (.pch) ファイルから作成されたすべてのオブジェクトファイルのデバッグ情報を補完します。 非推奨になりました。

## <a name="syntax"></a>構文

```
/Yd
```

## <a name="remarks"></a>解説

**/Yd** は非推奨とされます。Visual C++ は、1つの .pdb ファイルに書き込む複数のオブジェクトをサポートするようになりました。代わりに **/zi** を使用してください。 非推奨のコンパイラオプションの一覧については、「[カテゴリ別に一覧表示さ](compiler-options-listed-by-category.md)れたコンパイラオプションの **非推奨のコンパイラオプション**」を参照してください。

デバッグ情報を含むライブラリを配布する必要がない場合は、 **/Z7** と **/yd** ではなく、 [/zi](z7-zi-zi-debug-information-format.md)オプションを使用します。

すべての .obj ファイルに完全なデバッグ情報を格納する必要があるのは、デバッグ情報を含むライブラリを配布する場合のみです。 コンパイル速度が低下し、かなりのディスク領域が必要になります。 **/Yd** を指定せずに **/yc** と **/Z7** を使用すると、コンパイラは、.pch ファイルから作成された最初の .obj ファイルに共通のデバッグ情報を格納します。 コンパイラは、この情報を .pch ファイルから作成された .obj ファイルに挿入しません。このメソッドは、情報への相互参照を挿入します。 .Pch ファイルを使用する .obj ファイルの数に関係なく、1つの .obj ファイルに共通のデバッグ情報が含まれています。

この既定の動作では、ビルド時間が短縮され、ディスク領域の要求が減少しますが、小さな変更に共通のデバッグ情報を含む .obj ファイルを再構築する必要がある場合は、望ましくありません。 この場合、コンパイラは、元の .obj ファイルへの相互参照を含むすべての .obj ファイルをリビルドする必要があります。 また、複数のプロジェクトで共通の .pch ファイルが使用されている場合、単一の .obj ファイルへの相互参照に依存することは困難です。

プリコンパイル済みヘッダーの詳細については、以下を参照してください。

- [/Y (プリコンパイル済みヘッダー)](y-precompiled-headers.md)

- [プリコンパイル済みヘッダーファイル](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="examples"></a>例

2つの基本ファイル (F .cpp と、それぞれにこれらの **#include** ステートメントを含む) があるとします。

```
#include "windows.h"
#include "etc.h"
```

次のコマンドは、プリコンパイル済みヘッダーファイル、.pch、オブジェクトファイルを作成します。

```
CL /YcETC.H /Z7 F.CPP
```

オブジェクトファイルの F .obj には、WINDOWS .h およびその他の .h (およびその他のヘッダーファイル) の型およびシンボル情報が含まれています。 プリコンパイル済みヘッダーを使用して、ソースファイルをコンパイルすることができます。

```
CL /YuETC.H /Z7 G.CPP
```

オブジェクトファイルの .obj には、プリコンパイル済みヘッダーのデバッグ情報は含まれませんが、単に F .obj ファイル内の情報を参照します。 F .obj ファイルとリンクする必要があることに注意してください。

プリコンパイル済みヘッダーが **/Z7** を使用してコンパイルされていない場合でも、 **/Z7** を使用した後のコンパイルで使用できます。 ただし、デバッグ情報は現在のオブジェクトファイルに配置され、プリコンパイル済みヘッダーに定義されている関数と型のローカルシンボルは、デバッガーでは使用できません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
