---
title: 遅延読み込みする Dll を指定する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7756499ddf24055feb1c540df13fbe8249edf42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373723"
---
# <a name="specifying-dlls-to-delay-load"></a>遅延読み込みする DLL の指定
遅延読み込みする Dll を指定することができます、 [/delayload](../../build/reference/delayload-delay-load-import.md):`dllname`リンカー オプション。 独自のバージョンのヘルパー関数を使う計画がない場合は、プログラムを delayimp.lib (デスクトップ アプリケーションの場合) または dloadhelper.lib (ストア アプリの場合) とリンクする必要もあります。  
  
 DLL の遅延読み込みの簡単な例を以下に示します。  
  
```  
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll  
#include <windows.h>  
// uncomment these lines to remove .libs from command line  
// #pragma comment(lib, "delayimp")  
// #pragma comment(lib, "user32")  
  
int main() {  
   // user32.dll will load at this point  
   MessageBox(NULL, "Hello", "Hello", MB_OK);  
}  
```  
  
 DEBUG バージョンのプロジェクトをビルドします。 デバッガーを使ってコードを段階的に実行すると、`MessageBox` に対する呼び出しを行なう場合のみ user32.dll が読み込まれることがわかります。  
  
## <a name="see-also"></a>関連項目  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)