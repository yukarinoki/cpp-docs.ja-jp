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
ms.openlocfilehash: 253f88ed50b9f064edf976277a4618e4f101ec7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331788"
---
# <a name="link-output"></a>LINK からの出力

リンク出力には、.exe ファイル、DLL、マップ ファイル、およびメッセージが含まれます。

## <a name="output-files"></a><a name="_core_output_files"></a>出力ファイル

LINK からの既定の出力ファイルは .exe ファイルです。 [/DLL](dll-build-a-dll.md)オプションを指定すると、.dll ファイルが作成されます。 出力ファイル名は、出力ファイル名[(/OUT)](out-output-file-name.md)オプションを使用して制御できます。

インクリメンタル モードでは、LINK は.ilk ファイルを作成して、プログラムの後のインクリメンタル ビルドのステータス情報を保持します。 ilk ファイルの詳細については[、「.ilk ファイル](dot-ilk-files-as-linker-input.md)」を参照してください。 インクリメンタル リンクの詳細については、「[インクリメンタル リンク (/INCREMENTAL)」](incremental-link-incrementally.md)オプションを参照してください。

リンクは、エクスポート (通常は DLL) を含むプログラムを作成するときに、.exp ファイルがビルドで使用されていない限り、.lib ファイルも作成します。 インポート ライブラリ ファイル名は[、/IMPLIB](implib-name-import-library.md)オプションを使用して制御できます。

[[マップファイルの生成] オプション (/MAP) が](map-generate-mapfile.md)指定されている場合、LINK はマップファイルを作成します。

デバッグ[情報の生成 (/DEBUG)](debug-generate-debug-info.md)オプションが指定されている場合、LINK はプログラムのデバッグ情報を含む PDB を作成します。

## <a name="other-output"></a><a name="_core_other_output"></a>その他の出力

他のコマンド`link`行入力を行わずに入力すると、LINK はオプションを要約した使用法ステートメントを表示します。

LINK は、[スタートアップ バナーを非表示 (/NOLOGO)](nologo-suppress-startup-banner-linker.md)オプションを使用しない限り、著作権とバージョンのメッセージを表示し、コマンド ファイル入力をエコーします。

[[進行状況メッセージの印刷] (/VERBOSE)](verbose-print-progress-messages.md)オプションを使用して、ビルドに関する追加の詳細を表示できます。

LINK は、エラー メッセージと警告メッセージを LNK*nnnn*という形式で発行します。 このエラー接頭部および数字の範囲は、LIB、ダンプビン、およびエディットビンでも使用されます。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
