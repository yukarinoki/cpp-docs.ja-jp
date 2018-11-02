---
title: CComSafeArrayBound クラス
ms.date: 11/04/2016
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
ms.openlocfilehash: d57e038a4ebc55d08b4518f25e37b4f2d9cee05d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429205"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound クラス

このクラスは、のラッパーを[SAFEARRAYBOUND](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearraybound)構造体。

## <a name="syntax"></a>構文

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|コンストラクターです。|
|[GetCount](#getcount)|要素の数を返すには、このメソッドを呼び出します。|
|[GetLowerBound](#getlowerbound)|下限の境界を返すには、このメソッドを呼び出します。|
|[です](#getupperbound)|上限の境界を返すには、このメソッドを呼び出します。|
|[SetCount](#setcount)|要素の数を設定するには、このメソッドを呼び出します。|
|[SetLowerBound](#setlowerbound)|下限の境界を設定するには、このメソッドを呼び出します。|

### <a name="operators"></a>演算子

|||
|-|-|
|[演算子 =](#operator_eq)|セット、`CComSafeArrayBound`に新しい値。|

## <a name="remarks"></a>Remarks

このクラスは、のラッパー、`SAFEARRAYBOUND`によって使用される構造[CComSafeArray](../../atl/reference/ccomsafearray-class.md)します。 クエリおよびの 1 つのディメンションの上限と下限の境界を設定するためのメソッドを提供する`CComSafeArray`オブジェクトと含まれる要素の数。 多次元`CComSafeArray`オブジェクトの配列を使用して`CComSafeArrayBound`オブジェクト、次元ごとに 1 つ。 そのためなどのメソッドを使用[GetCount](#getcount)、このメソッドは多次元配列の要素の合計数を返しますしないことに注意してください。

**ヘッダー:** atlsafe.h

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsafe.h

##  <a name="ccomsafearraybound"></a>  CComSafeArrayBound::CComSafeArrayBound

コンストラクターです。

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>パラメーター

*ulCount*<br/>
配列の要素数。

*lLowerBound*<br/>
配列の番号を下限値です。

### <a name="remarks"></a>Remarks

配列が、Visual C プログラムからアクセスする場合は、下限が 0 として定義することをお勧めします。 配列の Visual Basic などの他の言語で使用する場合は、別の下限値を使用する方が望ましい場合があります。

##  <a name="getcount"></a>  CComSafeArrayBound::GetCount

要素の数を返すには、このメソッドを呼び出します。

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>戻り値

要素の数を返します。

### <a name="remarks"></a>Remarks

場合、関連付けられている`CComSafeArray`オブジェクトは、多次元配列を表す、このメソッドは最も右にあるディメンション内の要素の合計数を返しますのみです。 使用[CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount)要素の合計数を取得します。

##  <a name="getlowerbound"></a>  CComSafeArrayBound::GetLowerBound

下限の境界を返すには、このメソッドを呼び出します。

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>戻り値

下限の境界を返します、`CComSafeArrayBound`オブジェクト。

##  <a name="getupperbound"></a>  CComSafeArrayBound::GetUpperBound

上限の境界を返すには、このメソッドを呼び出します。

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>戻り値

上限を返します、`CComSafeArrayBound`オブジェクト。

### <a name="remarks"></a>Remarks

上限は、要素と下限の境界値の数によって異なります。 たとえば、下限の境界が 0 で、要素の数が 10 の場合、上限が 9 を自動的に設定されます。

##  <a name="operator_eq"></a>  CComSafeArrayBound::operator =

セット、`CComSafeArrayBound`に新しい値。

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>パラメーター

*バインドされています。*<br/>
`CComSafeArrayBound` オブジェクト。

*ulCount*<br/>
要素の数。

### <a name="return-value"></a>戻り値

ポインターを返します、`CComSafeArrayBound`オブジェクト。

### <a name="remarks"></a>Remarks

`CComSafeArrayBound`既存を使用してオブジェクトを割り当てることが`CComSafeArrayBound`、またはする下限の境界の場合は既定で設定を 0 には、要素の数を指定しています。

##  <a name="setcount"></a>  CComSafeArrayBound::SetCount

要素の数を設定するには、このメソッドを呼び出します。

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>パラメーター

*ulCount*<br/>
要素の数。

### <a name="return-value"></a>戻り値

内の要素の数を返します、`CComSafeArrayBound`オブジェクト。

##  <a name="setlowerbound"></a>  CComSafeArrayBound::SetLowerBound

下限の境界を設定するには、このメソッドを呼び出します。

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>パラメーター

*lLowerBound*<br/>
下限値です。

### <a name="return-value"></a>戻り値

新しい下限の境界を返します、`CComSafeArrayBound`オブジェクト。

### <a name="remarks"></a>Remarks

配列が、Visual C プログラムからアクセスする場合は、下限が 0 として定義することをお勧めします。 配列の Visual Basic などの他の言語で使用する場合は、別の下限値を使用する方が望ましい場合があります。

上限は、要素と下限の境界値の数によって異なります。 たとえば、下限の境界が 0 で、要素の数が 10 の場合、上限が 9 を自動的に設定されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
