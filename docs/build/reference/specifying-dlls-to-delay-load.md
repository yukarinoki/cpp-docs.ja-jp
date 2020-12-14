---
description: 詳細については、「遅延読み込みする Dll の指定」を参照してください。
title: 遅延読み込みする DLL の指定
ms.date: 11/04/2016
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
ms.openlocfilehash: ece96ea6f818c7e0bc6b6e032ce523e96a9f4ecb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224544"
---
# <a name="specifying-dlls-to-delay-load"></a>遅延読み込みする DLL の指定

[/Delayload](delayload-delay-load-import.md): リンカーオプションを使用して、遅延読み込みする dll を指定でき `dllname` ます。 独自のバージョンのヘルパー関数を使う計画がない場合は、プログラムを delayimp.lib (デスクトップ アプリケーションの場合) または dloadhelper.lib (ストア アプリの場合) とリンクする必要もあります。

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

[リンカーによる Delay-Loaded Dll のサポート](linker-support-for-delay-loaded-dlls.md)
