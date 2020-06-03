---
title: クラスを制御します。
ms.date: 11/04/2016
f1_keywords:
- CComCurrency
- ATLCUR/ATL::CComCurrency
- ATLCUR/ATL::CComCurrency::CComCurrency
- ATLCUR/ATL::CComCurrency::GetCurrencyPtr
- ATLCUR/ATL::CComCurrency::GetFraction
- ATLCUR/ATL::CComCurrency::GetInteger
- ATLCUR/ATL::CComCurrency::Round
- ATLCUR/ATL::CComCurrency::SetFraction
- ATLCUR/ATL::CComCurrency::SetInteger
- ATLCUR/ATL::CComCurrency::m_currency
helpviewer_keywords:
- CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
ms.openlocfilehash: 541944e03e9caf6cba15612cf9e7cbbd239555ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327945"
---
# <a name="ccomcurrency-class"></a>クラスを制御します。

`CComCurrency` には、CURRENCY オブジェクトを作成および管理するためのメソッドと演算子があります。

## <a name="syntax"></a>構文

```
class CComCurrency
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComCurrency::CComCurrency](#ccomcurrency)|`CComCurrency` オブジェクトのコンストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|`m_currency` データ メンバーのアドレスを返します。|
|[CComCurrency::GetFraction](#getfraction)|`CComCurrency` オブジェクトの小数部を返すには、このメソッドを呼び出します。|
|[CComCurrency::GetInteger](#getinteger)|`CComCurrency` オブジェクトの整数部を返すには、このメソッドを呼び出します。|
|[CComCurrency::Round](#round)|`CComCurrency` オブジェクトを最も近い整数値に四捨五入するには、このメソッドを呼び出します。|
|[CComCurrency::SetFraction](#setfraction)|`CComCurrency` オブジェクトの小数部を設定するには、このメソッドを呼び出します。|
|[CComCurrency::SetInteger](#setinteger)|`CComCurrency` オブジェクトの整数部を設定するには、このメソッドを呼び出します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[コミュカレンシー::演算子 -](#operator_-)|この演算子は、`CComCurrency` オブジェクトで減算を実行するために使用します。|
|[通貨:演算子 !=](#operator_neq)|2 つの `CComCurrency` オブジェクトが等しくないかどうかを比較します。|
|[通貨::演算子 *](#operator_star)|この演算子は、`CComCurrency` オブジェクトで乗算を実行するために使用します。|
|[通貨:演算子 *=](#operator_star_eq)|この演算子は、`CComCurrency` オブジェクトで乗算を実行し、オブジェクトに結果を代入するために使用します。|
|[通貨::演算子 /](#operator_div)|この演算子は、`CComCurrency` オブジェクトで除算を実行するために使用します。|
|[CComCurrency::operator /=](#operator_div_eq)|この演算子は、`CComCurrency` オブジェクトで除算を実行し、オブジェクトに結果を代入するために使用します。|
|[通貨::演算子 +](#operator_add)|この演算子は、`CComCurrency` オブジェクトで加算を実行するために使用します。|
|[通貨:演算子 +=](#operator_add_eq)|この演算子は、`CComCurrency` オブジェクトで加算を実行し、結果を現在のオブジェクトに代入するために使用します。|
|[コミュカレンシー::演算子<](#operator_lt)|この演算子は、2 つの `CComCurrency` オブジェクトを比較して、小さい方を決定します。|
|[<演算子 =](#operator_lt_eq)|この演算子では、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または小さい方を決定します。|
|[通貨::演算子 =](#operator_eq)|この演算子は、`CComCurrency` オブジェクトに新しい値を割り当てます。|
|[通貨:演算子 -=](#operator_-_eq)|この演算子は、`CComCurrency` オブジェクトで減算を実行し、オブジェクトに結果を代入するために使用します。|
|[通貨:演算子 ==](#operator_eq_eq)|この演算子は、2 つの `CComCurrency` オブジェクトが等しいかどうかを比較します。|
|[コミュカレンシー::演算子>](#operator_gt)|この演算子は、2 つの `CComCurrency` オブジェクトを比較して、大きい方を決定します。|
|[>演算子 =](#operator_gt_eq)|この演算子は、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または大きい方を決定します。|
|[通貨::オペレーター通貨](#operator_currency)|CURRENCY オブジェクトをキャストします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComCurrency::m_currency](#m_currency)|クラスインスタンスによって作成された通貨変数。|

## <a name="remarks"></a>解説

`CComCurrency` は、CURRENCY データ型のラッパーです。 CURRENCY は、10,000 倍した値を 8 バイトの 2 の補数で表現した整数値として実装されます。 これは、15 桁の整数部と 4 桁の小数部を持つ固定小数点数として表現されます。 CURRENCY データ型は、通貨に関連する計算、または精度が重要となる固定小数点数の計算に非常に役立ちます。

ラッパー`CComCurrency`は、この固定小数点型の算術演算、代入演算、および比較演算を実装します。 固定小数点数の計算中に発生する可能性のある丸め誤差を制御するために、サポートするアプリケーションが選択されています。

`CComCurrency` オブジェクトは、小数点の左側に値を格納する整数部と小数点の右側に値を格納する小数部という 2 つの構成要素を使用した形で、小数点の左側と右側の数値にアクセスできます。 小数部は、-9999 (CY_MIN_FRACTION) から +9999 (CY_MAX_FRACTION) までの整数値として内部に格納されます。 メソッド[CComCurrency::GetFraction](#getfraction)は、10000 (CY_SCALE倍の値をスケールして返します。

オブジェクトの整数部と小数部の要素を`CComCurrency`指定する場合、小数部の要素は 0 から 9999 の範囲の数値であることを覚えておいてください。 これは、小数点の後の有効桁数に 2 桁のみを使用して金額を表す米ドルなどの通貨を扱う場合に重要です。 最後の 2 桁が表示されていない場合でも考慮する必要があります。

|[値]|考えられる CComCurrency の割り当て|
|-----------|---------------------------------------|
|$10.50|コムカレンシー(10,5000)*または*コム通貨(10.50)|
|$10.05|コミュカレンシー(10,500)*または*コム通貨(10.05)|

値  CY_MIN_FRACTION、CY_MAX_FRACTION、および  CY_SCALE は、atlcur.h で定義されています。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcur.h

## <a name="ccomcurrencyccomcurrency"></a><a name="ccomcurrency"></a>コミュカレンシー::コム通貨

コンストラクターです。

```
CComCurrency() throw();
CComCurrency(const CComCurrency& curSrc) throw();
CComCurrency(CURRENCY cySrc) throw();
CComCurrency(DECIMAL dSrc);
CComCurrency(ULONG ulSrc);
CComCurrency(USHORT usSrc);
CComCurrency(CHAR cSrc);
CComCurrency(DOUBLE dSrc);
CComCurrency(FLOAT fSrc);
CComCurrency(LONG lSrc);
CComCurrency(SHORT sSrc);
CComCurrency(BYTE bSrc);
CComCurrency(LONGLONG nInteger, SHORT nFraction);
explicit CComCurrency(LPDISPATCH pDispSrc);
explicit CComCurrency(const VARIANT& varSrc);
explicit CComCurrency(LPCWSTR szSrc);
explicit CComCurrency(LPCSTR szSrc);
```

### <a name="parameters"></a>パラメーター

*カースrc*<br/>
既存の `CComCurrency` オブジェクトです。

*サイスルク*<br/>
CURRENCY 型の変数。

*bSrc*, *dSrc*, *fSrc*, *lSrc*, *sSrc*, *ulSrc, usSrc*<br/>
メンバ変数`m_currency`に与えられた初期値。

*Csrc*<br/>
メンバ変数`m_currency`に与えられた初期値を含む文字。

*整数* *、nFraction*<br/>
初期通貨値の整数部と小数部の要素。 詳細については[、CComCurrency](../../atl/reference/ccomcurrency-class.md)の概要を参照してください。

*pDispSrc*<br/>
ポインター `IDispatch` 。

*varSrc*<br/>
バリアント型の変数。 現在のスレッドのロケールは、変換を実行するために使用されます。

*szSrc*<br/>
初期値を含む Unicode または ANSI 文字列。 現在のスレッドのロケールは、変換を実行するために使用されます。

### <a name="remarks"></a>解説

このコンストラクターは[、CComCurrency::m_currency](#m_currency)の初期値を設定し、整数、文字列、浮動小数点数、CURRENCY 変数、およびその他`CComCurrency`のオブジェクトを含む幅広いデータ型を受け入れます。 値が指定されていない場合は`m_currency`、0 に設定されます。

オーバーフローなどのエラーが発生した場合、エラーを記述する HRESULT を使用して、空の例外指定`AtlThrow`(**throw()**) 呼び出しを行うコンストラクター。

浮動小数点値または倍精度浮動小数点値を使用して値を代入する場合`CComCurrency(10.50)`は、と`CComCurrency(10,5000)`同等であり`CComCurrency(10,50)`、値は割り当てずに注意してください。

## <a name="ccomcurrencygetcurrencyptr"></a><a name="getcurrencyptr"></a>コミュランシ::ゲット通貨プター

`m_currency` データ メンバーのアドレスを返します。

```
CURRENCY* GetCurrencyPtr() throw();
```

### <a name="return-value"></a>戻り値

データ メンバのアドレス`m_currency`を返します。

## <a name="ccomcurrencygetfraction"></a><a name="getfraction"></a>コミュカレンシー::ゲットフラクション

`CComCurrency`オブジェクトの小数部の要素を返します。

```
SHORT GetFraction() const;
```

### <a name="return-value"></a>戻り値

データ メンバーの小数部`m_currency`の要素を返します。

### <a name="remarks"></a>解説

小数部は、-9999 (CY_MIN_FRACTION) から +9999 (CY_MAX_FRACTION) の間の 4 桁の整数値です。 `GetFraction`は、この値を 10000 (CY_SCALE) でスケールして返します。 CY_MIN_FRACTION、CY_MAX_FRACTION、およびCY_SCALEの値は、atlcur.h で定義されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]

## <a name="ccomcurrencygetinteger"></a><a name="getinteger"></a>通貨を設定します。

`CComCurrency`オブジェクトの整数コンポーネントを取得します。

```
LONGLONG GetInteger() const;
```

### <a name="return-value"></a>戻り値

データ メンバーの整数コンポーネント`m_currency`を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]

## <a name="ccomcurrencym_currency"></a><a name="m_currency"></a>コム通貨::m_currency

通貨データ メンバー。

```
CURRENCY m_currency;
```

### <a name="remarks"></a>解説

このメンバーは、このクラスのメソッドによってアクセスおよび操作される通貨を保持します。

## <a name="ccomcurrencyoperator--"></a><a name="operator_-"></a>コミュカレンシー::演算子 -

この演算子は、`CComCurrency` オブジェクトで減算を実行するために使用します。

```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
`CComCurrency` オブジェクト。

