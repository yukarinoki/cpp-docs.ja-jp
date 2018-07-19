---
title: LINK からの出力 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae68de707ece35825a32a404ce14032d4bbd3141
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376729"
---
# <a name="link-output"></a>LINK からの出力
Link からの出力には、.exe ファイル、Dll、マップ ファイル、およびメッセージが含まれています。  
  
##  <a name="_core_output_files"></a> 出力ファイル  
 既定の出力ファイルのリンクからは、.exe ファイルです。 場合、 [/DLL](../../build/reference/dll-build-a-dll.md)オプションを指定すると、リンクは、.dll ファイルを構築します。 出力ファイル名を指定できます、[出力ファイル名 (/out)](../../build/reference/out-output-file-name.md)オプション。  
  
 Incremental モードでは、リンクは、プログラムの以降のインクリメンタル ビルドの状態情報を保持するために、.ilk ファイルを作成します。 .Ilk ファイルに関する詳細については、「 [.ilk ファイル](../../build/reference/dot-ilk-files-as-linker-input.md)です。 インクリメンタル リンクの詳細については、次を参照してください。、[インクリメンタル リンク (/incremental)](../../build/reference/incremental-link-incrementally.md)オプション。  
  
 リンクを作成するときを含むプログラム (通常は DLL) のエクスポートも作成 .lib ファイル、ビルドで .exp ファイルが使用された場合を除き、します。 インポート ライブラリ ファイル名を指定できます、 [/IMPLIB](../../build/reference/implib-name-import-library.md)オプション。  
  
 場合、[マップ ファイルの生成 (/map)](../../build/reference/map-generate-mapfile.md)オプションを指定すると、マップ ファイルが作成されます。  
  
 場合、[デバッグ情報の生成 (/debug)](../../build/reference/debug-generate-debug-info.md)オプションを指定すると、プログラムのデバッグ情報を格納する pdb ファイルが作成されます。  
  
##  <a name="_core_other_output"></a> 他の出力  
 入力すると`link`他のコマンド ライン入力しなくてもリンクがそのオプションを要約した法を表示します。  
  
 リンクは、著作権およびバージョン メッセージが表示され、しない限り、コマンド ファイルからの入力をエコー、[著作権 (/NOLOGO)](../../build/reference/nologo-suppress-startup-banner-linker.md)オプションを使用します。  
  
 使用することができます、[進行状況メッセージを印刷 (/verbose)](../../build/reference/verbose-print-progress-messages.md)ビルドに関するその他の詳細を表示するにはオプションです。  
  
 リンク LNK フォームでのエラーと警告メッセージが発行された*nnnn*です。 このエラーのプレフィックスと番号の範囲は LIB、DUMPBIN、および EDITBIN によっても使われます。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)