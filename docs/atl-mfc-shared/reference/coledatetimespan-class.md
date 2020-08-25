---
title: COleDateTimeSpan クラス
ms.date: 03/27/2019
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
ms.openlocfilehash: 746cfdce3265dff7e5b20a5135aa026aca9facdf
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832101"
---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan クラス

時間間隔の相対時間を表します。

## <a name="syntax"></a>構文

```
class COleDateTimeSpan
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|`COleDateTimeSpan` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleDateTimeSpan:: Format](#format)|オブジェクトの書式設定された文字列形式を生成 `COleDateTimeSpan` します。|
|[COleDateTimeSpan::GetDays](#getdays)|このオブジェクトが表すスパンの日の部分を返し `COleDateTimeSpan` ます。|
|[COleDateTimeSpan:: GetHours](#gethours)|このオブジェクトが表すスパンの時間部分を返し `COleDateTimeSpan` ます。|
|[COleDateTimeSpan:: GetMinutes](#getminutes)|このオブジェクトが表すスパンの分の部分を返し `COleDateTimeSpan` ます。|
|[COleDateTimeSpan:: GetSeconds](#getseconds)|このオブジェクトが表すスパンの2番目の部分を返し `COleDateTimeSpan` ます。|
|[COleDateTimeSpan:: GetStatus](#getstatus)|このオブジェクトの状態 (有効) を取得し `COleDateTimeSpan` ます。|
|[COleDateTimeSpan:: GetTotalDays](#gettotaldays)|このオブジェクトが表す日数を返し `COleDateTimeSpan` ます。|
|[COleDateTimeSpan:: GetTotalHours](#gettotalhours)|このオブジェクトが表す時間数を返し `COleDateTimeSpan` ます。|
|[COleDateTimeSpan:: GetTotalMinutes](#gettotalminutes)|このオブジェクトが表す分数を返し `COleDateTimeSpan` ます。|
|[COleDateTimeSpan:: GetTotalSeconds](#gettotalseconds)|このオブジェクトが表す秒数を返し `COleDateTimeSpan` ます。|
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|このオブジェクトの値を設定 `COleDateTimeSpan` します。|
|[COleDateTimeSpan:: SetStatus](#setstatus)|このオブジェクトの状態 (有効性) を設定し `COleDateTimeSpan` ます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|-|-|
|[演算子 +、-](#operator_add_-)|値の符号を追加、削除、および変更し `COleDateTimeSpan` ます。|
|[operator + =、-=](#operator_add_eq_-_eq)|`COleDateTimeSpan`この値から値を加算および減算 `COleDateTimeSpan` します。|
|[operator =](#operator_eq)|値をコピー `COleDateTimeSpan` します。|
|[operator = =、<、<=](#coledatetimespan_relational_operators)|2つ `COleDateTimeSpan` の値を比較します。|
|[double 演算子](#operator_double)|この `COleDateTimeSpan` 値をに変換 **`double`** します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleDateTimeSpan:: m_span](#m_span)|このオブジェクトの基になるを格納 **`double`** `COleDateTimeSpan` します。|
|[COleDateTimeSpan:: m_status](#m_status)|このオブジェクトの状態を格納 `COleDateTimeSpan` します。|

## <a name="remarks"></a>解説

`COleDateTimeSpan` に基底クラスがありません。

は、 `COleDateTimeSpan` 時間を日数で保持します。

`COleDateTimeSpan` は、付随するクラス [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)と共に使用されます。 `COleDateTime``DATE`OLE オートメーションのデータ型をカプセル化します。 `COleDateTime` 絶対時刻値を表します。 すべて `COleDateTime` の計算には値が含ま `COleDateTimeSpan` れます。 これらのクラス間の関係は、 [CTime](../../atl-mfc-shared/reference/ctime-class.md) と [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)の間の関係に似ています。

クラスとクラスの詳細については、 `COleDateTime` `COleDateTimeSpan` 「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** ATLComTime .h

## <a name="coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a> COleDateTimeSpan 関係演算子

比較演算子。

```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```

### <a name="parameters"></a>パラメーター

*dateSpan*<br/>
比較対象の `COleDateTimeSpan`。

### <a name="return-value"></a>戻り値

これらの演算子は、2つの日付/時間範囲の値を比較し、条件が true の場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

> [!NOTE]
> いずれかのオペランドが無効な場合、ATLASSERT が発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

## <a name="coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a> COleDateTimeSpan::COleDateTimeSpan

`COleDateTimeSpan` オブジェクトを構築します。

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>パラメーター

*dblSpanSrc*<br/>
新しいオブジェクトにコピーされる日数 `COleDateTimeSpan` 。

*Ldays*、 *nhours*、 *nhours*、 *nhours*<br/>
新しいオブジェクトにコピーする日付と時刻の値を示し `COleDateTimeSpan` ます。

### <a name="remarks"></a>解説

これらのすべてのコンストラクターは `COleDateTimeSpan` 、指定された値に初期化された新しいオブジェクトを作成します。 これらの各コンストラクターの簡単な説明を次に示します。

- **COleDateTimeSpan ()**`COleDateTimeSpan`0 に初期化されたオブジェクトを構築します。

- **COleDateTimeSpan (** `dblSpanSrc` **)** は、 `COleDateTimeSpan` 浮動小数点値からオブジェクトを構築します。

- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)** は、 `COleDateTimeSpan` 指定した数値に初期化されたオブジェクトを構築します。

新しいオブジェクトの状態 `COleDateTimeSpan` が有効に設定されます。

値の境界の詳細については `COleDateTimeSpan` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

## <a name="coledatetimespanformat"></a><a name="format"></a> COleDateTimeSpan:: Format

オブジェクトの書式設定された文字列形式を生成 `COleDateTimeSpan` します。

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>パラメーター

*pFormat*<br/>
書式設定文字列に類似した書式設定文字列 `printf` 。 書式指定コードの前にパーセント () 記号を付けると、 `%` 対応するコンポーネントが置き換えられ `COleDateTimeSpan` ます。 書式設定文字列内のその他の文字は、返された文字列にそのままコピーされます。 の書式設定コードの値と意味を `Format` 以下に示します。

- **% H** 現在の日の時間

- **% M** 現在の時間 (分)

- **% S** 現在の1分間の秒数

- **%%** パーセント記号

上記の4つの書式コードは、形式が受け入れる唯一のコードです。

-

*nID*<br/>
書式制御文字列のリソース ID。

### <a name="return-value"></a>戻り値

`CString`書式設定された日付/時間範囲の値を格納している。

### <a name="remarks"></a>解説

これらの関数を呼び出して、期間の値の書式設定された表現を作成します。 このオブジェクトの状態 `COleDateTimeSpan` が null の場合、戻り値は空の文字列になります。 状態が無効である場合は、文字列リソース IDS_INVALID_DATETIMESPAN によって返される文字列が指定されます。

この関数のフォームの簡単な説明を次に示します。

**形式 (** *pformat* **)**<br/>
この形式では、のように、特殊な書式指定コードの前にパーセント記号 (%) を付けた書式指定文字列を使用して、値の書式を設定し `printf` ます。 書式設定文字列は、パラメーターとして関数に渡されます。

**形式 (** *nID* **)**<br/>
この形式では、のように、特殊な書式指定コードの前にパーセント記号 (%) を付けた書式指定文字列を使用して、値の書式を設定し `printf` ます。 書式設定文字列はリソースです。 この文字列リソースの ID は、パラメーターとして渡されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

## <a name="coledatetimespangetdays"></a><a name="getdays"></a> COleDateTimeSpan::GetDays

この日付/時間範囲の値の日の部分を取得します。

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲値の日付部分。

### <a name="remarks"></a>解説

この関数からの戻り値の範囲は、約-3615000 ~ 3615000 です。

オブジェクトの値を照会するその他の関数につい `COleDateTimeSpan` ては、次のメンバー関数を参照してください。

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

## <a name="coledatetimespangethours"></a><a name="gethours"></a> COleDateTimeSpan:: GetHours

この日付/時間範囲値の時間部分を取得します。

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲の値の時間部分。

### <a name="remarks"></a>解説

この関数の戻り値の範囲は、-23 ~ 23 です。

オブジェクトの値を照会するその他の関数につい `COleDateTimeSpan` ては、次のメンバー関数を参照してください。

- [GetDays](#getdays)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

## <a name="coledatetimespangetminutes"></a><a name="getminutes"></a> COleDateTimeSpan:: GetMinutes

この日付/時間範囲の値の分の部分を取得します。

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲の値の分の部分。

### <a name="remarks"></a>解説

この関数からの戻り値の範囲は、-59 ~ 59 です。

オブジェクトの値を照会するその他の関数につい `COleDateTimeSpan` ては、次のメンバー関数を参照してください。

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

## <a name="coledatetimespangetseconds"></a><a name="getseconds"></a> COleDateTimeSpan:: GetSeconds

この日付/時間範囲の値の2番目の部分を取得します。

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲の値の秒部分。

### <a name="remarks"></a>解説

この関数からの戻り値の範囲は、-59 ~ 59 です。

オブジェクトの値を照会するその他の関数につい `COleDateTimeSpan` ては、次のメンバー関数を参照してください。

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

## <a name="coledatetimespangetstatus"></a><a name="getstatus"></a> COleDateTimeSpan:: GetStatus

このオブジェクトの状態 (有効) を取得し `COleDateTimeSpan` ます。

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>戻り値

この値の状態 `COleDateTimeSpan` 。

### <a name="remarks"></a>解説

戻り値は、クラス内で定義されている列挙型によって定義され `DateTimeSpanStatus` `COleDateTimeSpan` ます。

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
};
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleDateTimeSpan::valid` このオブジェクトが有効であることを示し `COleDateTimeSpan` ます。