### <a name="return-value"></a>戻り値

減算`CComCurrency`の結果を表すオブジェクトを返します。 オーバーフローなどのエラーが発生した場合、この演算子はエラーを説明する`AtlThrow`HRESULT を使用して呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_neq"></a>通貨:演算子 !=

この演算子は、2 つのオブジェクトが不等比較を行います。

```
bool operator!= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
比較される `CComCurrency` オブジェクト。

### <a name="return-value"></a>戻り値

比較対象の項目がオブジェクトと等しくない場合は`CComCurrency`TRUE を返します。それ以外の場合は FALSE。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star"></a>通貨::演算子 *

この演算子は、`CComCurrency` オブジェクトで乗算を実行するために使用します。

```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```

### <a name="parameters"></a>パラメーター

*nオペランド*<br/>
乗数。

*電流*<br/>
乗`CComCurrency`数として使用されるオブジェクト。

### <a name="return-value"></a>戻り値

乗算の`CComCurrency`結果を表すオブジェクトを返します。 オーバーフローなどのエラーが発生した場合、この演算子はエラーを説明する`AtlThrow`HRESULT を使用して呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star_eq"></a>コミュカレンシー::演算子\*=

この演算子は、`CComCurrency` オブジェクトで乗算を実行し、オブジェクトに結果を代入するために使用します。

```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```

### <a name="parameters"></a>パラメーター

*nオペランド*<br/>
乗数。

*電流*<br/>
乗`CComCurrency`数として使用されるオブジェクト。

### <a name="return-value"></a>戻り値

更新された`CComCurrency`オブジェクトを返します。 オーバーフローなどのエラーが発生した場合、この演算子はエラーを説明する`AtlThrow`HRESULT を使用して呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div"></a>通貨::演算子 /

この演算子は、`CComCurrency` オブジェクトで除算を実行するために使用します。

```
CComCurrency operator/(long nOperand) const;
```

### <a name="parameters"></a>パラメーター

*nオペランド*<br/>
除数。

### <a name="return-value"></a>戻り値

除算`CComCurrency`の結果を表すオブジェクトを返します。 除数が 0 の場合、アサートエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div_eq"></a>通貨:演算子 /=

この演算子は、`CComCurrency` オブジェクトで除算を実行し、オブジェクトに結果を代入するために使用します。

```
const CComCurrency& operator/= (long nOperand);
```

### <a name="parameters"></a>パラメーター

*nオペランド*<br/>
除数。

### <a name="return-value"></a>戻り値

更新された`CComCurrency`オブジェクトを返します。 除数が 0 の場合、アサートエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add"></a>通貨::演算子 +

この演算子は、`CComCurrency` オブジェクトで加算を実行するために使用します。

```
CComCurrency operator+(const CComCurrency& cur) const;
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
元`CComCurrency`のオブジェクトに追加するオブジェクト。

