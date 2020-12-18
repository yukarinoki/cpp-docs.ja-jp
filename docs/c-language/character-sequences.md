---
description: '詳細情報: 文字シーケンス'
title: 文字シーケンス
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: ac5642371389047bd8ce3a83e02dc13802167dc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305079"
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
