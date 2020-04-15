---
title: ATL 演算子
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: 8c15daa1d2b12c58323ef5ef75559a2ab911ad93
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319235"
---
# <a name="atl-operators"></a>ATL 演算子

このセクションでは、ATL グローバル演算子のリファレンス トピックを示します。

|演算子|説明|
|--------------|-----------------|
|[演算子 ==](#operator_eq_eq)|2 つの`CSid`オブジェクトまたは`SID`構造体が等しいかどうかを比較します。|
|[演算子 !=](#operator_neq)|2 つの`CSid`オブジェクトまたは`SID`構造体の不等比較。|
|[演算子<](#operator_lt)|演算子の左側`CSid`のオブジェクト`SID`または構造体が右側の`CSid`オブジェクトまたは`SID`構造体より小さいかどうかをテストします (C++ 標準ライブラリの互換性のため)。|
|[演算子>](#operator_gt)|演算子の左側`CSid`のオブジェクト`SID`または構造体が右側の`CSid`オブジェクトまたは`SID`構造体より大きいかどうかをテストします (C++ 標準ライブラリの互換性のため)。|
|[演算子<=](#operator_lt__eq)|演算子の左側`CSid`のオブジェクト`SID`または構造体が右側の`CSid`オブジェクトまたは`SID`構造体以下であるかどうかをテストします (C++ 標準ライブラリの互換性のため)。|
|[演算子>=](#operator_gt__eq)|演算子の左側`CSid`のオブジェクト`SID`または構造体が右側の`CSid`オブジェクトまたは`SID`構造体と等しいか、または等しいかどうかをテストします (C++ 標準ライブラリの互換性のため)。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h.

## <a name="operator-"></a><a name="operator_eq_eq"></a>演算子 ==

`CSid`オブジェクトまたは`SID`(セキュリティ識別子) 構造体が等しいかどうかを比較します。

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid`2`SID`番目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は TRUE を返し、等しくない場合は FALSE を返します。

## <a name="operator-"></a><a name="operator_neq"></a>演算子 !=

`CSid`オブジェクトまたは`SID`(セキュリティ識別子) 構造体の不等比較。

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid`2`SID`番目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

オブジェクトが等しくない場合は TRUE を返し、等しい場合は FALSE を返します。

## <a name="operator-"></a><a name="operator_lt"></a>オペレータ<

演算子の左側`CSid`のオブジェクト`SID`または構造体が右側の`CSid`オブジェクトまたは`SID`構造体より小さいかどうかをテストします (C++ 標準ライブラリの互換性のため)。

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid`2`SID`番目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

*lhs*オブジェクトのアドレスが*rhs*オブジェクトのアドレスより小さい場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトまたは`CSid``SID`構造体のアドレスに対して動作し、C++ 標準ライブラリ コレクション クラスとの互換性を提供するために実装されます。

## <a name="operator-"></a><a name="operator_gt"></a>オペレータ>

演算子の左側`CSid`のオブジェクト`SID`または構造体が右側の`CSid`オブジェクトまたは`SID`構造体より大きいかどうかをテストします (C++ 標準ライブラリの互換性のため)。

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid`2`SID`番目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

*lhs*のアドレスが*rhs*のアドレスより大きい場合は TRUE を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトまたは`CSid``SID`構造体のアドレスに対して動作し、C++ 標準ライブラリ コレクション クラスとの互換性を提供するために実装されます。

## <a name="operator-"></a><a name="operator_lt__eq"></a>演算子<=

演算子の左側`CSid`のオブジェクト`SID`または構造体が右側の`CSid`オブジェクトまたは`SID`構造体以下であるかどうかをテストします (C++ 標準ライブラリの互換性のため)。

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid`2`SID`番目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

それ以外の場合は *、lhs*のアドレスが*rhs*のアドレス以下の場合は TRUE を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトまたは`CSid``SID`構造体のアドレスに対して動作し、C++ 標準ライブラリ コレクション クラスとの互換性を提供するために実装されます。

## <a name="operator-"></a><a name="operator_gt__eq"></a>演算子>=

演算子の左側`CSid`のオブジェクト`SID`または構造体が右側の`CSid`オブジェクトまたは`SID`構造体と等しいか、または等しいかどうかをテストします (C++ 標準ライブラリの互換性のため)。

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid`2`SID`番目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

それ以外の場合は *、lhs*のアドレスが*rhs*のアドレス以上の場合は TRUE を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトまたは`CSid``SID`構造体のアドレスに対して動作し、C++ 標準ライブラリ コレクション クラスとの互換性を提供するために実装されます。
