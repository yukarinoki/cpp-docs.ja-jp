---
title: 4.4 OMP_NESTED
ms.date: 11/04/2016
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
ms.openlocfilehash: e45b8901c56923ab37ca387a5f057c5b41af21f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453622"
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED

`OMP_NESTED`環境変数を有効または入れ子になった並列処理が有効になっているか、呼び出すことによって無効になっている場合を除き、入れ子になった並列処理を無効になります、 `o` **mp_set_nested**ライブラリ ルーチン。 場合に設定**TRUE**、入れ子になった並列処理が有効になって; に設定されている場合**FALSE**、入れ子になった並列処理が無効になっています。 既定値は**FALSE**します。

例:

```
setenv OMP_NESTED TRUE
```

## <a name="cross-reference"></a>相互参照をします。

- `omp_set_nested` 関数を参照してください[セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 ページの。