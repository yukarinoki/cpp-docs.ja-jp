---
title: LINK の入力ファイル
ms.date: 11/04/2016
f1_keywords:
- link
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
ms.openlocfilehash: 9fb2e6b8ee0f8ddc1512c605373671ae1c93c0b8
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413252"
---
# <a name="link-input-files"></a>LINK の入力ファイル

リンカーは、オブジェクト、インポートと標準ライブラリ、リソース、モジュールの定義、およびコマンドの入力が含まれているファイルに指定します。 リンクは、ファイルの内容に関する判断を行うファイルの拡張機能を使用しません。 代わりに、リンクは、各入力ファイルがファイルの種類を判断するを調べます。

コマンドラインでのオブジェクト ファイルは、コマンドラインで表示される順序で処理されます。 ライブラリは、次の注意点がありますも、コマンドラインの順序で検索されます。シンボルは未解決のときライブラリからのオブジェクト ファイルで検索のライブラリで最初に、され、コマンドラインから次のライブラリと[/DEFAULTLIB (既定のライブラリの指定)](../../build/reference/defaultlib-specify-default-library.md)ディレクティブ、し、コマンドラインの先頭のすべてのライブラリを

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
