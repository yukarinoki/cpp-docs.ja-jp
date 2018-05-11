---
title: discard_block_engine クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::discard_block_engine
dev_langs:
- C++
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b814f64f340577508add6bf3c0f85ffac0786db7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="discardblockengine-class"></a>discard_block_engine クラス

ベースとなるエンジンから返された値を破棄することによってランダム シーケンスを生成します。

## <a name="syntax"></a>構文

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>パラメーター

`Engine` ベース エンジンの種類。

`P` **ブロック サイズ**です。 各ブロックの値の数。

`R` **使用されるブロック**です。 使用される各ブロックの値の数。 残りは破棄されます (`P` - `R`)。 **前提条件**: `0 < R ≤ P`

## <a name="members"></a>メンバー

||||
|-|-|-|
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|

エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。

## <a name="remarks"></a>コメント

このテンプレート クラスは、ベースのエンジンによって返された値の一部を破棄することで値を生成するエンジン アダプターを表します。

## <a name="requirements"></a>要件

**ヘッダー:** \<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)<br/>
