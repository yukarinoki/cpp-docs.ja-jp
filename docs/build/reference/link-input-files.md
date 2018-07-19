---
title: 入力ファイルのリンク |Microsoft ドキュメント
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
ms.openlocfilehash: 8d61a24916c3b56cf666a85483414f86753f7f59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374828"
---
# <a name="link-input-files"></a>LINK の入力ファイル
リンカーは、オブジェクト、インポートおよび標準ライブラリ、リソース、モジュールの定義、およびコマンドの入力を含むファイルを提供します。 リンクは、ファイルの内容に関する想定を行うにはファイル拡張子を使用しません。 代わりに、リンクは、各入力ファイルがファイルの種類を判断するを調べます。  
  
 コマンドラインでのオブジェクト ファイルは、コマンドラインに表示される順序で処理されます。 ライブラリは、次に注意して同様に、コマンドラインの順序で検索されます: シンボルは未解決の場合、ライブラリからのオブジェクト ファイルで最初に検索されるのライブラリで、し、コマンドラインから次のライブラリ[/DEFAULTLIB (既定のライブラリの指定)](../../build/reference/defaultlib-specify-default-library.md)ディレクティブは、その後に、コマンドラインの先頭のすべてのライブラリです。  
  
> [!NOTE]
>  リンクでは、応答ファイルおよび順序ファイルでコメントの始まりとしてセミコロン (またはその他の文字) を不要になった受け取ります。 セミコロンは、モジュール定義ファイル (.def) 内のコメントの始まりとしてのみ認識されます。  
  
 リンクは、入力ファイルの次の種類を使用します。  
  
-   [.obj ファイル](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [.netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [.lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [.exp ファイル](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [.def ファイル](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [.pdb ファイル](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [.res ファイル](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [.exe ファイル](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [.txt ファイル](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [.ilk ファイル](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)