---
title: COleVariant クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41a93a89ed0ace158a0864d7987cafd838eed304
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853742"
---
# <a name="colevariant-class"></a>COleVariant クラス
カプセル化、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)データ型。  
  
## <a name="syntax"></a>構文  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleVariant::COleVariant](#colevariant)|`COleVariant` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleVariant::Attach](#attach)|バリアントをアタッチ、`COleVariant`します。|  
|[COleVariant::ChangeType](#changetype)|このバリアントの型を変更`COleVariant`オブジェクト。|  
|[COleVariant::Clear](#clear)|これをクリア`COleVariant`オブジェクト。|  
|[COleVariant::Detach](#detach)|バリアント型からのデタッチ、`COleVariant`と変化形を返します。|  
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|既存の配列からバイト配列を取得します。|  
|[COleVariant::SetString](#setstring)|文字列を ANSI では通常、特定の型に設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|変換を`COleVariant`値に、`LPCVARIANT`します。|  
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|変換を`COleVariant`オブジェクトを`LPVARIANT`します。|  
|[COleVariant::operator =](#operator_eq)|コピーを`COleVariant`値。|  
|[COleVariant::operator = =](#operator_eq_eq)|2 つ`COleVariant`値。|  
|[COleVariant::operator &lt; &lt;、 &gt;&gt;](#operator_lt_lt__gt_gt)|出力を`COleVariant`値を`CArchive`または`CDumpContext`入力し、`COleVariant`オブジェクトから`CArchive`します。|  
  
## <a name="remarks"></a>Remarks  
 このデータ型は、OLE オートメーションで使用されます。 具体的には、 [DISPPARAMS](http://msdn.microsoft.com/a16e5a21-766e-4287-b039-13429aa78f8b)構造体には、VARIANT 構造体の配列へのポインターが含まれています。 A`DISPPARAMS`構造を使用してパラメーターを渡す[idispatch::invoke](http://msdn.microsoft.com/964ade8e-9d8a-4d32-bd47-aa678912a54d)します。  
  
> [!NOTE]
>  このクラスから派生、`VARIANT`構造体。 つまり、渡すことができます、`COleVariant`を呼び出して取得するパラメーターで、`VARIANT`とのデータ メンバー、`VARIANT`構造体のアクセス可能なデータ メンバーである`COleVariant`します。  
  
 2 つの関連の MFC クラス[COleCurrency](../../mfc/reference/colecurrency-class.md)と[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)バリアント データ型の通貨をカプセル化 ( `VT_CY`) と日付 ( `VT_DATE`)。 `COleVariant`クラスは、DAO クラスで広く使用は、たとえば、このクラスの一般的な使用法のこれらのクラスを参照してください[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)と[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)します。  
  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)、[通貨](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e)、 [DISPPARAMS](http://msdn.microsoft.com/a16e5a21-766e-4287-b039-13429aa78f8b)、および[idispatch::invoke](http://msdn.microsoft.com/964ade8e-9d8a-4d32-bd47-aa678912a54d) Windows SDK 内のエントリ。  
  
 詳細については、`COleVariant`クラスと OLE オートメーションを使用して、記事の「を渡すパラメーターで OLE オートメーション」を参照してください[Automation](../../mfc/automation.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagVARIANT`  
  
 `COleVariant`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="attach"></a>  COleVariant::Attach  
 アタッチするには、この関数を呼び出して、指定された[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)を現在のオブジェクト`COleVariant`オブジェクト。  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *varSrc*  
 既存の`VARIANT`オブジェクトを現在アタッチされる`COleVariant`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この関数は、設定、 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)の*varSrc* VT_EMPTY にします。  
  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)と[VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) Windows SDK 内のエントリ。  
  
##  <a name="colevariant"></a>  COleVariant::COleVariant  
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
 *varSrc*  
 既存の`COleVariant`または`VARIANT`新しいにコピーされるオブジェクト`COleVariant`オブジェクト。  
  
 *pSrc*  
 ポインターを`VARIANT`新しいにコピーされるオブジェクト`COleVariant`オブジェクト。  
  
 *lpszSrc*  
 新しいにコピーされる null で終わる文字列`COleVariant`オブジェクト。  
  
 *vtSrc*  
 `VARTYPE`新しい`COleVariant`オブジェクト。  
  
 *strSrc*  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクト。  
  
 *nSrc*、 *lSrc*  
 新しい `COleVariant` オブジェクトにコピーされる数値。  
  
 *vtSrc*  
 `VARTYPE`新しい`COleVariant`オブジェクト。  
  
 *curSrc*  
 A [COleCurrency](../../mfc/reference/colecurrency-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクト。  
  
 *fltSrc*、 *dblSrc*  
 新しい `COleVariant` オブジェクトにコピーされる数値。  
  
 *timeSrc*  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクト。  
  
 *arrSrc*  
 A [CByteArray](../../mfc/reference/cbytearray-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクト。  
  
 *lbSrc*  
 A [CLongBinary](../../mfc/reference/clongbinary-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクト。  
  
 *pidl*  
 ポインターを[ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321)構造に新しいコピーされる`COleVariant`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 これらすべてのコンス トラクターが新規作成`COleVariant`オブジェクトが、指定した値に初期化します。 これらのコンス トラクターのそれぞれの簡単な説明に従います。  
  
- **COleVariant ()** 空を作成します。 `COleVariant` VT_EMPTY オブジェクト。  
  
- **COleVariant (** *varSrc* **)** 、既存のコピー`VARIANT`または`COleVariant`オブジェクト。 バリアント型は保持されます。  
  
- **COleVariant (** `pSrc` **)** 、既存のコピー`VARIANT`または`COleVariant`オブジェクト。 バリアント型は保持されます。  
  
- **COleVariant (** `lpszSrc` **)** VT_BSTR (UNICODE)、新しいオブジェクトに文字列をコピーします。  
  
- **COleVariant (** `lpszSrc` **、** `vtSrc` **)** 新しいオブジェクトに文字列をコピーします。 パラメーター *vtSrc* VT_BSTR (UNICODE) または VT_BSTRT (ANSI) にする必要があります。  
  
- **COleVariant (** `strSrc` **)** VT_BSTR (UNICODE)、新しいオブジェクトに文字列をコピーします。  
  
- **COleVariant (** `nSrc` **)** VT_UI1、新しいオブジェクトに 8 ビット整数をコピーします。  
  
- **COleVariant (** `nSrc` **、** `vtSrc` **)** 16 ビット整数 (またはブール値) を新しいオブジェクトにコピーします。 パラメーター *vtSrc* VT_I2 または VT_BOOL にする必要があります。  
  
- **COleVariant (** `lSrc` **、** `vtSrc` **)** 32 ビット整数 (または SCODE 値) を新しいオブジェクトにコピーします。 パラメーター *vtSrc* VT_I4、VT_BOOL、VT_ERROR、する必要があります。  
  
- **COleVariant (** `curSrc` **)** コピー、 `COleCurrency` VT_CY、新しいオブジェクトの値。  
  
- **COleVariant (** `fltSrc` **)** VT_R4、新しいオブジェクトに 32 ビット浮動小数点値をコピーします。  
  
- **COleVariant (** `dblSrc` **)** VT_R8、新しいオブジェクトに 64 ビット浮動小数点値をコピーします。  
  
- **COleVariant (** `timeSrc` **)** コピー、`COleDateTime`に新しいオブジェクトの VT_DATE 値。  
  
- **COleVariant (** `arrSrc` **)** コピー、`CByteArray`オブジェクトに新しいオブジェクト、VT_EMPTY します。  
  
- **COleVariant (** `lbSrc` **)** コピー、`CLongBinary`オブジェクトに新しいオブジェクト、VT_EMPTY します。  
  
 SCODE の詳細については、次を参照してください。 [COM エラー コードの構造](http://msdn.microsoft.com/library/windows/desktop/ms690088)Windows SDK に含まれています。  
  
##  <a name="changetype"></a>  COleVariant::ChangeType  
 このバリアントの値の型に変換します`COleVariant`オブジェクト。  
  
```  
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *vartype*  
 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)この`COleVariant`オブジェクト。  
  
 *pSrc*  
 ポインター、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)変換するオブジェクト。 この値が NULL の場合この`COleVariant`オブジェクトは、変換のソースとして使用されます。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)、 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)、および[VariantChangeType](http://msdn.microsoft.com/48a51e32-95d7-4eeb-8106-f5043ffa2fd1) Windows SDK 内のエントリ。  
  
##  <a name="clear"></a>  COleVariant::Clear  
 `VARIANT` を消去します。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarks  
 このオブジェクトの VARTYPE を VT_EMPTY に設定します。 `COleVariant`デストラクターは、この関数を呼び出します。  
  
 詳細については、次を参照してください。、 `VARIANT`、VARTYPE、および`VariantClear`Windows SDK 内のエントリ。  
  
##  <a name="detach"></a>  COleVariant::Detach  
 基になるデタッチ[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)これからオブジェクト`COleVariant`オブジェクト。  
  
```  
VARIANT Detach();
```  
  
### <a name="remarks"></a>Remarks  
 この関数は、設定、 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)この`COleVariant`VT_EMPTY するオブジェクト。  
  
> [!NOTE]
>  呼び出した後`Detach`を呼び出す呼び出し元の責任は`VariantClear`、結果として`VARIANT`構造体。  
  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)、 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)、および[VariantClear](http://msdn.microsoft.com/28741d81-8404-4f85-95d3-5c209ec13835) Windows SDK 内のエントリ。  
  
##  <a name="getbytearrayfromvariantarray"></a>  COleVariant::GetByteArrayFromVariantArray  
 既存の配列からバイト配列を取得します。  
  
```  
void GetByteArrayFromVariantArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>パラメーター  
 *バイト数*  
 既存への参照を[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクト。  
  
##  <a name="operator_lpcvariant"></a>  COleVariant::operator LPCVARIANT  
 このキャスト演算子、`VARIANT`値がこれからコピー先の構造`COleVariant`オブジェクト。  
  
```  
operator LPCVARIANT() const; 
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="operator_lpvariant"></a>  COleVariant::operator LPVARIANT  
 このキャスト演算子を呼び出す`VARIANT`この構造体`COleVariant`オブジェクト。  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Remarks  
  
> [!CAUTION]
>  値を変更、`VARIANT`これの値を変更する構造体のこの関数によって返されたポインターによってアクセス`COleVariant`オブジェクト。  
  
##  <a name="operator_eq"></a>  COleVariant::operator =  
 これらのオーバー ロードされた代入演算子はコピー元の値をこの`COleVariant`オブジェクト。  
  
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
 各演算子の簡単な説明に従います。  
  
- **operator = (** *varSrc * * *)** 既存のバリアントにコピーまたは`COleVariant`オブジェクトをこのオブジェクトにします。  
  
- **operator = (** `pSrc` **)** からアクセスされるバリアント オブジェクトのコピー *pSrc*このオブジェクトにします。  
  
- **operator = (** `lpszSrc` **)** このオブジェクトに null で終わる文字列をコピーし、VARTYPE を VT_BSTR に設定します。  
  
- **演算子 = (** `strSrc` **)** コピー、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)にこのオブジェクトと設定を VT_BSTR VARTYPE オブジェクト。  
  
- **operator = (** `nSrc` **)** 8 または 16 ビット整数値をこのオブジェクトにコピーします。 場合*nSrc* 8 ビット値は、この VARTYPE が VT_UI1 に設定されます。 場合*nSrc*は 16 ビットの値とこの VARTYPE、VT_BOOL、保持している以外の場合は、VT_I2 に設定されています。  
  
- **operator = (** `lSrc` **)** 32 ビット整数値をこのオブジェクトにコピーします。 この VARTYPE VT_ERROR がある場合は保持されます。それ以外の場合、VT_I4 に設定されます。  
  
- **演算子 = (** `curSrc` **)** コピー、 [COleCurrency](../../mfc/reference/colecurrency-class.md)オブジェクトをこのオブジェクトと VT_CY に VARTYPE を設定します。  
  
- **operator = (** `fltSrc` **)** 32 ビットの浮動小数点値をこのオブジェクトにコピーし、VT_R4、VARTYPE に設定します。  
  
- **operator = (** `dblSrc` **)** 64 ビットの浮動小数点値をこのオブジェクトにコピーし、VARTYPE を VT_R8 に設定します。  
  
- **演算子 = (** `dateSrc` **)** コピー、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトをこのオブジェクトと VT_DATE に VARTYPE を設定します。  
  
- **演算子 = (** `arrSrc` **)** コピー、 [CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトをこの`COleVariant`オブジェクト。  
  
- **演算子 = (** `lbSrc` **)** コピー、 [CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクトをこの`COleVariant`オブジェクト。  
  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)と[VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) Windows SDK 内のエントリ。  
  
##  <a name="operator_eq_eq"></a>  COleVariant::operator = =  
 この演算子は、2 つのバリアント値を比較し、それらが等しい場合は 0 以外の値を返しますそれ以外の場合 0 を返します。  
  
```  
BOOL operator==(const VARIANT& varSrc) const; 
BOOL operator==(LPCVARIANT pSrc) const;
```  
  
##  <a name="operator_lt_lt__gt_gt"></a>  COleVariant::operator &lt; &lt;、 &gt;&gt;  
 出力を`COleVariant`値を`CArchive`または`CdumpContext`入力し、`COleVariant`オブジェクトから`CArchive`します。  
  
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
 `COleVariant`挿入 ( **< \<**) 診断ダンプおよびアーカイブに格納する演算子をサポートしています。 抽出 ( **>>**) 演算子は、アーカイブからの読み込みをサポートしています。  
  
##  <a name="setstring"></a>  COleVariant::SetString  
 特定の型に文字列を設定します。  
  
```  
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszSrc*  
 新しいにコピーされる null で終わる文字列`COleVariant`オブジェクト。  
  
 *vtSrc*  
 新しい VARTYPE`COleVariant`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 パラメーター *vtSrc* VT_BSTR (UNICODE) または VT_BSTRT (ANSI) にする必要があります。 `SetString` 以降の既定の ANSI に文字列を設定に使用される通常、 [COleVariant::COleVariant](#colevariant)文字列または文字列ポインター パラメーターとしない VARTYPE でコンス トラクターは UNICODE です。  
  
 非 UNICODE ビルドの DAO レコード セットは、文字列を ansi を想定しています。 したがって、dao の場合に使用する関数`COleVariant`UNICODE レコード セットを作成していない場合、オブジェクトが使用する必要があります、 **COleVariant::COleVariant (** `lpszSrc` **、** `vtSrc` **)** 形式を持つコンス トラクターの*vtSrc* VT_BSTRT (ANSI) に設定または使用`SetString`で*vtSrc* ANSI 文字列の作成に VT_BSTRT に設定します。 たとえば、`CDaoRecordset`関数[CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek)と[たび](../../mfc/reference/cdaorecordset-class.md#setfieldvalue)使用`COleVariant`パラメーターとしてのオブジェクト。 これらのオブジェクトは、DAO レコード セットが UNICODE でない場合、ANSI にすることがあります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)



