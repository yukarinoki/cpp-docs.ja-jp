---
description: '詳細情報: `/Fi` (出力ファイル名のプリプロセス)'
title: /Fi (出力ファイル名のプリプロセス)
ms.date: 08/12/2020
f1_keywords:
- /Fi
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
ms.openlocfilehash: c598730b19b843aa312df71d745ed363d082cc43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192227"
---
# <a name="fi-preprocess-output-file-name"></a>`/Fi` (プリプロセス出力ファイル名)

[ `/P` (ファイルにプリプロセスする)](p-preprocess-to-a-file.md)コンパイラオプションが前処理された出力を書き込む出力ファイルの名前を指定します。

## <a name="syntax"></a>構文

> **`/Fi`**_`pathname`_

### <a name="parameters"></a>パラメーター

*`pathname`*\
コンパイラオプションによって生成される出力ファイルの相対パスまたは絶対パスとファイル名 **`/P`** 。 または、複数の *`.i`* 入力ファイルが指定されている場合は、出力ファイルのディレクトリパス。 オプションとの間にスペースを入れないで **`/Fi`** *`pathname`* ください。

## <a name="remarks"></a>解説

コンパイラオプションを **`/Fi`** コンパイラオプションと組み合わせて使用し **`/P`** ます。 が **`/P`** 指定されていない場合は、 **`/Fi`** コマンドラインの警告 D9007 が発生します。

パラメーターのディレクトリパス (円記号で終わるパス) のみを指定した場合 **`\`** *`pathname`* は、ソースファイルのベース名が、前処理された出力ファイルのベース名として使用されます。 パラメーターには、 *`pathname`* 特定のファイル名拡張子は必要ありません。 ただし、ファイル名拡張子を指定しない場合は ". i" の拡張子が使用されます。

### <a name="example"></a>例

次のコマンドラインでは、プリコードを実行し、 *`PROGRAM.cpp`* コメントを保持 [`#line`](../../preprocessor/hash-line-directive-c-cpp.md) し、ディレクティブを追加して、結果をファイルに書き込み *`MYPROCESS.i`* ます。

```cmd
CL /P /FiMYPROCESS.I PROGRAM.CPP
```

このコマンドラインは、次のように、とと *`main.cpp`* *`helper.cpp`* *`main.i`* *`helper.i`* いう名前のサブディレクトリにとを組み込み *`preprocessed`* ます。

```cmd
CL /P /Fi".\\preprocessed\\" main.cpp helper.cpp
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. ソースファイルまたはプロジェクトの [ **プロパティページ** ] ダイアログボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**] [  >  **プリプロセッサ**] プロパティページを選択します。

1. [前処理] を [ **ファイル** ] プロパティに **[はい]** に設定します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **`/Fi`** *`pathname`* **追加オプション** ] ボックスにコンパイラオプションを入力します。 プロジェクトに対してこのプロパティを設定する場合は、ファイル名ではなくディレクトリパスのみを指定してください。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[`/P` (ファイルへの前処理)](p-preprocess-to-a-file.md)<br/>
[パス名の指定](specifying-the-pathname.md)
