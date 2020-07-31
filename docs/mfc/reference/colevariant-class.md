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
ms.openlocfilehash: 63bce4695e4e1142b797f24cfbbae71638177d04
ms.sourcegitcommit: 13f42c339fb7af935e3a93ac80e350d5e784c9f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "87470902"
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
|[COleVariant:: COleVariant](#colevariant)|`COleVariant` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleVariant:: Attach](#attach)|バリアントをに結び付け `COleVariant` ます。|
|[COleVariant:: ChangeType](#changetype)|このオブジェクトのバリアント型を変更 `COleVariant` します。|
|[COleVariant:: Clear](#clear)|この `COleVariant` オブジェクトをクリアします。|
|[COleVariant::D etach](#detach)|から VARIANT を切り離し、 `COleVariant` バリアントを返します。|
|[COleVariant:: GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|既存の variant 配列からバイト配列を取得します。|
|[COleVariant:: SetString](#setstring)|文字列を特定の型 (通常は ANSI) に設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[COleVariant:: operator LPCVARIANT](#operator_lpcvariant)|値をに変換 `COleVariant` `LPCVARIANT` します。|
|[COleVariant:: operator LPVARIANT](#operator_lpvariant)|オブジェクトをに変換 `COleVariant` `LPVARIANT` します。|
|[COleVariant:: operator =](#operator_eq)|値をコピー `COleVariant` します。|
|[COleVariant:: operator = =](#operator_eq_eq)|2つ `COleVariant` の値を比較します。|
|[COleVariant:: operator &lt; &lt; 、&gt;&gt;](#operator_lt_lt__gt_gt)|値を `COleVariant` `CArchive` またはに出力 `CDumpContext` し、 `COleVariant` からオブジェクトを入力し `CArchive` ます。|

## <a name="remarks"></a>Remarks

このデータ型は、OLE オートメーションで使用されます。 具体的には、 [Dispparams](/windows/win32/api/oaidl/ns-oaidl-dispparams)構造体には、VARIANT 構造体の配列へのポインターが含まれています。 `DISPPARAMS`構造体は、パラメーターを[IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)に渡すために使用されます。

> [!NOTE]
> このクラスは、 `VARIANT` 構造体から派生します。 これは、を呼び出すパラメーターでを渡すことができ、 `COleVariant` `VARIANT` 構造体のデータメンバー `VARIANT` がのアクセス可能なデータメンバーであることを意味し `COleVariant` ます。

2つの関連する MFC クラス[COleCurrency](../../mfc/reference/colecurrency-class.md)および[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)は、variant データ型 CURRENCY ( `VT_CY` ) と DATE () をカプセル化し `VT_DATE` ます。 クラスは、 `COleVariant` DAO クラスで広く使用されています。このクラスの一般的な使用方法については、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)や[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)などのクラスを参照してください。

詳細については、Windows SDK の「 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant)」、「 [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy-r1)」、「 [Dispparams](/windows/win32/api/oaidl/ns-oaidl-dispparams)」、および「 [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)エントリ」を参照してください。

クラスの詳細 `COleVariant` および ole オートメーションでの使用方法については、記事「[オートメーション](../../mfc/automation.md)」の「ole オートメーションでのパラメーターの引き渡し」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="colevariantattach"></a><a name="attach"></a>COleVariant:: Attach

この関数を呼び出して、指定した[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)オブジェクトを現在のオブジェクトにアタッチし `COleVariant` ます。

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>パラメーター

*varSrc*<br/>
`VARIANT`現在のオブジェクトにアタッチする既存のオブジェクト `COleVariant` 。

### <a name="remarks"></a>Remarks

この関数は、 *Varsrc*の VARTYPE を VT_EMPTY に設定します。

詳細については、Windows SDK の[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)と[varenum](/windows/win32/api/wtypes/ne-wtypes-varenum)のエントリを参照してください。

## <a name="colevariantcolevariant"></a><a name="colevariant"></a>COleVariant:: COleVariant

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
`COleVariant` `VARIANT` 新しいオブジェクトにコピーされる既存のまたはオブジェクト `COleVariant` 。

*.Psrc*<br/>
`VARIANT`新しいオブジェクトにコピーされるオブジェクトへのポインター `COleVariant` 。

*lpszSrc*<br/>
新しいオブジェクトにコピーされる null で終わる文字列 `COleVariant` 。

*vtSrc*<br/>
`VARTYPE`新しい `COleVariant` オブジェクトの。

*strSrc*<br/>
新しいオブジェクトにコピーされる[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト `COleVariant` 。

*nSrc*、 *lsrc*新しいオブジェクトにコピーする数値 `COleVariant` 。

*vtSrc*<br/>
`VARTYPE`新しい `COleVariant` オブジェクトの。

*curSrc*<br/>
新しいオブジェクトにコピーされる[COleCurrency](../../mfc/reference/colecurrency-class.md)オブジェクト `COleVariant` 。

*Fltsrc*、 *dblsrc*<br/>
新しい `COleVariant` オブジェクトにコピーされる数値。

*timeSrc*<br/>
新しいオブジェクトにコピーされる[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト `COleVariant` 。

*arrSrc*<br/>
新しいオブジェクトにコピーされる[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクト `COleVariant` 。

*lbSrc*<br/>
新しいオブジェクトにコピーされる[CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクト `COleVariant` 。

*pidl*<br/>
新しいオブジェクトにコピーされる[Itemidlist](/windows/win32/api/shtypes/ns-shtypes-itemidlist)構造体へのポインター `COleVariant` 。

### <a name="remarks"></a>Remarks

これらのすべてのコンストラクター `COleVariant` は、指定された値に初期化された新しいオブジェクトを作成します。 これらの各コンストラクターの簡単な説明を次に示します。

- **COleVariant ()**`COleVariant`VT_EMPTY 空のオブジェクトを作成します。

- **COleVariant (** *varsrc* **)** 既存 `VARIANT` のまたは `COleVariant` オブジェクトをコピーします。 バリアント型は保持されます。

- **COleVariant (** *psrc* **)** 既存 `VARIANT` のまたは `COleVariant` オブジェクトをコピーします。 バリアント型は保持されます。

- **COleVariant (** *lpszsrc* **)** 新しいオブジェクト VT_BSTR (UNICODE) に文字列をコピーします。

- **COleVariant (** *lpszsrc* **、** *vtsrc* **)** 新しいオブジェクトに文字列をコピーします。 *Vtsrc*のパラメーターには、VT_BSTR (UNICODE) または VT_BSTRT (ANSI) を指定する必要があります。

- **COleVariant (** *strsrc* **)** 新しいオブジェクト VT_BSTR (UNICODE) に文字列をコピーします。

- **COleVariant (** *nSrc* **)** 新しいオブジェクト VT_UI1 に8ビットの整数をコピーします。

- **COleVariant (** *nSrc* **、** *vtsrc* **)** 新しいオブジェクトに16ビット整数 (またはブール値) をコピーします。 パラメーター *Vtsrc*は VT_I2 または VT_BOOL である必要があります。

- **COleVariant (** *lsrc* **、** *vtsrc* **)** 32ビット整数 (または SCODE 値) を新しいオブジェクトにコピーします。 *Vtsrc*のパラメーターには、VT_I4、VT_ERROR、または VT_BOOL を指定する必要があります。

- **COleVariant (** *cursrc* **)**`COleCurrency`新しいオブジェクト VT_CY に値をコピーします。

- **COleVariant (** *fltsrc* **)** 新しいオブジェクト VT_R4 に32ビット浮動小数点値をコピーします。

- **COleVariant (** *dblsrc* **)** 新しいオブジェクト VT_R8 に64ビット浮動小数点値をコピーします。

- **COleVariant (** *timesrc* **)**`COleDateTime`新しいオブジェクト VT_DATE に値をコピーします。

- **COleVariant (** *arrsrc* **)** オブジェクトを `CByteArray` 新しいオブジェクト VT_EMPTY にコピーします。

- **COleVariant (** *lbSrc* **)** オブジェクトを `CLongBinary` 新しいオブジェクト VT_EMPTY にコピーします。

SCODE の詳細については、「Windows SDK の[COM エラーコードの構造](/windows/win32/com/structure-of-com-error-codes)」を参照してください。

## <a name="colevariantchangetype"></a><a name="changetype"></a>COleVariant:: ChangeType

このオブジェクトのバリアント値の型を変換 `COleVariant` します。

```cpp
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>パラメーター

*vartype*<br/>
このオブジェクトの VARTYPE `COleVariant` 。

*.Psrc*<br/>
変換する[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)オブジェクトへのポインター。 この値が NULL の場合、この `COleVariant` オブジェクトは変換のソースとして使用されます。

### <a name="remarks"></a>Remarks

詳細については、Windows SDK の「 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant)」、「 [varenum](/windows/win32/api/wtypes/ne-wtypes-varenum)」、および「 [VariantChangeType](/windows/win32/api/oleauto/nf-oleauto-variantchangetype) 」の各エントリを参照してください。

## <a name="colevariantclear"></a><a name="clear"></a>COleVariant:: Clear

`VARIANT` を消去します。

```cpp
void Clear();
```

### <a name="remarks"></a>Remarks

これにより、このオブジェクトの VARTYPE が VT_EMPTY に設定されます。 デストラクターは、 `COleVariant` この関数を呼び出します。

詳細については、 `VARIANT` Windows SDK の、VARTYPE、およびエントリを参照してください `VariantClear` 。

## <a name="colevariantdetach"></a><a name="detach"></a>COleVariant::D etach

基になる[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)オブジェクトをこのオブジェクトからデタッチし `COleVariant` ます。

```
VARIANT Detach();
```

### <a name="remarks"></a>Remarks

この関数は、このオブジェクトの VARTYPE を `COleVariant` VT_EMPTY に設定します。

> [!NOTE]
> を呼び出した後 `Detach` 、 `VariantClear` 結果の構造体に対してを呼び出すのは呼び出し元の責任です `VARIANT` 。

詳細については、Windows SDK の「 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant)」、「 [varenum](/windows/win32/api/wtypes/ne-wtypes-varenum)」、および「 [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) 」の各エントリを参照してください。

## <a name="colevariantgetbytearrayfromvariantarray"></a><a name="getbytearrayfromvariantarray"></a>COleVariant:: GetByteArrayFromVariantArray

既存の variant 配列からバイト配列を取得します。

```cpp
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>パラメーター

*メモリ*<br/>
既存の[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトへの参照。

## <a name="colevariantoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>COleVariant:: operator LPCVARIANT

このキャスト演算子は、 `VARIANT` このオブジェクトから値がコピーされる構造体を返し `COleVariant` ます。

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>Remarks

## <a name="colevariantoperator-lpvariant"></a><a name="operator_lpvariant"></a>COleVariant:: operator LPVARIANT

このキャスト演算子を呼び出して、このオブジェクトの基になる構造体にアクセスし `VARIANT` `COleVariant` ます。

```
operator LPVARIANT();
```

### <a name="remarks"></a>Remarks

> [!CAUTION]
> `VARIANT`この関数によって返されるポインターによってアクセスされる構造体の値を変更すると、このオブジェクトの値が変更され `COleVariant` ます。

## <a name="colevariantoperator-"></a><a name="operator_eq"></a>COleVariant:: operator =

これらのオーバーロードされた代入演算子は、source 値をこのオブジェクトにコピー `COleVariant` します。

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

### <a name="remarks"></a>Remarks

各演算子の簡単な説明を次に示します。

- **operator = (** *varsrc* **)** 既存のバリアントまたは `COleVariant` オブジェクトをこのオブジェクトにコピーします。

- **operator = (** *psrc* **)***Psrc*によってアクセスされるバリアントオブジェクトをこのオブジェクトにコピーします。

- **operator = (** *lpszsrc* **)** Null で終わる文字列をこのオブジェクトにコピーし、VARTYPE を VT_BSTR に設定します。

- **operator = (** *strsrc* **)**[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトをこのオブジェクトにコピーし、VARTYPE を VT_BSTR に設定します。

- **operator = (** *nSrc* **)** 8ビットまたは16ビットの整数値をこのオブジェクトにコピーします。 *NSrc*が8ビット値の場合、このの VARTYPE は VT_UI1 に設定されます。 *NSrc*が16ビット値で、このの VARTYPE が VT_BOOL 場合は、保持されます。それ以外の場合は、VT_I2 に設定されます。

- **operator = (** *lsrc* **)** 32ビット整数値をこのオブジェクトにコピーします。 このの VARTYPE が VT_ERROR 場合は、保持されます。それ以外の場合は、VT_I4 に設定されます。

- **operator = (** *cursrc* **)**[COleCurrency](../../mfc/reference/colecurrency-class.md)オブジェクトをこのオブジェクトにコピーし、VARTYPE を VT_CY に設定します。

- **operator = (** *fltsrc* **)** 32ビットの浮動小数点値をこのオブジェクトにコピーし、VARTYPE を VT_R4 に設定します。

- **operator = (** *dblsrc* **)** 64ビットの浮動小数点値をこのオブジェクトにコピーし、VARTYPE を VT_R8 に設定します。

- **operator = (** ? *rc* **)**[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトをこのオブジェクトにコピーし、VARTYPE を VT_DATE に設定します。

- **operator = (** *arrsrc* **)**[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトをこのオブジェクトにコピー `COleVariant` します。

- **operator = (** *lbSrc* **)**[CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクトをこのオブジェクトにコピー `COleVariant` します。

詳細については、Windows SDK の[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)と[varenum](/windows/win32/api/wtypes/ne-wtypes-varenum)のエントリを参照してください。

## <a name="colevariantoperator-"></a><a name="operator_eq_eq"></a>COleVariant:: operator = =

この演算子は、2つのバリアント型の値を比較し、等しい場合は0以外の値を返します。それ以外の場合は0です。

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

## <a name="colevariantoperator-ltlt-gtgt"></a><a name="operator_lt_lt__gt_gt"></a>COleVariant:: operator &lt; &lt; 、&gt;&gt;

値を `COleVariant` `CArchive` またはに出力 `CdumpContext` し、 `COleVariant` からオブジェクトを入力し `CArchive` ます。

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

### <a name="remarks"></a>Remarks

`COleVariant`挿入 ( **\<\<**) operator supports diagnostic dumping and storing to an archive. The extraction (**>>** ) 演算子は、アーカイブからの読み込みをサポートしています。

## <a name="colevariantsetstring"></a><a name="setstring"></a>COleVariant:: SetString

文字列を特定の型に設定します。

```cpp
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>パラメーター

*lpszSrc*<br/>
新しいオブジェクトにコピーされる null で終わる文字列 `COleVariant` 。

*VtSrc*<br/>
新しいオブジェクトの VARTYPE `COleVariant` 。

### <a name="remarks"></a>Remarks

*Vtsrc*のパラメーターには、VT_BSTR (UNICODE) または VT_BSTRT (ANSI) を指定する必要があります。 `SetString`は通常、文字列または文字列ポインターパラメーターを持つ[COleVariant:: COleVariant](#colevariant)コンストラクターの既定値で、VARTYPE が UNICODE ではないため、文字列を ANSI に設定するために使用されます。

UNICODE 以外のビルドの DAO レコードセットは、文字列が ANSI であることを想定しています。 したがって、オブジェクトを使用する DAO 関数の `COleVariant` 場合、UNICODE レコードセットを作成しない場合は、 *vtsrc*が VT_BSTRT (ansi) に設定されているコンストラクターの**COleVariant:: COleVariant (** *lpszsrc* **,** *vtsrc* **)** 形式のコンストラクターを使用するか、 `SetString` *vtsrc* VT_BSTRT set を使用して ansi 文字列を作成する必要があります。 たとえば、関数の `CDaoRecordset` [cdaorecordset:: Seek](../../mfc/reference/cdaorecordset-class.md#seek)と[cdaorecordset:: SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue)は、 `COleVariant` パラメーターとしてオブジェクトを使用します。 DAO レコードセットが UNICODE でない場合、これらのオブジェクトは ANSI である必要があります。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
