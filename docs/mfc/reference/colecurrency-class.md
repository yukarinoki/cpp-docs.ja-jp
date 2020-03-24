---
title: COleCurrency クラス
ms.date: 08/29/2019
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
helpviewer_keywords:
- COleCurrency [MFC], COleCurrency
- COleCurrency [MFC], Format
- COleCurrency [MFC], GetStatus
- COleCurrency [MFC], ParseCurrency
- COleCurrency [MFC], SetCurrency
- COleCurrency [MFC], SetStatus
- COleCurrency [MFC], m_cur
- COleCurrency [MFC], m_status
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
ms.openlocfilehash: 1e32d75599f51ba277180341df60762a02a82fe5
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150929"
---
# <a name="colecurrency-class"></a>COleCurrency クラス

OLE オートメーションで使用される `CURRENCY` データ型をカプセル化します。

## <a name="syntax"></a>構文

```
class COleCurrency
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[COleCurrency:: COleCurrency](#colecurrency)|`COleCurrency` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[COleCurrency:: Format](#format)|`COleCurrency` オブジェクトの書式設定された文字列形式を生成します。|
|[COleCurrency:: GetStatus](#getstatus)|この `COleCurrency` オブジェクトの状態 (有効) を取得します。|
|[COleCurrency::P Arセキュリティー](#parsecurrency)|文字列から通貨値を読み取り、`COleCurrency`の値を設定します。|
|[COleCurrency:: SetCurrency](#setcurrency)|この `COleCurrency` オブジェクトの値を設定します。|
|[COleCurrency:: SetStatus](#setstatus)|この `COleCurrency` オブジェクトの状態 (有効性) を設定します。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[operator =](#operator_eq)|`COleCurrency` 値をコピーします。|
|[演算子 +、-](#operator_plus_minus)|`COleCurrency` 値の符号を加算、減算、および変更します。|
|[operator + =、-=](#operator_plus_minus_eq)|この `COleCurrency` オブジェクトの `COleCurrency` 値を加算および減算します。|
|[演算子 */](#operator_star)|`COleCurrency` 値を整数値でスケーリングします。|
|[operator * =、/=](#operator_star_div_eq)|この `COleCurrency` 値を整数値でスケーリングします。|
|[演算子 < <](#operator_stream)|`CArchive` または `CDumpContext`に `COleCurrency` 値を出力します。|
|[演算子 > >](#operator_stream)|`CArchive`から `COleCurrency` オブジェクトを入力します。|
|[演算子の通貨](#operator_currency)|`COleCurrency` 値を通貨に変換します。|
|[operator = =、<、< = など](#colecurrency_relational_operators)|2つの `COleCurrency` 値を比較します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|説明|
|----------|-----------------|
|[COleCurrency:: m_cur](#m_cur)|この `COleCurrency` オブジェクトの基になる通貨を格納します。|
|[COleCurrency:: m_status](#m_status)|この `COleCurrency` オブジェクトの状態を格納します。|

## <a name="remarks"></a>コメント

`COleCurrency` には基底クラスがありません。

通貨は、1万によってスケーリングされた8バイトの2の補数整数値として実装されます。 これは、15 桁の整数部と 4 桁の小数部を持つ固定小数点数として表現されます。 通貨データ型は、金額を含む計算や、精度が重要な固定小数点計算に非常に便利です。 これは、OLE オートメーションの `VARIANT` データ型に使用できる型の1つです。

`COleCurrency` は、この固定小数点型に対するいくつかの基本的な算術演算も実装します。 サポートされている操作は、固定小数点数の計算中に発生する丸め誤差を制御するために選択されています。

## <a name="inheritance-hierarchy"></a>継承階層

`COleCurrency`

## <a name="requirements"></a>要件

**ヘッダー :** afxdisp.h

##  <a name="colecurrencycolecurrency"></a><a name="colecurrency"></a>COleCurrency:: COleCurrency

`COleCurrency` オブジェクトを構築します。

```
COleCurrency();
COleCurrency(CURRENCY cySrc);
COleCurrency(const COleCurrency& curSrc);
COleCurrency(const VARIANT& varSrc);

COleCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>パラメーター

