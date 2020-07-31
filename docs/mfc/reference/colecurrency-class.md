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
ms.openlocfilehash: ced4554701cef5fd6f790b9e37f4c1b41746b1ad
ms.sourcegitcommit: 13f42c339fb7af935e3a93ac80e350d5e784c9f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "87470967"
---
# <a name="colecurrency-class"></a>COleCurrency クラス

OLE オートメーションで使用される `CURRENCY` データ型をカプセル化します。

## <a name="syntax"></a>構文

```
class COleCurrency
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleCurrency:: COleCurrency](#colecurrency)|`COleCurrency` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleCurrency:: Format](#format)|オブジェクトの書式設定された文字列形式を生成 `COleCurrency` します。|
|[COleCurrency:: GetStatus](#getstatus)|このオブジェクトの状態 (有効) を取得し `COleCurrency` ます。|
|[COleCurrency::P Arセキュリティー](#parsecurrency)|文字列から通貨値を読み取り、の値を設定し `COleCurrency` ます。|
|[COleCurrency:: SetCurrency](#setcurrency)|このオブジェクトの値を設定 `COleCurrency` します。|
|[COleCurrency:: SetStatus](#setstatus)|このオブジェクトの状態 (有効性) を設定し `COleCurrency` ます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator =](#operator_eq)|値をコピー `COleCurrency` します。|
|[演算子 +、-](#operator_plus_minus)|値の符号を加算、減算、および変更し `COleCurrency` ます。|
|[operator + =、-=](#operator_plus_minus_eq)|このオブジェクトの値を加算および減算し `COleCurrency` `COleCurrency` ます。|
|[演算子 */](#operator_star)|`COleCurrency`整数値で値をスケーリングします。|
|[operator * =、/=](#operator_star_div_eq)|この `COleCurrency` 値を整数値でスケーリングします。|
|[ <<演算子](#operator_stream)|値を `COleCurrency` `CArchive` またはに出力 `CDumpContext` します。|
|[ >>演算子](#operator_stream)|`COleCurrency`からオブジェクトを入力 `CArchive` します。|
|[演算子の通貨](#operator_currency)|値を `COleCurrency` 通貨に変換します。|
|[operator = =、<、<= など](#colecurrency_relational_operators)|2つ `COleCurrency` の値を比較します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleCurrency:: m_cur](#m_cur)|このオブジェクトの基になる通貨を格納 `COleCurrency` します。|
|[COleCurrency:: m_status](#m_status)|このオブジェクトの状態を格納 `COleCurrency` します。|

## <a name="remarks"></a>Remarks

`COleCurrency`に基底クラスがありません。

通貨は、1万によってスケーリングされた8バイトの2の補数整数値として実装されます。 これは、15 桁の整数部と 4 桁の小数部を持つ固定小数点数として表現されます。 通貨データ型は、金額を含む計算や、精度が重要な固定小数点計算に非常に便利です。 OLE オートメーションのデータ型に使用できる型の1つです `VARIANT` 。

`COleCurrency`は、この固定小数点型の基本的な算術演算も実装します。 サポートされている操作は、固定小数点数の計算中に発生する丸め誤差を制御するために選択されています。

## <a name="inheritance-hierarchy"></a>継承階層

`COleCurrency`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="colecurrencycolecurrency"></a><a name="colecurrency"></a>COleCurrency:: COleCurrency

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
新しいオブジェクトにコピーされる通貨値 `COleCurrency` 。

*curSrc*<br/>
`COleCurrency`新しいオブジェクトにコピーされる既存のオブジェクト `COleCurrency` 。

*varSrc*<br/>
`VARIANT` `COleVariant` 通貨値 (VT_CY) に変換して新しいオブジェクトにコピーする既存のデータ構造 (オブジェクトなど) `COleCurrency` 。

*nunits*、 *nFractionalUnits*は、新しいオブジェクトにコピーされる値の単位と小数部 (1/10000) を示し `COleCurrency` ます。

### <a name="remarks"></a>Remarks

これらのすべてのコンストラクターは `COleCurrency` 、指定された値に初期化された新しいオブジェクトを作成します。 これらの各コンストラクターの簡単な説明を次に示します。 特に明記されていない限り、新しい項目の状態 `COleCurrency` は "有効" に設定されます。

- COleCurrency () は、 `COleCurrency` 0 (ゼロ) に初期化されたオブジェクトを構築します。

- COleCurrency ( `cySrc` ) は、 `COleCurrency` [通貨](/windows/win32/api/wtypes/ns-wtypes-cy-r1)値からオブジェクトを構築します。

- COleCurrency ( `curSrc` ) は、 `COleCurrency` 既存のオブジェクトからオブジェクトを構築 `COleCurrency` します。 新しいオブジェクトは、ソースオブジェクトと同じ状態になります。

- COleCurrency ( `varSrc` ) は、 `COleCurrency` オブジェクトを構築します。 [バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)構造体またはオブジェクトから `COleVariant` 通貨 (VT_CY) 値への変換を試みます。 この変換が成功した場合は、変換後の値が新しいオブジェクトにコピーされ `COleCurrency` ます。 そうでない場合は、オブジェクトの値 `COleCurrency` がゼロ (0) に設定され、その状態が無効になります。

- COleCurrency ( `nUnits` , `nFractionalUnits` ) は、 `COleCurrency` 指定された数値コンポーネントからオブジェクトを構築します。 小数部分の絶対値が1万を超える場合は、その単位に適切な調整が行われます。 単位と小数部は、符号付き長の値によって指定されることに注意してください。

詳細については、Windows SDK の「 [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy-r1) 」と「 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 」のエントリを参照してください。

### <a name="example"></a>例

次の例は、ゼロパラメーターと2つのパラメーターのコンストラクターの効果を示しています。

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

## <a name="colecurrencyformat"></a><a name="format"></a>COleCurrency:: Format

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

`CString`書式設定された通貨値を格納している。

### <a name="remarks"></a>Remarks

この値は、ローカル言語仕様 (ロケール Id) を使用して書式設定されます。 返される値に通貨記号は含まれません。 このオブジェクトの状態 `COleCurrency` が null の場合、戻り値は空の文字列になります。 状態が無効である場合は、文字列リソース IDS_INVALID_CURRENCY によって返される文字列が指定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

## <a name="colecurrencygetstatus"></a><a name="getstatus"></a>COleCurrency:: GetStatus

指定したオブジェクトの状態 (有効性) を取得するには、このメンバー関数を呼び出し `COleCurrency` ます。

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>戻り値

この値の状態を返し `COleCurrency` ます。

### <a name="remarks"></a>Remarks

戻り値は、クラス内で定義されている列挙型によって定義され `CurrencyStatus` `COleCurrency` ます。

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleCurrency::valid`このオブジェクトが有効であることを示し `COleCurrency` ます。

