---
title: LINK からの出力
ms.date: 11/04/2016
helpviewer_keywords:
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
ms.openlocfilehash: 8323723f2049d3db469e874c91b99f4cfb561c72
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439317"
---
# <a name="link-output"></a>LINK からの出力

リンクの出力には、.exe ファイル、Dll、mapfiles、およびメッセージが含まれます。

##  <a name="_core_output_files"></a>出力ファイル

リンクからの既定の出力ファイルは .exe ファイルです。 [/Dll](dll-build-a-dll.md)オプションが指定されている場合、LINK は .dll ファイルをビルドします。 出力ファイル名は、[出力ファイル名 (/out)](out-output-file-name.md)オプションを使用して制御できます。

インクリメンタルモードでは、リンクを使用すると、プログラムの後で増分ビルドを行うための状態情報を保持するための .ilk ファイルが作成されます。 .Ilk ファイルの詳細については、「 [.Ilk ファイル](dot-ilk-files-as-linker-input.md)」を参照してください。 インクリメンタルリンクの詳細については、「[インクリメンタル (/INCREMENTAL)](incremental-link-incrementally.md)オプションのリンク」を参照してください。

リンクによって、エクスポート (通常は DLL) を含むプログラムが作成されるときに、ビルドで .exp ファイルが使用されていない限り、.lib ファイルもビルドされます。 インポートライブラリのファイル名は、 [/IMPLIB](implib-name-import-library.md)オプションを使用して制御できます。

[[マップの生成 (/map)](map-generate-mapfile.md) ] オプションが指定されている場合、LINK は mapfile を作成します。

[[デバッグ情報の生成 (/debug)](debug-generate-debug-info.md) ] オプションが指定されている場合、LINK はプログラムのデバッグ情報を格納する PDB を作成します。

##  <a name="_core_other_output"></a>その他の出力

他のコマンドライン入力を使用せずに `link` を入力すると、そのオプションを要約する使用法ステートメントがリンクに表示されます。

リンクは著作権およびバージョンメッセージを表示し、[著作権情報の[非](nologo-suppress-startup-banner-linker.md)表示] オプションを使用しない限り、コマンドファイル入力をエコーします。

[[進行状況メッセージの印刷] (/verbose)](verbose-print-progress-messages.md)オプションを使用すると、ビルドに関する追加の詳細情報を表示できます。

リンクの問題のエラーメッセージと警告メッセージは、LNK*nnnn*という形式で送信されます。 このエラーのプレフィックスと数値の範囲は、LIB、DUMPBIN、EDITBIN でも使用されます。

## <a name="see-also"></a>参照

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