*cySrc*<br/>
新しい `COleCurrency` オブジェクトにコピーされる通貨値。

*curSrc*<br/>
新しい `COleCurrency` オブジェクトにコピーされる既存の `COleCurrency` オブジェクト。

*varSrc*<br/>
通貨値 (VT_CY) に変換して新しい `COleCurrency` オブジェクトにコピーする、既存の `VARIANT` データ構造体 (場合によっては `COleVariant` オブジェクト)。

*nunits*、 *nFractionalUnits*は、新しい `COleCurrency` オブジェクトにコピーする値の単位と小数部 (1/10000) を示します。

### <a name="remarks"></a>コメント

これらのすべてのコンストラクターは、指定された値に初期化された新しい `COleCurrency` オブジェクトを作成します。 これらの各コンストラクターの簡単な説明を次に示します。 特に明記されていない限り、新しい `COleCurrency` 項目の状態は [有効] に設定されます。

- COleCurrency () は、0 (ゼロ) に初期化された `COleCurrency` オブジェクトを構築します。

- COleCurrency (`cySrc`) は、[通貨](/windows/win32/api/wtypes/ns-wtypes-cy~r1)値から `COleCurrency` オブジェクトを構築します。

- COleCurrency (`curSrc`) 既存の `COleCurrency` オブジェクトから `COleCurrency` オブジェクトを構築します。 新しいオブジェクトは、ソースオブジェクトと同じ状態になります。

- COleCurrency (`varSrc`) `COleCurrency` オブジェクトを構築します。 [バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)構造体または `COleVariant` オブジェクトから通貨 (VT_CY) 値への変換を試みます。 この変換が成功した場合は、変換後の値が新しい `COleCurrency` オブジェクトにコピーされます。 そうでない場合は、`COleCurrency` オブジェクトの値がゼロ (0) に設定され、その状態が無効になります。

- COleCurrency (`nUnits`、`nFractionalUnits`) は、指定された数値コンポーネントから `COleCurrency` オブジェクトを構築します。 小数部分の絶対値が1万を超える場合は、その単位に適切な調整が行われます。 単位と小数部は、符号付き長の値によって指定されることに注意してください。

詳細については、Windows SDK の「 [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1) 」と「 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 」のエントリを参照してください。

### <a name="example"></a>例

次の例は、ゼロパラメーターと2つのパラメーターのコンストラクターの効果を示しています。

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

##  <a name="colecurrencyformat"></a><a name="format"></a>COleCurrency:: Format

通貨値の書式設定された表現を作成するには、このメンバー関数を呼び出します。

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
ロケール設定のフラグを示します。 通貨に関連するのは、次のフラグのみです。

- LOCALE_NOUSEROVERRIDE は、カスタムユーザー設定ではなく、システムの既定のロケール設定を使用します。

*lcid*<br/>
変換に使用するロケール ID を示します。

### <a name="return-value"></a>戻り値

書式設定された通貨値を格納している `CString`。

### <a name="remarks"></a>コメント

この値は、ローカル言語仕様 (ロケール Id) を使用して書式設定されます。 返される値に通貨記号は含まれません。 この `COleCurrency` オブジェクトの状態が null の場合、戻り値は空の文字列になります。 状態が無効である場合は、文字列リソース IDS_INVALID_CURRENCY によって返される文字列が指定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

##  <a name="colecurrencygetstatus"></a><a name="getstatus"></a>COleCurrency:: GetStatus

指定された `COleCurrency` オブジェクトの状態 (有効性) を取得するには、このメンバー関数を呼び出します。

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>戻り値

この `COleCurrency` 値の状態を返します。

### <a name="remarks"></a>コメント

戻り値は、`COleCurrency` クラス内で定義されている `CurrencyStatus` 列挙型によって定義されます。

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

  - `COleCurrency::valid` は、この `COleCurrency` オブジェクトが有効であることを示します。

  - `COleCurrency::invalid` は、この `COleCurrency` オブジェクトが無効であることを示します。つまり、値が正しくない可能性があります。

  - `COleCurrency::null` は、この `COleCurrency` オブジェクトが null であること、つまり、このオブジェクトに値が指定されていないことを示します。 ( C++ Null ではなく、"値がない" というデータベースの意味では "null" になります)。