- `COleCurrency::invalid`このオブジェクトが無効であることを示します。つまり `COleCurrency` 、値が正しくない可能性があります。

- `COleCurrency::null`このオブジェクトが null であること、つまり `COleCurrency` 、このオブジェクトに値が指定されていないことを示します。 (これは、C++ NULL ではなく、"値がない" というデータベースの意味では "null" です)。

オブジェクトの状態 `COleCurrency` は、次の場合には無効です。

- 値が、 `COleVariant` 通貨値に変換できなかったバリアントまたは値から設定されている場合は。

- このオブジェクトの算術演算中にオーバーフローまたはアンダーフローが発生した場合 (やなど) `+=` **\*=** 。

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

## <a name="colecurrencym_cur"></a><a name="m_cur"></a>COleCurrency:: m_cur

このオブジェクトの基になる[通貨](/windows/win32/api/wtypes/ns-wtypes-cy-r1)構造 `COleCurrency` 。

### <a name="remarks"></a>Remarks

> [!CAUTION]
> `CURRENCY`この関数によって返されるポインターによってアクセスされる構造体の値を変更すると、このオブジェクトの値が変更され `COleCurrency` ます。 このオブジェクトの状態は変更されません `COleCurrency` 。

詳細については、Windows SDK の「 [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy-r1) 」エントリを参照してください。

## <a name="colecurrencym_status"></a><a name="m_status"></a>COleCurrency:: m_status

