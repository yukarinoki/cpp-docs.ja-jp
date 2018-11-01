---
title: 4.1 OMP_SCHEDULE
ms.date: 11/04/2016
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
ms.openlocfilehash: 4731299a4f7203dd01f660ea25bf2f5b58060630
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432696"
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE

**OMP_SCHEDULE**にのみ適用されます**の**と**の並列**をスケジュールの種類を持つディレクティブ**ランタイム**します。 このようなすべてのループのスケジュールの種類とチャンクのサイズは、認識されているスケジュールの種類のいずれかをする、省略可能なこの環境変数を設定して実行時に設定できます*chunk_size*します。

**の**と**の並列**ディレクティブを他にも、スケジュールの種類を持つ**ランタイム**、 **OMP_SCHEDULE**は無視されます。 この環境変数の既定値は、実装で定義されます。 場合、省略可能な*chunk_size*設定すると、値は正である必要があります。 場合*chunk_size*設定、値 1 が想定されている以外の場合、**静的**スケジュールします。 **静的**スケジュール、既定のチャンク サイズは、ループの反復領域をループに適用されるスレッドの数で割った値に設定されています。

例:

```
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

## <a name="cross-references"></a>クロス リファレンス

- **ディ**レクティブを参照してください[セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) [11] ページ。

- **並列**ディレクティブを参照してください[セクション 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) 16 ページ。