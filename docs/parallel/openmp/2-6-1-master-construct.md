---
title: 2.6.1 master コンストラクト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d82ae673e428c635172f35f9b0f682aa65dc2b8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445634"
---
# <a name="261-master-construct"></a>2.6.1 master コンストラクト

**マスター**ディレクティブは、チームのマスター スレッドによって実行される構造化ブロックを指定する構成を識別します。 構文、**マスター**ディレクティブを次に示します。

```
#pragma omp master new-linestructured-block
```

チームの他のスレッドでは、関連付けられている構造化ブロックは実行されません。 エントリまたは master コンストラクトから終了のいずれかの暗黙の壁がなくなります。