### <a name="return-value"></a>戻り値

加算の`CComCurrency`結果を表すオブジェクトを返します。 オーバーフローなどのエラーが発生した場合、この演算子はエラーを説明する`AtlThrow`HRESULT を使用して呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add_eq"></a>通貨:演算子 +=

この演算子は、`CComCurrency` オブジェクトで加算を実行し、結果を現在のオブジェクトに代入するために使用します。

```
const CComCurrency& operator+= (const CComCurrency& cur);
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
`CComCurrency` オブジェクトです。

### <a name="return-value"></a>戻り値

更新された`CComCurrency`オブジェクトを返します。 オーバーフローなどのエラーが発生した場合、この演算子はエラーを説明する`AtlThrow`HRESULT を使用して呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt"></a>コミュカレンシー::演算子&lt;

この演算子は、2 つの `CComCurrency` オブジェクトを比較して、小さい方を決定します。

```
bool operator<(const CComCurrency& cur) const;
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
`CComCurrency` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが 2 番目のオブジェクトより小さい場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt_eq"></a>コミュカレンシー::演算子&lt;=

この演算子では、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または小さい方を決定します。

```
bool operator<= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
`CComCurrency` オブジェクト。

### <a name="return-value"></a>戻り値

1 つ目のオブジェクトが 2 番目のオブジェクト以下の場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq"></a>通貨::演算子 =

この演算子は、`CComCurrency` オブジェクトに新しい値を割り当てます。

```
const CComCurrency& operator= (const CComCurrency& curSrc) throw();
const CComCurrency& operator= (CURRENCY cySrc) throw();
const CComCurrency& operator= (FLOAT fSrc);
const CComCurrency& operator= (SHORT sSrc);
const CComCurrency& operator= (LONG lSrc);
const CComCurrency& operator= (BYTE bSrc);
const CComCurrency& operator= (USHORT usSrc);
const CComCurrency& operator= (DOUBLE dSrc);
const CComCurrency& operator= (CHAR cSrc);
const CComCurrency& operator= (ULONG ulSrc);
const CComCurrency& operator= (DECIMAL dSrc);
```

### <a name="parameters"></a>パラメーター

*カースrc*<br/>
`CComCurrency` オブジェクト。

*サイスルク*<br/>
CURRENCY 型の変数。

*sSrc*, *fSrc*, *lSrc*, *bSrc*, *usSrc*, *dSrc*, *cSrc*, *ulSrc*, *dSrc*<br/>
`CComCurrency`オブジェクトに割り当てる数値。

### <a name="return-value"></a>戻り値

更新された`CComCurrency`オブジェクトを返します。 オーバーフローなどのエラーが発生した場合、この演算子はエラーを説明する`AtlThrow`HRESULT を使用して呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]

## <a name="ccomcurrencyoperator--"></a><a name="operator_-_eq"></a>通貨:演算子 -=

この演算子は、`CComCurrency` オブジェクトで減算を実行し、オブジェクトに結果を代入するために使用します。

```
const CComCurrency& operator-= (const CComCurrency& cur);
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
`CComCurrency` オブジェクト。