`COleCurrency` オブジェクトの状態は、次の場合には無効です。

- 値がバリアントまたは `COleVariant` 値から設定されている場合は、通貨値に変換できません。

- 算術代入演算中にこのオブジェクトでオーバーフローまたはアンダーフローが発生した場合は、`+=` や **\*=** です。

- 無効な値がこのオブジェクトに割り当てられた場合は。

- このオブジェクトの状態が[SetStatus](#setstatus)を使用して明示的に無効に設定された場合は。

状態が無効に設定されている可能性のある操作の詳細については、次のメンバー関数を参照してください。

- [COleCurrency](#colecurrency)

- [operator =](#operator_eq)

- [演算子 +-](#operator_plus_minus)

- [operator + = および-=](#operator_plus_minus_eq)

- [演算子 */](#operator_star)

- [演算子 * = および/=](#operator_star_div_eq)

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

##  <a name="colecurrencym_cur"></a><a name="m_cur"></a>COleCurrency:: m_cur

この `COleCurrency` オブジェクトの基になる[通貨](/windows/win32/api/wtypes/ns-wtypes-cy~r1)構造。

### <a name="remarks"></a>コメント

> [!CAUTION]
>  この関数によって返されるポインターによってアクセスされる `CURRENCY` 構造の値を変更すると、この `COleCurrency` オブジェクトの値が変更されます。 この `COleCurrency` オブジェクトの状態は変更されません。

詳細については、Windows SDK の「 [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1) 」エントリを参照してください。

##  <a name="colecurrencym_status"></a><a name="m_status"></a>COleCurrency:: m_status

このデータメンバーの型は `CurrencyStatus`列挙型であり、`COleCurrency` クラス内で定義されます。

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>コメント

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleCurrency::valid` は、この `COleCurrency` オブジェクトが有効であることを示します。

- `COleCurrency::invalid` は、この `COleCurrency` オブジェクトが無効であることを示します。つまり、値が正しくない可能性があります。

- `COleCurrency::null` は、この `COleCurrency` オブジェクトが null であること、つまり、このオブジェクトに値が指定されていないことを示します。 ( C++ Null ではなく、"値がない" というデータベースの意味では "null" になります)。

`COleCurrency` オブジェクトの状態は、次の場合には無効です。

- 値がバリアントまたは `COleVariant` 値から設定されている場合は、通貨値に変換できません。

- 算術代入演算中にこのオブジェクトでオーバーフローまたはアンダーフローが発生した場合は、`+=` や **\*=** です。

- 無効な値がこのオブジェクトに割り当てられた場合は。

- このオブジェクトの状態が[SetStatus](#setstatus)を使用して明示的に無効に設定された場合は。

状態が無効に設定されている可能性のある操作の詳細については、次のメンバー関数を参照してください。

- [COleCurrency](#colecurrency)

- [operator =](#operator_eq)

- [演算子 +、-](#operator_plus_minus)

- [operator + =、-=](#operator_plus_minus_eq)

- [演算子 */](#operator_star)

- [operator * =、/=](#operator_star_div_eq)

> [!CAUTION]
>  このデータメンバーは、高度なプログラミングの状況を対象としています。 インラインメンバー関数[GetStatus](#getstatus)および[SetStatus](#setstatus)を使用する必要があります。 このデータメンバーを明示的に設定する方法については、「`SetStatus`」を参照してください。

##  <a name="colecurrencyoperator-"></a><a name="operator_eq"></a>COleCurrency:: operator =

これらのオーバーロードされた代入演算子は、source currency 値をこの `COleCurrency` オブジェクトにコピーします。

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>コメント

各演算子の簡単な説明を次に示します。

- **operator = (** `cySrc` **)** `CURRENCY` 値が `COleCurrency` オブジェクトにコピーされ、その状態が有効に設定されます。

- **operator = (** `curSrc` **)** オペランドの値と状態。既存の `COleCurrency` オブジェクトは、この `COleCurrency` オブジェクトにコピーされます。

- **operator = (** *varsrc* **)** `VARIANT` 値 (または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト) から通貨 (`VT_CY`) への変換が成功すると、変換後の値がこの `COleCurrency` オブジェクトにコピーされ、その状態が有効に設定されます。 変換に失敗した場合、`COleCurrency` オブジェクトの値は0に設定され、その状態は無効になります。

詳細については、Windows SDK の「 [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1) 」と「 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 」のエントリを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

##  <a name="colecurrencyoperator---"></a><a name="operator_plus_minus"></a>COleCurrency:: operator +、-

これらの演算子を使用すると、2つの `COleCurrency` 値の相互間の加算と減算を行ったり、`COleCurrency` 値の符号を変更したりすることができます。

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>コメント

オペランドのいずれかが null の場合、結果の `COleCurrency` 値の状態は null になります。

算術演算がオーバーフローした場合、結果として得られる `COleCurrency` 値は無効になります。

オペランドが無効で、もう一方が null でない場合、結果の `COleCurrency` 値の状態は無効になります。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

##  <a name="colecurrencyoperator---"></a><a name="operator_plus_minus_eq"></a>COleCurrency:: operator + =、-=

この `COleCurrency` オブジェクトとの間で `COleCurrency` 値の加算と減算を行うことができます。

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>コメント

オペランドのいずれかが null の場合、この `COleCurrency` オブジェクトの状態は null に設定されます。

算術演算がオーバーフローした場合、この `COleCurrency` オブジェクトの状態は無効に設定されます。

オペランドのいずれかが無効で、もう一方が null でない場合、この `COleCurrency` オブジェクトの状態は無効に設定されます。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

##  <a name="colecurrencyoperator--and-"></a><a name="operator_star"></a>COleCurrency:: operator \* および/

`COleCurrency` 値を整数値でスケーリングできます。

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>コメント

`COleCurrency` オペランドが null の場合、結果の `COleCurrency` 値の状態は null になります。

算術演算がオーバーフローまたはアンダーフローする場合、結果の `COleCurrency` 値の状態は無効になります。

`COleCurrency` オペランドが無効な場合、結果の `COleCurrency` 値の状態は無効になります。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

##  <a name="colecurrencyoperator--"></a><a name="operator_star_div_eq"></a>COleCurrency:: operator \*=、/=

この `COleCurrency` 値を整数値でスケーリングできます。

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>コメント

`COleCurrency` オペランドが null の場合、この `COleCurrency` オブジェクトの状態は null に設定されます。

算術演算がオーバーフローした場合、この `COleCurrency` オブジェクトの状態は無効に設定されます。

`COleCurrency` オペランドが無効な場合、この `COleCurrency` オブジェクトの状態は無効に設定されます。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

##  <a name="colecurrencyoperator-ltlt-gtgt"></a><a name="operator_stream"></a>COleCurrency:: operator &lt;&lt;、&gt;&gt;

診断ダンプをサポートし、アーカイブに保存します。

```
friend CDumpContext& operator<<(
    CDumpContext& dc,
    COleCurrency curSrc);

friend CArchive& operator<<(
    CArchive& ar,
    COleCurrency curSrc);

friend CArchive& operator>>(
    CArchive& ar,
    COleCurrency& curSrc);
```

### <a name="remarks"></a>コメント

抽出 ( **>>** ) 操作では、アーカイブからの読み込みがサポートされています。

##  <a name="colecurrencyoperator-currency"></a><a name="operator_currency"></a>COleCurrency:: operator CURRENCY

この `COleCurrency` オブジェクトから値がコピーされる `CURRENCY` 構造体を返します。

```
operator CURRENCY() const;
```

### <a name="remarks"></a>コメント

##  <a name="colecurrencyparsecurrency"></a><a name="parsecurrency"></a>COleCurrency::P Arセキュリティー

文字列を解析して通貨値を読み取るには、このメンバー関数を呼び出します。

```
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT);

throw(CMemoryException*);
throw(COleException*);
```

### <a name="parameters"></a>パラメーター

*lpszCurrency*<br/>
解析される null で終わる文字列へのポインター。

*dwFlags*<br/>
ロケール設定のフラグ (場合によっては、次のフラグ) を示します。

- LOCALE_NOUSEROVERRIDE は、カスタムユーザー設定ではなく、システムの既定のロケール設定を使用します。

*lcid*<br/>
変換に使用するロケール ID を示します。

### <a name="return-value"></a>戻り値

文字列が通貨値に正常に変換された場合は0以外の値。それ以外の場合は0。

### <a name="remarks"></a>コメント

ソース文字列内の数値以外の文字の意味には、ローカル言語仕様 (ロケール Id) が使用されます。

ロケール ID の値の詳細については、「[複数の言語のサポート](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages)」を参照してください。

文字列が通貨値に正常に変換された場合、この `COleCurrency` オブジェクトの値がその値に設定され、その状態が有効になります。

文字列を通貨値に変換できなかった場合、または数値のオーバーフローがあった場合、この `COleCurrency` オブジェクトの状態は無効になります。

メモリ割り当てエラーのために文字列の変換に失敗した場合、この関数は[CMemoryException](../../mfc/reference/cmemoryexception-class.md)をスローします。 その他のエラー状態では、この関数は[COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

##  <a name="colecurrency-relational-operators"></a><a name="colecurrency_relational_operators"></a>COleCurrency 関係演算子

2つの通貨値を比較して、条件が true の場合は0以外の値を返します。それ以外の場合は0です。

```
BOOL operator==(const COleCurrency& cur) const;
BOOL operator!=(const COleCurrency& cur) const;
BOOL operator<(const COleCurrency& cur) const;
BOOL operator>(const COleCurrency& cur) const;
BOOL operator<=(const COleCurrency& cur) const;
BOOL operator>=(const COleCurrency& cur) const;
```

### <a name="remarks"></a>コメント

> [!NOTE]
>  順序付け操作 ( **<** 、 **\<=** 、 **>** 、 **>=** ) の戻り値は、いずれかのオペランドの状態が null または無効の場合には定義されていません。 等値演算子 (`==`、`!=`) は、オペランドの状態を考慮します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

##  <a name="colecurrencysetcurrency"></a><a name="setcurrency"></a>COleCurrency:: SetCurrency

この `COleCurrency` オブジェクトの単位と小数部を設定するには、このメンバー関数を呼び出します。

```
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>パラメーター

*Nunits*は *、この*`COleCurrency` オブジェクトにコピーされる値の単位と小数部 (1/10000) を示します。

### <a name="remarks"></a>コメント

小数部分の絶対値が1万より大きい場合は、次の例の3番目の例に示すように、適切な調整が単位に対して行われます。

単位と小数部は、符号付き長の値によって指定されることに注意してください。 次の4つの例は、パラメーターの符号が異なる場合に何が起こるかを示しています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

##  <a name="colecurrencysetstatus"></a><a name="setstatus"></a>COleCurrency:: SetStatus

この `COleCurrency` オブジェクトの状態 (有効性) を設定するには、このメンバー関数を呼び出します。

```
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>パラメーター

*status*<br/>
この `COleCurrency` オブジェクトの新しい状態。

### <a name="remarks"></a>コメント

*Status*パラメーターの値は、`COleCurrency` クラス内で定義されている `CurrencyStatus` 列挙型によって定義されます。

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleCurrency::valid` は、この `COleCurrency` オブジェクトが有効であることを示します。

- `COleCurrency::invalid` は、この `COleCurrency` オブジェクトが無効であることを示します。つまり、値が正しくない可能性があります。

- `COleCurrency::null` は、この `COleCurrency` オブジェクトが null であること、つまり、このオブジェクトに値が指定されていないことを示します。 ( C++ Null ではなく、"値がない" というデータベースの意味では "null" になります)。

> [!CAUTION]
>  この関数は、高度なプログラミングの状況に適しています。 この関数は、このオブジェクトのデータを変更しません。 この値は、通常、状態を null または無効に設定するために使用されます。 代入演算子 ( [operator =](#operator_eq)) と[setcurrency](#setcurrency)では、ソース値に基づいてオブジェクトの状態がに設定されることに注意してください。

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleVariant クラス](../../mfc/reference/colevariant-class.md)
