---
title: コンパイラの警告 C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: 43c2f5d9092cdbad14e429349bd7d04e236b75e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447282"
---
# <a name="compiler-warning-c4335"></a>コンパイラの警告 C4335

Mac ファイル形式が検出されました: ソース ファイルを DOS または UNIX のいずれかの形式に変換してください

ソース ファイルの最初の行の行終端文字は、UNIX ('\n') または DOS (\r\n) ではなく Macintosh スタイル ('\r') です。

この警告はエラーとして常に発行されます。  参照してください[警告](../../preprocessor/warning.md)プラグマについてはこの警告を無効にする方法。  また、この警告がコンパイル単位あたり 1 回発行のみです。 そのため、複数ある場合は`#include`Macintosh 形式でファイルを指定するディレクティブ、C4335 はのみ発行されます。

Macintosh の形式でファイルを生成する方法の 1 つを使用して、 **保存オプションの**(上、**ファイル**メニュー) Visual Studio でします。

## <a name="example"></a>例

次の例では、C4335 が生成されます。

```
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```