- `COleDateTimeSpan::invalid` このオブジェクトが無効であることを示します。つまり `COleDateTimeSpan` 、値が正しくない可能性があります。

- `COleDateTimeSpan::null` このオブジェクトが null であること、つまり `COleDateTimeSpan` 、このオブジェクトに値が指定されていないことを示します。 (これは、C++ NULL ではなく、"値がない" というデータベースの意味では "null" です)。

オブジェクトの状態 `COleDateTimeSpan` は、次の場合には無効です。

- このオブジェクトの算術演算の実行中にオーバーフローまたはアンダーフローが発生した場合 (つまり、 `+=` または) `-=` 。

- 無効な値がこのオブジェクトに割り当てられた場合は。

- このオブジェクトの状態が、を使用して明示的に無効に設定された場合は `SetStatus` 。

状態が無効に設定されている可能性のある操作の詳細については、「 [COleDateTimeSpan:: operator +,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) and [COleDateTimeSpan:: operator + =,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)」を参照してください。

値の境界の詳細については `COleDateTimeSpan` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimespangettotaldays"></a><a name="gettotaldays"></a> COleDateTimeSpan:: GetTotalDays

この日付/時間範囲の値を日単位で取得します。

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲の値は、日数で表されます。 この関数は、double 型を返すためにプロトタイプ宣言されていますが、常に整数値を返します。

