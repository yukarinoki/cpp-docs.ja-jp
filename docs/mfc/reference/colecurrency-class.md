---
title: COleCurrency クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5295638019b04abe4f404a36b8cdf641b1f92a4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075776"
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
|[COleCurrency::COleCurrency](#colecurrency)|`COleCurrency` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleCurrency::Format](#format)|書式設定された文字列表現を生成、`COleCurrency`オブジェクト。|
|[COleCurrency::GetStatus](#getstatus)|この状態 (有効) を取得`COleCurrency`オブジェクト。|
|[COleCurrency::ParseCurrency](#parsecurrency)|文字列から通貨値を読み取っての値を設定`COleCurrency`します。|
|[COleCurrency::SetCurrency](#setcurrency)|この値を設定`COleCurrency`オブジェクト。|
|[COleCurrency::SetStatus](#setstatus)|状態 (有効) を設定します。`COleCurrency`オブジェクト。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[演算子 =](#operator_eq)|コピーを`COleCurrency`値。|
|[演算子 +、-](#operator_plus_minus)|追加、減算、およびの符号を変更`COleCurrency`値。|
|[演算子 + =、=](#operator_plus_minus_eq)|追加し、減算、`COleCurrency`値からこの`COleCurrency`オブジェクト。|
|[演算子 */](#operator_star)|スケール、`COleCurrency`の値を整数値。|
|[演算子 * =、/、=](#operator_star_div_eq)|これを拡大または縮小`COleCurrency`の値を整数値。|
|[演算子 <<](#operator_stream)|出力を`COleCurrency`値を`CArchive`または`CDumpContext`します。|
|[演算子 >>](#operator_stream)|入力、`COleCurrency`オブジェクトから`CArchive`します。|
|[演算子の通貨](#operator_currency)|変換を`COleCurrency`値を通貨に換算します。|
|[演算子 = =、<、< = など。](#colecurrency_relational_operators)|2 つ`COleCurrency`値。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleCurrency::m_cur](#m_cur)|これを基になる通貨を含む`COleCurrency`オブジェクト。|
|[COleCurrency::m_status](#m_status)|この状態を含む`COleCurrency`オブジェクト。|

## <a name="remarks"></a>Remarks

`COleCurrency` 基本クラスはありません。

通貨は、8 バイト、2 の補数の整数値が 10,000 を掛けとして実装されます。 これは、15 桁の整数部と 4 桁の小数部を持つ固定小数点数として表現されます。 通貨データ型は、精度が重要な関連する計算、または固定小数点のすべての計算に非常に便利です。 使用可能な型の 1 つは、 `VARIANT` OLE オートメーションのデータ型。

`COleCurrency` この固定小数点型のいくつか基本的な算術演算も実装します。 固定小数点の計算中に発生する丸めの誤差を制御するには、サポートされている操作を選択されています。

## <a name="inheritance-hierarchy"></a>継承階層

`COleCurrency`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

##  <a name="colecurrency"></a>  COleCurrency::COleCurrency

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
新しいにコピーされる通貨値`COleCurrency`オブジェクト。

*curSrc*<br/>
既存の`COleCurrency`新しいにコピーされるオブジェクト`COleCurrency`オブジェクト。

*varSrc*<br/>
既存の`VARIANT`データ構造 (可能性があります、`COleVariant`オブジェクト) を通貨値 (VT_CY) に変換し、新しいコピーを`COleCurrency`オブジェクト。

*nUnits*、 *nFractionalUnits*新しいにコピーされるユニットと (1/10,000 秒間) で値の小数部の一部を示します。`COleCurrency`オブジェクト。

### <a name="remarks"></a>Remarks

これらのコンス トラクターのすべてが新規作成`COleCurrency`オブジェクトが、指定した値に初期化します。 これらのコンス トラクターのそれぞれの簡単な説明に従います。 明記されない限り、新しいステータス`COleCurrency`項目が有効に設定されます。

- COleCurrency() コンストラクトを`COleCurrency`オブジェクトの 0 (ゼロ) に初期化します。

- COleCurrency (`cySrc`) を構築、`COleCurrency`オブジェクトから、[通貨](/windows/desktop/api/wtypes/ns-wtypes-tagcy)値。

- COleCurrency (`curSrc`) を構築、`COleCurrency`既存のオブジェクト`COleCurrency`オブジェクト。 新しいオブジェクトには、ソース オブジェクトと同じ状態があります。

- COleCurrency (`varSrc`) を構築、`COleCurrency`オブジェクト。 変換を試みます、[バリアント](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant)構造または`COleVariant`オブジェクト (VT_CY) の通貨値から。 新しい変換後の値がコピーされるこの変換が成功した場合は、`COleCurrency`オブジェクト。 値ではそうでない場合、`COleCurrency`オブジェクトがゼロ (0) とその状態を無効に設定します。

- `COleCurrency(`nUnits`, `nFractionalUnits`) Constructs a `COleCurrency' 指定した数値のコンポーネントからのオブジェクト。 小数部分の絶対値が 10,000 を超える場合は、ユニットに適切な調整が行われます。 部と小数部が符号付き long 値が指定されているに注意してください。

詳細については、次を参照してください。、[通貨](/windows/desktop/api/wtypes/ns-wtypes-tagcy)と[バリアント](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant)Windows SDK 内のエントリ。

### <a name="example"></a>例

次の例では、パラメーターの 0 と 2 つのパラメーターのコンス トラクターの効果を示します。

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

##  <a name="format"></a>  COleCurrency::Format

通貨値の書式設定された表現を作成するには、このメンバー関数を呼び出します。

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
ロケールの設定のフラグを示します。 次のフラグのみでは、通貨に関連します。

- LOCALE_NOUSEROVERRIDE では、カスタム ユーザー設定ではなく、システムの既定のロケール設定を使用します。

*lcid*<br/>
変換に使用するロケール ID を示します。

### <a name="return-value"></a>戻り値

A`CString`通貨の書式設定された値を格納します。

### <a name="remarks"></a>Remarks

ローカルの言語仕様 (ロケール Id) を使用して値が書式設定します。 返される値では、通貨記号が含まれていません。 場合のこの状態`COleCurrency`オブジェクトが null、戻り値は空の文字列。 状態が有効でない場合、戻り値の文字列は、文字列リソース IDS_INVALID_CURRENCY によって指定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

##  <a name="getstatus"></a>  COleCurrency::GetStatus

状態 (有効) を取得するには、このメンバー関数を呼び出して、指定された`COleCurrency`オブジェクト。

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>戻り値

この状態を返します`COleCurrency`値。

### <a name="remarks"></a>Remarks

戻り値は、`CurrencyStatus`列挙型内で定義されている、`COleCurrency`クラス。

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

これらのステータス値の簡単な説明は、次の一覧を参照してください。

  - `COleCurrency::valid` 示しますこの`COleCurrency`オブジェクトが無効です。

  - `COleCurrency::invalid` 示しますこの`COleCurrency`オブジェクトは無効です。 つまり、その値誤りがあります。

  - `COleCurrency::null` 示しますこの`COleCurrency`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"使用しない場合の値、"C++ の NULL ではなくデータベースという意味で"null")。

状態、`COleCurrency`オブジェクトが無効で、次の場合。

- バリアントからその値が設定されている場合または`COleVariant`値を通貨値に変換できませんでした。

- このオブジェクトが、オーバーフローまたはアンダー フロー、代入演算操作中にたとえば場合、`+=`または **\* =** します。

- 場合は、無効な値は、このオブジェクトに割り当てられました。

- このオブジェクトの状態が明示的に設定を使用して無効に[SetStatus](#setstatus)します。

操作の詳細については、無効なメンバー関数は、次を参照して状態を設定する可能性があります。

- [COleCurrency](#colecurrency)

- [演算子 =](#operator_eq)

- [演算子 + -](#operator_plus_minus)

- [operator + = および =](#operator_plus_minus_eq)

- [演算子 */](#operator_star)

- [演算子 * = および =/](#operator_star_div_eq)

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

##  <a name="m_cur"></a>  COleCurrency::m_cur

基になる[通貨](/windows/desktop/api/wtypes/ns-wtypes-tagcy)この構造体`COleCurrency`オブジェクト。

### <a name="remarks"></a>Remarks

> [!CAUTION]
>  値を変更、`CURRENCY`これの値を変更する構造体のこの関数によって返されたポインターによってアクセス`COleCurrency`オブジェクト。 この状態は変更されません`COleCurrency`オブジェクト。

詳細については、次を参照してください。、[通貨](/windows/desktop/api/wtypes/ns-wtypes-tagcy)Windows SDK 内のエントリ。

##  <a name="m_status"></a>  COleCurrency::m_status

このデータ メンバーの型は、列挙型`CurrencyStatus`、内で定義されている、`COleCurrency`クラス。

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>Remarks

これらのステータス値の簡単な説明は、次の一覧を参照してください。

- `COleCurrency::valid` 示しますこの`COleCurrency`オブジェクトが無効です。

- `COleCurrency::invalid` 示しますこの`COleCurrency`オブジェクトは無効です。 つまり、その値誤りがあります。

- `COleCurrency::null` 示しますこの`COleCurrency`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"使用しない場合の値、"C++ の NULL ではなくデータベースという意味で"null")。

状態、`COleCurrency`オブジェクトが無効で、次の場合。

- バリアントからその値が設定されている場合または`COleVariant`値を通貨値に変換できませんでした。

- このオブジェクトが、オーバーフローまたはアンダー フロー、代入演算操作中にたとえば場合、`+=`または **\* =** します。

- 場合は、無効な値は、このオブジェクトに割り当てられました。

- このオブジェクトの状態が明示的に設定を使用して無効に[SetStatus](#setstatus)します。

操作の詳細については、無効なメンバー関数は、次を参照して状態を設定する可能性があります。

- [COleCurrency](#colecurrency)

- [演算子 =](#operator_eq)

- [演算子 +、-](#operator_plus_minus)

- [演算子 + =、=](#operator_plus_minus_eq)

- [演算子 */](#operator_star)

- [演算子 * =、/、=](#operator_star_div_eq)

> [!CAUTION]
>  このデータ メンバーは、高度なプログラミングに適しています。 インライン メンバー関数を使用する必要があります[GetStatus](#getstatus)と[SetStatus](#setstatus)します。 参照してください`SetStatus`の他の注意に関するこのデータ メンバーを明示的に設定します。

##  <a name="operator_eq"></a>  COleCurrency::operator =

これらのオーバー ロードされた代入演算子は、これに元の通貨値をコピー`COleCurrency`オブジェクト。

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
  const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>Remarks

各演算子の簡単な説明に従います。

- **operator = (** `cySrc` **)** 、`CURRENCY`値にコピーされます、`COleCurrency`オブジェクトとその状態が有効に設定されます。

- **演算子 = (** `curSrc` **)** 値および状態の既存のオペランドの`COleCurrency`にこのオブジェクトがコピーされた`COleCurrency`オブジェクト。

- **演算子 = (** *varSrc* **)** 場合の変換、`VARIANT`値 (または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト) の通貨 ( `VT_CY`) は、成功すると、変換後の値はこれにコピーするは`COleCurrency`オブジェクトとその状態が有効に設定されます。 変換が成功すると、ない場合の値、`COleCurrency`オブジェクトが 0 とその状態を無効に設定します。

詳細については、次を参照してください。、[通貨](/windows/desktop/api/wtypes/ns-wtypes-tagcy)と[バリアント](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant)Windows SDK 内のエントリ。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

##  <a name="operator_plus_minus"></a>  COleCurrency::operator +、-

これらの演算子を許可する加算および減算する 2 つに`COleCurrency`値と、互いの符号を変更する、`COleCurrency`値。

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>Remarks

結果の状態は null オペランドのいずれかの場合`COleCurrency`値は null です。

かどうか、算術演算オーバーフローすると、その結果、`COleCurrency`値が無効です。

オペランドが無効なと、その他の場合は、not null、結果の状態`COleCurrency`値が無効です。

有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

##  <a name="operator_plus_minus_eq"></a>  COleCurrency::operator + =、=

加算および減算することは、`COleCurrency`値との間この`COleCurrency`オブジェクト。

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>Remarks

この状態は null オペランドのいずれかがかどうか`COleCurrency`オブジェクトが設定を null にします。

かどうか、算術演算がオーバーフローした、この状態`COleCurrency`オブジェクトが設定されて無効にします。

オペランドのいずれかが有効ではないと、もう一方が null でない場合のこの状態`COleCurrency`オブジェクトが設定されて無効にします。

有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

##  <a name="operator_star"></a>  COleCurrency::operator\*と/

スケールすることは、`COleCurrency`の値を整数の値。

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>Remarks

場合、`COleCurrency`オペランドが null の場合、結果の状態`COleCurrency`値は null です。

算術演算がオーバーフローした場合、またはアンダー フロー、結果の状態`COleCurrency`値が無効です。

場合、`COleCurrency`オペランドが無効ですが、結果の状態`COleCurrency`値が無効です。

有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

##  <a name="operator_star_div_eq"></a>  COleCurrency::operator \*=、/、=

これは、拡張することは`COleCurrency`の値を整数の値。

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>Remarks

場合、`COleCurrency`オペランドが null の場合、この状態`COleCurrency`オブジェクトの設定を null にします。

かどうか、算術演算がオーバーフローした、この状態`COleCurrency`オブジェクトが設定されて無効にします。

場合、`COleCurrency`オペランドが無効ですが、この状態`COleCurrency`オブジェクトの設定を無効。

有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

##  <a name="operator_stream"></a>  COleCurrency::operator &lt; &lt;、 &gt;&gt;

診断ダンプとアーカイブへの格納をサポートしています。

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

抽出 ( **>>**) 演算子は、アーカイブからの読み込みをサポートしています。

##  <a name="operator_currency"></a>  COleCurrency::operator 通貨

返します、`CURRENCY`値がこれからコピー先の構造`COleCurrency`オブジェクト。

```
operator CURRENCY() const;
```

### <a name="remarks"></a>Remarks

##  <a name="parsecurrency"></a>  COleCurrency::ParseCurrency

通貨値を読み取るための文字列を解析するには、このメンバー関数を呼び出します。

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
解析するには null で終わる文字列へのポインター。

*dwFlags*<br/>
ロケールの設定、フラグのフラグを示します。

- LOCALE_NOUSEROVERRIDE では、カスタム ユーザー設定ではなく、システムの既定のロケール設定を使用します。

*lcid*<br/>
変換に使用するロケール ID を示します。

### <a name="return-value"></a>戻り値

以外の場合は 0 それ以外の場合、通貨の値の文字列を正常に変換されました。

### <a name="remarks"></a>Remarks

ソース文字列に数値以外の文字の意味は、ローカルの言語仕様 (ロケール Id) を使用します。

ロケール ID の値の詳細については、次を参照してください。[複数の言語をサポートしている](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages)します。

文字列が通貨に変換できた場合の値、この値`COleCurrency`オブジェクトが有効な値をその状態を設定します。

文字列が通貨値に変換できませんでしたか、この数値のオーバーフローがあった場合`COleCurrency`オブジェクトが無効です。

この関数がスローするメモリ割り当てエラーのため文字列の変換に失敗した場合、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)します。 その他のエラー状態の場合は、この関数がスローされます、 [COleException](../../mfc/reference/coleexception-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

##  <a name="colecurrency_relational_operators"></a>  COleCurrency 関係演算子

2 つの通貨値を比較し、条件が true である場合は 0 以外を返しますそれ以外の場合 0 を返します。

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
>  順序付けの操作の戻り値 ( **<**、 **\< =**、 **>**、 **>=**) オペランドのいずれかの状態が null または無効な場合は定義されません。 等値演算子 ( `==`、 `!=`) のオペランドの状態を検討してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

##  <a name="setcurrency"></a>  COleCurrency::SetCurrency

ユニットとこれの小数部を設定するには、このメンバー関数を呼び出す`COleCurrency`オブジェクト。

```
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>パラメーター

*nUnits*、 *nFractionalUnits*これにコピーされるユニットと (1/10,000 秒間) で値の小数部の一部を示します。`COleCurrency`オブジェクト。

### <a name="remarks"></a>Remarks

小数部分の絶対値が 10,000 を超える場合は、3 番目の例を次に示すように、単位、適切な調整が行われました。

部と小数部が符号付き long 値が指定されているに注意してください。 4 番目の次の例では、パラメーターにある符号が異なるときの動作を示しています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

##  <a name="setstatus"></a>  COleCurrency::SetStatus

この状態 (有効) を設定するには、このメンバー関数を呼び出す`COleCurrency`オブジェクト。

```
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>パラメーター

*status*<br/>
この新しいステータス`COleCurrency`オブジェクト。

### <a name="remarks"></a>Remarks

*状態*パラメーターの値によって定義されます、`CurrencyStatus`列挙型内で定義されている、`COleCurrency`クラス。

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

これらのステータス値の簡単な説明は、次の一覧を参照してください。

- `COleCurrency::valid` 示しますこの`COleCurrency`オブジェクトが無効です。

- `COleCurrency::invalid` 示しますこの`COleCurrency`オブジェクトは無効です。 つまり、その値誤りがあります。

- `COleCurrency::null` 示しますこの`COleCurrency`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"使用しない場合の値、"C++ の NULL ではなくデータベースという意味で"null")。

> [!CAUTION]
>  この関数は、高度なプログラミングに適しています。 この関数では、このオブジェクトのデータは変更されません。 Null または無効な状態を設定する最もよく使用されます。 なお、代入演算子 ([演算子 =](#operator_eq)) と[SetCurrency](#setcurrency)にソースの値に基づいて、オブジェクトの状態を設定しないでください。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleVariant クラス](../../mfc/reference/colevariant-class.md)
