---
title: -Fe (EXE ファイルの名前) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fe
dev_langs:
- C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0afd8a863c9b8482e2b7f3868047845818bd2923
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377058"
---
# <a name="fe-name-exe-file"></a>/Fe (EXE ファイルの名前の指定)

名前とディレクトリの .exe ファイルまたはコンパイラによって作成された DLL を指定します。

## <a name="syntax"></a>構文

> **/Fe**[_pathname_]  
> **/Fe:** _pathname_  

### <a name="arguments"></a>引数

*pathname*<br/>
相対パスまたは絶対パスと基本ファイル名またはディレクトリ、または生成された実行可能ファイルを使用する基本ファイル名に相対パスまたは絶対パス。

## <a name="remarks"></a>コメント

**/Fe**オプションでは、出力ディレクトリ、出力実行可能ファイル名、またはその両方、生成された実行可能ファイルを指定することができます。 場合*pathname*パスの区切り文字で終わる (**&#92;**)、出力ディレクトリのみを指定すると見なされます。 それ以外の場合の最後のコンポーネント*pathname*は出力ファイルのベース名との残りの部分として使用*pathname*出力ディレクトリを指定します。 場合*pathname*パスの区切り記号はありません。 現在のディレクトリに出力ファイル名を指定すると見なされます。 *Pathname*二重引用符で囲む必要があります (**"**) スペースなどの短いパスにすることはできません任意の文字が含まれている場合、文字、または拡張パス コンポーネント 8 文字より長く時間。

ときに、 **/Fe**オプションが指定されていない、またはで名前が指定されていない場合、ファイルの基本*pathname*コンパイラは、出力ファイルの指定された最初のソースまたはオブジェクトのファイル ベースの名前を使用して既定の名前コマンドラインと拡張子 .exe または .dll です。

指定した場合、 [(コンパイルなしのリンク)/c](c-compile-without-linking.md)オプション、 **/Fe**も何も起こりません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 開く、**構成プロパティ** > **リンカー** > **全般**プロパティ ページ。

1. 変更、**出力ファイル**プロパティです。 選択**OK**して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>」を参照してください。

## <a name="example"></a>例

次のコマンドラインは、コンパイルし、現在のディレクトリ内のすべての C ソース ファイルをリンクします。 生成された実行可能ファイルは PROCESS.exe という"C:\Users\User Name\repos\My Project\bin"のディレクトリに作成します。

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>例

次のコマンドラインでの実行可能ファイルを作成する`C:\BIN`現在のディレクトリ内の最初のソース ファイルと同じベース名。

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[パス名の指定](../../build/reference/specifying-the-pathname.md)<br/>
