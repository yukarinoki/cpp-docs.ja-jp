---
title: COleVariant クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 0966aa28595d5384fd6877f30452d3cc24853f29
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079210"
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
|[COleVariant::Attach](#attach)|アタッチ、**バリアント**を`COleVariant`です。|  
|[COleVariant::ChangeType](#changetype)|このバリアント型を変更する`COleVariant`オブジェクト。|  
|[COleVariant::Clear](#clear)|これを消去`COleVariant`オブジェクト。|  
|[COleVariant::Detach](#detach)|デタッチ、**バリアント**から、`COleVariant`を返します、**バリアント**です。|  
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|既存のバリアント配列からバイト配列を取得します。|  
|[COleVariant::SetString](#setstring)|文字列を ANSI では通常、特定の種類に設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|変換、`COleVariant`値に、`LPCVARIANT`です。|  
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|変換、`COleVariant`オブジェクトに、`LPVARIANT`です。|  
|[COleVariant::operator =](#operator_eq)|コピー、`COleVariant`値。|  
|[COleVariant::operator = =](#operator_eq_eq)|比較する 2 つ`COleVariant`値。|  
|[COleVariant::operator &lt; &lt;、 &gt;&gt;](#operator_lt_lt__gt_gt)|出力、`COleVariant`値`CArchive`または`CDumpContext`を入力し、`COleVariant`オブジェクトから`CArchive`です。|  
  
## <a name="remarks"></a>Remarks  
 このデータ型は OLE オートメーションで使用されます。 具体的には、 [DISPPARAMS](http://msdn.microsoft.com/a16e5a21-766e-4287-b039-13429aa78f8b)構造体には配列へのポインターが含まれています**バリアント**構造体。 A **DISPPARAMS**構造を使用してパラメーターを渡す[idispatch::invoke](http://msdn.microsoft.com/964ade8e-9d8a-4d32-bd47-aa678912a54d)です。  
  
> [!NOTE]
>  このクラスから派生、**バリアント**構造体。 つまり、渡すことができます、`COleVariant`のパラメーターです、**バリアント**こととのデータ メンバーの**バリアント**構造のアクセス可能なデータ メンバーである`COleVariant`です。  
  
 2 つの関連の MFC クラス[COleCurrency](../../mfc/reference/colecurrency-class.md)と[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)バリアント データ型をカプセル化**通貨**( `VT_CY`) および**日付**( `VT_DATE`). `COleVariant` DAO クラスでクラスは、広範囲に使用されます。 たとえば、このクラスの一般的な使用法のこれらのクラスを参照してください[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)と[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)です。  
  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)、[通貨](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e)、 [DISPPARAMS](http://msdn.microsoft.com/a16e5a21-766e-4287-b039-13429aa78f8b)、および[idispatch::invoke](http://msdn.microsoft.com/964ade8e-9d8a-4d32-bd47-aa678912a54d) Windows SDK 内のエントリ。  
  
 詳細については、`COleVariant`クラスおよび OLE オートメーションでの使用の資料に「パラメーターで OLE オートメーションの受け渡し」を参照してください[オートメーション](../../mfc/automation.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagVARIANT`  
  
 `COleVariant`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="attach"></a>  COleVariant::Attach  
 アタッチするには、この関数を呼び出して、指定された[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)現在オブジェクト`COleVariant`オブジェクト。  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *varSrc*  
 既存の**バリアント**に現在アタッチされているオブジェクト`COleVariant`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この関数は、設定、 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)の*varSrc*に`VT_EMPTY`です。  
  
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
 既存の`COleVariant`または**バリアント**新しいにコピーされるオブジェクト`COleVariant`オブジェクト。  
  
 *pSrc*  
 ポインター、**バリアント**新しいにコピーされるオブジェクト`COleVariant`オブジェクト。  
  
 *lpszSrc*  
 Null で終わる文字列にコピーされる新しい`COleVariant`オブジェクト。  
  
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
 ポインター、 [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321)新しいにコピーされる構造`COleVariant`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 これらすべてのコンストラクタが新規作成`COleVariant`オブジェクトが、指定した値に初期化します。 これらのコンス トラクターのそれぞれの簡単な説明に従います。  
  
- **COleVariant ()** 、空を作成`COleVariant`オブジェクト、`VT_EMPTY`です。  
  
- **COleVariant (** *varSrc* **)** 、既存のコピー**バリアント**または`COleVariant`オブジェクト。 バリアント型は保持されます。  
  
- **COleVariant (** `pSrc` **)** 、既存のコピー**バリアント**または`COleVariant`オブジェクト。 バリアント型は保持されます。  
  
- **COleVariant (** `lpszSrc` **)** 、新しいオブジェクトに文字列をコピー `VT_BSTR` (UNICODE)。  
  
- **COleVariant (** `lpszSrc` **、** `vtSrc` **)** 新しいオブジェクトに文字列をコピーします。 パラメーター *vtSrc*する必要があります`VT_BSTR`(UNICODE) または`VT_BSTRT`(ANSI)。  
  
- **COleVariant (** `strSrc` **)** 、新しいオブジェクトに文字列をコピー **VT_BSTR** (UNICODE)。  
  
- **COleVariant (** `nSrc` **)** を 8 ビット整数を新しいオブジェクトにコピー`VT_UI1`です。  
  
- **COleVariant (** `nSrc` **、** `vtSrc` **)** 16 ビット整数 (またはブール値) を新しいオブジェクトにコピーします。 パラメーター *vtSrc*する必要があります`VT_I2`または`VT_BOOL`です。  
  
- **COleVariant (** `lSrc` **、** `vtSrc` **)** 32 ビット整数のコピー (または`SCODE`値) が新しいオブジェクトにします。 パラメーター *vtSrc*する必要があります`VT_I4`、 `VT_ERROR`、または`VT_BOOL`です。  
  
- **COleVariant (** `curSrc` **)** コピー、 **COleCurrency**が新しいオブジェクトに値`VT_CY`です。  
  
- **COleVariant (** `fltSrc` **)** 32 ビット浮動小数点値を新しいオブジェクトにコピー`VT_R4`です。  
  
- **COleVariant (** `dblSrc` **)** 64 ビット浮動小数点値を新しいオブジェクトにコピー`VT_R8`です。  
  
- **COleVariant (** `timeSrc` **)** コピー、`COleDateTime`が新しいオブジェクトに値`VT_DATE`です。  
  
- **COleVariant (** `arrSrc` **)** コピー、`CByteArray`オブジェクトに新しいオブジェクト、`VT_EMPTY`です。  
  
- **COleVariant (** `lbSrc` **)** コピー、`CLongBinary`オブジェクトに新しいオブジェクト、`VT_EMPTY`です。  
  
 詳細については`SCODE`を参照してください[COM エラー コードの構造体](http://msdn.microsoft.com/library/windows/desktop/ms690088)Windows SDK に含まれています。  
  
##  <a name="changetype"></a>  COleVariant::ChangeType  
 このバリアント型の値の型を変換`COleVariant`オブジェクト。  
  
```  
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *vartype*  
 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)この`COleVariant`オブジェクト。  
  
 *pSrc*  
 ポインター、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)変換するオブジェクト。 この値が場合**NULL**、この`COleVariant`オブジェクトは、変換のソースとして使用します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)、 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)、および[VariantChangeType](http://msdn.microsoft.com/48a51e32-95d7-4eeb-8106-f5043ffa2fd1) Windows SDK 内のエントリ。  
  
##  <a name="clear"></a>  COleVariant::Clear  
 消去、**バリアント**です。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarks  
 これにより設定、 **VARTYPE**をこのオブジェクトの`VT_EMPTY`します。 `COleVariant`デストラクターはこの関数を呼び出します。  
  
 詳細については、次を参照してください。、 `VARIANT`、 `VARTYPE`、および`VariantClear`Windows SDK 内のエントリ。  
  
##  <a name="detach"></a>  COleVariant::Detach  
 基になるデタッチ[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)オブジェクトからこの`COleVariant`オブジェクト。  
  
```  
VARIANT Detach();
```  
  
### <a name="remarks"></a>Remarks  
 この関数は、設定、 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)この`COleVariant`オブジェクトを`VT_EMPTY`です。  
  
> [!NOTE]
>  呼び出した後`Detach`を呼び出して、呼び出し元の責任である**VariantClear**で、結果として得られる**バリアント**構造体。  
  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)、 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4)、および[VariantClear](http://msdn.microsoft.com/28741d81-8404-4f85-95d3-5c209ec13835) Windows SDK 内のエントリ。  
  
##  <a name="getbytearrayfromvariantarray"></a>  COleVariant::GetByteArrayFromVariantArray  
 既存のバリアント配列からバイト配列を取得します。  
  
```  
void GetByteArrayFromVariantArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>パラメーター  
 *バイト数*  
 既存への参照を[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクト。  
  
##  <a name="operator_lpcvariant"></a>  COleVariant::operator LPCVARIANT  
 このキャスト演算子を返します、`VARIANT`構造体の値がこれからコピー`COleVariant`オブジェクト。  
  
```  
operator LPCVARIANT() const; 
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="operator_lpvariant"></a>  COleVariant::operator LPVARIANT  
 基になるにアクセスするには、このキャスト演算子を呼び出す`VARIANT`この構造体`COleVariant`オブジェクト。  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Remarks  
  
> [!CAUTION]
>  値を変更、**バリアント**の値を変更する構造体がこの関数によって返されるポインターは、アクセス`COleVariant`オブジェクト。  
  
##  <a name="operator_eq"></a>  COleVariant::operator =  
 これらのオーバー ロードされた代入演算子は、これに元の値をコピー`COleVariant`オブジェクト。  
  
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
  
- **演算子 = = (** *varSrc * * *)**、既存のコピー**バリアント**または`COleVariant`オブジェクトをこのオブジェクトにします。  
  
- **演算子 = = (** `pSrc` **)** コピー、**バリアント**によってアクセスされるオブジェクト*pSrc*このオブジェクトにします。  
  
- **演算子 = = (** `lpszSrc` **)** このオブジェクトに null で終わる文字列をコピーし、設定、 **VARTYPE**に`VT_BSTR`です。  
  
- **演算子 = = (** `strSrc` **)** コピー、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトをこのオブジェクトと設定、 **VARTYPE**に`VT_BSTR`です。  
  
- **演算子 = = (** `nSrc` **)** 8 ビットまたは 16 ビット整数値をこのオブジェクトにコピーします。 場合*nSrc* 、8 ビット値には、 **VARTYPE**このに設定されている`VT_UI1`です。 場合*nSrc* 16 ビット値は、および**VARTYPE**このが`VT_BOOL`、それ以外の保持に設定されている`VT_I2`です。  
  
- **演算子 = = (** `lSrc` **)** 32 ビット整数値をこのオブジェクトにコピーします。 場合、 **VARTYPE**このが`VT_ERROR`、それ以外の保持に設定されている`VT_I4`です。  
  
- **演算子 = = (** `curSrc` **)** コピー、 [COleCurrency](../../mfc/reference/colecurrency-class.md)オブジェクトをこのオブジェクトと設定、 **VARTYPE**に`VT_CY`です。  
  
- **演算子 = = (** `fltSrc` **)** 32 ビット浮動小数点値をこのオブジェクトにコピーし、設定、 **VARTYPE**に`VT_R4`です。  
  
- **演算子 = = (** `dblSrc` **)** 64 ビットの浮動小数点値をこのオブジェクトにコピーし、設定、 **VARTYPE**に`VT_R8`です。  
  
- **演算子 = = (** `dateSrc` **)** コピー、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトをこのオブジェクトと設定、 **VARTYPE**に`VT_DATE`です。  
  
- **演算子 = = (** `arrSrc` **)** コピー、 [CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトをこの`COleVariant`オブジェクト。  
  
- **演算子 = = (** `lbSrc` **)** コピー、 [CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクトをこの`COleVariant`オブジェクト。  
  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)と[VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) Windows SDK 内のエントリ。  
  
##  <a name="operator_eq_eq"></a>  COleVariant::operator = =  
 この演算子は、2 つのバリアント値を比較し、それらが等しい場合は 0 以外を返しますそれ以外の場合 0 を返します。  
  
```  
BOOL operator==(const VARIANT& varSrc) const; 
BOOL operator==(LPCVARIANT pSrc) const;
```  
  
##  <a name="operator_lt_lt__gt_gt"></a>  COleVariant::operator &lt; &lt;、 &gt;&gt;  
 出力、`COleVariant`値`CArchive`または**CdumpContext**を入力し、`COleVariant`オブジェクトから`CArchive`です。  
  
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
 `COleVariant`挿入 ( **< \<**) 診断ダンプとアーカイブを格納する演算子をサポートしています。 抽出 ( **>>**) 演算子は、アーカイブからの読み込みをサポートしています。  
  
##  <a name="setstring"></a>  COleVariant::SetString  
 特定の種類を文字列を設定します。  
  
```  
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszSrc*  
 Null で終わる文字列にコピーされる新しい`COleVariant`オブジェクト。  
  
 *vtSrc*  
 **VARTYPE**新しい`COleVariant`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 パラメーター *vtSrc*する必要があります`VT_BSTR`(UNICODE) または`VT_BSTRT`(ANSI)。 `SetString` 通常は文字列を ANSI に設定の既定のために使用、 [COleVariant::COleVariant](#colevariant)文字列または文字列ポインター パラメーター、およびなしのコンス トラクター **VARTYPE**は UNICODE です。  
  
 UNICODE 以外のビルドにおける DAO レコード セットには、ansi 文字列が必要です。 したがって、dao を使用するを関数`COleVariant`UNICODE レコード セットを作成していない場合は、オブジェクト、行う必要があります、 **COleVariant::COleVariant (** `lpszSrc` **、** `vtSrc` **)** 形式を持つコンス トラクターの*vtSrc*に設定`VT_BSTRT`(ANSI) を使用または`SetString`で*vtSrc*に設定`VT_BSTRT`ANSI 文字列の作成にします。 たとえば、`CDaoRecordset`関数[CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek)と[たび](../../mfc/reference/cdaorecordset-class.md#setfieldvalue)使用`COleVariant`パラメーターとしてオブジェクト。 DAO レコード セットが UNICODE でない場合、これらのオブジェクトは ANSI をする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)



