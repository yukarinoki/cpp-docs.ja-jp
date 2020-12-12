---
description: '詳細情報: affinity_partitioner クラス'
title: affinity_partitioner クラス
ms.date: 11/04/2016
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
ms.openlocfilehash: 44aa693d5007507e33f062a673713d1ddbda3172
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172324"
---
# <a name="affinity_partitioner-class"></a>affinity_partitioner クラス

`affinity_partitioner` クラスは `static_partitioner` クラスに似ていますが、ワーカー スレッドへのマッピングのサブ範囲の選択によってキャッシュの関係が向上します。 同じデータ セットに対してループ処理が再実行されるときにパフォーマンスを大幅に向上させることができ、データはキャッシュに収まります。 データの局所性のメリットを利用するには、特定のデータ セットに対して実行される並列ループの以降のイテレーションで、同じ `affinity_partitioner` オブジェクトを使用する必要があります。

## <a name="syntax"></a>構文

```cpp
class affinity_partitioner;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[affinity_partitioner](#ctor)|`affinity_partitioner` オブジェクトを構築します。|
|[~ affinity_partitioner デストラクター](#dtor)|オブジェクトを破棄 `affinity_partitioner` します。|

## <a name="inheritance-hierarchy"></a>継承階層

`affinity_partitioner`

## <a name="requirements"></a>要件

**ヘッダー:** ppl

**名前空間:** concurrency

## <a name="affinity_partitioner"></a><a name="dtor"></a> ~ affinity_partitioner

オブジェクトを破棄 `affinity_partitioner` します。

```cpp
~affinity_partitioner();
```

## <a name="affinity_partitioner"></a><a name="ctor"></a> affinity_partitioner

`affinity_partitioner` オブジェクトを構築します。

```cpp
affinity_partitioner();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
