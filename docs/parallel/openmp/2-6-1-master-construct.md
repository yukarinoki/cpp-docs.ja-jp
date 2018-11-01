---
title: 2.6.1 master コンストラクト
ms.date: 11/04/2016
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
ms.openlocfilehash: 0501b1fdfbd36829cee2793fc0f7bb03daeda900
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475531"
---
# <a name="261-master-construct"></a>2.6.1 master コンストラクト

**マスター**ディレクティブは、チームのマスター スレッドによって実行される構造化ブロックを指定する構成を識別します。 構文、**マスター**ディレクティブを次に示します。

```
#pragma omp master new-linestructured-block
```

チームの他のスレッドでは、関連付けられている構造化ブロックは実行されません。 エントリまたは master コンストラクトから終了のいずれかの暗黙の壁がなくなります。