---
title: クラスを変更します。
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
ms.openlocfilehash: 3cb3217e02323f8a0afcd1639e6e24ee7b0f136e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366137"
---
# <a name="colecurrency-class"></a>クラスを変更します。

OLE オートメーションで使用される `CURRENCY` データ型をカプセル化します。

## <a name="syntax"></a>構文

```
class COleCurrency
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コレ通貨::コレ通貨](#colecurrency)|`COleCurrency` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロール通貨::フォーマット](#format)|オブジェクトの書式付き文字列形式を`COleCurrency`生成します。|
|[コントロール通貨::ステータスを取得します。](#getstatus)|この`COleCurrency`オブジェクトの状態 (有効性) を取得します。|
|[コレ通貨::Pお粗い通貨](#parsecurrency)|文字列から CURRENCY 値を読み取り、`COleCurrency`値を設定します。|
|[コレ通貨::設定通貨](#setcurrency)|この`COleCurrency`オブジェクトの値を設定します。|
|[コントロール通貨::ステータスを設定します。](#setstatus)|この`COleCurrency`オブジェクトのステータス (有効性) を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[演算子 =](#operator_eq)|値を`COleCurrency`コピーします。|
|[演算子 +、 -](#operator_plus_minus)|`COleCurrency`値の符号を加算、減算、および変更します。|
|[演算子 +=、-=](#operator_plus_minus_eq)|この`COleCurrency`オブジェクトの値を`COleCurrency`加算および減算します。|
|[演算子 */](#operator_star)|整数値で`COleCurrency`値をスケールします。|
|[演算子 *=、 /=](#operator_star_div_eq)|この`COleCurrency`値を整数値でスケールします。|
|[演算子 <<](#operator_stream)|値を`COleCurrency`または`CDumpContext``CArchive`に出力します。|
|[演算子 >>](#operator_stream)|から`CArchive`オブジェクトを`COleCurrency`入力します。|
|[オペレーター通貨](#operator_currency)|値を`COleCurrency`通貨に変換します。|
|[演算子 ==、<、<=など](#colecurrency_relational_operators)|2 つの`COleCurrency`値を比較します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コレ通貨:m_cur](#m_cur)|この`COleCurrency`オブジェクトの基になる通貨が含まれています。|
|[コレ通貨::m_status](#m_status)|このオブジェクトの状態を`COleCurrency`格納します。|

## <a name="remarks"></a>解説

`COleCurrency`は基本クラスを持っていません。

CURRENCY は、8 バイト、2 の補数の整数値として 10,000 倍に実装されます。 これは、15 桁の整数部と 4 桁の小数部を持つ固定小数点数として表現されます。 通貨データ型は、お金を含む計算や、精度が重要な固定小数点計算に非常に便利です。 OLE オートメーションのデータ型に`VARIANT`使用できる型の 1 つです。

`COleCurrency`また、この固定小数点型に対する基本的な算術演算も実装します。 固定小数点計算中に発生する丸め誤差を制御するために、サポートされている操作が選択されています。

## <a name="inheritance-hierarchy"></a>継承階層

`COleCurrency`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="colecurrencycolecurrency"></a><a name="colecurrency"></a>コレ通貨::コレ通貨

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

*サイスルク*<br/>
新しい`COleCurrency`オブジェクトにコピーされる通貨値。

*カースrc*<br/>
新しい`COleCurrency``COleCurrency`オブジェクトにコピーされる既存のオブジェクト。

*varSrc*<br/>
通貨値`VARIANT`(VT_CY)`COleVariant`に変換され、新しい`COleCurrency`オブジェクトにコピーされる既存のデータ構造 (オブジェクトなど)。

*n単位**、nFractional 単位*新しい`COleCurrency`オブジェクトにコピーする値の単位と小数部 (1/10,000 単位) を示します。

### <a name="remarks"></a>解説

これらのコンストラクターは、すべて、指定`COleCurrency`された値に初期化された新しいオブジェクトを作成します。 これらの各コンストラクターの簡単な説明を次に示します。 特に明記されていない限り、新`COleCurrency`しい項目のステータスは有効に設定されます。

- 0 (ゼロ) に`COleCurrency`初期化されたオブジェクトを構築します。

- `cySrc`通貨[値から](/windows/win32/api/wtypes/ns-wtypes-cy~r1)オブジェクトを`COleCurrency`構築します。

- `curSrc`既存のオブジェクトからオブジェクトを`COleCurrency`構築`COleCurrency`します。 新しいオブジェクトのステータスは、ソース オブジェクトと同じです。

- `varSrc`オブジェクトを構築します`COleCurrency`。 [バリアント型 (VARIANT)](/windows/win32/api/oaidl/ns-oaidl-variant)の`COleVariant`構造またはオブジェクトを通貨 (VT_CY) 値に変換しようとします。 この変換が成功すると、変換された値が新しい`COleCurrency`オブジェクトにコピーされます。 値が設定されていない場合、`COleCurrency`オブジェクトの値はゼロ (0) に設定され、状態は無効になります。

- COleCurrency(`nUnits` `nFractionalUnits`, )`COleCurrency`指定された数値コンポーネントからオブジェクトを構築します。 小数部の絶対値が 10,000 より大きい場合は、単位に適切な調整が行われます。 単位と小数部は符号付き長整数で指定されます。

詳細については、Windows SDK の[通貨](/windows/win32/api/wtypes/ns-wtypes-cy~r1)および[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)のエントリを参照してください。

### <a name="example"></a>例

次の例は、0 パラメーターと 2 つのパラメーターのコンストラクターの効果を示しています。

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

## <a name="colecurrencyformat"></a><a name="format"></a>コントロール通貨::フォーマット

通貨値の書式化された表現を作成します。

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
ロケール設定のフラグを示します。 通貨に関連するフラグは次のフラグのみです。

- LOCALE_NOUSEROVERRIDEカスタム ユーザー設定ではなく、システムの既定のロケール設定を使用します。

*lcid*<br/>
変換に使用するロケール ID を示します。

### <a name="return-value"></a>戻り値

書式設定`CString`された通貨の値を含む A。

### <a name="remarks"></a>解説

ローカル言語仕様 (ロケール ID) を使用して値をフォーマットします。 通貨記号は、返される値には含まれません。 この`COleCurrency`オブジェクトの状態が null の場合、戻り値は空の文字列です。 状態が無効な場合、戻り値の文字列は文字列リソース IDS_INVALID_CURRENCYによって指定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

## <a name="colecurrencygetstatus"></a><a name="getstatus"></a>コントロール通貨::ステータスを取得します。

指定された`COleCurrency`オブジェクトの状態 (有効性) を取得するには、このメンバー関数を呼び出します。

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>戻り値

この`COleCurrency`値の状態を返します。

### <a name="remarks"></a>解説

戻り値は、クラス内`CurrencyStatus`で定義されている列挙型によって定義されます`COleCurrency`。

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleCurrency::valid`この`COleCurrency`オブジェクトが有効であることを示します。

