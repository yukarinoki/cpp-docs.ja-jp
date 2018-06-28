---
title: CMFCRibbonStatusBarPane クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f59822504e317ee43ad7fb84345fa616fe72fae
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038433"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane クラス
`CMFCRibbonStatusBarPane`クラスは、リボン ステータス バーに追加できるリボン要素を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|`CMFCRibbonStatusBarPane` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|ウィンドウが切り詰めなしで表示できる最も長いテキスト文字列を定義する文字列を返します。|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|テキストの配置の現在の設定を返します。|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|アニメーションが進行中かどうかを判断します。|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|リボン ステータス バーの拡張領域内のウィンドウがあるかどうかを判断します。|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(上書き[CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder))。|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(上書き[CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground))。|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|ウィンドウが切り詰めなしで表示できる最も長いテキスト文字列を定義します。|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|アニメーションを使用できるイメージ リストをペインに割り当てます。|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|テキストの配置を設定します。|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|ペインに割り当てられているアニメーションを開始します。|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|ペインに割り当てられているアニメーションを停止します。 .|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|ペインに割り当てられているアニメーションを停止するときに、フレームワークによって呼び出されます。|  
  
## <a name="example"></a>例  
 次の例は、`CMFCRibbonStatusBarPane` クラスのさまざまなメソッドの使用方法を説明しています。 例では、作成する方法を示しています、`CMFCRibbonStatusBarPane`オブジェクト、ステータス バー ペインのラベルのテキストの配置設定、ステータス バー ペインが切り詰めなしで表示されることができますを使用できるイメージ リストをステータス バー ペインにアタッチする最も長いテキストを定義します。nimation、およびアニメーションを開始します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>  CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 ステータス バーのウィンドウのオブジェクトを構築します。  
  
```  
CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    BOOL bIsStatic=FALSE,  
    HICON hIcon=NULL,  
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nCmdID*  
 ウィンドウのコマンド ID を指定します。  
  
 [in]*lpszText*  
 ウィンドウに表示するテキスト文字列を指定します。  
  
 [in]*bIsStatic*  
 場合`TRUE`、ステータス ウィンドウを強調表示されているまたはをクリックして選択されていることはできません。  
  
 [in]*hIcon*  
 ウィンドウに表示されるアイコンのハンドルを指定します。  
  
 [in]*lpszAlmostLargeText*  
 ウィンドウが表示可能な最大長の文字列を指定します。  
  
 [in]*hBmpAnimationList*  
 アニメーションで使用されているイメージ リストへのハンドルを指定します。  
  
 [in]*cxAnimation*  
 (ピクセル単位)、アニメーションで使用されているイメージ リストのアイコンの幅を指定します。  
  
 [in]*clrTrnsp*  
 アニメーションで使用されているイメージ リストのイメージの透明色を指定します。  
  
 [in]*uiAnimationListResID*  
 アニメーションで使用されているイメージ リストのリソース ID を指定します。  
  
##  <a name="getalmostlargetext"></a>  CMFCRibbonStatusBarPane::GetAlmostLargeText  
 ステータス バー ペインを表示できる最も長いテキスト文字列を取得します。  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ステータス バー ペインを表示できる最も長いテキスト文字列。  
  
##  <a name="gettextalign"></a>  CMFCRibbonStatusBarPane::GetTextAlign  
 ステータス バー ペインのラベルのテキストの配置の現在の設定を取得します。  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの現在のテキスト配置:  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT です。  
  
##  <a name="isanimation"></a>  CMFCRibbonStatusBarPane::IsAnimation  
 アニメーションが進行中かどうかを判断します。  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` アニメーションの実行中である場合`FALSE`それ以外の場合。  
  
##  <a name="isextended"></a>  CMFCRibbonStatusBarPane::IsExtended  
 リボン ステータス バーの拡張領域内のウィンドウがあるかどうかを決定します。  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウがステータス バーの拡張領域にある場合は。 それ以外の場合は `FALSE`。  
  
##  <a name="ondrawborder"></a>  CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*CDC**  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onfillbackground"></a>  CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onfinishanimation"></a>  CMFCRibbonStatusBarPane::OnFinishAnimation  
 フレームワークは、ウィンドウに割り当てられているアニメーションの終了時にこのメソッドを呼び出します。  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>Remarks  
 `StopAnimation` メソッドの呼び出し、`OnFinishAnimation`メソッドで、アニメーションの終了時にデータのクリーンアップを行うこともできます。  
  
##  <a name="setalmostlargetext"></a>  CMFCRibbonStatusBarPane::SetAlmostLargeText  
 ステータス バー ペインが切り詰めなしで表示できる最も長いテキストを定義します。  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszAlmostLargeText*  
 ステータス バー ペインが切り詰めなしで表示できる最も長い文字列を指定します。  
  
### <a name="remarks"></a>Remarks  
 ライブラリは、テキストのサイズを計算する*lpszAlmostLargeText*を指定し、それに応じて、ウィンドウのサイズを変更します。 ウィンドウで、まだ適合しない場合は、テキストが切り捨てられます。  
  
##  <a name="setanimationlist"></a>  CMFCRibbonStatusBarPane::SetAnimationList  
 ステータス バー ペインに、アニメーションを使用できるイメージ リストをアタッチします。  
  
```  
void SetAnimationList(
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hBmpAnimationList*  
 イメージ リストへのハンドルを指定します。  
  
 [in]*cxAnimation*  
 イメージ リストには、フレームのピクセル単位の幅を指定します。  
  
 [in]*clrTransp*  
 イメージ リストの透明色を指定します。  
  
 [in]*uiAnimationListResID*  
 イメージ リストのリソース ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` イメージ リストが、ステータス バー ペインを正常にアタッチされている場合`FALSE`それ以外の場合。  
  
##  <a name="settextalign"></a>  CMFCRibbonStatusBarPane::SetTextAlign  
 ステータス バー ペインのラベルのテキストの配置を設定します。  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nAlign*  
 テキストの配置を指定します。  
  
### <a name="remarks"></a>Remarks  
 *nAlign*値は次のいずれかを持つことができます。  
  
- `TA_LEFT`: 左寄せ  
  
- `TA_CENTER:` 中央揃え  
  
- `TA_RIGHT:` 右揃え  
  
##  <a name="startanimation"></a>  CMFCRibbonStatusBarPane::StartAnimation  
 ペインに割り当てるアニメーションを開始します。  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nFrameDelay*  
 アニメーションのフレーム レートをミリ秒単位で指定します。  
  
 [in]*nDuration*  
 ミリ秒単位でアニメーションの再生にどのくらいの期間を指定します。 無限ループに-1 を使用します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す前に、イメージ リストへのハンドルを指定する必要があります`StartAnimation`を使用して`SetAnimationList`です。  
  
##  <a name="stopanimation"></a>  CMFCRibbonStatusBarPane::StopAnimation  
 ステータス バー ペインに割り当てられているアニメーションを停止します。  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar クラス](../../mfc/reference/cmfcribbonstatusbar-class.md)
