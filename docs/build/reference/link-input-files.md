---
title: 入力ファイルのリンク |Microsoft Docs
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
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5974914e736278ebb336b6814661845740855fe6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710243"
---
# <a name="link-input-files"></a>LINK の入力ファイル

リンカーは、オブジェクト、インポートと標準ライブラリ、リソース、モジュールの定義、およびコマンドの入力が含まれているファイルに指定します。 リンクは、ファイルの内容に関する判断を行うファイルの拡張機能を使用しません。 代わりに、リンクは、各入力ファイルがファイルの種類を判断するを調べます。

コマンドラインでのオブジェクト ファイルは、コマンドラインで表示される順序で処理されます。 ライブラリは、次の注意点がありますも、コマンドラインの順序で検索されます: ときライブラリからのオブジェクト ファイルでは検索ライブラリで最初に、され、コマンドラインから次のライブラリの未解決のシンボルを[/DEFAULTLIB (既定のライブラリの指定)](../../build/reference/defaultlib-specify-default-library.md)ディレクティブ、およびコマンドラインの先頭にすべてのライブラリにします。

> [!NOTE]
>  リンクでは、応答ファイルおよびファイルの順序でのコメントの始まりとしてセミコロン (またはその他の任意の文字) を不要になった受け取ります。 セミコロンは、モジュール定義ファイル (.def) 内のコメントの始まりとしてのみ認識されます。

リンクは、次の種類の入力ファイルを使用します。

- [.obj ファイル](../../build/reference/dot-obj-files-as-linker-input.md)

- [.netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)

- [.lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)

- [.exp ファイル](../../build/reference/dot-exp-files-as-linker-input.md)

- [.def ファイル](../../build/reference/dot-def-files-as-linker-input.md)

- [.pdb ファイル](../../build/reference/dot-pdb-files-as-linker-input.md)

- [.res ファイル](../../build/reference/dot-res-files-as-linker-input.md)

- [.exe ファイル](../../build/reference/dot-exe-files-as-linker-input.md)

- [.txt ファイル](../../build/reference/dot-txt-files-as-linker-input.md)

- [.ilk ファイル](../../build/reference/dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)