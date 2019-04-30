---
title: simple_partitioner クラス
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: 372773926903da32f1690904b34cd143a04940dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337246"
---
# <a name="simplepartitioner-class"></a>simple_partitioner クラス

`simple_partitioner` クラスは、`parallel_for` によって反復処理される範囲の静的パーティション分割を表します。 パーティショナーは範囲をチャンクに分割します。各チャンクには、少なくともチャンク サイズによって指定された数のイテレーションが含まれます。

## <a name="syntax"></a>構文

```
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

## <a name="requirements"></a>必要条件

**ヘッダー:** ppl.h

**名前空間:** concurrency

##  <a name="dtor"></a> ~simple_partitioner

`simple_partitioner` オブジェクトを破棄します。

```
~simple_partitioner();
```

##  <a name="ctor"></a> simple_partitioner

`simple_partitioner` オブジェクトを構築します。

```
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>パラメーター

*_Chunk_size*<br/>
パーティションの最小サイズ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
