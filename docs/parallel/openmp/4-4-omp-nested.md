---
title: 4.4 OMP_NESTED |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1083269f31ebc710da24430635ff8381e3f2147a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419517"
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED

`OMP_NESTED`環境変数を有効または入れ子になった並列処理が有効になっているか、呼び出すことによって無効になっている場合を除き、入れ子になった並列処理を無効になります、 `o` **mp_set_nested**ライブラリ ルーチン。 場合に設定**TRUE**、入れ子になった並列処理が有効になって; に設定されている場合**FALSE**、入れ子になった並列処理が無効になっています。 既定値は**FALSE**します。

例:

```
setenv OMP_NESTED TRUE
```

## <a name="cross-reference"></a>相互参照をします。

- `omp_set_nested` 関数を参照してください[セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 ページの。