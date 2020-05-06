---
title: 文字シーケンス
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: 42fb6b61771feb3eaedfb4ce1e674003df91b263
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312688"
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

## <a name="see-also"></a>関連項目

[プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)
