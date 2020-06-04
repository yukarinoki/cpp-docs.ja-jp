---
title: ATL 演算子
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: fe5363d3d05123c17e45254898e2210797400022
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168853"
---
# <a name="atl-operators"></a>ATL 演算子

ここでは、ATL グローバル演算子のリファレンストピックについて説明します。

|演算子|説明|
|--------------|-----------------|
|[operator = =](#operator_eq_eq)|2つ`CSid`のオブジェクト`SID`または構造体が等しいかどうかを比較します。|
|[operator! =](#operator_neq)|2つ`CSid`のオブジェクト`SID`または構造体が等しくないかどうかを比較します。|
|[<演算子](#operator_lt)|演算子の左側`CSid`のオブジェクト`SID`または構造体が右辺の`CSid`オブジェクトまた`SID`は構造体より小さいかどうかをテストします (C++ 標準ライブラリの互換性のため)。|
|[>演算子](#operator_gt)|演算子の左側`CSid`のオブジェクト`SID`または構造体が右辺の`CSid`オブジェクトまた`SID`は構造体より大きいかどうかをテストします (C++ 標準ライブラリの互換性のため)。|
|[operator <=](#operator_lt__eq)|演算子の左側`CSid`のオブジェクト`SID`または構造体が右辺の`CSid`オブジェクトまた`SID`は構造体以下かどうかをテストします (C++ 標準ライブラリの互換性のため)。|
|[operator >=](#operator_gt__eq)|演算子の左側`CSid`のオブジェクト`SID`または構造体が右辺の`CSid`オブジェクトまた`SID`は構造体以上であるかどうかをテストします (C++ 標準ライブラリの互換性のため)。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity .h。

## <a name="operator-"></a><a name="operator_eq_eq"></a>operator = =

オブジェクト`CSid`または`SID` (セキュリティ識別子) 構造が等しいかどうかを比較します。

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid` 2 番`SID`目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は TRUE、等しくない場合は FALSE を返します。

## <a name="operator-"></a><a name="operator_neq"></a>operator! =

オブジェクト`CSid`または`SID` (セキュリティ識別子) 構造体が等しくないかどうかを比較します。

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid` 2 番`SID`目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

オブジェクトが等しくない場合は TRUE、等しい場合は FALSE を返します。

## <a name="operator-"></a><a name="operator_lt"></a>< 演算子

演算子の左側`CSid`のオブジェクト`SID`または構造体が右辺の`CSid`オブジェクトまた`SID`は構造体より小さいかどうかをテストします (C++ 標準ライブラリの互換性のため)。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid` 2 番`SID`目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

*Lhs*オブジェクトのアドレスが*rhs*オブジェクトのアドレスより小さい場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この演算子は、 `CSid`オブジェクトまたは`SID`構造体のアドレスに対して作用し、C++ 標準ライブラリコレクションクラスとの互換性を提供するために実装されます。

## <a name="operator-"></a><a name="operator_gt"></a>> 演算子

演算子の左側`CSid`のオブジェクト`SID`または構造体が右辺の`CSid`オブジェクトまた`SID`は構造体より大きいかどうかをテストします (C++ 標準ライブラリの互換性のため)。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid` 2 番`SID`目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

*Lhs*のアドレスが*rhs*のアドレスより大きい場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この演算子は、 `CSid`オブジェクトまたは`SID`構造体のアドレスに対して作用し、C++ 標準ライブラリコレクションクラスとの互換性を提供するために実装されます。

## <a name="operator-"></a><a name="operator_lt__eq"></a>operator <=

演算子の左側`CSid`のオブジェクト`SID`または構造体が右辺の`CSid`オブジェクトまた`SID`は構造体以下かどうかをテストします (C++ 標準ライブラリの互換性のため)。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid` 2 番`SID`目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

*Lhs*のアドレスが*rhs*のアドレス以下の場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この演算子は、 `CSid`オブジェクトまたは`SID`構造体のアドレスに対して作用し、C++ 標準ライブラリコレクションクラスとの互換性を提供するために実装されます。

## <a name="operator-"></a><a name="operator_gt__eq"></a>operator >=

演算子の左側`CSid`のオブジェクト`SID`または構造体が右辺の`CSid`オブジェクトまた`SID`は構造体以上であるかどうかをテストします (C++ 標準ライブラリの互換性のため)。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する`CSid`最初の`SID`オブジェクトまたは構造体。

*rhs*<br/>
比較する`CSid` 2 番`SID`目のオブジェクトまたは構造体。

### <a name="return-value"></a>戻り値

*Lhs*のアドレスが*rhs*のアドレス以上の場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この演算子は、 `CSid`オブジェクトまたは`SID`構造体のアドレスに対して作用し、C++ 標準ライブラリコレクションクラスとの互換性を提供するために実装されます。
