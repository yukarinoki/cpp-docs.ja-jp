---
title: CMFCCaptionBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c40f4d836d662bde1f49b9a0639b771d10db667
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar クラス
A`CMFCCaptionBar`オブジェクトは 3 つの要素を表示できるコントロール バー: ボタン、テキスト ラベル、およびビットマップ。 表示できる各要素の数は 1 つずつです。 各要素は、コントロールの左端、右端、または中央に揃えて配置できます。 また、キャプション バーの上部または下部の境界線にフラット スタイルまたは 3D スタイルを適用することもできます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCCaptionBar::Create](#create)|キャプション バー コントロールを作成し、それにアタッチ、`CMFCCaptionBar`オブジェクト。|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|キャプション バーとその親のフレームの間で別のペインを動的に挿入するかどうかを示します。 (上書き[cbasepane::doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore))。|  
|[CMFCCaptionBar::EnableButton](#enablebutton)|有効またはキャプション バーにあるボタンを無効にします。|  
|[CMFCCaptionBar::GetAlignment](#getalignment)|指定した要素の配置を返します。|  
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|キャプション バーの境界線のサイズを返します。|  
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|キャプション バーのボタンの外接する四角形を取得します。|  
|[CMFCCaptionBar::GetMargin](#getmargin)|キャプション バーの要素の端と、キャプション バー コントロールの端の間の距離を返します。|  
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|キャプション バーをメッセージ バー モードであるかどうかを指定します。|  
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|キャプション バーのビットマップ イメージを削除します。|  
|[CMFCCaptionBar::RemoveButton](#removebutton)|キャプション バーから、ボタンを削除します。|  
|[CMFCCaptionBar::RemoveIcon](#removeicon)|キャプション バーからアイコンを削除します。|  
|[CMFCCaptionBar::RemoveText](#removetext)|キャプション バーのテキスト ラベルを削除します。|  
|[CMFCCaptionBar::SetBitmap](#setbitmap)|キャプション バーのビットマップ イメージを設定します。|  
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|キャプション バーの境界線のサイズを設定します。|  
|[CMFCCaptionBar::SetButton](#setbutton)|キャプション バーのボタンを設定します。|  
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|ボタンが押された状態のままになるかどうかを指定します。|  
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|ボタンのツールヒントを設定します。|  
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|キャプション バーの境界線スタイルを設定します。|  
|[CMFCCaptionBar::SetIcon](#seticon)|キャプション バーのアイコンを設定します。|  
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|キャプション バーの画像のツールヒントを設定します。|  
|[CMFCCaptionBar::SetMargin](#setmargin)|キャプション バーの要素の端と、キャプション バー コントロールの端の間の距離を設定します。|  
|[CMFCCaptionBar::SetText](#settext)|キャプション バーのテキスト ラベルを設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|キャプション バーの背景を埋めるために、フレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|キャプション バーの境界線を描画するためにフレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|キャプション バーのボタンを描画するためにフレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|キャプション バーの画像を描画するためにフレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|キャプション バーのテキストを描画するためにフレームワークによって呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|キャプション バーの背景色。|  
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|キャプション バーの境界線の色。|  
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|キャプション バーのテキストの色。|  
  
## <a name="remarks"></a>コメント  
 キャプション バーを作成するには、次の手順を実行します。  
  
1.  構築、`CMFCCaptionBar`オブジェクト。 通常、フレーム ウィンドウ クラスに、キャプション バーを追加します。  
  
2.  呼び出す、 [CMFCCaptionBar::Create](#create)キャプション バー コントロールを作成しをアタッチする方法、`CMFCCaptionBar`オブジェクト。  
  
3.  呼び出す[CMFCCaptionBar::SetButton](#setbutton)、 [CMFCCaptionBar::SetText](#settext)、 [CMFCCaptionBar::SetIcon](#seticon)、および[CMFCCaptionBar::SetBitmap](#setbitmap)キャプション バーの要素を設定します。  
  
 ボタンの要素を設定すると、ボタンをコマンド ID を割り当てる必要があります。 ユーザーが、ボタンのキャプション バーのルートをクリックしたとき、`WM_COMMAND`を親フレーム ウィンドウにこの ID を持つメッセージ。  
  
 キャプション バーは、Microsoft Office 2007 アプリケーションで表示されるメッセージ バーをエミュレートするメッセージ バー モードも作業ができます。 メッセージ バー モード、キャプション バーが表示されます、ビットマップ、メッセージ、およびボタン (通常、ダイアログ ボックスが開きます。)ビットマップにツールヒントを割り当てることができます。  
  
 メッセージ バー モードを有効にするを呼び出す[CMFCCaptionBar::Create](#create)に 4 番目のパラメーター (bIsMessageBarMode) を設定および`TRUE`です。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCCaptionBar`クラスです。 例がキャプション バー コントロールを作成、キャプション バーの 3D 罫線の設定、(ピクセル単位) のキャプション バーの要素の端と、キャプション バー コントロールの端との間の距離を設定、キャプション バーのボタンを設定する方法を示します、ボタンのツールヒントを設定、キャプション バーのテキスト ラベル、ビットマップ イメージのキャプション バーの設定およびキャプション バーにイメージのツールヒントを設定します。 このコード スニペットの一部である、 [MS Office 2007 デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcaptionbar.h  
  
##  <a name="create"></a>  CMFCCaptionBar::Create  
 キャプション バー コントロールを作成し、それにアタッチ、`CMFCCaptionBar`オブジェクト。  
  
```  
BOOL Create(
    DWORD dwStyle,  
    CWnd* pParentWnd,  
    UINT uID,  
    int nHeight=-1,  
    BOOL bIsMessageBarMode=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 キャプション バーのスタイルの論理 OR の組み合わせ。  
  
 `pParentWnd`  
 キャプション バー コントロールの親ウィンドウです。  
  
 `uID`  
 キャプション バー コントロールの ID。  
  
 `nHeight`  
 (ピクセル単位) のキャプション バー コントロールの高さ。 -1 の場合、高さは、アイコン、テキスト、キャプション バー コントロールを表示するボタンの高さに基づいて計算されます。  
  
 `bIsMessageBarMode`  
 `TRUE` キャプション バー モードの場合、メッセージ バーです。`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` キャプション バー コントロールが正常に作成された場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CMFCCaptionBar` 2 つのステップ内のオブジェクト。 最初、コンス トラクターを呼び出すし、その後呼び出す、 `Create` Windows コントロールを作成し、それにアタッチするメソッド、`CMFCCaptionBar`オブジェクト。  
  
##  <a name="doesallowdyninsertbefore"></a>  CMFCCaptionBar::DoesAllowDynInsertBefore  
 キャプション バーとその親のフレームの間で別のペインを動的に挿入するかどうかを示します。  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します`FALSE`オーバーライドされない限り、します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablebutton"></a>  CMFCCaptionBar::EnableButton  
 有効またはキャプション バーにあるボタンを無効にします。  
  
```  
void EnableButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` ボタンを有効にする`FALSE` ボタンを無効にします。  
  
##  <a name="getalignment"></a>  CMFCCaptionBar::GetAlignment  
 指定した要素の配置を返します。  
  
```  
BarElementAlignment GetAlignment(BarElement elem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `elem`  
 キャプション バーには、配置を取得するための要素が表示されます。  
  
### <a name="return-value"></a>戻り値  
 たとえば、ボタンやビットマップ、テキスト、アイコンなど、要素の配置です。  
  
### <a name="remarks"></a>コメント  
 要素の配置には、次の値のいずれかを指定できます。  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="getbordersize"></a>  CMFCCaptionBar::GetBorderSize  
 キャプション バーの境界線のサイズを返します。  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 枠線のピクセル単位のサイズ。  
  
##  <a name="getbuttonrect"></a>  CMFCCaptionBar::GetButtonRect  
 キャプション バーのボタンの外接する四角形を取得します。  
  
```  
CRect GetButtonRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CRect`キャプション バーのボタンの外接する四角形の座標を格納しているオブジェクト。  
  
##  <a name="getmargin"></a>  CMFCCaptionBar::GetMargin  
 キャプション バーの要素の端と、キャプション バー コントロールの端の間の距離を返します。  
  
```  
int GetMargin() const;  
```  
  
### <a name="return-value"></a>戻り値  
 (ピクセル単位) のキャプション バーの要素の端と、キャプション バー コントロールの端の間の距離。  
  
##  <a name="ismessagebarmode"></a>  CMFCCaptionBar::IsMessageBarMode  
 キャプション バーをメッセージ バー モードであるかどうかを指定します。  
  
```  
BOOL IsMessageBarMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` キャプション バー モードの場合、メッセージ バーです。`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 メッセージ バー モードでは、キャプション バーには、ツールヒント、メッセージ テキスト、ボタンの画像が表示されます。  
  
##  <a name="m_clrbarbackground"></a>  CMFCCaptionBar::m_clrBarBackground  
 キャプション バーの背景色。  
  
```  
COLORREF m_clrBarBackground  
```  
  
##  <a name="m_clrbarborder"></a>  CMFCCaptionBar::m_clrBarBorder  
 キャプション バーの境界線の色。  
  
```  
COLORREF m_clrBarBorder  
```  
  
##  <a name="m_clrbartext"></a>  CMFCCaptionBar::m_clrBarText  
 キャプション バーのテキストの色。  
  
```  
COLORREF m_clrBarText  
```  
  
##  <a name="ondrawbackground"></a>  CMFCCaptionBar::OnDrawBackground  
 キャプション バーの背景を埋めるために、フレームワークによって呼び出されます。  
  
```  
virtual void OnDrawBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 キャプション バーのデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 入力に外接する四角形。  
  
### <a name="remarks"></a>コメント  
 `OnDrawBackground`キャプション バーの背景が入力すると、メソッドが呼び出されます。 既定の実装を使用して背景を塗りつぶす、 [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)色。  
  
 このメソッドをオーバーライドする`CMFCCaptionBar`キャプション バーの外観をカスタマイズするクラスを派生します。  
  
##  <a name="ondrawborder"></a>  CMFCCaptionBar::OnDrawBorder  
 キャプション バーの境界線を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 枠線の表示に使用されるデバイス コンテキスト。  
  
 [入力] `rect`  
 外接する四角形。  
  
### <a name="remarks"></a>コメント  
 既定では、罫線には、フラット スタイルが設定されています。  
  
 このメソッドをオーバーライドする`CMFCCaptionBar`キャプション バーの境界線の外観をカスタマイズするクラスを派生します。  
  
##  <a name="ondrawbutton"></a>  CMFCCaptionBar::OnDrawButton  
 キャプション バーのボタンを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawButton(
    CDC* pDC,  
    CRect rect,  
    const CString& strButton,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンを表示するために使用しているデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 ボタンの外接する四角形。  
  
 [入力] `strButton`  
 ボタンのテキスト ラベル。  
  
 [入力] `bEnabled`  
 `TRUE` ボタンが有効である場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドする`CMFCCaptionBar`キャプション バーのボタンの外観をカスタマイズするクラスを派生します。  
  
##  <a name="ondrawimage"></a>  CMFCCaptionBar::OnDrawImage  
 キャプション バーの画像を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 イメージを表示するために使用しているデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 イメージの外接する四角形を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドする`CMFCCaptionBar`イメージの外観をカスタマイズするクラスを派生します。  
  
##  <a name="ondrawtext"></a>  CMFCCaptionBar::OnDrawText  
 キャプション バーのテキストを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンを表示するために使用しているデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 テキストの外接する四角形。  
  
 [入力] `strText`  
 表示するテキスト文字列。  
  
### <a name="remarks"></a>コメント  
 既定の実装を使用して、テキストを表示する`CDC::DrawText`と[CMFCCaptionBar::m_clrBarText](#m_clrbartext)色。  
  
 このメソッドをオーバーライドする`CMFCCaptionBar`キャプション バーのテキストの外観をカスタマイズするクラスを派生します。  
  
##  <a name="removebitmap"></a>  CMFCCaptionBar::RemoveBitmap  
 キャプション バーのビットマップ イメージを削除します。  
  
```  
void RemoveBitmap();
```  
  
##  <a name="removebutton"></a>  CMFCCaptionBar::RemoveButton  
 キャプション バーから、ボタンを削除します。  
  
```  
void RemoveButton();
```  
  
### <a name="remarks"></a>コメント  
 キャプション バーの要素のレイアウトは自動的に調整されます。  
  
##  <a name="removeicon"></a>  CMFCCaptionBar::RemoveIcon  
 キャプション バーからアイコンを削除します。  
  
```  
void RemoveIcon();
```  
  
##  <a name="removetext"></a>  CMFCCaptionBar::RemoveText  
 キャプション バーのテキスト ラベルを削除します。  
  
```  
void RemoveText();
```  
  
##  <a name="setbitmap"></a>  CMFCCaptionBar::SetBitmap  
 キャプション バーのビットマップ イメージを設定します。  
  
```  
void SetBitmap(
    HBITMAP hBitmap,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

 
void SetBitmap(
    UINT uiBmpResID,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hBitmap`  
 設定するビットマップへのハンドルです。  
  
 [入力] `clrTransparent`  
 ビットマップの透明色を指定する RGB 値。  
  
 [入力] `bStretch`  
 場合`TRUE`イメージを外接する四角形に収まりきらない場合、ビットマップを拡大します。 それ以外の場合、ビットマップは拡張されていません。  
  
 [入力] `bmpAlignment`  
 ビットマップの配置です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、キャプション バーにビットマップを設定できます。  
  
 前のビットマップは自動的に破棄されます。 キャプション バーにアイコンが表示されますが呼び出されるためかどうか、 [CMFCCaptionBar::SetIcon](#seticon)メソッドを呼び出すことによって、アイコンを削除しない限り、ビットマップは表示されません[CMFCCaptionBar::RemoveIcon](#removeicon)です。  
  
 ビットマップの配置で指定されたとおり、`bmpAlignment`パラメーター。  このパラメーターには、次の `BarElementAlignment` 値のいずれかを指定できます。  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setbordersize"></a>  CMFCCaptionBar::SetBorderSize  
 キャプション バーの境界線のサイズを設定します。  
  
```  
void SetBorderSize(int nSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nSize`  
 キャプション バーの境界線のピクセル単位の新しいサイズ。  
  
##  <a name="setbutton"></a>  CMFCCaptionBar::SetButton  
 キャプション バーのボタンを設定します。  
  
```  
void SetButton(
    LPCTSTR lpszLabel,  
    UINT uiCmdUI,  
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,  
    BOOL bHasDropDownArrow=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszLabel`  
 ボタンのコマンドのラベル。  
  
 `uiCmdUI`  
 ボタンのコマンド id。  
  
 `btnAlignmnet`  
 ボタンの配置です。  
  
 `bHasDropDownArrow`  
 `TRUE` ボタンは、ドロップダウン矢印を表示する場合`FALSE`それ以外の場合。  
  
##  <a name="setbuttonpressed"></a>  CMFCCaptionBar::SetButtonPressed  
 ボタンが押された状態のままになるかどうかを指定します。  
  
```  
void SetButtonPressed(BOOL bPresed=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bPresed`  
 `TRUE` ボタンが押された状態の状態を保持する場合`FALSE`それ以外の場合。  
  
##  <a name="setbuttontooltip"></a>  CMFCCaptionBar::SetButtonToolTip  
 ボタンのツールヒントを設定します。  
  
```  
void SetButtonToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszToolTip`  
 ツールヒントのキャプション。  
  
 [入力] `lpszDescription`  
 ツールヒントの説明。  
  
##  <a name="setflatborder"></a>  CMFCCaptionBar::SetFlatBorder  
 キャプション バーの境界線スタイルを設定します。  
  
```  
void SetFlatBorder(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bFlat`  
 `TRUE` キャプション バーの境界線のフラット場合。 `FALSE` 境界線が 3D である場合。  
  
##  <a name="seticon"></a>  CMFCCaptionBar::SetIcon  
 キャプション バーのアイコンを設定します。  
  
```  
void SetIcon(
    HICON hIcon,  
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hIcon`  
 設定アイコンのハンドルです。  
  
 [入力] `iconAlignment`  
 アイコンの配置です。  
  
### <a name="remarks"></a>コメント  
 キャプション バーには、アイコンまたはビットマップのいずれかを表示できます。 参照してください[CMFCCaptionBar::SetBitmap](#setbitmap)ビットマップを表示する方法を確認します。 アイコンとビットマップの両方を設定すると場合、常にアイコンが表示されます。 呼び出す[CMFCCaptionBar::RemoveIcon](#removeicon)キャプション バーからアイコンを削除します。  
  
 よると、アイコンを整列、`iconAlignment`パラメーター。 次のいずれか`BarElementAlignment`値。  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setimagetooltip"></a>  CMFCCaptionBar::SetImageToolTip  
 キャプション バーには、イメージのツールヒントを設定します。  
  
```  
void SetImageToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszToolTip`  
 ツールヒントのテキストです。  
  
 [入力] `lpszDescription`  
 ツールヒントの説明。  
  
##  <a name="setmargin"></a>  CMFCCaptionBar::SetMargin  
 キャプション バーの要素の端と、キャプション バー コントロールの端の間の距離を設定します。  
  
```  
void SetMargin(int nMargin);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nMargin`  
 (ピクセル単位) のキャプション バーの要素の端と、キャプション バー コントロールの端の間の距離。  
  
##  <a name="settext"></a>  CMFCCaptionBar::SetText  
 キャプション バーのテキスト ラベルを設定します。  
  
```  
void SetText(
    const CString& strText,  
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strText`  
 設定するテキスト文字列。  
  
 [入力] `textAlignment`  
 テキストの配置。  
  
### <a name="remarks"></a>コメント  
 テキスト ラベルを配置して指定されたとおり、`textAlignment`パラメーター。 次のいずれか`BarElementAlignment`値。  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
