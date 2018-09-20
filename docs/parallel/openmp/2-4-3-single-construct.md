---
title: 2.4.3 単一のコンストラクト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81abf5324c215b9011ecbd774626a213c2eda653
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376501"
---
# <a name="243-single-construct"></a>2.4.3 single コンストラクト

**単一**ディレクティブ (必ずしもマスター スレッド) のチームで 1 つのスレッドによって、関連付けられている構造化ブロックが実行されることを指定する構成要素を識別します。 構文、**単一**ディレクティブを次に示します。

```
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

句は、次のいずれか。

**private(** *variable-list* **)**

**firstprivate(** *variable-list* **)**

**copyprivate (** *変数一覧* **)**

**nowait**

後に暗黙の壁が、**単一**れない限り、作成、 **nowait**句を指定します。

制限は、**単一**ディレクティブは、次のとおり。

- 1 つだけ**nowait**句に表示できる、**単一**ディレクティブ。

- **Copyprivate**句を使用しないで、 **nowait**句。

## <a name="cross-references"></a>クロス リファレンス

- **プライベート**、 **firstprivate**、および**copyprivate**句を参照してください[セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 ページにします。