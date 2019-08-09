---
title: independent_bits_engine クラス
ms.date: 11/04/2016
f1_keywords:
- random/std::independent_bits_engine
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
ms.openlocfilehash: a90e4be4ff6e92734f6b2e6804f8059be78e66b9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456340"
---
# <a name="independentbitsengine-class"></a>independent_bits_engine クラス

ベースのエンジンから返された値のビットを再パックすることで、指定したビット数で数値のランダム シーケンスを生成します。

## <a name="syntax"></a>構文

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>パラメーター

*双発*\
ベースのエンジンの型。

*リダイレクト*\
**ワード サイズ**。 生成される各数値のサイズ (ビット数)。 **前提条件**: `0 < W ≤ numeric_limits<UIntType>::digits`

*UIntType*\
結果を表す符号なし整数型。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。

## <a name="members"></a>メンバー

||||
|-|-|-|
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|

エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。

## <a name="remarks"></a>Remarks

このテンプレートクラスは、ベースのエンジンによって返される値からビットを再パックことによって値を生成する*エンジンアダプター*を表します。これにより、 *W*ビットの値が生成されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)
