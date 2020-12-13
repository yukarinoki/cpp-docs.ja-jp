---
description: '詳細情報: CComSafeArrayBound クラス'
title: CComSafeArrayBound クラス
ms.date: 05/06/2019
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
ms.openlocfilehash: 09672e4a74db8998b887a093e0f15202903cfcf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142249"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound クラス

このクラスは、 [SAFEARRAYBOUND](/windows/win32/api/oaidl/ns-oaidl-safearraybound) 構造体のラッパーです。

## <a name="syntax"></a>構文

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|機能|説明|
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|コンストラクターです。|
|[GetCount](#getcount)|要素の数を取得するには、このメソッドを呼び出します。|
|[Get下限](#getlowerbound)|下限を返すには、このメソッドを呼び出します。|
|[System.array.getupperbound](#getupperbound)|上限を返すには、このメソッドを呼び出します。|
|[SetCount](#setcount)|要素の数を設定するには、このメソッドを呼び出します。|
|[Set下限バインド](#setlowerbound)|下限を設定するには、このメソッドを呼び出します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[operator =](#operator_eq)|を `CComSafeArrayBound` 新しい値に設定します。|

## <a name="remarks"></a>解説

このクラスは、 `SAFEARRAYBOUND` [CComSafeArray](../../atl/reference/ccomsafearray-class.md)によって使用される構造体のラッパーです。 オブジェクトの1つの次元の上限と下限、 `CComSafeArray` およびオブジェクトに含まれる要素の数を照会および設定するためのメソッドが用意されています。 多次元 `CComSafeArray` オブジェクトは `CComSafeArrayBound` 、各次元に1つずつ、オブジェクトの配列を使用します。 したがって、 [GetCount](#getcount)などのメソッドを使用する場合、このメソッドは多次元配列内の要素の合計数を返さないことに注意してください。

**ヘッダー:** atlsafe.h

## <a name="requirements"></a>要件

**ヘッダー:** atlsafe.h

## <a name="ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a> CComSafeArrayBound::CComSafeArrayBound

コンストラクターです。

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>パラメーター

*ulCount*<br/>
配列の要素数。

*左辺のバインド*<br/>
配列の番号付け元となる下限。

### <a name="remarks"></a>解説

C++ プログラムから配列にアクセスする場合は、下限を0として定義することをお勧めします。 配列を他の言語 (Visual Basic など) と共に使用する場合は、別の下限値を使用することをお勧めします。

## <a name="ccomsafearrayboundgetcount"></a><a name="getcount"></a> CComSafeArrayBound:: GetCount

要素の数を取得するには、このメソッドを呼び出します。

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>戻り値

要素の数を返します。

### <a name="remarks"></a>解説

関連付けられた `CComSafeArray` オブジェクトが多次元配列を表している場合、このメソッドは、右端の次元にある要素の合計数のみを返します。 要素の合計数を取得するには、 [CComSafeArray:: GetCount](../../atl/reference/ccomsafearray-class.md#getcount) を使用します。

## <a name="ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a> CComSafeArrayBound:: Get下限バインド

下限を返すには、このメソッドを呼び出します。

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの下限を返し `CComSafeArrayBound` ます。

## <a name="ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a> CComSafeArrayBound:: System.array.getupperbound

上限を返すには、このメソッドを呼び出します。

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの上限を返し `CComSafeArrayBound` ます。

### <a name="remarks"></a>解説

上限は、要素の数と下限の値によって異なります。 たとえば、下限が0で要素の数が10の場合、上限は自動的に9に設定されます。

## <a name="ccomsafearrayboundoperator-"></a><a name="operator_eq"></a> CComSafeArrayBound:: operator =

を `CComSafeArrayBound` 新しい値に設定します。

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>パラメーター

*バインディング*<br/>
`CComSafeArrayBound` オブジェクト。

*ulCount*<br/>
要素の数。

### <a name="return-value"></a>戻り値

オブジェクトへのポインターを返し `CComSafeArrayBound` ます。

### <a name="remarks"></a>解説

オブジェクトは、 `CComSafeArrayBound` 既存のを使用するか、要素の数を指定することによって割り当てることができ `CComSafeArrayBound` ます。この場合、下限は既定で0に設定されます。

## <a name="ccomsafearrayboundsetcount"></a><a name="setcount"></a> CComSafeArrayBound:: SetCount

要素の数を設定するには、このメソッドを呼び出します。

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>パラメーター

*ulCount*<br/>
要素の数。

### <a name="return-value"></a>戻り値

オブジェクト内の要素の数を返し `CComSafeArrayBound` ます。

## <a name="ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a> CComSafeArrayBound:: Set下限バインド

下限を設定するには、このメソッドを呼び出します。

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>パラメーター

*左辺のバインド*<br/>
下限値です。

### <a name="return-value"></a>戻り値

オブジェクトの新しい下限を返し `CComSafeArrayBound` ます。

### <a name="remarks"></a>解説

配列に Visual C++ プログラムからアクセスする場合は、下限を0として定義することをお勧めします。 配列を他の言語 (Visual Basic など) と共に使用する場合は、別の下限値を使用することをお勧めします。

上限は、要素の数と下限の値によって異なります。 たとえば、下限が0で要素の数が10の場合、上限は自動的に9に設定されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
