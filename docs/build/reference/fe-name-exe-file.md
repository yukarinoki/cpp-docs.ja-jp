---
title: /Fe (EXE ファイルの名前の指定)
ms.date: 11/04/2016
f1_keywords:
- /fe
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
ms.openlocfilehash: f0bd8f3a96555cc29d06f74fb44a73bbed32889b
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825579"
---
# <a name="fe-name-exe-file"></a>/Fe (EXE ファイルの名前の指定)

コンパイラによって作成された .exe ファイルまたは DLL の名前とディレクトリを指定します。

## <a name="syntax"></a>構文

> **/Fe**[_パス名_] \
> **/Fe:** _パス名_

### <a name="arguments"></a>引数

*パス名*<br/>
相対パスまたは絶対パスと基本ファイル名、またはディレクトリへの相対パスまたは絶対パス、または生成された実行可能ファイルに使用する基本ファイル名。

## <a name="remarks"></a>解説

**/Fe**オプションを使用すると、生成された実行可能ファイルに対して出力ディレクトリ、出力実行可能ファイル名、またはその両方を指定できます。 パスの区切り記号 (**&#92;**) でパス*名*が終了した場合、出力ディレクトリのみを指定すると見なされます。 それ以外の場合は、*パス名*の最後のコンポーネントが出力ファイルのベース名として使用され、残りの*パス名*は出力ディレクトリを指定します。 パス*名*にパスの区切り文字がない場合は、現在のディレクトリに出力ファイル名を指定することを前提としています。 パス*名*を二重引用符 (**"**) で囲む必要があります。これには、スペース、拡張文字、パスコンポーネントの長さが8文字を超える文字が含まれています。

**/Fe**オプションが指定されていない場合、またはファイルのベース名が*pathname*に指定されていない場合、コンパイラは、コマンドラインで指定された最初のソースファイルまたはオブジェクトファイルのベース名、および拡張子 .exe または .dll を使用して、出力ファイルに既定の名前を付けます。

[/C (リンクを使用せずにコンパイル)](c-compile-without-linking.md)オプションを指定すると、 **/Fe**は無効になります。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **構成プロパティ** > の [**リンカー** > **全般**] プロパティページを開きます。

1. "**出力ファイル**" プロパティを変更します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A> 」を参照してください。

## <a name="example"></a>例

次のコマンドラインは、現在のディレクトリにあるすべての C ソースファイルをコンパイルしてリンクします。 生成された実行可能ファイルの名前は、"C:\Users\User Name\repos\My Project\bin" というディレクトリに作成されます。

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>例

次のコマンドラインは、現在のディレクトリ`C:\BIN`内の最初のソースファイルと同じベース名を使用して、に実行可能ファイルを作成します。

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[パス名の指定](specifying-the-pathname.md)<br/>
