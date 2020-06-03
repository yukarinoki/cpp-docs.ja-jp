---
title: CFileTimeSpan クラス
description: アクティブ テンプレート ライブラリ (ATL) クラスとマイクロソフト ファウンデーション クラス (MFC) CFileTimeSpan クラスは、時間間隔を FILETIME 単位で管理します。
ms.date: 01/10/2020
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
ms.openlocfilehash: 87737ea1c778660a68510b484bcdfa3a4670e8ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317847"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan クラス

このクラスには、ファイルに関連付けられた相対日付と時刻の値を管理するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```cpp
class CFileTimeSpan
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を使用します。](#cfiletimespan)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を見る](#gettimespan)|`CFileTimeSpan`オブジェクトから期間を取得します。|
|[を切り開く](#settimespan)|`CFileTimeSpan`オブジェクトの期間を設定します。|

### <a name="public-operators"></a>公共事業者

|名前|説明|
|----------|-----------------|
|[を使用する -](#operator_-)|オブジェクトの減算を`CFileTimeSpan`実行します。|
|[を指定します。](#operator_neq)|2 つの `CFileTimeSpan` オブジェクトが等しくないかどうかを比較します。|
|[Cファイルタイムスパン::演算子 +](#operator_add)|オブジェクトに対して`CFileTimeSpan`追加を実行します。|
|[Cファイルタイムスパン::演算子 +=](#operator_add_eq)|オブジェクトに対して`CFileTimeSpan`追加を実行し、その結果を現在のオブジェクトに割り当てます。|
|[を使用します。&lt;](#operator_lt)|2 つの`CFileTimeSpan`オブジェクトを比較して、小さい方を決定します。|
|[を使用します。&lt;=](#operator_lt_eq)|2 つの`CFileTimeSpan`オブジェクトを比較して、等しいか、小さい方を判断します。|
|[Cファイルタイムスパン::演算子 =](#operator_eq)|代入演算子。|
|[Cファイルタイムスパン::演算子 -=](#operator_-_eq)|オブジェクトに対して減`CFileTimeSpan`算を実行し、その結果を現在のオブジェクトに割り当てます。|
|[Cファイルタイムスパン::演算子 ==](#operator_eq_eq)|2 つの `CFileTimeSpan` オブジェクトが等しいかどうかを比較します。|
|[を使用します。&gt;](#operator_gt)|2 つの`CFileTimeSpan`オブジェクトを比較して、大きい方を決定します。|
|[を使用します。&gt;=](#operator_gt_eq)|2 つの`CFileTimeSpan`オブジェクトを比較して、等しいか、大きいかを判断します。|

## <a name="remarks"></a>解説

この`CFileTimeSpan`クラスには、ファイルシステムが使用する単位で相対的な期間を処理するメソッドが用意されています。 これらの単位は、ファイルの作成日時、最終アクセス時、最後に変更されたファイル操作など、ファイル操作でよく使用されます。 このクラスのメソッドは[、CFileTime クラス](../../atl-mfc-shared/reference/cfiletime-class.md)オブジェクトと共に頻繁に使用されます。

## <a name="example"></a>例

[「CFileTime::ミリ秒](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)」の例を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atltime.h

## <a name="cfiletimespancfiletimespan"></a><a name="cfiletimespan"></a>を使用します。

コンストラクターです。

```cpp
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
既存の `CFileTimeSpan` オブジェクトです。

*nスパン*\
FILETIME 単位の期間。

### <a name="remarks"></a>解説

オブジェクト`CFileTimeSpan`は、既存`CFileTimeSpan`のオブジェクトを使用して作成することも、100 ナノ秒の FILETIME 単位で 64 ビット値として表現することもできます。 詳細については、「 [CFileTime](cfiletime-class.md)」を参照してください。 既定のコンストラクターは、期間を 0 に設定します。

## <a name="cfiletimespangettimespan"></a><a name="gettimespan"></a>を見る

`CFileTimeSpan`オブジェクトから期間を取得します。