### <a name="remarks"></a>解説

この関数からの戻り値の範囲は、3.65 e6 と 3.65 e6 です。

オブジェクトの値を照会するその他の関数につい `COleDateTimeSpan` ては、次のメンバー関数を参照してください。

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

## <a name="coledatetimespangettotalhours"></a><a name="gettotalhours"></a> COleDateTimeSpan:: GetTotalHours

この日付/時間範囲値を時間で表した値を取得します。

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間間隔の値 (時間単位)。 この関数は、double 型を返すためにプロトタイプ宣言されていますが、常に整数値を返します。

### <a name="remarks"></a>解説

この関数の戻り値の範囲は、8.77 e7 と 8.77 e7 の間です。

オブジェクトの値を照会するその他の関数につい `COleDateTimeSpan` ては、次のメンバー関数を参照してください。

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>例

[Gettotaldays](#gettotaldays)の例を参照してください。

## <a name="coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a> COleDateTimeSpan:: GetTotalMinutes

この日付/時間範囲の値を分単位で取得します。

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間間隔の値を分単位で表します。 この関数は、double 型を返すためにプロトタイプ宣言されていますが、常に整数値を返します。

### <a name="remarks"></a>解説

この関数の戻り値の範囲は、5.26 e9 と 5.26 e9 の間です。

オブジェクトの値を照会するその他の関数につい `COleDateTimeSpan` ては、次のメンバー関数を参照してください。

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>例

[Gettotaldays](#gettotaldays)の例を参照してください。

## <a name="coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a> COleDateTimeSpan:: GetTotalSeconds

この日付/時間範囲の値を秒単位で取得します。

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間間隔の値 (秒単位)。 この関数は、double 型を返すためにプロトタイプ宣言されていますが、常に整数値を返します。

### <a name="remarks"></a>解説

この関数からの戻り値は、3.16 e11 から 3.16 e11 までの範囲です。

オブジェクトの値を照会するその他の関数につい `COleDateTimeSpan` ては、次のメンバー関数を参照してください。

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

### <a name="example"></a>例

[Gettotaldays](#gettotaldays)の例を参照してください。

## <a name="coledatetimespanm_span"></a><a name="m_span"></a> COleDateTimeSpan:: m_span

**`double`** このオブジェクトの基になる値 `COleDateTime` 。

```
double m_span;
```

### <a name="remarks"></a>解説

この値は、日付/時間間隔を日数で表します。

> [!CAUTION]
> データメンバーの値を変更すると **`double`** 、このオブジェクトの値が変更され `COleDateTimeSpan` ます。 このオブジェクトの状態は変更されません `COleDateTimeSpan` 。

## <a name="coledatetimespanm_status"></a><a name="m_status"></a> COleDateTimeSpan:: m_status

このデータメンバーの型は列挙型であり、 `DateTimeSpanStatus` クラス内で定義されてい `COleDateTimeSpan` ます。

```
DateTimeSpanStatus m_status;
```

### <a name="remarks"></a>解説

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleDateTimeSpan::valid` このオブジェクトが有効であることを示し `COleDateTimeSpan` ます。

- `COleDateTimeSpan::invalid` このオブジェクトが無効であることを示します。つまり `COleDateTimeSpan` 、値が正しくない可能性があります。

- `COleDateTimeSpan::null` このオブジェクトが null であること、つまり `COleDateTimeSpan` 、このオブジェクトに値が指定されていないことを示します。 (これは、C++ NULL ではなく、"値がない" というデータベースの意味では "null" です)。

オブジェクトの状態 `COleDateTimeSpan` は、次の場合には無効です。

- このオブジェクトの算術演算の実行中にオーバーフローまたはアンダーフローが発生した場合 (つまり、 `+=` または) `-=` 。

- 無効な値がこのオブジェクトに割り当てられた場合は。

- このオブジェクトの状態が [SetStatus](#setstatus)を使用して明示的に無効に設定された場合は。

状態が無効に設定されている可能性のある操作の詳細については、「 [COleDateTimeSpan:: operator +,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) and [COleDateTimeSpan:: operator + =,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)」を参照してください。

> [!CAUTION]
> このデータメンバーは、高度なプログラミングの状況を対象としています。 インラインメンバー関数 [GetStatus](#getstatus) および [SetStatus](#setstatus)を使用する必要があります。 `SetStatus`このデータメンバーを明示的に設定する方法については、「」を参照してください。

値の境界の詳細については `COleDateTimeSpan` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimespanoperator-"></a><a name="operator_eq"></a> COleDateTimeSpan:: operator =

値をコピー `COleDateTimeSpan` します。

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>解説

このオーバーロードされた代入演算子は、ソースの日付/時間範囲の値をこのオブジェクトにコピー `COleDateTimeSpan` します。

## <a name="coledatetimespanoperator---"></a><a name="operator_add_-"></a> COleDateTimeSpan:: operator +、-

値の符号を追加、削除、および変更し `COleDateTimeSpan` ます。

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>解説

最初の2つの演算子を使用すると、日付/時間範囲の値を加算および減算できます。 3番目の方法では、日付/時間範囲の値の符号を変更できます。

オペランドのいずれかが null の場合、結果の値の状態 `COleDateTimeSpan` は null になります。

オペランドのいずれかが無効で、もう一方が null でない場合、結果の値の状態 `COleDateTimeSpan` は無効になります。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status) メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

## <a name="coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a> COleDateTimeSpan:: operator + =、-=

`COleDateTimeSpan`この値から値を加算および減算 `COleDateTimeSpan` します。

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>解説

これらの演算子を使用すると、このオブジェクトから日付/時間範囲の値を加算および減算でき `COleDateTimeSpan` ます。 オペランドのいずれかが null の場合、結果の値の状態 `COleDateTimeSpan` は null になります。

オペランドのいずれかが無効で、もう一方が null でない場合、結果の値の状態 `COleDateTimeSpan` は無効になります。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status) メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

## <a name="coledatetimespanoperator-double"></a><a name="operator_double"></a> COleDateTimeSpan:: operator double

この `COleDateTimeSpan` 値をに変換 **`double`** します。

```
operator double() const throw();
```

### <a name="remarks"></a>解説

この演算子は、この値の値を、 `COleDateTimeSpan` 浮動小数点数として返します。

## <a name="coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a> COleDateTimeSpan::SetDateTimeSpan

この日付/時間範囲値の値を設定します。

```cpp
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>パラメーター

*Ldays*、 *nhours*、 *nhours*、 *nhours*<br/>
このオブジェクトにコピーする日付範囲と期間の値を示し `COleDateTimeSpan` ます。

### <a name="remarks"></a>解説

オブジェクトの値を照会する関数につい `COleDateTimeSpan` ては、次のメンバー関数を参照してください。

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]

## <a name="coledatetimespansetstatus"></a><a name="setstatus"></a> COleDateTimeSpan:: SetStatus

このオブジェクトの状態 (有効性) を設定し `COleDateTimeSpan` ます。

```cpp
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>パラメーター

*status*<br/>
このオブジェクトの新しいステータス値 `COleDateTimeSpan` 。

### <a name="remarks"></a>解説

*Status*パラメーターの値は、クラス内で定義されている列挙型によって定義され `DateTimeSpanStatus` `COleDateTimeSpan` ます。

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleDateTimeSpan::valid` このオブジェクトが有効であることを示し `COleDateTimeSpan` ます。

- `COleDateTimeSpan::invalid` このオブジェクトが無効であることを示します。つまり `COleDateTimeSpan` 、値が正しくない可能性があります。

- `COleDateTimeSpan::null` このオブジェクトが null であること、つまり `COleDateTimeSpan` 、このオブジェクトに値が指定されていないことを示します。 (これは、C++ NULL ではなく、"値がない" というデータベースの意味では "null" です)。

   > [!CAUTION]
   > この関数は、高度なプログラミングの状況に適しています。 この関数は、このオブジェクトのデータを変更しません。 この値は、通常、状態を **null** または **無効**に設定するために使用されます。 代入演算子 ([operator =](#operator_eq)) と [SetDateTimeSpan](#setdatetimespan) は、ソース値に基づいてオブジェクトの状態を設定することに注意してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>関連項目

[COleDateTime クラス](../../atl-mfc-shared/reference/coledatetime-class.md)<br/>
[CTime クラス](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