- `COleCurrency::invalid`この`COleCurrency`オブジェクトが無効であることを示します。つまり、その値が正しくない可能性があります。

- `COleCurrency::null`この`COleCurrency`オブジェクトが null、つまり、このオブジェクトに値が指定されていない場合を示します。 (これは、C++ の NULL とは対照的に、"値を持たない" というデータベースの意味での "null" です。

オブジェクトの`COleCurrency`ステータスは、次の場合無効です。

- その値がバリアント型 (VARIANT)`COleVariant`または通貨値に変換できなかった値から設定されている場合。

- このオブジェクトが算術代入操作中にオーバーフローまたはアンダーフローを経験した場合は、たとえば`+=`、**\*** または などです。

- 無効な値がこのオブジェクトに割り当てられていた場合。

- このオブジェクトの状態が[SetStatus](#setstatus)を使用して明示的に無効に設定されている場合。

状態を無効に設定できる操作の詳細については、次のメンバー関数を参照してください。

- [COleCurrency](#colecurrency)

- [演算子 =](#operator_eq)

- [演算子 + -](#operator_plus_minus)

- [演算子 += および -=](#operator_plus_minus_eq)

- [演算子 * /](#operator_star)

- [演算子 *= および /=](#operator_star_div_eq)

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

## <a name="colecurrencym_cur"></a><a name="m_cur"></a>コレ通貨:m_cur

この`COleCurrency`オブジェクトの基になる[CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1)構造体。

### <a name="remarks"></a>解説

> [!CAUTION]
> この関数によって返される`CURRENCY`ポインターがアクセスする構造体の値を変更すると、この`COleCurrency`オブジェクトの値が変更されます。 この`COleCurrency`オブジェクトのステータスは変更されません。

詳細については、Windows SDK の[通貨](/windows/win32/api/wtypes/ns-wtypes-cy~r1)エントリを参照してください。

## <a name="colecurrencym_status"></a><a name="m_status"></a>コレ通貨::m_status

このデータ メンバの型は、クラス内で`CurrencyStatus`定義される列挙型です`COleCurrency`。

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>解説

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleCurrency::valid`この`COleCurrency`オブジェクトが有効であることを示します。

- `COleCurrency::invalid`この`COleCurrency`オブジェクトが無効であることを示します。つまり、その値が正しくない可能性があります。

- `COleCurrency::null`この`COleCurrency`オブジェクトが null、つまり、このオブジェクトに値が指定されていない場合を示します。 (これは、C++ の NULL とは対照的に、"値を持たない" というデータベースの意味での "null" です。

オブジェクトの`COleCurrency`ステータスは、次の場合無効です。

- その値がバリアント型 (VARIANT)`COleVariant`または通貨値に変換できなかった値から設定されている場合。

- このオブジェクトが算術代入操作中にオーバーフローまたはアンダーフローを経験した場合は、たとえば`+=`、**\*** または などです。

- 無効な値がこのオブジェクトに割り当てられていた場合。

- このオブジェクトの状態が[SetStatus](#setstatus)を使用して明示的に無効に設定されている場合。

状態を無効に設定できる操作の詳細については、次のメンバー関数を参照してください。

- [COleCurrency](#colecurrency)

- [演算子 =](#operator_eq)

- [演算子 +、 -](#operator_plus_minus)

- [演算子 +=、-=](#operator_plus_minus_eq)

- [演算子 */](#operator_star)

- [演算子 *=、 /=](#operator_star_div_eq)

> [!CAUTION]
> このデータ メンバーは、高度なプログラミングの状況に適しています。 インライン メンバー関数[GetStatus](#getstatus)と[SetStatus](#setstatus)を使用する必要があります。 この`SetStatus`データ メンバーの明示的な設定に関する詳細な注意については、「」を参照してください。

## <a name="colecurrencyoperator-"></a><a name="operator_eq"></a>コントロール通貨::演算子 =

これらのオーバーロードされた代入演算子は、ソース通貨値をこの`COleCurrency`オブジェクトにコピーします。

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>解説

各演算子の簡単な説明を次に示します。

- **演算子 =(** `cySrc` **)** 値`CURRENCY`が`COleCurrency`オブジェクトにコピーされ、その状態が有効に設定されます。

- **演算子 =(** `curSrc` **)** オペランドの値とステータスは、既存`COleCurrency`のオブジェクトに`COleCurrency`コピーされます。

- 演算子 *=(varSrc)* **)** **operator =(** 値 (または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト) から通貨 ( `VT_CY`) への変換が成功すると、変換された値がこの`COleCurrency`オブジェクトにコピーされ、状態が有効に設定されます。 `VARIANT` 変換が成功しなかった場合、`COleCurrency`オブジェクトの値は 0 に設定され、その状態は無効になります。

詳細については、Windows SDK の[通貨](/windows/win32/api/wtypes/ns-wtypes-cy~r1)および[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)のエントリを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus"></a>コントロール通貨::演算子 +、 -

これらの演算子を使用すると、2 つの`COleCurrency`値を相互に加算したり、相互に値を引いたり`COleCurrency`、値の符号を変更したりできます。

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>解説

オペランドのどちらかが null の場合、結果`COleCurrency`の値の状況は NULL になります。

算術演算がオーバーフローした場合、結果`COleCurrency`の値は無効です。

オペランドが無効で、もう一方が NULL でない場合、結果`COleCurrency`の値の状況は無効です。

有効、無効、および NULL の状態値の詳細については[、m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus_eq"></a>コントロール通貨::演算子 +=、-=

この`COleCurrency`オブジェクトに対して値を`COleCurrency`加算したり、このオブジェクトから値を減算したりできます。

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>解説

オペランドのいずれかが null の場合、この`COleCurrency`オブジェクトの状況は null に設定されます。

算術演算がオーバーフローすると、この`COleCurrency`オブジェクトの状態は無効に設定されます。

どちらかのオペランドが無効で、もう一方のオペランドが NULL でない場合、`COleCurrency`このオブジェクトのステータスは無効に設定されます。

有効、無効、および NULL の状態値の詳細については[、m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

## <a name="colecurrencyoperator--and-"></a><a name="operator_star"></a>コントロール通貨::演算子\*と/

整数値で値を`COleCurrency`スケールできます。

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>解説

オペランドが`COleCurrency`null の場合、結果`COleCurrency`の値の状況は null になります。

算術演算がオーバーフローまたはアンダーフローの場合、結果の`COleCurrency`値の状況は無効です。

オペランドが`COleCurrency`無効な場合、結果`COleCurrency`の値の状況は無効です。

有効、無効、および NULL の状態値の詳細については[、m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

## <a name="colecurrencyoperator--"></a><a name="operator_star_div_eq"></a>コントロール通貨::演算子\*=、/=

整数値でスケール`COleCurrency`できます。

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>解説

オペランドが`COleCurrency`null の場合、この`COleCurrency`オブジェクトの状況は null に設定されます。

算術演算がオーバーフローすると、この`COleCurrency`オブジェクトの状態は無効に設定されます。

オペランドが`COleCurrency`無効な場合、この`COleCurrency`オブジェクトのステータスは無効に設定されます。

有効、無効、および NULL の状態値の詳細については[、m_status](#m_status)メンバー変数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

## <a name="colecurrencyoperator-ltlt-gtgt"></a><a name="operator_stream"></a>コントロール通貨::演算子&lt;&lt;、&gt;&gt;

アーカイブへの診断ダンプと保存をサポートします。

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

### <a name="remarks"></a>解説

抽出 ( **>>**) 演算子は、アーカイブからのロードをサポートします。

## <a name="colecurrencyoperator-currency"></a><a name="operator_currency"></a>コレ通貨::演算子通貨

この`COleCurrency`オブジェクト`CURRENCY`から値がコピーされる構造体を返します。

```
operator CURRENCY() const;
```

### <a name="remarks"></a>解説

## <a name="colecurrencyparsecurrency"></a><a name="parsecurrency"></a>コレ通貨::Pお粗い通貨

通貨値を読み取るために文字列を解析します。

```
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT);

throw(CMemoryException*);
throw(COleException*);
```

### <a name="parameters"></a>パラメーター

*通貨を設定します。*<br/>
解析対象の NULL で終わる文字列へのポインター。

*dwFlags*<br/>
ロケール設定のフラグを示します。場合によっては次のフラグを示します。

- LOCALE_NOUSEROVERRIDEカスタム ユーザー設定ではなく、システムの既定のロケール設定を使用します。

*lcid*<br/>
変換に使用するロケール ID を示します。

### <a name="return-value"></a>戻り値

文字列が通貨値に正常に変換された場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

ソース文字列内の非数値文字の意味に、ローカル言語仕様 (ロケール ID) を使用します。

ロケール ID 値の詳細については、「[複数言語のサポート](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages)」を参照してください。

文字列が通貨値に正常に変換された場合、この`COleCurrency`オブジェクトの値はその値に設定され、状態は有効に設定されます。

文字列を通貨値に変換できなかった場合、または数値オーバーフローがあった場合、この`COleCurrency`オブジェクトのステータスは無効です。

メモリ割り当てエラーが原因で文字列変換が失敗した場合、この関数は[CMemoryException](../../mfc/reference/cmemoryexception-class.md)をスローします。 他のエラー状態では、この関数は[COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

## <a name="colecurrency-relational-operators"></a><a name="colecurrency_relational_operators"></a>COleCurrency 関係演算子

2 つの通貨値を比較し、条件が真の場合は 0 以外を返します。それ以外の場合は 0。

```
BOOL operator==(const COleCurrency& cur) const;
BOOL operator!=(const COleCurrency& cur) const;
BOOL operator<(const COleCurrency& cur) const;
BOOL operator>(const COleCurrency& cur) const;
BOOL operator<=(const COleCurrency& cur) const;
BOOL operator>=(const COleCurrency& cur) const;
```

### <a name="remarks"></a>解説

> [!NOTE]
> いずれかのオペランドの状態が NULL**<** または**\<** 無効**>** の**>=** 場合、順序付け操作 ( , , ) の戻り値は未定義です。 等値演算子 ( `==` `!=`, ) は、オペランドの状況を考慮します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

## <a name="colecurrencysetcurrency"></a><a name="setcurrency"></a>コレ通貨::設定通貨

このメンバー関数を呼び出して、この`COleCurrency`オブジェクトの単位と小数部を設定します。

```
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>パラメーター

*n単位**、nFractional 単位*この`COleCurrency`オブジェクトにコピーする値の単位と小数部 (1/10,000 単位) を示します。

### <a name="remarks"></a>解説

小数部の絶対値が 10,000 より大きい場合、次の例の 3 番目に示すように、単位に対して適切な調整が行われます。

単位と小数部は符号付き長整数で指定されます。 次の例の 4 番目は、パラメーターの符号が異なる場合に何が起こるかを示しています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

## <a name="colecurrencysetstatus"></a><a name="setstatus"></a>コントロール通貨::ステータスを設定します。

このメンバー関数を呼び出して、この`COleCurrency`オブジェクトの状態 (有効性) を設定します。

```
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>パラメーター

*status*<br/>
この`COleCurrency`オブジェクトの新しいステータス。

### <a name="remarks"></a>解説

*status*パラメーターの値は、クラス`CurrencyStatus`内で定義される列挙型によって定義されます`COleCurrency`。

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleCurrency::valid`この`COleCurrency`オブジェクトが有効であることを示します。

- `COleCurrency::invalid`この`COleCurrency`オブジェクトが無効であることを示します。つまり、その値が正しくない可能性があります。

- `COleCurrency::null`この`COleCurrency`オブジェクトが null、つまり、このオブジェクトに値が指定されていない場合を示します。 (これは、C++ の NULL とは対照的に、"値を持たない" というデータベースの意味での "null" です。

> [!CAUTION]
> この関数は、高度なプログラミングの状況に対応します。 この関数は、このオブジェクトのデータを変更しません。 ほとんどの場合、この状態を null または無効に設定するために使用されます。 代入演算子 ([演算子 =](#operator_eq)) と[SetCurrency](#setcurrency)は、ソース値に基づいてオブジェクトのステータスを設定します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleVariant クラス](../../mfc/reference/colevariant-class.md)
