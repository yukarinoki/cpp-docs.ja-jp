---
description: 詳細については、「/Fd (プログラムデータベースファイル名)」を参照してください。
title: /Fd (プログラム データベース ファイル名)
ms.date: 11/04/2016
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
ms.openlocfilehash: 3990cdd6c560dfdeaef7078a29e965831c2a9504
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200664"
---
# <a name="fd-program-database-file-name"></a>/Fd (プログラム データベース ファイル名)

[/Z7、/zi、/zi (デバッグ情報の形式)](z7-zi-zi-debug-information-format.md)によって作成されたプログラムデータベース (PDB) ファイルのファイル名を指定します。

## <a name="syntax"></a>構文

```
/Fdpathname
```

## <a name="remarks"></a>解説

**/Fd** を使用しない場合、pdb ファイル名は既定で VC *x* 0 .pdb に設定されます。ここで *x* は、使用されている Visual C++ のメジャーバージョンです。

ファイル名を含まないパス名 (パスは円記号で終わる) を指定すると、コンパイラは、指定されたディレクトリに VC *x* 0 .pdb という名前の .pdb ファイルを作成します。

拡張子を含まないファイル名を指定すると、コンパイラは拡張子として .pdb を使用します。

このオプションは、最小限のリビルドとインクリメンタルコンパイルに使用される状態 (.idb) ファイルにも名前を指定します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[出力ファイル]** プロパティ ページをクリックします。

1. **プログラムデータベースの "ファイル名**" プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>

## <a name="example"></a>例

このコマンドラインでは、PROG という名前の .pdb ファイルと、PROG という名前の .idb ファイルを作成します。

```
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP
```

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[パス名の指定](specifying-the-pathname.md)
