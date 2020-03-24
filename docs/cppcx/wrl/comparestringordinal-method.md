---
title: CompareStringOrdinal メソッド
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: 1291084395b02602b7a3de9013df6720d2e237fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214098"
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal メソッド

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
inline INT32 CompareStringOrdinal(
   HSTRING lhs,
   HSTRING rhs)
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初の HSTRING。

*rhs*<br/>
比較する2番目の HSTRING。

## <a name="return-value"></a>戻り値

|値|条件|
|-----------|---------------|
|-1|*lhs*は*rhs*未満です。|
|0|*lhs*は*rhs*と等しくなります。|
|1|*lhs*は*rhs*より大きくなっています。|

## <a name="remarks"></a>解説

指定した2つの HSTRING オブジェクトを比較し、それらの相対位置を並べ替え順序で示す整数を返します。

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper::D etails

## <a name="see-also"></a>参照

[Microsoft::WRL::Wrappers::Details 名前空間](microsoft-wrl-wrappers-details-namespace.md)
