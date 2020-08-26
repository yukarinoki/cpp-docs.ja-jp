---
title: shuffle_order_engine クラス
ms.date: 11/04/2016
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
ms.openlocfilehash: 49841d0527d82bf5877322a7c4dab17e95a3360e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846200"
---
# <a name="shuffle_order_engine-class"></a>shuffle_order_engine クラス

ベースのエンジンから返された値を並べ替えることで、ランダム シーケンスを生成します。

## <a name="syntax"></a>構文

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>パラメーター

*双発*\
ベースのエンジンの型。

*Kb*\
**テーブルサイズ**。 バッファー (テーブル) 内の要素の数。 **前提条件**: `0 < K`

## <a name="members"></a>メンバー

`shuffle_order_engine::shuffle_order_engine`\
`shuffle_order_engine::base`\
`shuffle_order_engine::base_type`\
`shuffle_order_engine::discard`\
`shuffle_order_engine::operator()`\
`shuffle_order_engine::seed`

エンジンメンバーの詳細については、「」を参照してください [\<random>](../standard-library/random.md) 。

## <a name="remarks"></a>解説

このクラステンプレートは、ベースエンジンによって返された値を並べ替えることによって値を生成する *エンジンアダプター* を表します。 各コンストラクターは、ベースエンジンによって返された *K* 値を使用して内部テーブルにデータを入力し、値が要求されたときにテーブルからランダムな要素が選択されます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)