このデータメンバーの型は列挙型であり `CurrencyStatus` 、クラス内で定義されてい `COleCurrency` ます。

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>Remarks

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleCurrency::valid`このオブジェクトが有効であることを示し `COleCurrency` ます。

- `COleCurrency::invalid`このオブジェクトが無効であることを示します。つまり `COleCurrency` 、値が正しくない可能性があります。

- `COleCurrency::null`このオブジェクトが null であること、つまり `COleCurrency` 、このオブジェクトに値が指定されていないことを示します。 (これは、C++ NULL ではなく、"値がない" というデータベースの意味では "null" です)。

オブジェクトの状態 `COleCurrency` は、次の場合には無効です。

- 値が、 `COleVariant` 通貨値に変換できなかったバリアントまたは値から設定されている場合は。

- このオブジェクトの算術演算中にオーバーフローまたはアンダーフローが発生した場合 (やなど) `+=` **\*=** 。

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
> このデータメンバーは、高度なプログラミングの状況を対象としています。 インラインメンバー関数[GetStatus](#getstatus)および[SetStatus](#setstatus)を使用する必要があります。 `SetStatus`このデータメンバーを明示的に設定する方法については、「」を参照してください。

## <a name="colecurrencyoperator-"></a><a name="operator_eq"></a>COleCurrency:: operator =

これらのオーバーロードされた代入演算子は、source currency 値をこのオブジェクトにコピー `COleCurrency` します。

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>Remarks

各演算子の簡単な説明を次に示します。

- **operator = (** `cySrc` **)** : `CURRENCY` 値がオブジェクトにコピーされ、 `COleCurrency` その状態が有効に設定されます。

- **operator = (** `curSrc` **)** オペランドの値と状態。既存の `COleCurrency` オブジェクトは、このオブジェクトにコピーされ `COleCurrency` ます。

- **operator = (** *varsrc* **)**`VARIANT`値 (または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト) から currency () への変換 `VT_CY` が成功すると、変換後の値がこのオブジェクトにコピーされ、 `COleCurrency` その状態が有効に設定されます。 変換が成功しなかった場合、オブジェクトの値 `COleCurrency` は0に設定され、その状態は無効になります。

詳細については、Windows SDK の「 [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy-r1) 」と「 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 」のエントリを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus"></a>COleCurrency:: operator +、-

これらの演算子を使用すると、2つの値の加算と減算を行ったり、値の符号を変更したりすることができ `COleCurrency` `COleCurrency` ます。

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>Remarks

オペランドのいずれかが null の場合、結果の値の状態 `COleCurrency` は null になります。

算術演算がオーバーフローした場合、結果の `COleCurrency` 値は無効になります。

オペランドが無効で、もう一方が null でない場合、結果の値の状態 `COleCurrency` は無効になります。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus_eq"></a>COleCurrency:: operator + =、-=

このオブジェクトとの間で値の加算と減算を行うことができ `COleCurrency` `COleCurrency` ます。

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>Remarks

オペランドのいずれかが null の場合、このオブジェクトの状態 `COleCurrency` は null に設定されます。

算術演算がオーバーフローした場合、このオブジェクトの状態 `COleCurrency` は無効に設定されます。

オペランドのいずれかが無効で、もう一方が null でない場合、このオブジェクトの状態 `COleCurrency` は無効に設定されます。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

## <a name="colecurrencyoperator--and-"></a><a name="operator_star"></a>COleCurrency:: operator \* および/

`COleCurrency`整数値で値をスケーリングできます。

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>Remarks

`COleCurrency`オペランドが null の場合、結果の値の状態 `COleCurrency` は null になります。

算術演算がオーバーフローまたはアンダーフローする場合、結果の `COleCurrency` 値の状態は無効になります。

`COleCurrency`オペランドが無効な場合、結果の値の状態 `COleCurrency` は無効になります。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

## <a name="colecurrencyoperator--"></a><a name="operator_star_div_eq"></a>COleCurrency:: operator \* =、/=

この `COleCurrency` 値を整数値でスケーリングできます。

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>Remarks

`COleCurrency`オペランドが null の場合、このオブジェクトの状態 `COleCurrency` は null に設定されます。

算術演算がオーバーフローした場合、このオブジェクトの状態 `COleCurrency` は無効に設定されます。

`COleCurrency`オペランドが無効な場合、このオブジェクトの状態 `COleCurrency` は無効に設定されます。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

## <a name="colecurrencyoperator-ltlt-gtgt"></a><a name="operator_stream"></a>COleCurrency:: operator &lt; &lt; 、&gt;&gt;

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

### <a name="remarks"></a>Remarks

抽出 ( **>>** ) 演算子は、アーカイブからの読み込みをサポートしています。

## <a name="colecurrencyoperator-currency"></a><a name="operator_currency"></a>COleCurrency:: operator CURRENCY

`CURRENCY`このオブジェクトから値がコピーされる構造体を返し `COleCurrency` ます。

```
operator CURRENCY() const;
```

### <a name="remarks"></a>Remarks

## <a name="colecurrencyparsecurrency"></a><a name="parsecurrency"></a>COleCurrency::P Arセキュリティー

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

### <a name="remarks"></a>Remarks

ソース文字列内の数値以外の文字の意味には、ローカル言語仕様 (ロケール Id) が使用されます。

ロケール ID の値の詳細については、「[複数の言語のサポート](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages)」を参照してください。

文字列が通貨値に正常に変換された場合、このオブジェクトの値 `COleCurrency` はその値に設定され、その状態が有効になります。

文字列を通貨値に変換できなかった場合、または数値のオーバーフローがあった場合、このオブジェクトの状態 `COleCurrency` は無効になります。

メモリ割り当てエラーのために文字列の変換に失敗した場合、この関数は[CMemoryException](../../mfc/reference/cmemoryexception-class.md)をスローします。 その他のエラー状態では、この関数は[COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

## <a name="colecurrency-relational-operators"></a><a name="colecurrency_relational_operators"></a>COleCurrency 関係演算子

2つの通貨値を比較して、条件が true の場合は0以外の値を返します。それ以外の場合は0です。

```
BOOL operator==(const COleCurrency& cur) const;
BOOL operator!=(const COleCurrency& cur) const;
BOOL operator<(const COleCurrency& cur) const;
BOOL operator>(const COleCurrency& cur) const;
BOOL operator<=(const COleCurrency& cur) const;
BOOL operator>=(const COleCurrency& cur) const;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> 順序付け操作 ( **<** 、、) の戻り **\<=**, **>** 値 **>=** は、いずれかのオペランドの状態が null または無効である場合は未定義です。 等値演算子 ( `==` , `!=` ) は、オペランドの状態を考慮します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

