---
description: '詳細情報: simple_partitioner クラス'
title: simple_partitioner クラス
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: 76dcac6d7fc2dce5b69d0a9dbefaf01420f8bcde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188691"
---
# <a name="simple_partitioner-class"></a>simple_partitioner クラス

`simple_partitioner` クラスは、`parallel_for` によって反復処理される範囲の静的パーティション分割を表します。 パーティショナーは範囲をチャンクに分割します。各チャンクには、少なくともチャンク サイズによって指定された数のイテレーションが含まれます。

## <a name="syntax"></a>構文

```cpp
class simple_partitioner;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[simple_partitioner](#ctor)|`simple_partitioner` オブジェクトを構築します。|
|[~ simple_partitioner デストラクター](#dtor)|`simple_partitioner` オブジェクトを破棄します。|

## <a name="inheritance-hierarchy"></a>継承階層

`simple_partitioner`

## <a name="requirements"></a>要件

**ヘッダー:** ppl

**名前空間:** concurrency

## <a name="simple_partitioner"></a><a name="dtor"></a> ~ simple_partitioner

`simple_partitioner` オブジェクトを破棄します。

```cpp
~simple_partitioner();
```

## <a name="simple_partitioner"></a><a name="ctor"></a> simple_partitioner

`simple_partitioner` オブジェクトを構築します。

```cpp
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>パラメーター

*_Chunk_size*<br/>
最小パーティションサイズ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
