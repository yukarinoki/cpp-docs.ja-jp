---
description: 詳細については、「ライブラリの管理」を参照してください。
title: ライブラリの管理
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLibrarianTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLibrarianTool.AdditionalDependencies
- VC.Project.VCLibrarianTool.RemoveObjects
- VC.Project.VCLibrarianTool.LibraryPaths
- VC.Project.VCLibrarianTool.OutputFile
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryNames
- VC.Project.VCLibrarianTool.AdditionalLibraryDirectories
- VC.Project.VCLibrarianTool.ListContentsFile
- VC.Project.VCLibrarianTool.ListContents
- VC.Project.VCLibrarianTool.SubSystemVersion
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryName
- VC.Project.VCLibrarianTool.SubSystem
helpviewer_keywords:
- /LIBPATH library manager option
- OUT library manager option
- CONVERT library manager option
- LIBPATH library manager option
- /LIST library manager option
- object files, building and modifying
- -LINK50COMPAT library manager option
- REMOVE library manager option
- SUBSYSTEM library manager option
- /LINK50COMPAT library manager option
- /OUT library manager option
- LIB [C++], managing COFF libraries
- -CONVERT library manager option
- LINK50COMPAT library manager option
- -OUT library manager option
- -REMOVE library manager option
- -LIST library manager option
- /SUBSYSTEM library manager option
- -SUBSYSTEM library manager option
- /REMOVE library manager option
- -LIBPATH library manager option
- object files
- LIST library manager option
- /CONVERT library manager option
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
ms.openlocfilehash: f862dfd460bb51cdf6e855c87b08b7426a5642d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199130"
---
# <a name="managing-a-library"></a>ライブラリの管理

LIB の既定のモードでは、COFF オブジェクトのライブラリを構築または変更します。 [/EXTRACT] (オブジェクトをファイルにコピーする場合) または [/DEF] (インポートライブラリをビルドする場合) を指定しない場合、LIB はこのモードで実行されます。

オブジェクトやライブラリからライブラリをビルドするには、次の構文を使用します。

```
LIB [options...] files...
```

このコマンドは、1つまたは複数の入力 *ファイル* からライブラリを作成します。 これらの *ファイル* には、coff オブジェクトファイル、32ビットの OMF オブジェクトファイル、または既存の coff ライブラリを指定できます。 LIB では、指定されたファイル内のすべてのオブジェクトを含むライブラリが1つ作成されます。 入力ファイルが32ビットの OMF オブジェクトファイルの場合、ライブラリを構築する前に、LIB によって COFF に変換されます。 LIB は、16ビットバージョンの LIB によって作成されたライブラリ内の32ビット OMF オブジェクトを受け付けることができません。 まず、16ビットの LIB を使用してオブジェクトを抽出する必要があります。その後、抽出されたオブジェクトファイルを32ビットの LIB への入力として使用できます。

既定では、LIB は、最初のオブジェクトまたはライブラリファイルの基本名と拡張子 .lib を使用して、出力ファイルに名前を指定します。 出力ファイルは現在のディレクトリに配置されます。 同じ名前のファイルが既に存在する場合は、出力ファイルによって既存のファイルが置き換えられます。 既存のライブラリを保持するには、/OUT オプションを使用して、出力ファイルの名前を指定します。

ライブラリのビルドと変更には、次のオプションが適用されます。

**/Libpath:** *dir*<br/>
環境ライブラリ パスをオーバーライドします。 詳細については、「 [/libpath](libpath-additional-libpath.md) オプションのリンク」の説明を参照してください。

**/LIST**<br/>
出力ライブラリに関する情報を標準出力に表示します。 出力をファイルにリダイレクトできます。 /LIST を使用すると、既存のライブラリの内容を変更せずに確認できます。

**/Name:** *ファイル名*<br/>
インポートライブラリの作成時に、インポートライブラリを作成する DLL の名前を指定します。

**/NODEFAULTLIB**<br/>
外部参照を解決するときに検索するライブラリの一覧から、1つまたは複数の既定のライブラリを削除します。 詳細については、「 [/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) 」を参照してください。

**/Out:** *ファイル名*<br/>
既定の出力ファイル名をオーバーライドします。 既定では、出力ライブラリは現在のディレクトリに作成され、最初のライブラリファイルまたはオブジェクトファイルのベース名がコマンドラインと拡張子 .lib になります。

**/Remove:** *オブジェクト*<br/>
指定された *オブジェクト* を出力ライブラリから除外します。 LIB は、すべてのオブジェクト (オブジェクトファイルまたはライブラリ内にあるかどうか) を組み合わせて出力ライブラリを作成し、/REMOVE. で指定されたオブジェクトを削除します。

**/SUBSYSTEM:**{**CONSOLE** &#124; **EFI_APPLICATION** &#124; **EFI_BOOT_SERVICE_DRIVER** &#124; **EFI_ROM** &#124; **EFI_RUNTIME_DRIVER** &#124; **ネイティブ** &#124; **POSIX** &#124; **WINDOWS** &#124; **WINDOWSCE**} [, # [. # #]]<br/>
出力ライブラリにリンクすることによって作成されたプログラムを実行する方法をオペレーティングシステムに指示します。 詳細については、LINK [/SUBSYSTEM](subsystem-specify-subsystem.md) オプションの説明を参照してください。

コマンドラインで指定した LIB オプションでは、大文字と小文字が区別されません。

LIB を使用して、次のライブラリ管理タスクを実行できます。

- オブジェクトをライブラリに追加するには、既存のライブラリのファイル名と新しいオブジェクトのファイル名を指定します。

- ライブラリを結合するには、ライブラリファイル名を指定します。 1つの LIB コマンドで、オブジェクトを追加したり、ライブラリを結合したりすることができます。

- ライブラリメンバーを新しいオブジェクトに置き換えるには、置換するメンバーオブジェクトを含むライブラリと、新しいオブジェクト (またはそれを含むライブラリ) のファイル名を指定します。 同じ名前のオブジェクトが複数の入力ファイルに存在する場合、LIB は LIB コマンドで指定された最後のオブジェクトを出力ライブラリに格納します。 ライブラリメンバーを置換する場合は、古いオブジェクトが含まれているライブラリの後に新しいオブジェクトまたはライブラリを指定してください。

- ライブラリからメンバーを削除するには、/REMOVE オプションを使用します。 LIB は、コマンドラインの順序に関係なく、すべての入力オブジェクトを結合した後に、/REMOVE のすべての仕様を処理します。

> [!NOTE]
> 同じ手順で、メンバーを削除してファイルに抽出することはできません。 まず、/EXTRACT を使用してメンバーオブジェクトを抽出し、次に/REMOVE. を使用して再度 LIB を実行する必要があります。 この動作は、他の Microsoft 製品で提供される16ビット LIB (OMF ライブラリの場合) とは異なります。

## <a name="see-also"></a>関連項目

[LIB リファレンス](lib-reference.md)
