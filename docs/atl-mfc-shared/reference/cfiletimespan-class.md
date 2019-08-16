---
title: CFileTimeSpan クラス
ms.date: 10/18/2018
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
ms.openlocfilehash: f9bb42ba4c142f671a83dcfa7e99cff940fff047
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491293"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan クラス

このクラスは、ファイルに関連付けられている相対的な日付と時刻の値を管理するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
class CFileTimeSpan
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|`CFileTimeSpan`オブジェクトから期間を取得するには、このメソッドを呼び出します。|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|`CFileTimeSpan`オブジェクトの期間を設定するには、このメソッドを呼び出します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CFileTimeSpan:: operator-](#operator_-)|`CFileTimeSpan`オブジェクトに対して減算を実行します。|
|[CFileTimeSpan:: operator! =](#operator_neq)|2 つの `CFileTimeSpan` オブジェクトが等しくないかどうかを比較します。|
|[CFileTimeSpan:: operator +](#operator_add)|`CFileTimeSpan`オブジェクトに対して加算を実行します。|
|[CFileTimeSpan:: operator + =](#operator_add_eq)|`CFileTimeSpan`オブジェクトに対して加算を実行し、その結果を現在のオブジェクトに代入します。|
|[CFileTimeSpan:: operator&lt;](#operator_lt)|2つ`CFileTimeSpan`のオブジェクトを比較して、小さい方を決定します。|
|[CFileTimeSpan:: operator&lt;=](#operator_lt_eq)|2つ`CFileTimeSpan`のオブジェクトを比較して等価性または小さい方を判断します。|
|[CFileTimeSpan:: operator =](#operator_eq)|代入演算子。|
|[CFileTimeSpan:: operator-=](#operator_-_eq)|`CFileTimeSpan`オブジェクトに対して減算を実行し、その結果を現在のオブジェクトに代入します。|
|[CFileTimeSpan::operator ==](#operator_eq_eq)|2 つの `CFileTimeSpan` オブジェクトが等しいかどうかを比較します。|
|[CFileTimeSpan:: operator&gt;](#operator_gt)|2つ`CFileTimeSpan`のオブジェクトを比較して、大きい方を判別します。|
|[CFileTimeSpan:: operator&gt;=](#operator_gt_eq)|2つ`CFileTimeSpan`のオブジェクトを比較して等価性または大きい方を判断します。|

## <a name="remarks"></a>Remarks

このクラスは、ファイルが作成されたとき、最後にアクセスしたとき、または最後に変更されたときに関連する操作を実行したときに発生する、相対的な時間の管理方法を提供します このクラスのメソッドは、 [CFileTime クラス](../../atl-mfc-shared/reference/cfiletime-class.md)オブジェクトと組み合わせて使用されることがよくあります。

## <a name="example"></a>例

[CFileTime:: ミリ秒](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)の例を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atltime. h

##  <a name="cfiletimespan"></a>CFileTimeSpan::CFileTimeSpan

コンストラクターです。

```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
既存の `CFileTimeSpan` オブジェクト。

*nSpan*<br/>
ミリ秒単位の時間。

### <a name="remarks"></a>Remarks

オブジェクト`CFileTimeSpan`は、既存`CFileTimeSpan`のオブジェクトを使用して作成することも、64ビット値として表すこともできます。 既定のコンストラクターは、時間間隔を0に設定します。

##  <a name="gettimespan"></a>  CFileTimeSpan::GetTimeSpan

`CFileTimeSpan`オブジェクトから期間を取得するには、このメソッドを呼び出します。

```
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>戻り値

時間間隔をミリ秒単位で返します。

##  <a name="operator_-"></a>  CFileTimeSpan::operator -

`CFileTimeSpan`オブジェクトに対して減算を実行します。

```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

2つの時間範囲の差の結果を表すオブジェクトを返します。`CFileTimeSpan`

##  <a name="operator_neq"></a>CFileTimeSpan:: operator! =

2 つの `CFileTimeSpan` オブジェクトが等しくないかどうかを比較します。

```
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

比較対象の項目が`CFileTimeSpan`オブジェクトと等しくない場合は TRUE、それ以外の場合は FALSE を返します。

##  <a name="operator_add"></a>CFileTimeSpan:: operator +

`CFileTimeSpan`オブジェクトに対して加算を実行します。

```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

2つの時間範囲の合計を格納しているオブジェクトを返します。`CFileTimeSpan`

##  <a name="operator_add_eq"></a>CFileTimeSpan:: operator + =

`CFileTimeSpan`オブジェクトに対して加算を実行し、その結果を現在のオブジェクトに代入します。

```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

2つの`CFileTimeSpan`時間範囲の合計を格納している更新されたオブジェクトを返します。

##  <a name="operator_lt"></a>  CFileTimeSpan::operator &lt;

2つ`CFileTimeSpan`のオブジェクトを比較して、小さい方を決定します。

```
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが2番目のオブジェクトよりも小さい (つまり、短い期間を表す) 場合は TRUE、それ以外の場合は FALSE を返します。

##  <a name="operator_lt_eq"></a>  CFileTimeSpan::operator &lt;=

2つ`CFileTimeSpan`のオブジェクトを比較して等価性または小さい方を判断します。

```
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトがより小さい場合 (つまり、より短い期間を表す)、または2番目のオブジェクトと等しい場合は TRUE、それ以外の場合は FALSE を返します。

##  <a name="operator_eq"></a>CFileTimeSpan:: operator =

代入演算子。

```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

更新さ`CFileTimeSpan`れたオブジェクトを返します。

##  <a name="operator_-_eq"></a>CFileTimeSpan:: operator-=

`CFileTimeSpan`オブジェクトに対して減算を実行し、その結果を現在のオブジェクトに代入します。

```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

更新さ`CFileTimeSpan`れたオブジェクトを返します。

##  <a name="operator_eq_eq"></a>CFileTimeSpan:: operator = =

2 つの `CFileTimeSpan` オブジェクトが等しいかどうかを比較します。

```
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は TRUE、それ以外の場合は FALSE を返します。

##  <a name="operator_gt"></a>  CFileTimeSpan::operator &gt;

2つ`CFileTimeSpan`のオブジェクトを比較して、大きい方を判別します。

```
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが2番目のオブジェクトよりも大きい (つまり、より長い期間を表す) 場合は TRUE、それ以外の場合は FALSE を返します。

##  <a name="operator_gt_eq"></a>  CFileTimeSpan::operator &gt;=

2つ`CFileTimeSpan`のオブジェクトを比較して等価性または大きい方を判断します。

```
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトがより大きい場合 (つまり、より長い期間を表す)、または2番目のオブジェクトと等しい場合は TRUE、それ以外の場合は FALSE を返します。

##  <a name="settimespan"></a>  CFileTimeSpan::SetTimeSpan

`CFileTimeSpan`オブジェクトの期間を設定するには、このメソッドを呼び出します。

```
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>パラメーター

*nSpan*<br/>
時間間隔の新しい値 (ミリ秒単位)。

## <a name="see-also"></a>関連項目

[返る](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTime クラス](../../atl-mfc-shared/reference/cfiletime-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
