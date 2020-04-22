---
title: /Fo (オブジェクト ファイル名)
description: Visual Studio の Microsoft C++ /Fo (オブジェクト ファイル名) コンパイラ オプションのリファレンス ガイド。
ms.date: 04/20/2020
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
ms.openlocfilehash: cd22ba745128fe1df67853d98c1495491b9ca840
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748976"
---
# <a name="fo-object-file-name"></a>/Fo (オブジェクト ファイルの名前の指定)

デフォルトの代わりに*`.obj`* 使用するオブジェクト () ファイル名またはディレクトリを指定します。

## <a name="syntax"></a>構文

> **`/Fo`**_パス_

## <a name="remarks"></a>解説

コンパイラー・オプション**`/Fo`** を使用して、CL コンパイラー・コマンドによって生成されたすべてのオブジェクト・ファイルの出力ディレクトリーを設定できます。 または、このファイルを使用して、単一のオブジェクト ファイルの名前を変更できます。

既定では、コンパイラによって生成されたオブジェクト ファイルは、現在のディレクトリに配置されます。 ソース ファイルの基本名と拡張子が付*`.obj`* けられます。

このオプションを**`/Fo`** 使用してオブジェクトファイルの名前を変更するには、出力ファイル名を*引数 pathname*として指定します。 オブジェクト ファイルの名前を変更する場合は、任意の名前と拡張子を使用できますが、推奨される規則は*`.obj`* を使用することです。 コンパイルするソース ファイルを複数指定**`/Fo`** した場合にファイル名を指定すると、コンパイラはコマンド ライン エラー D8036 を生成します。

オプションを**`/Fo`** 使用して、CL コマンドで作成されたすべてのオブジェクト・ファイルの出力ディレクトリーを設定するには *、pathname*引数としてディレクトリーを指定します。 ディレクトリは *、引数 pathname*の末尾のスラッシュで示されます。 指定されたディレクトリが存在する必要があります。自動的に作成されません。

## <a name="example"></a>例

次のコマンド ラインは、ドライブ D 上の既存のディレクトリ*\\(中間*) に*sample.obj*という名前のオブジェクト ファイルを作成します。

```cmd
CL /Fo"D:\intermediate\" /EHsc /c sample.cpp
```

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>オプションを Visual Studio で設定するか、プログラムで設定する

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ** > **C/C++** > **出力ファイル]** プロパティ ページを選択します。

1. **[オブジェクト ファイル名]** プロパティを変更して、出力ディレクトリを設定します。 IDE では、オブジェクトファイルの拡張子が*`.obj`*.

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[パス名の指定](specifying-the-pathname.md)
