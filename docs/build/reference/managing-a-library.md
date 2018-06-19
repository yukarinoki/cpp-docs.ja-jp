---
title: ライブラリの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97c6da9e12e9071b4792476d2e49739a55d7ea8e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379641"
---
# <a name="managing-a-library"></a>ライブラリの管理
LIB の既定のモードは、ビルドまたは COFF オブジェクトのライブラリの変更があります。 LIB は、/EXTRACT (オブジェクトをファイルにコピー) または/DEF (インポート ライブラリのビルド) を指定しないと、このモードで実行されます。  
  
 オブジェクトまたはライブラリからライブラリをビルドするには、次の構文を使用します。  
  
```  
LIB [options...] files...  
```  
  
 このコマンドは、1 つまたは複数の入力からライブラリを作成*ファイル*です。 *ファイル*COFF オブジェクト ファイル、32 ビット OMF オブジェクト ファイル、または既存の COFF ライブラリを指定できます。 LIB では、指定したファイルのすべてのオブジェクトが含まれている 1 つのライブラリを作成します。 入力ファイルが 32 ビット OMF オブジェクト ファイルの場合に変換された COFF ライブラリを構築する前にします。 LIB は、16 ビット版の LIB によって作成されたライブラリ内の 32 ビット OMF オブジェクトを受け入れることができません。 まず; オブジェクトを抽出するのに 16 ビット LIB を使用する必要があります。32 ビット LIB への入力として抽出したオブジェクト ファイルを使用できます。  
  
 LIB 既定では、最初のオブジェクトまたはライブラリ ファイルと、拡張機能の基本名を使用して出力ファイルの名前です。 lib です。 出力ファイルは、現在のディレクトリに格納されます。 同じ名前のファイルが既に存在する場合、出力ファイルには、既存のファイルが置き換えられます。 既存のライブラリを維持するには、/OUT オプションを使用して、出力ファイルの名前を指定します。  
  
 次のオプションは、ビルドとライブラリの変更に適用されます。  
  
 /LIBPATH: `dir`  
 環境ライブラリ パスをオーバーライドします。 詳細については、リンクの説明を参照してください。 [/LIBPATH](../../build/reference/libpath-additional-libpath.md)オプション。  
  
 /一覧表示  
 標準出力に出力ライブラリに関する情報を表示します。 出力は、ファイルにリダイレクトすることができます。 /LIST を使用すると、それを変更することがなく、既存のライブラリの内容を判断します。  
  
 /NAME:*ファイル名*  
 インポート ライブラリをビルドする場合は、インポート ライブラリを作成する対象の DLL の名前を指定します。  
  
 /NODEFAULTLIB  
 外部参照を解決するときに、検索するライブラリの一覧から 1 つまたは複数の既定のライブラリを削除します。 参照してください[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)詳細についてはします。  
  
 /入力出力:*ファイル名*  
 既定の出力ファイル名をオーバーライドします。 既定では、コマンドラインと拡張機能では、最初のライブラリまたはオブジェクトの次のファイルの基本名と、現在のディレクトリに出力ライブラリが作成されます。 lib です。  
  
 削除:*オブジェクト*  
 指定した*オブジェクト*出力ライブラリからです。 LIB、出力ライブラリを作成 (オブジェクト ファイルまたはライブラリでは問わず)、すべてのオブジェクトを結合して/REMOVE で指定されたオブジェクトが削除されます。  
  
 /SUBSYSTEM: {コンソール&AMP;#124;EFI_APPLICATION &AMP;#124; EFI_BOOT_SERVICE_DRIVER &AMP;#124; EFI_ROM &AMP;#124; EFI_RUNTIME_DRIVER&AMP;#124;ネイティブ&AMP;#124;POSIX &AMP;#124; WINDOWS &AMP;#124; WINDOWSCE} [、#[. ##]  
 オペレーティング システムに出力ライブラリにリンクすることによって作成されたプログラムを実行する方法を説明します。 詳細については、リンクの説明を参照してください。 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)オプション。  
  
 コマンドラインで指定された LIB オプションは、大文字と小文字ではありません。  
  
 LIB を使用して、次のライブラリ管理タスクを実行できます。  
  
-   オブジェクトをライブラリに追加するのには、既存のライブラリのファイル名と新しいオブジェクトのファイル名を指定します。  
  
-   ライブラリを結合するには、ライブラリのファイル名を指定します。 オブジェクトを追加し、1 つの LIB コマンドとライブラリを結合できます。  
  
-   ライブラリ メンバーを新しいオブジェクトで置き換えるには、置き換えられるメンバー オブジェクトを含むライブラリと、新しいオブジェクト (または含まれているライブラリ) のファイル名を指定します。 同じ名前を持つオブジェクトは、1 つ以上の入力ファイル内に存在、LIB によって出力ライブラリに LIB コマンドで指定された最後のオブジェクトが保存されます。 ライブラリ メンバーを置換するときは、古いオブジェクトが含まれているライブラリの後に、新しいオブジェクトまたはライブラリを指定することを確認します。  
  
-   ライブラリからメンバーを削除するには、/REMOVE オプションを使用します。 LIB は、/REMOVE コマンド ライン順序に関係なく、すべての入力オブジェクトを結合した後の任意の仕様を処理します。  
  
> [!NOTE]
>  メンバーを削除両方と同じ手順でファイルを抽出できません。 /EXTRACT を使用して、メンバー オブジェクトを抽出しを使用して再び/REMOVE LIB を実行する必要があります最初。 この動作は、他の Microsoft 製品で提供される (OMF ライブラリ) の 16 ビット LIB の動作とは異なります。  
  
## <a name="see-also"></a>関連項目  
 [LIB リファレンス](../../build/reference/lib-reference.md)