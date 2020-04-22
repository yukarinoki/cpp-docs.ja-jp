---
title: クラス
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
ms.openlocfilehash: 8f6a26c2724146f8723dee3ddce60ddce6995ec8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747150"
---
# <a name="coledatetimespan-class"></a>クラス

相対時間、期間を表します。

## <a name="syntax"></a>構文

```
class COleDateTimeSpan
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を使用します。](#coledatetimespan)|`COleDateTimeSpan` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を指定します。](#format)|オブジェクトの書式付き文字列形式を`COleDateTimeSpan`生成します。|
|[を見る](#getdays)|このオブジェクトが表す範囲の日`COleDateTimeSpan`の部分を返します。|
|[時間数を取得します。](#gethours)|このオブジェクトが表す範囲の時間`COleDateTimeSpan`の部分を返します。|
|[を切り取る](#getminutes)|この`COleDateTimeSpan`オブジェクトが表す範囲の分の部分を返します。|
|[を切り取る](#getseconds)|この`COleDateTimeSpan`オブジェクトが表す範囲の 2 番目の部分を返します。|
|[を使用します。](#getstatus)|この`COleDateTimeSpan`オブジェクトの状態 (有効性) を取得します。|
|[を見る](#gettotaldays)|このオブジェクトが表す日数`COleDateTimeSpan`を返します。|
|[時間数を取得します。](#gettotalhours)|このオブジェクトが表す時間`COleDateTimeSpan`数を返します。|
|[を使用します。](#gettotalminutes)|このオブジェクトが表す分`COleDateTimeSpan`数を返します。|
|[を切り取る](#gettotalseconds)|このオブジェクトが表す秒`COleDateTimeSpan`数を返します。|
|[を切り取る](#setdatetimespan)|この`COleDateTimeSpan`オブジェクトの値を設定します。|
|[を設定します。](#setstatus)|この`COleDateTimeSpan`オブジェクトのステータス (有効性) を設定します。|

### <a name="public-operators"></a>パブリック演算子

|||
|-|-|
|[演算子 +、 -](#operator_add_-)|値の符号を加算、減算`COleDateTimeSpan`、および変更します。|
|[演算子 +=、-=](#operator_add_eq_-_eq)|この`COleDateTimeSpan`値から値`COleDateTimeSpan`を加算および減算します。|
|[演算子 =](#operator_eq)|値を`COleDateTimeSpan`コピーします。|
|[演算子 ==,<,<=](#coledatetimespan_relational_operators)|2`COleDateTimeSpan`つの値を比較します。|
|[演算子 double](#operator_double)|この`COleDateTimeSpan`値を**倍精度浮動小数点数**に変換します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[を使用 m_spanします。](#m_span)|この`COleDateTimeSpan`オブジェクトの基になる**double**が含まれます。|
|[を使用 m_statusします。](#m_status)|このオブジェクトの状態を`COleDateTimeSpan`格納します。|

## <a name="remarks"></a>解説

`COleDateTimeSpan`は基本クラスを持っていません。

A`COleDateTimeSpan`は数日で時間を守ります。

`COleDateTimeSpan`は、コンパニオン クラス[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)と共に使用されます。 `COleDateTime`は、OLE`DATE`オートメーションのデータ型をカプセル化します。 `COleDateTime`は絶対時間値を表します。 すべての`COleDateTime`計算には値`COleDateTimeSpan`が含まれます。 これらのクラス間の関係は[、CTime](../../atl-mfc-shared/reference/ctime-class.md)と[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)の間の関係に似ています。

クラスと クラスの`COleDateTime`詳細`COleDateTimeSpan`については、「[日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** アトルコムタイム.h

## <a name="coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a>関係演算子

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

*日付スパン*<br/>
比較対象の `COleDateTimeSpan`。

### <a name="return-value"></a>戻り値

これらの演算子は、2 つの日付/期間の値を比較し、条件が true の場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

> [!NOTE]
> いずれかのオペランドが無効な場合は、ATLASSERT が発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

## <a name="coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a>を使用します。

`COleDateTimeSpan` オブジェクトを構築します。

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>パラメーター

*ドブルスパンスrc*<br/>
新しい`COleDateTimeSpan`オブジェクトにコピーされる日数。

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
新しい`COleDateTimeSpan`オブジェクトにコピーする曜日と時刻の値を指定します。

### <a name="remarks"></a>解説

これらのコンストラクターは、すべて、指定`COleDateTimeSpan`された値に初期化された新しいオブジェクトを作成します。 これらの各コンストラクターの簡単な説明を次に示します。

- **を使用します。** 0 に`COleDateTimeSpan`初期化されたオブジェクトを構築します。

- **を使用します**`dblSpanSrc`**。** 浮動小数点値から`COleDateTimeSpan`オブジェクトを構築します。

- **COleDateTimeSpan(** `lDays` **,** `nHours` **,** `nMins` **, )** `nSecs` **)** 指定した`COleDateTimeSpan`数値に初期化されたオブジェクトを構築します。

新しい`COleDateTimeSpan`オブジェクトのステータスが有効に設定されます。

`COleDateTimeSpan`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

## <a name="coledatetimespanformat"></a><a name="format"></a>を指定します。

オブジェクトの書式付き文字列形式を`COleDateTimeSpan`生成します。

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>パラメーター

*pフォーマット*<br/>
書式指定文字列に似た`printf`書式指定文字列。 フォーマット コードの前にパーセント記号`%`() が付いた書式コード`COleDateTimeSpan`は、対応するコンポーネントに置き換えられます。 書式指定文字列内の他の文字は、変更されずに返された文字列にコピーされます。 フォーマットコードの値と意味`Format`を以下に示します。

- **%H**現在の日の時間

- **%M**現在の時間の分

- **%S**現在の分の秒数

- **%%** パーセント記号

上記の 4 つの形式コードは、Format が受け入れる唯一のコードです。

-

*nID*<br/>
書式制御文字列のリソース ID。

### <a name="return-value"></a>戻り値

書式設定`CString`された日付/時間範囲の値を含む A。

### <a name="remarks"></a>解説

これらの関数を呼び出して、期間値の書式化された表現を作成します。 この`COleDateTimeSpan`オブジェクトの状態が null の場合、戻り値は空の文字列です。 状態が無効な場合、戻り値の文字列は文字列リソース IDS_INVALID_DATETIMESPANによって指定されます。

この関数のフォームの簡単な説明を次に示します。

**フォーマット(** *p フォーマット***)**<br/>
このフォームでは、パーセント記号 (%)の前に付いた特殊な書式指定コードを含む書式指定文字列を使用`printf`して、値の書式を設定します。 書式指定文字列は、関数にパラメーターとして渡されます。

**フォーマット(** *nID* **)**<br/>
このフォームでは、パーセント記号 (%)の前に付いた特殊な書式指定コードを含む書式指定文字列を使用`printf`して、値の書式を設定します。 書式指定文字列はリソースです。 この文字列リソースの ID は、パラメーターとして渡されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

## <a name="coledatetimespangetdays"></a><a name="getdays"></a>を見る

この日付/期間値の日の部分を取得します。

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>戻り値

この日付/期間値の日部分。

### <a name="remarks"></a>解説

この関数からの戻り値の範囲は約 - 3,615,000 から 3,615,000 です。

`COleDateTimeSpan`オブジェクトの値を照会するその他の関数については、次のメンバー関数を参照してください。

- [GetHours](#gethours)

- [ゲットミニッツ](#getminutes)

- [秒を取得します。](#getseconds)

- [合計日数を取得する](#gettotaldays)

- [合計時間を取得します。](#gettotalhours)

- [合計分を取得します。](#gettotalminutes)

- [合計秒数を取得します。](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

## <a name="coledatetimespangethours"></a><a name="gethours"></a>時間数を取得します。

この日付/期間値の時間部分を取得します。

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲の値の時間部分。

### <a name="remarks"></a>解説

この関数からの戻り値は、- 23 から 23 の範囲です。

`COleDateTimeSpan`オブジェクトの値を照会するその他の関数については、次のメンバー関数を参照してください。

- [ゲットデイズ](#getdays)

- [ゲットミニッツ](#getminutes)

- [秒を取得します。](#getseconds)

- [合計日数を取得する](#gettotaldays)

- [合計時間を取得します。](#gettotalhours)

- [合計分を取得します。](#gettotalminutes)

- [合計秒数を取得します。](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

## <a name="coledatetimespangetminutes"></a><a name="getminutes"></a>を切り取る

この日付/時間範囲の値の分の部分を取得します。

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲の値の分の部分。

### <a name="remarks"></a>解説

この関数の戻り値の範囲は 59 ~ 59 です。

`COleDateTimeSpan`オブジェクトの値を照会するその他の関数については、次のメンバー関数を参照してください。

- [ゲットデイズ](#getdays)

- [GetHours](#gethours)

- [秒を取得します。](#getseconds)

- [合計日数を取得する](#gettotaldays)

- [合計時間を取得します。](#gettotalhours)

- [合計分を取得します。](#gettotalminutes)

- [合計秒数を取得します。](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

## <a name="coledatetimespangetseconds"></a><a name="getseconds"></a>を切り取る

この日付/時間範囲の値の 2 番目の部分を取得します。

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲の値の秒部分。

### <a name="remarks"></a>解説

この関数の戻り値の範囲は 59 ~ 59 です。

`COleDateTimeSpan`オブジェクトの値を照会するその他の関数については、次のメンバー関数を参照してください。

- [ゲットデイズ](#getdays)

- [GetHours](#gethours)

- [ゲットミニッツ](#getminutes)

- [合計日数を取得する](#gettotaldays)

- [合計時間を取得します。](#gettotalhours)

- [合計分を取得します。](#gettotalminutes)

- [合計秒数を取得します。](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

## <a name="coledatetimespangetstatus"></a><a name="getstatus"></a>を使用します。

この`COleDateTimeSpan`オブジェクトの状態 (有効性) を取得します。

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTimeSpan`値の状態。

