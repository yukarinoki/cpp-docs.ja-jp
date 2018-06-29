---
title: CPropExchange クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
dev_langs:
- C++
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fef6d3e30791d2a08a82d1b152cd849cd4ebf24b
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078409"
---
# <a name="cpropexchange-class"></a>CPropExchange クラス
OLE コントロールの永続性の実装をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|バイナリ ラージ オブジェクト (BLOB) のプロパティを交換します。|  
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|フォントのプロパティを交換します。|  
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|コントロールとファイルのプロパティを交換します。|  
|[CPropExchange::ExchangeProp](#exchangeprop)|すべての組み込み型のプロパティを交換します。|  
|[CPropExchange::ExchangeVersion](#exchangeversion)|OLE コントロールのバージョン番号を交換します。|  
|[CPropExchange::GetVersion](#getversion)|OLE コントロールのバージョン番号を取得します。|  
|[CPropExchange::IsAsynchronous](#isasynchronous)|プロパティの交換が非同期的に行うかどうかを判断します。|  
|[CPropExchange::IsLoading](#isloading)|プロパティがされているかどうかを示すから保存またはコントロールに読み込まれます。|  
  
## <a name="remarks"></a>Remarks  
 `CPropExchange` 基本クラスはありません。  
  
 プロパティの exchange の方向とコンテキストを確立します。  
  
 永続化とは、コントロールの状態については、そのプロパティ、コントロール自体と、メディア間で表される通常の交換です。  
  
 派生したオブジェクトを構築するために、フレームワーク`CPropExchange`から読み込まれる OLE コントロールのプロパティができたことを通知には、または記憶域の永続的なをするストアド プロシージャです。  
  
 フレームワークがこれにポインターを渡します`CPropExchange`オブジェクトをコントロールの`DoPropExchange`関数。 目的のコントロールのコントロールのスターター ファイルを作成するウィザードを使用した場合`DoPropExchange`関数呼び出し`COleControl::DoPropExchange`です。 基本クラスのバージョンを交換コントロールのストック プロパティです。コントロールに追加した exchange プロパティに、派生クラスのバージョンを変更します。  
  
 `CPropExchange` コントロールのプロパティをシリアル化または負荷またはコントロールの作成時にコントロールのプロパティを初期化するために使用します。 `ExchangeProp`と`ExchangeFontProp`のメンバー関数は`CPropExchange`にプロパティを格納し、別のメディアからそれらを読み込むことができます。  
  
 使用する方法についての`CPropExchange`、記事を参照して[MFC ActiveX コントロール: プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CPropExchange`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxctl.h  
  
##  <a name="exchangeblobprop"></a>  CPropExchange::ExchangeBlobProp  
 バイナリ ラージ オブジェクト (BLOB) データを格納するプロパティをシリアル化します。  
  
```  
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,  
    HGLOBAL* phBlob,  
    HGLOBAL hBlobDefault = NULL) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pszPropName*  
 交換されるプロパティの名前。  
  
 *phBlob*  
 プロパティを格納する場所を指す変数へのポインター (変数は、通常、クラスのメンバー)。  
  
 *hBlobDefault*  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 プロパティの値を読み取りに、必要に応じて、によって参照される変数に書き込み*phBlob*です。 場合*hBlobDefault*を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化が失敗したときに使用されます。  
  
 関数は、 **CArchivePropExchange::ExchangeBlobProp**、 **CResetPropExchange::ExchangeBlobProp**、および**CPropsetPropExchange::ExchangeBlobProp**オーバーライドこの純粋仮想関数。  
  
##  <a name="exchangefontprop"></a>  CPropExchange::ExchangeFontProp  
 記憶域メディアとコントロールの間でのフォント プロパティを交換します。  
  
```  
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,  
    CFontHolder& font,  
    const FONTDESC* pFontDesc,  
    LPFONTDISP pFontDispAmbient) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pszPropName*  
 交換されるプロパティの名前。  
  
 *フォント*  
 参照、 [CFontHolder](../../mfc/reference/cfontholder-class.md)フォント プロパティを含むオブジェクト。  
  
 *pFontDesc*  
 ポインター、 [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782) font プロパティの既定の状態を初期化するための値を含む構造体と*pFontDispAmbient*は**NULL**です。  
  
 *pFontDispAmbient*  
 ポインター、**この**font プロパティの既定の状態を初期化するために使用するフォントのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 フォントのプロパティは、コントロールに、メディアから読み込まれるは、フォントの特性は、メディアから取得されます、`CFontHolder`によって参照されるオブジェクト*フォント*で初期化されます。 Font プロパティが格納される場合のフォント オブジェクト内の特性がメディアに書き込まれます。  
  
 関数は、 **CArchivePropExchange::ExchangeFontProp**、 **CResetPropExchange::ExchangeFontProp**、および**CPropsetPropExchange::ExchangeFontProp**オーバーライドこの純粋仮想関数。  
  
##  <a name="exchangepersistentprop"></a>  CPropExchange::ExchangePersistentProp  
 コントロールとファイルのプロパティを交換します。  
  
```  
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,  
    LPUNKNOWN* ppUnk,  
    REFIID iid,  
    LPUNKNOWN pUnkDefault) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pszPropName*  
 交換されるプロパティの名前。  
  
 *ppUnk*  
 プロパティへのポインターを含む変数を指すポインター **IUnknown**インターフェイス (この変数は、通常、クラスのメンバー)。  
  
 *iid*  
 コントロールを使用するプロパティのインターフェイスのインターフェイス ID です。  
  
 *pUnkDefault*  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 プロパティは、コントロールに、ファイルから読み込まれるが場合、プロパティが作成され、ファイルを使用して初期化します。 プロパティが格納されている場合、その値は、ファイルに書き込まれます。  
  
 関数は、 **CArchivePropExchange::ExchangePersistentProp**、 **CResetPropExchange::ExchangePersistentProp**、および**CPropsetPropExchange::ExchangePersistentProp**純粋仮想関数をオーバーライドします。  
  
##  <a name="exchangeprop"></a>  CPropExchange::ExchangeProp  
 記憶域メディアとコントロールの間でプロパティを交換します。  
  
```  
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,  
    VARTYPE vtProp,  
    void* pvProp,  
    const void* pvDefault = NULL) = 0 ;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pszPropName*  
 交換されるプロパティの名前。  
  
 *vtProp*  
 交換されるプロパティの型を指定する記号です。 指定できる値は次のとおりです。  
  
|シンボル|プロパティの型|  
|------------|-------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_BOOL`|**BOOL**|  
|`VT_BSTR`|`CString`|  
|`VT_CY`|**CY**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
  
 *pvProp*  
 プロパティの値へのポインター。  
  
 *pvDefault*  
 プロパティの既定値へのポインター。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 プロパティが読み込まれるとき、メディアからのコントロールに、プロパティの値はメディアから取得されによって指されるオブジェクトに格納されている*pvProp*です。 プロパティは、メディアに格納される場合、オブジェクトの値を指す*pvProp*はメディアに書き込まれます。  
  
 関数は、 **CArchivePropExchange::ExchangeProp**、 **CResetPropExchange::ExchangeProp**、および**CPropsetPropExchange::ExchangeProp**この純粋なオーバーライド仮想関数。  
  
##  <a name="exchangeversion"></a>  CPropExchange::ExchangeVersion  
 バージョン番号の永続化を処理するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,  
    DWORD dwVersionDefault,  
    BOOL bConvert);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwVersionLoaded*  
 読み込まれている永続的なデータのバージョン番号が格納される変数への参照。  
  
 *dwVersionDefault*  
 コントロールの現在のバージョン番号。  
  
 *bConvert*  
 現在のバージョンに永続的なデータを変換または読み込まれたものと同じバージョンのまま保持するかどうかを示します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合は 0 です。  
  
##  <a name="getversion"></a>  CPropExchange::GetVersion  
 コントロールのバージョン番号を取得するには、この関数を呼び出します。  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのバージョン番号。  
  
##  <a name="isasynchronous"></a>  CPropExchange::IsAsynchronous  
 プロパティの交換が非同期的に行うかどうかを判断します。  
  
```  
BOOL IsAsynchronous();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティは TRUE を返しますが FALSE では非同期、交換されます。  
  
##  <a name="isloading"></a>  CPropExchange::IsLoading  
 プロパティがされているかどうかを判断するには、この関数を呼び出すコントロールに読み込みまたはそこから保存します。  
  
```  
BOOL IsLoading();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティが読み込まれる場合は 0 以外。それ以外の場合 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)



