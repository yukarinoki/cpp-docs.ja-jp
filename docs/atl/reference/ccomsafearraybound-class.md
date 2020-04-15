---
title: クラスを指定します。
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
ms.openlocfilehash: 2c2f8b787e5366ec893538a88049f6f53dc35caf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327382"
---
# <a name="ccomsafearraybound-class"></a>クラスを指定します。

このクラスは[、SAFEARRAYBOUND](/windows/win32/api/oaidl/ns-oaidl-safearraybound)構造体のラッパーです。

## <a name="syntax"></a>構文

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[ココムセーフアレイバウンド](#ccomsafearraybound)|コンストラクターです。|
|[GetCount](#getcount)|要素の数を返します。|
|[ローワーバウンドを取得します。](#getlowerbound)|下限を返します。|
|[ゲットアッパーバウンド](#getupperbound)|上限を返します。|
|[カウントを設定します。](#setcount)|要素の数を設定します。|
|[ローワーバウンドの設定](#setlowerbound)|下限を設定します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 =](#operator_eq)|を新`CComSafeArrayBound`しい値に設定します。|

## <a name="remarks"></a>解説

このクラスは`SAFEARRAYBOUND`[、CCom セーフアレイ](../../atl/reference/ccomsafearray-class.md)によって使用される構造体のラッパーです。 `CComSafeArray`オブジェクトの 1 つの次元の上限と下限、およびオブジェクトに含まれる要素の数を照会および設定するためのメソッドを提供します。 多次元`CComSafeArray`オブジェクトは、次元ごとに`CComSafeArrayBound`1 つずつオブジェクトの配列を使用します。 したがって、 [GetCount](#getcount)などのメソッドを使用する場合、このメソッドは多次元配列内の要素の合計数を返さないことに注意してください。

**ヘッダー:** atlsafe.h

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsafe.h

## <a name="ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a>ココムセーフアレイバウンド::CComセーフアレイバウンド

コンストラクターです。

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>パラメーター

*ウルカウント*<br/>
配列の要素数。

*lローワーバウンド*<br/>
配列の番号が付けられた下限。

### <a name="remarks"></a>解説

C++ プログラムから配列にアクセスする場合は、下限を 0 として定義することをお勧めします。 配列を Visual Basic などの他の言語で使用する場合は、別の下限値を使用することをお勧めできます。

## <a name="ccomsafearrayboundgetcount"></a><a name="getcount"></a>を指定します。

要素の数を返します。

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>戻り値

要素の数を返します。

### <a name="remarks"></a>解説

関連付けられた`CComSafeArray`オブジェクトが多次元配列を表す場合、このメソッドは右端の次元の要素の総数のみを返します。 要素の総数を取得するには[、CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount)を使用します。

## <a name="ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a>を取得します。

下限を返します。

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの下限を`CComSafeArrayBound`返します。

## <a name="ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a>ココムセーフアレイバウンド::ゲットアッパーバウンド

上限を返します。

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの上限を`CComSafeArrayBound`返します。

### <a name="remarks"></a>解説

上限は、要素の数と下限値によって異なります。 たとえば、下限が 0 で要素の数が 10 の場合、上限は自動的に 9 に設定されます。

## <a name="ccomsafearrayboundoperator-"></a><a name="operator_eq"></a>次の操作を行います。

を新`CComSafeArrayBound`しい値に設定します。

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>パラメーター

*バインド*<br/>
`CComSafeArrayBound` オブジェクト。

*ウルカウント*<br/>
要素の数。

### <a name="return-value"></a>戻り値

オブジェクトへのポインターを`CComSafeArrayBound`返します。

### <a name="remarks"></a>解説

オブジェクト`CComSafeArrayBound`は、既存`CComSafeArrayBound`の を使用して割り当てることも、要素の数を指定して割り当てることもできます。

## <a name="ccomsafearrayboundsetcount"></a><a name="setcount"></a>バインド::セットカウント

要素の数を設定します。

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>パラメーター

*ウルカウント*<br/>
要素の数。

### <a name="return-value"></a>戻り値

オブジェクト内の要素の数を`CComSafeArrayBound`返します。

## <a name="ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a>を設定します。

下限を設定します。

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>パラメーター

*lローワーバウンド*<br/>
下限値です。

### <a name="return-value"></a>戻り値

オブジェクトの新しい下限を`CComSafeArrayBound`返します。

### <a name="remarks"></a>解説

Visual C++ プログラムから配列にアクセスする場合は、下限を 0 として定義することをお勧めします。 配列を Visual Basic などの他の言語で使用する場合は、別の下限値を使用することをお勧めできます。

上限は、要素の数と下限値によって異なります。 たとえば、下限が 0 で要素の数が 10 の場合、上限は自動的に 9 に設定されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