### <a name="remarks"></a>解説

戻り値は、クラス内`DateTimeSpanStatus`で定義される列挙型によって定義されます`COleDateTimeSpan`。

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
};
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleDateTimeSpan::valid`この`COleDateTimeSpan`オブジェクトが有効であることを示します。

- `COleDateTimeSpan::invalid`この`COleDateTimeSpan`オブジェクトが無効であることを示します。つまり、その値が正しくない可能性があります。

- `COleDateTimeSpan::null`この`COleDateTimeSpan`オブジェクトが null、つまり、このオブジェクトに値が指定されていない場合を示します。 (これは、C++ の NULL とは対照的に、"値を持たない" というデータベースの意味での "null" です。

オブジェクトの`COleDateTimeSpan`ステータスは、次の場合無効です。

- このオブジェクトが算術代入操作中にオーバーフローまたはアンダーフローを経験した場合、`+=`すなわち、 または`-=`.

- 無効な値がこのオブジェクトに割り当てられていた場合。

- このオブジェクトの状態が、 を使用して`SetStatus`明示的に無効に設定されている場合。

ステータスを無効に設定できる操作の詳細については[、「COleDateTimeSpan::演算子 +、および](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) [COleDateTimeSpan:演算子 +=、-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)」を参照してください。

`COleDateTimeSpan`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimespangettotaldays"></a><a name="gettotaldays"></a>を見る

日付/期間の値を取得します。

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>戻り値

この日付/期間の値は日単位で表されます。 この関数はプロトタイプで倍精度浮動小数点数を返しますが、常に整数値を返します。

### <a name="remarks"></a>解説

この関数からの戻り値の範囲は約 - 3.65e6 から 3.65e6 です。

`COleDateTimeSpan`オブジェクトの値を照会するその他の関数については、次のメンバー関数を参照してください。

- [ゲットデイズ](#getdays)

- [GetHours](#gethours)

- [ゲットミニッツ](#getminutes)

- [秒を取得します。](#getseconds)

- [合計時間を取得します。](#gettotalhours)

- [合計分を取得します。](#gettotalminutes)

- [合計秒数を取得します。](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

## <a name="coledatetimespangettotalhours"></a><a name="gettotalhours"></a>時間数を取得します。

この日付/時間範囲の値を時間単位で取得します。

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>戻り値

この日付/期間の値は、時間単位で表されます。 この関数はプロトタイプで倍精度浮動小数点数を返しますが、常に整数値を返します。

### <a name="remarks"></a>解説

この関数からの戻り値は、約 - 8.77e7 から 8.77e7 の範囲です。

`COleDateTimeSpan`オブジェクトの値を照会するその他の関数については、次のメンバー関数を参照してください。

- [ゲットデイズ](#getdays)

- [GetHours](#gethours)

- [ゲットミニッツ](#getminutes)

- [秒を取得します。](#getseconds)

- [合計日数を取得する](#gettotaldays)

- [合計分を取得します。](#gettotalminutes)

- [合計秒数を取得します。](#gettotalseconds)

### <a name="example"></a>例

[「合計日数の取得](#gettotaldays)」の例を参照してください。

## <a name="coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a>を使用します。

この日付/時間範囲の値を分単位で取得します。

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲の値は分単位で表されます。 この関数はプロトタイプで倍精度浮動小数点数を返しますが、常に整数値を返します。

### <a name="remarks"></a>解説

この関数からの戻り値の範囲は、約 - 5.26e9 から 5.26e9 です。

`COleDateTimeSpan`オブジェクトの値を照会するその他の関数については、次のメンバー関数を参照してください。

- [ゲットデイズ](#getdays)

- [GetHours](#gethours)

- [ゲットミニッツ](#getminutes)

- [秒を取得します。](#getseconds)

- [合計日数を取得する](#gettotaldays)

- [合計時間を取得します。](#gettotalhours)

- [合計秒数を取得します。](#gettotalseconds)

### <a name="example"></a>例

[「合計日数の取得](#gettotaldays)」の例を参照してください。

## <a name="coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a>を切り取る

この日付/時間範囲の値を秒単位で取得します。

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>戻り値

この日付/時間範囲の値は秒で表されます。 この関数はプロトタイプで倍精度浮動小数点数を返しますが、常に整数値を返します。

### <a name="remarks"></a>解説

この関数からの戻り値の範囲は約 - 3.16e11 から 3.16e11 です。

`COleDateTimeSpan`オブジェクトの値を照会するその他の関数については、次のメンバー関数を参照してください。

- [ゲットデイズ](#getdays)

- [GetHours](#gethours)

- [ゲットミニッツ](#getminutes)

- [秒を取得します。](#getseconds)

- [合計日数を取得する](#gettotaldays)

- [合計時間を取得します。](#gettotalhours)

- [合計分を取得します。](#gettotalminutes)

### <a name="example"></a>例

[「合計日数の取得](#gettotaldays)」の例を参照してください。

## <a name="coledatetimespanm_span"></a><a name="m_span"></a>を使用 m_spanします。

この`COleDateTime`オブジェクトの基になる**double**値。

```
double m_span;
```

### <a name="remarks"></a>解説

この値は、日付/期間を日数で表します。

> [!CAUTION]
> **double**データ メンバーの値を変更すると、この`COleDateTimeSpan`オブジェクトの値が変更されます。 この`COleDateTimeSpan`オブジェクトのステータスは変更されません。

## <a name="coledatetimespanm_status"></a><a name="m_status"></a>を使用 m_statusします。

このデータ メンバの型は、`DateTimeSpanStatus``COleDateTimeSpan`クラス内で定義されている列挙型です。

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

- `COleDateTimeSpan::valid`この`COleDateTimeSpan`オブジェクトが有効であることを示します。

- `COleDateTimeSpan::invalid`この`COleDateTimeSpan`オブジェクトが無効であることを示します。つまり、その値が正しくない可能性があります。

- `COleDateTimeSpan::null`この`COleDateTimeSpan`オブジェクトが null、つまり、このオブジェクトに値が指定されていない場合を示します。 (これは、C++ の NULL とは対照的に、"値を持たない" というデータベースの意味での "null" です。

オブジェクトの`COleDateTimeSpan`ステータスは、次の場合無効です。

- このオブジェクトが算術代入操作中にオーバーフローまたはアンダーフローを経験した場合、`+=`すなわち、 または`-=`.

- 無効な値がこのオブジェクトに割り当てられていた場合。

- このオブジェクトの状態が[SetStatus](#setstatus)を使用して明示的に無効に設定されている場合。

ステータスを無効に設定できる操作の詳細については[、「COleDateTimeSpan::演算子 +、および](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) [COleDateTimeSpan:演算子 +=、-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)」を参照してください。

> [!CAUTION]
> このデータ メンバーは、高度なプログラミングの状況に適しています。 インライン メンバー関数[GetStatus](#getstatus)と[SetStatus](#setstatus)を使用する必要があります。 この`SetStatus`データ メンバーの明示的な設定に関する詳細な注意については、「」を参照してください。

`COleDateTimeSpan`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimespanoperator-"></a><a name="operator_eq"></a>を指定します。

値を`COleDateTimeSpan`コピーします。

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>解説

このオーバーロードされた代入演算子は、ソースの日付/期間値をこの`COleDateTimeSpan`オブジェクトにコピーします。

## <a name="coledatetimespanoperator---"></a><a name="operator_add_-"></a>:演算子 +、 -

値の符号を加算、減算`COleDateTimeSpan`、および変更します。

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>解説

最初の 2 つの演算子では、日付/期間の値を加算および減算できます。 3 つ目は、日付/期間値の符号を変更できます。

オペランドのどちらかが null の場合、結果`COleDateTimeSpan`の値の状況は NULL になります。

どちらかのオペランドが無効で、もう一方が NULL でない場合、結果の`COleDateTimeSpan`値の状況は無効です。

有効、無効、および NULL の状態値の詳細については[、m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

## <a name="coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>:演算子 +=、-=

この`COleDateTimeSpan`値から値`COleDateTimeSpan`を加算および減算します。

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>解説

これらの演算子を使用すると、この`COleDateTimeSpan`オブジェクトの日付/期間値を加算および減算できます。 オペランドのどちらかが null の場合、結果`COleDateTimeSpan`の値の状況は NULL になります。

どちらかのオペランドが無効で、もう一方が NULL でない場合、結果の`COleDateTimeSpan`値の状況は無効です。

有効、無効、および NULL の状態値の詳細については[、m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

## <a name="coledatetimespanoperator-double"></a><a name="operator_double"></a>2 倍の演算子

この`COleDateTimeSpan`値を**倍精度浮動小数点数**に変換します。

```
operator double() const throw();
```

### <a name="remarks"></a>解説

この演算子は、この`COleDateTimeSpan`値の値を浮動小数点数の日数として返します。

## <a name="coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a>を切り取る

この日付/時間範囲の値を設定します。

```cpp
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>パラメーター

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
この`COleDateTimeSpan`オブジェクトにコピーする日付範囲と期間の値を示します。