```cpp
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>戻り値

100 ナノ秒の FILETIME 単位で期間を返します。 詳細については、「 [CFileTime](cfiletime-class.md)」を参照してください。

## <a name="cfiletimespanoperator--"></a><a name="operator_-"></a>を使用する -

オブジェクトの減算を`CFileTimeSpan`実行します。

```cpp
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

2`CFileTimeSpan`つの期間の差の結果を表すオブジェクトを返します。

## <a name="cfiletimespanoperator-"></a><a name="operator_neq"></a>を指定します。

2 つの `CFileTimeSpan` オブジェクトが等しくないかどうかを比較します。

```cpp
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

比較される項目がオブジェクトと等しくない場合は TRUE`CFileTimeSpan`を返します。それ以外の場合は FALSE。

## <a name="cfiletimespanoperator-"></a><a name="operator_add"></a>Cファイルタイムスパン::演算子 +

オブジェクトに対して`CFileTimeSpan`追加を実行します。

```cpp
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

2`CFileTimeSpan`つの期間の合計を含むオブジェクトを返します。

## <a name="cfiletimespanoperator-"></a><a name="operator_add_eq"></a>Cファイルタイムスパン::演算子 +=

オブジェクトに対して`CFileTimeSpan`加算を実行し、その結果を現在のオブジェクトに割り当てます。

```cpp
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

2 つの`CFileTimeSpan`期間の合計を含む更新されたオブジェクトを返します。

## <a name="cfiletimespanoperator-lt"></a><a name="operator_lt"></a>を使用します。&lt;

2 つの`CFileTimeSpan`オブジェクトを比較して、小さい方を決定します。

```cpp
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが 2 番目のオブジェクトより短い (つまり、短い期間を表す) 場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cfiletimespanoperator-lt"></a><a name="operator_lt_eq"></a>を使用します。&lt;=

2 つの`CFileTimeSpan`オブジェクトを比較して、等しいか、小さい方を判断します。

```cpp
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが短い (つまり、短い期間を表す) か、2 番目のオブジェクトと等しい場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cfiletimespanoperator-"></a><a name="operator_eq"></a>Cファイルタイムスパン::演算子 =

代入演算子。

```cpp
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

更新された`CFileTimeSpan`オブジェクトを返します。

## <a name="cfiletimespanoperator--"></a><a name="operator_-_eq"></a>Cファイルタイムスパン::演算子 -=

オブジェクトに対して減`CFileTimeSpan`算を実行し、その結果を現在のオブジェクトに割り当てます。

```cpp
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

更新された`CFileTimeSpan`オブジェクトを返します。

## <a name="cfiletimespanoperator-"></a><a name="operator_eq_eq"></a>Cファイルタイムスパン::演算子 ==

2 つの `CFileTimeSpan` オブジェクトが等しいかどうかを比較します。

```cpp
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cfiletimespanoperator-gt"></a><a name="operator_gt"></a>を使用します。&gt;

2 つの`CFileTimeSpan`オブジェクトを比較して、大きい方を決定します。

```cpp
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが 2 番目のオブジェクトより大きい場合 (つまり、長い期間を表す) 場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cfiletimespanoperator-gt"></a><a name="operator_gt_eq"></a>を使用します。&gt;=

2 つの`CFileTimeSpan`オブジェクトを比較して、等しいか、大きいかを判断します。

```cpp
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*\
比較される `CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが長い (つまり、長い期間を表す) か、2 番目のオブジェクトと等しい場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cfiletimespansettimespan"></a><a name="settimespan"></a>を切り開く

`CFileTimeSpan`オブジェクトの期間を設定します。

```cpp
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>パラメーター

*nスパン*\
100 ナノ秒の FILETIME 単位の期間の新しい値。 詳細については、「 [CFileTime](cfiletime-class.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime)\
[クラス](cfiletime-class.md)\
[階層グラフ](../../mfc/hierarchy-chart.md)\
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