## <a name="colecurrencysetcurrency"></a><a name="setcurrency"></a>COleCurrency:: SetCurrency

このメンバー関数を呼び出して、このオブジェクトの単位と小数部を設定し `COleCurrency` ます。

```cpp
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>パラメーター

*nunits*、 *nFractionalUnits*は、このオブジェクトにコピーされる値の単位と小数部 (1/10000) を示し `COleCurrency` ます。

### <a name="remarks"></a>Remarks

小数部分の絶対値が1万より大きい場合は、次の例の3番目の例に示すように、適切な調整が単位に対して行われます。

単位と小数部は、符号付き長の値によって指定されることに注意してください。 次の4つの例は、パラメーターの符号が異なる場合に何が起こるかを示しています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

## <a name="colecurrencysetstatus"></a><a name="setstatus"></a>COleCurrency:: SetStatus

このメンバー関数を呼び出して、このオブジェクトの状態 (有効性) を設定し `COleCurrency` ます。

```cpp
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>パラメーター

*status*<br/>
このオブジェクトの新しい状態 `COleCurrency` 。

### <a name="remarks"></a>Remarks

*Status*パラメーターの値は、クラス内で定義されている列挙型によって定義され `CurrencyStatus` `COleCurrency` ます。

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleCurrency::valid`このオブジェクトが有効であることを示し `COleCurrency` ます。

- `COleCurrency::invalid`このオブジェクトが無効であることを示します。つまり `COleCurrency` 、値が正しくない可能性があります。

- `COleCurrency::null`このオブジェクトが null であること、つまり `COleCurrency` 、このオブジェクトに値が指定されていないことを示します。 (これは、C++ NULL ではなく、"値がない" というデータベースの意味では "null" です)。

> [!CAUTION]
> この関数は、高度なプログラミングの状況に適しています。 この関数は、このオブジェクトのデータを変更しません。 この値は、通常、状態を null または無効に設定するために使用されます。 代入演算子 ( [operator =](#operator_eq)) と[setcurrency](#setcurrency)では、ソース値に基づいてオブジェクトの状態がに設定されることに注意してください。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleVariant クラス](../../mfc/reference/colevariant-class.md)
