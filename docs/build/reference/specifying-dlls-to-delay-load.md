---
description: 遅延読み込みのための Dll の指定に関する詳細情報
title: 遅延読み込みする Dll の指定
ms.date: 01/19/2021
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.openlocfilehash: de8c2e3cb9605cbc6dbc215a0449348c12295c17
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667498"
---
# <a name="specify-dlls-to-delay-load"></a>遅延読み込みする Dll の指定

リンカーオプションを使用して、読み込みを遅延させる Dll を指定でき [`/delayload:dllname`](delayload-delay-load-import.md) ます。 独自のバージョンのヘルパー関数を使用する予定がない場合 *`delayimp.lib`* は、(デスクトップアプリケーションの場合) または (UWP アプリの場合) にプログラムをリンクする必要もあり *`dloadhelper.lib`* ます。

DLL の遅延読み込みの簡単な例を次に示します。

```cpp
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

DEBUG バージョンのプロジェクトをビルドします。 デバッガーを使用してコードをステップ実行すると、の *`user32.dll`* 呼び出しを行ったときにのみが読み込まれることがわかり `MessageBox` ます。

## <a name="see-also"></a>こちらもご覧ください

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md)