### <a name="return-value"></a>戻り値

更新された`CComCurrency`オブジェクトを返します。 オーバーフローなどのエラーが発生した場合、この演算子はエラーを説明する`AtlThrow`HRESULT を使用して呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq_eq"></a>通貨:演算子 ==

この演算子は、2 つの `CComCurrency` オブジェクトが等しいかどうかを比較します。

```
bool operator== (const CComCurrency& cur) const;
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
比較対象の `CComCurrency` オブジェクト。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合 (つまり、両方の`m_currency`オブジェクトの整数と小数の両方のデータ メンバーが同じ値を持つ場合)、FALSE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt"></a>コミュカレンシー::演算子&gt;

この演算子は、2 つの `CComCurrency` オブジェクトを比較して、大きい方を決定します。

```
bool operator>(const CComCurrency& cur) const;
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
`CComCurrency` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが 2 番目のオブジェクトより大きい場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt_eq"></a>コミュカレンシー::演算子&gt;=

この演算子は、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または大きい方を決定します。

```
bool operator>= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>パラメーター

*電流*<br/>
`CComCurrency` オブジェクト。

### <a name="return-value"></a>戻り値

1 つ目のオブジェクトが 2 番目のオブジェクト以上の場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]

## <a name="ccomcurrencyoperator-currency"></a><a name="operator_currency"></a>通貨::オペレーター通貨

これらの演算子は、オブジェクトを`CComCurrency`CURRENCY データ型にキャストするために使用されます。

```
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```

### <a name="return-value"></a>戻り値

CURRENCY オブジェクトへの参照を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]

## <a name="ccomcurrencyround"></a><a name="round"></a>コム通貨::ラウンド

通貨を指定した小数点以下の桁数に丸める場合に呼び出します。

```
HRESULT Roundint nDecimals);
```

### <a name="parameters"></a>パラメーター

*n小数点以下*<br/>
0 から 4`m_currency`の範囲で丸められる桁数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]

## <a name="ccomcurrencysetfraction"></a><a name="setfraction"></a>コミュカレンシー::セッターフラクション

`CComCurrency` オブジェクトの小数部を設定するには、このメソッドを呼び出します。

```
HRESULT SetFraction(SHORT nFraction);
```

### <a name="parameters"></a>パラメーター

*nフラクション*<br/>
`m_currency`データ メンバーの小数部コンポーネントに割り当てられる値。 小数部の要素の符号は整数コンポーネントと同じでなければならず、値は -9999 (CY_MIN_FRACTION) から +9999 (CY_MAX_FRACTION) の範囲内になければなりません。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]

## <a name="ccomcurrencysetinteger"></a><a name="setinteger"></a>通貨::整数

`CComCurrency` オブジェクトの整数部を設定するには、このメソッドを呼び出します。

```
HRESULT SetInteger(LONGLONG nInteger);
```

### <a name="parameters"></a>パラメーター

*整数*<br/>
`m_currency`データ メンバーの整数コンポーネントに割り当てられる値。 整数コンポーネントの符号は、既存の小数部の符号と一致する必要があります。

*nInteger*は、CY_MAX_INTEGER包括的な範囲CY_MIN_INTEGERにする必要があります。 これらの値は、atlcur.h で定義されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]

## <a name="see-also"></a>関連項目

[クラスを変更します。](../../mfc/reference/colecurrency-class.md)<br/>
[通貨](/windows/win32/api/wtypes/ns-wtypes-cy~r1)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
