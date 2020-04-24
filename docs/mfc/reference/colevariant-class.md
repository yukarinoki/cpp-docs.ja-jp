---
title: COleVariant クラス
ms.date: 11/04/2016
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
ms.openlocfilehash: 7d8abea39a9baa3f447ca0d5f3ab1183367d531f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753712"
---
# <a name="colevariant-class"></a>COleVariant クラス

[VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) データ型をカプセル化します。

## <a name="syntax"></a>構文

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を使用します。](#colevariant)|`COleVariant` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コレバリアント:アタッチ](#attach)|バリアントを にアタッチ`COleVariant`します。|
|[を変更します。](#changetype)|この`COleVariant`オブジェクトのバリアント型を変更します。|
|[コレバリアント::クリア](#clear)|この `COleVariant` オブジェクトをクリアします。|
|[コレバリアント::Dエタッハ](#detach)|バリアント型を a`COleVariant`からデタッチし、バリアント型を返します。|
|[を指定します。](#getbytearrayfromvariantarray)|既存のバリアント配列からバイト配列を取得します。|
|[文字列を設定します。](#setstring)|文字列を特定の型 (通常は ANSI) に設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[を指定します。](#operator_lpcvariant)|値を`COleVariant`に変換します`LPCVARIANT`。|
|[を使用します。](#operator_lpvariant)|オブジェクトを`COleVariant`に変換します`LPVARIANT`。|
|[変な値::演算子 =](#operator_eq)|値を`COleVariant`コピーします。|
|[==演算子](#operator_eq_eq)|2 つの`COleVariant`値を比較します。|
|[演算子 , &lt; &lt;&gt;&gt;](#operator_lt_lt__gt_gt)|`COleVariant`値を出力`CArchive`し`CDumpContext`、`COleVariant`オブジェクトを`CArchive`入力します。|

## <a name="remarks"></a>解説

このデータ型は、OLE オートメーションで使用されます。 具体的には[、DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-dispparams)構造体には、バリアント型の構造体の配列へのポインターが含まれています。 構造体`DISPPARAMS`を使用してパラメーターを渡します[。](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)

> [!NOTE]
> このクラスは、構造体から`VARIANT`派生します。 つまり`COleVariant`、 を呼び出`VARIANT`すパラメーターで、`VARIANT`構造体のデータ メンバーが アクセス可能なデータ メンバーであることを`COleVariant`示します。

2 つの関連する MFC クラス[COleCurrency](../../mfc/reference/colecurrency-class.md)と[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)は、バリアント型のデータ型 CURRENCY ( `VT_CY`) と日付 ( )`VT_DATE`をカプセル化します。 この`COleVariant`クラスは DAO クラスで広く使用されています。このクラスの一般的な使用方法については、これらのクラスを[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)参照[してください](../../mfc/reference/cdaorecordset-class.md)。

詳細については、[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)、[通貨](/windows/win32/api/wtypes/ns-wtypes-cy~r1)、[ディスイスパッシム](/windows/win32/api/oaidl/ns-oaidl-dispparams)、および[IDispatch::呼び出し](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)のエントリを参照してください。

OLE オートメーションでの`COleVariant`クラスとその使用方法の詳細については、[記事](../../mfc/automation.md)「オートメーション」の「OLE オートメーションでパラメータを渡す」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="colevariantattach"></a><a name="attach"></a>コレバリアント:アタッチ

指定された[VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant)オブジェクトを現在`COleVariant`のオブジェクトにアタッチします。

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>パラメーター

*varSrc*<br/>
現在`COleVariant`の`VARIANT`オブジェクトにアタッチされる既存のオブジェクト。

### <a name="remarks"></a>解説

この関数は *、varSrc*の VARTYPE をVT_EMPTYに設定します。

詳細については、Windows SDK の[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)および[VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)のエントリを参照してください。

## <a name="colevariantcolevariant"></a><a name="colevariant"></a>を使用します。

`COleVariant` オブジェクトを構築します。

```
COleVariant();
COleVariant(const VARIANT& varSrc);
COleVariant(const COleVariant& varSrc);
COleVariant(LPCVARIANT pSrc);
COleVariant(LPCTSTR lpszSrc);
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc);
COleVariant(CString& strSrc);
COleVariant(BYTE nSrc);
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2);
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4);
COleVariant(const COleCurrency& curSrc);
COleVariant(float fltSrc);
COleVariant(double dblSrc);
COleVariant(const COleDateTime& timeSrc);
COleVariant(const CByteArray& arrSrc);
COleVariant(const CLongBinary& lbSrc);
COleVariant(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>パラメーター

*varSrc*<br/>
新しい`COleVariant``COleVariant`オブジェクト`VARIANT`にコピーされる既存のオブジェクトまたはオブジェクト。

*pSrc*<br/>
新しい`VARIANT``COleVariant`オブジェクトにコピーされるオブジェクトへのポインター。

*lpszSrc*<br/>
新しい`COleVariant`オブジェクトにコピーされる null で終わる文字列。

*vtSrc*<br/>
新`VARTYPE`しい`COleVariant`オブジェクトの。

*ストルスク*<br/>
新しい`COleVariant`オブジェクトにコピーされる[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

*nSrc* *、lSrc*新しい`COleVariant`オブジェクトにコピーされる数値。

*vtSrc*<br/>
新`VARTYPE`しい`COleVariant`オブジェクトの。

*カースrc*<br/>
新しい`COleVariant`オブジェクトにコピーされる[COleCurrency](../../mfc/reference/colecurrency-class.md)オブジェクト。

*fltSrc* *,dblSrc*<br/>
新しい `COleVariant` オブジェクトにコピーされる数値。

*タイムスrc*<br/>
新しい`COleVariant`オブジェクトにコピーされる[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。

*アールスrc*<br/>
新しい`COleVariant`オブジェクトにコピーされる[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクト。

*lbSrc*<br/>
新しい`COleVariant`オブジェクトにコピーされる[CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクト。

*Pidl*<br/>
新しい`COleVariant`オブジェクトにコピーされる[ITEMIDLIST](/windows/win32/api/shtypes/ns-shtypes-itemidlist)構造体へのポインター。

### <a name="remarks"></a>解説

これらのコンストラクターは、すべて、`COleVariant`指定された値に初期化された新しいオブジェクトを作成します。 これらの各コンストラクターの簡単な説明を次に示します。

- **コレバリアント/** VT_EMPTY、空`COleVariant`のオブジェクトを作成します。

- **を指定します***varSrc***。** 既存`VARIANT`のオブジェクトまたは`COleVariant`オブジェクトをコピーします。 バリアント型は保持されます。

- **を指定します***pSrc***。** 既存`VARIANT`のオブジェクトまたは`COleVariant`オブジェクトをコピーします。 バリアント型は保持されます。

- **を指定します***lpszSrc***。** 文字列を新しいオブジェクトにコピーします。VT_BSTR (UNICODE)

- **を指定します***lpszSrc***,***vtSrc***。** 文字列を新しいオブジェクトにコピーします。 *vtSrc*パラメーターは、VT_BSTR (UNICODE) または VT_BSTRT (ANSI) でなければなりません。

- **を指定します***strSrc***。** 文字列を新しいオブジェクトにコピーします。VT_BSTR (UNICODE)

- **を指定します***nSrc***。** VT_UI1、新しいオブジェクトに 8 ビット整数をコピーします。

- **を指定します***nSrc***,***vtSrc***。** 16 ビットの整数 (またはブール値) を新しいオブジェクトにコピーします。 パラメーター *vtSrc*はVT_I2またはVT_BOOLでなければなりません。

- **を指定します***lSrc***,***vtSrc***。** 32 ビット整数 (または SCODE 値) を新しいオブジェクトにコピーします。 パラメーター *vtSrc*は、VT_I4、VT_ERROR、またはVT_BOOLでなければなりません。

- **を返す***curSrc* **(** 値を`COleCurrency`新しいオブジェクトにコピーVT_CY。

- **コレバリアント(** *fltSrc* **)** 32 ビット浮動小数点値を新しいオブジェクトにコピーVT_R4。

- **を使用します***dblSrc***。** 64 ビット浮動小数点値を新しいオブジェクトにコピーVT_R8。

- **を指定します***timeSrc***。** 値を`COleDateTime`新しいオブジェクトにコピーVT_DATE。

- **コレバリアント(** *arrSrc* **)** オブジェクトを`CByteArray`新しいオブジェクトにコピーします。VT_EMPTY。

- **コレバリアント(** *lbSrc* **)** オブジェクトを`CLongBinary`新しいオブジェクトにコピーします。VT_EMPTY。

SCODE の詳細については、Windows SDK[の COM エラー コードの構造](/windows/win32/com/structure-of-com-error-codes)を参照してください。

## <a name="colevariantchangetype"></a><a name="changetype"></a>を変更します。

この`COleVariant`オブジェクトのバリアント値の型を変換します。

```cpp
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>パラメーター

*Vartype*<br/>
この`COleVariant`オブジェクトの VARTYPE。

*pSrc*<br/>
変換する[バリアント型 (VARIANT)](/windows/win32/api/oaidl/ns-oaidl-variant)オブジェクトへのポインター。 この値が NULL の`COleVariant`場合、このオブジェクトは変換のソースとして使用されます。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[「バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)型[、VARENUM」、](/windows/win32/api/wtypes/ne-wtypes-varenum)および[「バリエーションの種類](/windows/win32/api/oleauto/nf-oleauto-variantchangetype)」の各エントリを参照してください。

## <a name="colevariantclear"></a><a name="clear"></a>コレバリアント::クリア

`VARIANT` を消去します。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

これにより、このオブジェクトの VARTYPE がVT_EMPTYに設定されます。 デス`COleVariant`トラクターはこの関数を呼び出します。

詳細については、Windows SDK`VARIANT`の「VARTYPE」および`VariantClear`「エントリ」を参照してください。

## <a name="colevariantdetach"></a><a name="detach"></a>コレバリアント::Dエタッハ

基になる[VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant)オブジェクトをこの`COleVariant`オブジェクトからデタッチします。

```
VARIANT Detach();
```

### <a name="remarks"></a>解説

この関数は、この`COleVariant`オブジェクトの VARTYPE をVT_EMPTYに設定します。

> [!NOTE]
> 呼び`Detach`出し後は、結果`VariantClear``VARIANT`の構造体を呼び出す必要があります。

詳細については、Windows SDK の[「バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)型[、VARENUM」、](/windows/win32/api/wtypes/ne-wtypes-varenum)および[「バリアントクリア](/windows/win32/api/oleauto/nf-oleauto-variantclear)」の各エントリを参照してください。

## <a name="colevariantgetbytearrayfromvariantarray"></a><a name="getbytearrayfromvariantarray"></a>を指定します。

既存のバリアント配列からバイト配列を取得します。

```cpp
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>パラメーター

*バイト*<br/>
既存の[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトへの参照。

## <a name="colevariantoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>を指定します。

このキャスト演算子は、`VARIANT`この`COleVariant`オブジェクトから値がコピーされた構造体を返します。

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>解説

## <a name="colevariantoperator-lpvariant"></a><a name="operator_lpvariant"></a>を使用します。

このキャスト演算子を呼び出して`VARIANT`、この`COleVariant`オブジェクトの基になる構造体にアクセスします。

```
operator LPVARIANT();
```

### <a name="remarks"></a>解説

> [!CAUTION]
> この関数によって返される`VARIANT`ポインターがアクセスする構造体の値を変更すると、この`COleVariant`オブジェクトの値が変更されます。

## <a name="colevariantoperator-"></a><a name="operator_eq"></a>変な値::演算子 =

これらのオーバーロードされた代入演算子は、ソース値をこの`COleVariant`オブジェクトにコピーします。

```
const COleVariant& operator=(const VARIANT& varSrc);
const COleVariant& operator=(LPCVARIANT pSrc);
const COleVariant& operator=(const COleVariant& varSrc);
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc);
const COleVariant& operator=(BYTE nSrc);
const COleVariant& operator=(short nSrc);
const COleVariant& operator=(long lSrc);
const COleVariant& operator=(const COleCurrency& curSrc);
const COleVariant& operator=(float fltSrc);
const COleVariant& operator=(double dblSrc);
const COleVariant& operator=(const COleDateTime& dateSrc);
const COleVariant& operator=(const CByteArray& arrSrc);
const COleVariant& operator=(const CLongBinary& lbSrc);
```

### <a name="remarks"></a>解説

各演算子の簡単な説明を次に示します。

- 演算子 *=(varSrc)* **)** **operator =(** 既存の VARIANT`COleVariant`またはオブジェクトをこのオブジェクトにコピーします。

- 演算子 *=(pSrc)* **)** **operator =(***pSrc*によってアクセスされた VARIANT オブジェクトをこのオブジェクトにコピーします。

- 演算子 *=(lpszSrc)* **)** **operator =(** NULL で終わる文字列をこのオブジェクトにコピーし、VARTYPE をVT_BSTRに設定します。

- 演算子 *=(strSrc)* **)** **operator =(**[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトをこのオブジェクトにコピーし、VARTYPE をVT_BSTRに設定します。

- 演算子 *=(nSrc)* **)** **operator =(** 8 ビットまたは 16 ビットの整数値をこのオブジェクトにコピーします。 *nSrc*が 8 ビット値の場合、この VARTYPE は VT_UI1 に設定されます。 *nSrc*が 16 ビット値で、この VARTYPE がVT_BOOL場合は、保持されます。それ以外の場合は、VT_I2に設定されます。

- 演算子 *=(lSrc)* **)** **operator =(** 32 ビット整数値をこのオブジェクトにコピーします。 この VARTYPE がVT_ERROR場合は、保持されます。それ以外の場合は、VT_I4に設定されます。

- 演算子 *=(curSrc)* **)** **operator =(** このオブジェクトに[COleCurrency](../../mfc/reference/colecurrency-class.md)オブジェクトをコピーし、varTYPE をVT_CYに設定します。

- 演算子 *=(fltSrc)* **)** **operator =(** 32 ビット浮動小数点値をこのオブジェクトにコピーし、VARTYPE をVT_R4に設定します。

- 演算子 *=(dblSrc)* **)** **operator =(** 64 ビット浮動小数点値をこのオブジェクトにコピーし、VARTYPE を VT_R8 に設定します。

- **演算子 =(***日付Src)* **)** このオブジェクトに[オブジェクト](../../atl-mfc-shared/reference/coledatetime-class.md)をコピーし、VT_DATEに VARTYPE を設定します。

- 演算子 *=(arrSrc)* **)** **operator =(** この`COleVariant`オブジェクトに[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトをコピーします。

- 演算子 *=(lbSrc)* **)** **operator =(** この`COleVariant`オブジェクトに[CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクトをコピーします。

詳細については、Windows SDK の[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)および[VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)のエントリを参照してください。

## <a name="colevariantoperator-"></a><a name="operator_eq_eq"></a>==演算子

この演算子は 2 つのバリアント値を比較し、等しい場合は 0 以外を返します。それ以外の場合は 0。

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

## <a name="colevariantoperator-ltlt-gtgt"></a><a name="operator_lt_lt__gt_gt"></a>演算子 , &lt; &lt;&gt;&gt;

`COleVariant`値を出力`CArchive`し`CdumpContext`、`COleVariant`オブジェクトを`CArchive`入力します。

```
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    OleVariant varSrc);

friend CArchive& AFXAPI operator<<(
    CArchive& ar,
    COleVariant varSrc);

friend CArchive& AFXAPI operator>>(
    CArchive& ar,
    COleVariant& varSrc);
```

### <a name="remarks"></a>解説

挿入`COleVariant`(**\<**) 演算子は、診断ダンプとアーカイブへの保管をサポートします。 抽出 (**>>**) 演算子は、アーカイブからのロードをサポートします。

## <a name="colevariantsetstring"></a><a name="setstring"></a>文字列を設定します。

文字列を特定の型に設定します。

```cpp
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>パラメーター

*lpszSrc*<br/>
新しい`COleVariant`オブジェクトにコピーされる null で終わる文字列。

*VtSrc*<br/>
新しい`COleVariant`オブジェクトの VARTYPE。

### <a name="remarks"></a>解説

*vtSrc*パラメーターは、VT_BSTR (UNICODE) または VT_BSTRT (ANSI) でなければなりません。 `SetString`文字列または文字列ポインター パラメーターを持つ[COleVariant::COleVariant](#colevariant)コンストラクターの既定値であり、VARTYPE が UNICODE ではないため、通常は文字列を ANSI に設定するために使用されます。

非 UNICODE ビルドの DAO レコードセットは、文字列が ANSI であると想定しています。 したがって、オブジェクトを使用`COleVariant`する DAO 関数の場合、UNICODE レコードセットを作成しない場合は、VT_BSTRT (ANSI) に設定されたコンストラクターの**COleVariant::COleVariant(** *lpszSrc* 、 *vtSrc* **)** 形式を使用`SetString`するか **,***、vtSrc*を使用して VT_BSTRT に設定して ANSI 文字列を作成する必要があります。 *vtSrc* たとえば、`CDaoRecordset`関数[CDaoRecordset::シーク](../../mfc/reference/cdaorecordset-class.md#seek)と[CDao レコードセット::セットフィールド値](../../mfc/reference/cdaorecordset-class.md#setfieldvalue)は、パラメーターとしてオブジェクトを使用`COleVariant`します。 DAO レコードセットが UNICODE でない場合、これらのオブジェクトは ANSI である必要があります。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
