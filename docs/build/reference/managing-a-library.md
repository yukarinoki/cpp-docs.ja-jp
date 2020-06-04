---
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
ms.openlocfilehash: de55059834a0887d487b7be38377af9984512b75
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336400"
---
# <a name="managing-a-library"></a>ライブラリの管理

LIB のデフォルトモードでは、COFF オブジェクトのライブラリを構築または変更します。 LIB は、/EXTRACT (オブジェクトをファイルにコピーする場合) または /DEF (インポート ライブラリをビルドする場合) を指定しない場合に、このモードで実行されます。

オブジェクトまたはライブラリからライブラリをビルドするには、次の構文を使用します。

```
LIB [options...] files...
```

このコマンドは、1 つ以上の入力*ファイル*からライブラリを作成します。 *ファイル*は、COFF オブジェクト・ファイル、32 ビット OMF オブジェクト・ファイル、または既存の COFF ライブラリーにすることができます。 LIB は、指定されたファイル内のすべてのオブジェクトを含む 1 つのライブラリーを作成します。 入力ファイルが 32 ビット OMF オブジェクト・ファイルの場合、LIB はライブラリーをビルドする前に、そのファイルを COFF に変換します。 LIB は、16 ビット版の LIB で作成されたライブラリー内にある 32 ビット OMF オブジェクトを受け入れることができません。 まず、16 ビットの LIB を使用してオブジェクトを抽出する必要があります。その後、抽出したオブジェクトファイルを32ビットLIBへの入力として使用できます。

デフォルトでは、LIB は、最初のオブジェクトまたはライブラリファイルのベース名と拡張子 .lib を使用して出力ファイルに名前を付けます。 出力ファイルは、現在のディレクトリに置かれます。 同じ名前のファイルが既に存在する場合は、出力ファイルが既存のファイルを置き換えます。 既存のライブラリを保持するには、/OUT オプションを使用して出力ファイルの名前を指定します。

ライブラリの構築と変更には、次のオプションが適用されます。

**/リブパス:** *dir*<br/>
環境ライブラリ パスをオーバーライドします。 詳細については、LINK [/LIBPATH](libpath-additional-libpath.md)オプションの説明を参照してください。

**/list**<br/>
出力ライブラリに関する情報を標準出力に表示します。 出力はファイルにリダイレクトできます。 /LIST を使用すると、既存のライブラリの内容を変更せずに確認できます。

**/NAME:** *ファイル名*<br/>
インポート ライブラリをビルドするときに、インポート ライブラリをビルドする DLL の名前を指定します。

**/NODEFAULTLIB**<br/>
外部参照を解決するときに、検索するライブラリの一覧から 1 つ以上の既定のライブラリを削除します。 詳細については[、/NODEFAULTLIB](nodefaultlib-ignore-libraries.md)を参照してください。

**/OUT:** *ファイル名*<br/>
既定の出力ファイル名を上書きします。 デフォルトでは、出力ライブラリは、コマンド ラインの最初のライブラリまたはオブジェクト ファイルのベース名と拡張子 .lib を使用して、現在のディレクトリに作成されます。

**/削除:** *オブジェクト*<br/>
指定した*オブジェクト*を出力ライブラリーから除外します。 LIB は、すべてのオブジェクト (オブジェクト ファイルまたはライブラリ内) を結合し、/REMOVE で指定されたオブジェクトを削除することによって、出力ライブラリを作成します。

**/サブシステム:**{**コンソール****&#124;** &#124; **EFI_ROM** **NATIVE** **EFI_BOOT_SERVICE_DRIVER** &#124; **EFI_APPLICATION** &#124; EFI_RUNTIME_DRIVER EFI_RUNTIME_DRIVER EFI_RUNTIME_DRIVER EFI_RUNTIME_DRIVER &#124; EFI_RUNTIME_DRIVER EFI_RUNTIME_DRIVER &#124; **WINDOWSCE**&#124; &#124; **&#124;** **&#124;のネイティブ**&#124; [],#[###]<br/>
出力ライブラリにリンクして作成されたプログラムを実行する方法をオペレーティング システムに指示します。 詳しくは、LINK [/SUBSYSTEM](subsystem-specify-subsystem.md)オプションの説明を参照してください。

コマンド行で指定された LIB オプションは、大文字と小文字を区別しません。

LIB を使用して、以下のライブラリー管理タスクを実行できます。

- オブジェクトをライブラリに追加するには、既存のライブラリのファイル名と新しいオブジェクトのファイル名を指定します。

- ライブラリを結合するには、ライブラリファイル名を指定します。 オブジェクトを追加し、ライブラリを 1 つの LIB コマンドで結合できます。

- ライブラリー・メンバーを新規オブジェクトに置き換えるには、置き換えるメンバー・オブジェクトを含むライブラリーと、新規オブジェクト (またはライブラリーを含む) のファイル名を指定します。 同じ名前のオブジェクトが複数の入力ファイルに存在する場合、LIB コマンドで指定された最後のオブジェクトが出力ライブラリーに入れられます。 ライブラリ メンバーを置き換える場合は、古いオブジェクトを含むライブラリの後に新しいオブジェクトまたはライブラリを指定してください。

- ライブラリからメンバーを削除するには、/REMOVE オプションを使用します。 LIB は、コマンド行の順序に関係なく、すべての入力オブジェクトを結合した後に、/REMOVE の仕様を処理します。

> [!NOTE]
> メンバーを削除して、同じステップでファイルに抽出することはできません。 最初に /EXTRACT を使用してメンバー オブジェクトを抽出し、次に /REMOVE を使用して LIB を再実行する必要があります。 この動作は、他のマイクロソフト製品で提供されている 16 ビット LIB (OMF ライブラリ用) の動作とは異なります。

## <a name="see-also"></a>関連項目

[LIB リファレンス](lib-reference.md)