### <a name="remarks"></a>解説

`COleDateTimeSpan`オブジェクトの値を照会する関数については、次のメンバー関数を参照してください。

- [ゲットデイズ](#getdays)

- [GetHours](#gethours)

- [ゲットミニッツ](#getminutes)

- [秒を取得します。](#getseconds)

- [合計日数を取得する](#gettotaldays)

- [合計時間を取得します。](#gettotalhours)

- [合計分を取得します。](#gettotalminutes)

- [合計秒数を取得します。](#gettotalseconds)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]

## <a name="coledatetimespansetstatus"></a><a name="setstatus"></a>を設定します。

この`COleDateTimeSpan`オブジェクトのステータス (有効性) を設定します。

```cpp
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>パラメーター

*status*<br/>
この`COleDateTimeSpan`オブジェクトの新しいステータス値。

### <a name="remarks"></a>解説

*Status*パラメーターの値は、クラス`DateTimeSpanStatus`内で定義される列挙型によって定義されます`COleDateTimeSpan`。

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleDateTimeSpan::valid`この`COleDateTimeSpan`オブジェクトが有効であることを示します。

- `COleDateTimeSpan::invalid`この`COleDateTimeSpan`オブジェクトが無効であることを示します。つまり、その値が正しくない可能性があります。

- `COleDateTimeSpan::null`この`COleDateTimeSpan`オブジェクトが null、つまり、このオブジェクトに値が指定されていない場合を示します。 (これは、C++ の NULL とは対照的に、"値を持たない" というデータベースの意味での "null" です。

   > [!CAUTION]
   > この関数は、高度なプログラミングの状況に対応します。 この関数は、このオブジェクトのデータを変更しません。 ほとんどの場合、この状態を**null**または**無効**に設定するために使用されます。 代入演算子 ([演算子 =](#operator_eq)) と[SetDateTimeSpan](#setdatetimespan)は、ソース値に基づいてオブジェクトのステータスを設定します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../atl-mfc-shared/reference/coledatetime-class.md)<br/>
[CTimeクラス](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[クラス](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
