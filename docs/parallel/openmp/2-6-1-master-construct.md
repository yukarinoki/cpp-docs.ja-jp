---
title: 2.6.1 master コンストラクト |Microsoft ドキュメント
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
ms.openlocfilehash: a60a8df380fdcc0052d8fe2d070c8d926bcb28f8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="261-master-construct"></a>2.6.1 master コンストラクト
**マスター**ディレクティブは、チームのマスター スレッドで実行される構造化ブロックを指定する構成を識別します。 構文、**マスター**ディレクティブは、次のようにします。  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 チームの他のスレッドでは、関連付けられている構造化ブロックは実行されません。 暗黙のバリアへのエントリまたは終了 master コンストラクトのいずれかではありません。