---
title: CFontHolder クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
dev_langs:
- C++
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba6e85500f87c1ea88c46418d1f6b698a2d10976
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954118"
---
# <a name="cfontholder-class"></a>CFontHolder クラス
ストック フォント プロパティを実装し、Windows のフォント オブジェクトと `IFont` インターフェイスの機能をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFontHolder  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFontHolder::CFontHolder](#cfontholder)|`CFontHolder` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFontHolder::GetDisplayString](#getdisplaystring)|コンテナーのプロパティ ブラウザーに表示される文字列を取得します。|  
|[CFontHolder::GetFontDispatch](#getfontdispatch)|フォントを返します`IDispatch`インターフェイスです。|  
|[CFontHolder::GetFontHandle](#getfonthandle)|Windows フォントにハンドルを返します。|  
|[CFontHolder::InitializeFont](#initializefont)|初期化、`CFontHolder`オブジェクト。|  
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|関連するフォントの情報を取得します。|  
|[CFontHolder::ReleaseFont](#releasefont)|切断、`CFontHolder`オブジェクトから、`IFont`と`IFontNotification`インターフェイスです。|  
|[CFontHolder::Select](#select)|デバイス コンテキストにフォント リソースを選択します。|  
|[CFontHolder::SetFont](#setfont)|接続、`CFontHolder`オブジェクトを`IFont`インターフェイスです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFontHolder::m_pFont](#m_pfont)|ポインター、`CFontHolder`オブジェクトの`IFont`インターフェイスです。|  
  
## <a name="remarks"></a>Remarks  
 `CFontHolder` 基本クラスはありません。  
  
 このクラスを使用すると、コントロールのカスタム フォントのプロパティを実装します。 このようなプロパティを作成する方法については、記事を参照してください。 [ActiveX コントロール: フォントの使用](../../mfc/mfc-activex-controls-using-fonts.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CFontHolder`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxctl.h  
  
##  <a name="cfontholder"></a>  CFontHolder::CFontHolder  
 `CFontHolder` オブジェクトを構築します。  
  
```  
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```  
  
### <a name="parameters"></a>パラメーター  
 *pNotify*  
 フォントへのポインター`IPropertyNotifySink`インターフェイスです。  
  
### <a name="remarks"></a>Remarks  
 呼び出す必要があります`InitializeFont`を使用する前に、結果のオブジェクトを初期化します。  
  
##  <a name="getdisplaystring"></a>  CFontHolder::GetDisplayString  
 コンテナーのプロパティ ブラウザーで表示できる文字列を取得します。  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *StrValue*  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)表示文字列を保持します。  
  
### <a name="return-value"></a>戻り値  
 文字列が取得できた場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch  
 フォントのディスパッチ インターフェイスへのポインターを取得するには、この関数を呼び出します。  
  
```  
LPFONTDISP GetFontDispatch();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CFontHolder`オブジェクトの`IFontDisp`インターフェイスです。 関数が呼び出すことに注意してください`GetFontDispatch`呼び出す必要があります`IUnknown::Release`が実行時にこのインターフェイス ポインターでします。  
  
### <a name="remarks"></a>Remarks  
 呼び出す`InitializeFont`呼び出す前に`GetFontDispatch`です。  
  
##  <a name="getfonthandle"></a>  CFontHolder::GetFontHandle  
 Windows フォントへのハンドルを取得するには、この関数を呼び出します。  
  
```  
HFONT GetFontHandle();

 
HFONT GetFontHandle(
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>パラメーター  
 *cyLogical*  
 論理ユニットは、コントロールを描画する四角形の高さ。  
  
 *cyHimetric*  
 高さの`MM_HIMETRIC`コントロールの単位。  
  
### <a name="return-value"></a>戻り値  
 フォント オブジェクトへのハンドルそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 比率*cyLogical*と*cyHimetric*フォントのポイント サイズの単位の論理単位で、適切な表示サイズを計算に使用される`MM_HIMETRIC`単位。  
  
 表示サイズ = ( *cyLogical* / *cyHimetric*) X のフォント サイズ  
  
 パラメーターなしのバージョンでは、画面のサイズが正しく構成フォントにハンドルを返します。  
  
##  <a name="initializefont"></a>  CFontHolder::InitializeFont  
 初期化、`CFontHolder`オブジェクト。  
  
```  
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,  
    LPDISPATCH pFontDispAmbient = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFontDesc*  
 フォントの説明の構造体へのポインター ( [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782)) フォントの特性を指定します。  
  
 *pFontDispAmbient*  
 コンテナーのアンビエント フォント プロパティへのポインター。  
  
### <a name="remarks"></a>Remarks  
 場合*pFontDispAmbient*は**NULL**、`CFontHolder`の複製にオブジェクトが接続されている、`IFont`コンテナーのアンビエント フォント プロパティで使用されるインターフェイス。  
  
 場合*pFontDispAmbient*は**NULL**のいずれかによって示されるフォントの説明から新しいフォント オブジェクトが作成される*pFontDesc*または、 *pFontDesc*は**NULL**既定の説明からです。  
  
 構築の後にこの関数を呼び出し、`CFontHolder`オブジェクト。  
  
##  <a name="m_pfont"></a>  CFontHolder::m_pFont  
 ポインター、`CFontHolder`オブジェクトの`IFont`インターフェイスです。  
  
```  
LPFONT m_pFont;  
```  
  
##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics  
 によって表される物理フォントに関する情報を取得、`CFontHolder`オブジェクト。  
  
```  
void QueryTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>パラメーター  
 *lptm*  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)情報を受け取る。  
  
##  <a name="releasefont"></a>  CFontHolder::ReleaseFont  
 この関数は切断、`CFontHolder`オブジェクトからその`IFont`インターフェイスです。  
  
```  
void ReleaseFont();
```  
  
##  <a name="select"></a>  CFontHolder::Select  
 この関数では、指定したデバイス コンテキストにコントロールのフォントを選択します。  
  
```  
CFont* Select(
    CDC* pDC,  
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 フォントの選択をデバイス コンテキスト。  
  
 *cyLogical*  
 論理ユニットは、コントロールを描画する四角形の高さ。  
  
 *cyHimetric*  
 高さの`MM_HIMETRIC`コントロールの単位。  
  
### <a name="return-value"></a>戻り値  
 置き換えられるフォントへのポインター。  
  
### <a name="remarks"></a>Remarks  
 参照してください[GetFontHandle](#getfonthandle)については、 *cyLogical*と*cyHimetric*パラメーター。  
  
##  <a name="setfont"></a>  CFontHolder::SetFont  
 任意の既存のフォントを解放し、接続、`CFontHolder`オブジェクトを`IFont`インターフェイスです。  
  
```  
void SetFont(LPFONT pNewFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *pNewFont*  
 新しいポインター`IFont`インターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPropExchange クラス](../../mfc/reference/cpropexchange-class.md)
