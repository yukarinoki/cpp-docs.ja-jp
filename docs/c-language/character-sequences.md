---
title: 文字シーケンス
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: dea24a2ae5887ea8c0111d8251ba4d9d03ccba0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489662"
---
# <a name="character-sequences"></a>文字シーケンス

**ANSI 3.8.2** ソース ファイルの文字シーケンスのマッピング

プリプロセッサ ステートメントは、ソース ファイル ステートメントと同じ文字セットを使用しますが、エスケープ シーケンスはサポートされていません。

したがって、インクルード ファイルのパスを指定するには、1 つの円記号 (バックスラッシュ) のみを使用します。

```
#include "path1\path2\myfile"
```

ソース コード内では、次のように、2 つの円記号 (バックスラッシュ) が必要です。

```
fil = fopen( "path1\\path2\\myfile", "rt" );
```

## <a name="see-also"></a>参照

[プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)