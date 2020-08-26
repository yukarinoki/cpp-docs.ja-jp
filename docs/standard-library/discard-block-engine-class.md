---
title: discard_block_engine クラス
ms.date: 11/04/2016
f1_keywords:
- random/std::discard_block_engine
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
ms.openlocfilehash: 6f7b11c360f58e6a838b22fbf2c68366dce973a3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846291"
---
# <a name="discard_block_engine-class"></a>discard_block_engine クラス

ベースとなるエンジンから返された値を破棄することによってランダム シーケンスを生成します。

## <a name="syntax"></a>構文

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>パラメーター

*双発*\
ベースのエンジンの型。

*Irtran-p*\
**ブロック サイズ**。 各ブロックの値の数。

*\R\n\r\n*\
**使用されるブロック**。 使用される各ブロックの値の数。 残りは破棄され `P`  -  `R` ます ()。 **前提条件**: `0 < R ≤ P`

## <a name="members"></a>メンバー

`discard_block_engine::discard_block_engine`\
`discard_block_engine::base`\
`discard_block_engine::base_type`\
`discard_block_engine::discard`\
`discard_block_engine::operator()`\
`discard_block_engine::seed`

エンジンメンバーの詳細については、「」を参照してください [\<random>](../standard-library/random.md) 。

## <a name="remarks"></a>解説

このクラステンプレートは、ベースエンジンによって返された値の一部を破棄することによって値を生成するエンジンアダプターを表します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)
