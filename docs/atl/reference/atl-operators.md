---
description: 詳細については、「ATL 演算子」を参照してください。
title: ATL 演算子
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: 8c336732aeee9146b89e300580c0fbee506ec343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158687"
---
# <a name="atl-operators"></a>ATL 演算子

ここでは、ATL グローバル演算子のリファレンストピックについて説明します。

|演算子|説明|
|--------------|-----------------|
|[operator = =](#operator_eq_eq)|2つ `CSid` のオブジェクトまたは `SID` 構造体が等しいかどうかを比較します。|
|[operator! =](#operator_neq)|2つ `CSid` のオブジェクトまたは構造体が等しくないかどうか `SID` を比較します。|
|[<演算子 ](#operator_lt)|`CSid`演算子の左側のオブジェクトまたは `SID` 構造体が右辺のオブジェクトまたは構造体より小さいかどうかをテスト `CSid` `SID` します (C++ 標準ライブラリの互換性のため)。|
|[>演算子 ](#operator_gt)|`CSid`演算子の左側のオブジェクトまたは `SID` 構造体が右辺のオブジェクトまたは構造体より大きいかどうかをテスト `CSid` `SID` します (C++ 標準ライブラリの互換性のため)。|
|[operator <=](#operator_lt__eq)|`CSid`演算子の左側のオブジェクトまたは `SID` 構造体が右辺のオブジェクトまたは構造体以下かどうかをテスト `CSid` `SID` します (C++ 標準ライブラリの互換性のため)。|
|[operator >=](#operator_gt__eq)|`CSid`演算子の左側のオブジェクトまたは構造体が右辺のオブジェクトまたは構造体以上であるかどうかをテスト `SID` `CSid` `SID` します (C++ 標準ライブラリの互換性のため)。|

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h。

## <a name="operator-"></a><a name="operator_eq_eq"></a> operator = =

`CSid`オブジェクトまたは `SID` (セキュリティ識別子) 構造が等しいかどうかを比較します。

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`CSid`比較する最初のオブジェクトまたは `SID` 構造体。

*rhs*<br/>
比較する2番目の `CSid` オブジェクトまたは `SID` 構造体。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は TRUE、等しくない場合は FALSE を返します。

## <a name="operator-"></a><a name="operator_neq"></a> operator! =

`CSid`オブジェクトまたは `SID` (セキュリティ識別子) 構造体が等しくないかどうかを比較します。

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`CSid`比較する最初のオブジェクトまたは `SID` 構造体。

*rhs*<br/>
比較する2番目の `CSid` オブジェクトまたは `SID` 構造体。

### <a name="return-value"></a>戻り値

オブジェクトが等しくない場合は TRUE、等しい場合は FALSE を返します。

## <a name="operator-"></a><a name="operator_lt"></a> < 演算子

`CSid`演算子の左側のオブジェクトまたは `SID` 構造体が右辺のオブジェクトまたは構造体より小さいかどうかをテスト `CSid` `SID` します (C++ 標準ライブラリの互換性のため)。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`CSid`比較する最初のオブジェクトまたは `SID` 構造体。

*rhs*<br/>
比較する2番目の `CSid` オブジェクトまたは `SID` 構造体。

### <a name="return-value"></a>戻り値

*Lhs* オブジェクトのアドレスが *rhs* オブジェクトのアドレスより小さい場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトまたは構造体のアドレスに対して作用 `CSid` `SID` し、C++ 標準ライブラリコレクションクラスとの互換性を提供するために実装されます。

## <a name="operator-"></a><a name="operator_gt"></a> > 演算子

`CSid`演算子の左側のオブジェクトまたは `SID` 構造体が右辺のオブジェクトまたは構造体より大きいかどうかをテスト `CSid` `SID` します (C++ 標準ライブラリの互換性のため)。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`CSid`比較する最初のオブジェクトまたは `SID` 構造体。

*rhs*<br/>
比較する2番目の `CSid` オブジェクトまたは `SID` 構造体。

### <a name="return-value"></a>戻り値

*Lhs* のアドレスが *rhs* のアドレスより大きい場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトまたは構造体のアドレスに対して作用 `CSid` `SID` し、C++ 標準ライブラリコレクションクラスとの互換性を提供するために実装されます。

## <a name="operator-"></a><a name="operator_lt__eq"></a> operator <=

`CSid`演算子の左側のオブジェクトまたは `SID` 構造体が右辺のオブジェクトまたは構造体以下かどうかをテスト `CSid` `SID` します (C++ 標準ライブラリの互換性のため)。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`CSid`比較する最初のオブジェクトまたは `SID` 構造体。

*rhs*<br/>
比較する2番目の `CSid` オブジェクトまたは `SID` 構造体。

### <a name="return-value"></a>戻り値

*Lhs* のアドレスが *rhs* のアドレス以下の場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトまたは構造体のアドレスに対して作用 `CSid` `SID` し、C++ 標準ライブラリコレクションクラスとの互換性を提供するために実装されます。

## <a name="operator-"></a><a name="operator_gt__eq"></a> operator >=

`CSid`演算子の左側のオブジェクトまたは構造体が右辺のオブジェクトまたは構造体以上であるかどうかをテスト `SID` `CSid` `SID` します (C++ 標準ライブラリの互換性のため)。

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`CSid`比較する最初のオブジェクトまたは `SID` 構造体。

*rhs*<br/>
比較する2番目の `CSid` オブジェクトまたは `SID` 構造体。

### <a name="return-value"></a>戻り値

*Lhs* のアドレスが *rhs* のアドレス以上の場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトまたは構造体のアドレスに対して作用 `CSid` `SID` し、C++ 標準ライブラリコレクションクラスとの互換性を提供するために実装されます。
