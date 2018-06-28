---
title: CMFCDesktopAlertWnd クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1947f93e65126df403feee658ade15648b081076
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039988"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class
`CMFCDesktopAlertWnd`クラスは、イベントについてユーザーに通知する画面に表示されるモードレス ダイアログ ボックスの機能を実装します。  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>構文  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Cmfcdesktopalertwnd::create](#create)|作成し、デスクトップ通知ウィンドウを初期化します。|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|アニメーションの速度を返します。|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|アニメーションの種類を返します。|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|自動終了のタイムアウトを返します。|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|キャプションの高さを返します。|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|画面上のデスクトップ通知ウィンドウの最後の有効な位置を返します。|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|透過性レベルを返します。|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|小さいキャプションのデスクトップ通知ウィンドウが表示されるかどうかを判断します。|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|ユーザーがデスクトップの通知 メニューにあるリンク ボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|子コントロールは、通知メッセージを送信するとき、またはアクセラレータのキーストロークを変換するとき、ユーザーが、メニューから項目を選択すると、フレームワークはこのメンバー関数を呼び出します。 (上書き[CWnd::OnCommand](../../mfc/reference/cwnd-class.md#oncommand))。|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|新しいアニメーションの速度を設定します。|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|アニメーションの種類を設定します。|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|自動終了のタイムアウトを設定します。|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|小さいキャプションと通常キャプションとを切り替えます。|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|透明度を設定します。|  
  
## <a name="remarks"></a>Remarks  
 デスクトップ通知ウィンドウを透過的にすることができます、アニメーション効果が表示されます (指定された遅延の後または閉じるボタンをクリックして、ユーザーが閉じるときに) を非表示にします。  
  
 デスクトップ通知ウィンドウは、アイコン、メッセージ テキスト (ラベル)、およびリンクを含む既定のダイアログ ボックスを含めることもできます。 または、デスクトップ通知ウィンドウでは、アプリケーションのリソースからのカスタム ダイアログを含めることができます。  
  
 2 つの手順では、デスクトップ通知ウィンドウを作成します。 最初に、構築するコンス トラクターを呼び出し、`CMFCDesktopAlertWnd`オブジェクト。 次に、呼び出し、 [cmfcdesktopalertwnd::create](#create) 、ウィンドウを作成し、アタッチにメンバー関数、`CMFCDesktopAlertWnd`オブジェクト。  
  
 `CMFCDesktopAlertWnd`オブジェクトは、デスクトップ通知ウィンドウのクライアント領域を格納する特殊な子ダイアログ ボックスを作成します。 ダイアログ ボックスでは、それに位置しているすべてのコントロールを所有します。  
  
 ポップアップ ウィンドウで、カスタム ダイアログ ボックスを表示するのには、次の手順を実行します。  
  
1.  `CMFCDesktopAlertDialog` の派生クラスを作成します。  
  
2.  リソースに、子のダイアログ ボックスのテンプレートを作成します。  
  
3.  呼び出す[cmfcdesktopalertwnd::create](#create)  ダイアログ ボックスのテンプレートと、派生クラスのランタイム クラス情報へのポインターのリソース ID を使用します。  
  
4.  プログラムのカスタム ダイアログ ボックス、ホストされるコントロールからのすべての通知を処理するか、これらの通知を直接処理するホストされるコントロールをプログラムします。  
  
 デスクトップ通知ウィンドウの動作を制御するのにには、次の関数を使用します。  
  
-   アニメーションの種類を呼び出すことによって設定[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)です。 有効なオプションを展開する、スライド、およびフェードアウトします。  
  
-   アニメーション フレームの速度を呼び出すことによって設定[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)です。  
  
-   呼び出して、透過性レベルを設定[CMFCDesktopAlertWnd::SetTransparency](#settransparency)です。  
  
-   サイズを変更、キャプションの小さなを呼び出して[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)です。 小さいキャプションは、高 7 のピクセルです。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCDesktopAlertWnd`を構成するクラス、`CMFCDesktopAlertWnd`オブジェクト。 この例では、アニメーションの種類を設定、ポップアップ ウィンドウの透明度、通知ウィンドウが小さいキャプションを表示することを指定および通知ウィンドウが自動的に閉じるまでに経過した時間を設定する方法を示します。 例では、作成し、デスクトップ通知ウィンドウを初期化する方法も示します。 このコード スニペットの一部である、[デスクトップ アラート デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxDesktopAlertWnd.h  
  
##  <a name="create"></a>  Cmfcdesktopalertwnd::create  
 作成し、デスクトップ通知ウィンドウを初期化します。  
  
```  
virtual BOOL Create(
    CWnd* pWndOwner,  
    UINT uiDlgResID,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1),  
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

 
virtual BOOL Create(
    CWnd* pWndOwner,  
    CMFCDesktopAlertWndInfo& params,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1));
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]*pWndOwner*  
 アラートのウィンドウの所有者を指定します。 その所有者は、デスクトップ通知ウィンドウのすべての通知を送信し、されます。 この値を `NULL` にすることはできません。  
  
 [in]*uiDlgResID*  
 アラートのウィンドウのリソース ID を指定します。  
  
 [in]*hMenu*  
 ユーザーがメニュー ボタンをクリックすると表示されるメニューを指定します。 場合`NULL`、メニュー ボタンは表示されません。  
  
 [in]*ptPos*  
 画面座標を使用して、通知ウィンドウが表示される最初の位置を指定します。 このパラメーターは、(-1,-1) には、画面の右下隅にある通知ウィンドウが表示されます。  
  
 [in]*pRTIDlgBar*  
 アラートのウィンドウのクライアント領域をカバーするカスタム ダイアログ ボックス クラスのランタイム クラス情報。  
  
 [in]*params*  
 通知ウィンドウの作成に使用されるパラメーターを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 通知ウィンドウが正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 アラートのウィンドウを作成するには、このメソッドを呼び出します。 アラートのウィンドウのクライアント領域には、ユーザーに表示されているすべてのコントロールをホストする子 ダイアログ ボックスが含まれています。  
  
 最初のメソッド オーバー ロードでは、アプリケーションのリソースから読み込まれた子 ダイアログ ボックスを含む通知ウィンドウを作成します。 最初のメソッド オーバー ロードでは、カスタム ダイアログ ボックス クラスのランタイム クラス情報も指定できます。  
  
 2 番目のメソッド オーバー ロードでは、既定のコントロールを含む通知ウィンドウを作成します。 変更することで表示するコントロールを指定することができます、 [CMFCDesktopAlertWndInfo クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)です。  
  
##  <a name="getanimationspeed"></a>  CMFCDesktopAlertWnd::GetAnimationSpeed  
 アニメーションの速度を返します。  
  
```  
UINT GetAnimationSpeed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミリ秒単位での通知ウィンドウのアニメーションの速度です。  
  
### <a name="remarks"></a>Remarks  
 アニメーション速度は、アラートのウィンドウが開き、終了する速度について説明します。  
  
##  <a name="getanimationtype"></a>  CMFCDesktopAlertWnd::GetAnimationType  
 アニメーションの種類を返します。  
  
```  
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```  
  
### <a name="return-value"></a>戻り値  
 次のアニメーションの種類のいずれか。  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="getautoclosetime"></a>  CMFCDesktopAlertWnd::GetAutoCloseTime  
 自動終了のタイムアウトを返します。  
  
```  
int GetAutoCloseTime() const;  
```  
  
### <a name="return-value"></a>戻り値  
 時間 (ミリ秒)、その後、[アラート] ウィンドウは自動的に閉じます。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、確認通知ウィンドウが自動的にクローズする前にどれ時間だけが経過する必要があります。  
  
##  <a name="getcaptionheight"></a>  CMFCDesktopAlertWnd::GetCaptionHeight  
 キャプションの高さを返します。  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>戻り値  
 (ピクセル単位) のキャプションの高さ。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、派生クラスでオーバーライドできます。 既定の実装で、いずれか: ポップアップ ウィンドウは、小規模のキャプション、または Windows API 関数から得られた値を表示する場合は、小さいキャプションの高さの値 (7 ピクセル単位) を返します`GetSystemMetrics(SM_CYSMCAPTION)`です。  
  
##  <a name="getlastpos"></a>  CMFCDesktopAlertWnd::GetLastPos  
 画面上のデスクトップ通知ウィンドウの最後の位置を返します。  
  
```  
CPoint GetLastPos() const;  
```  
  
### <a name="return-value"></a>戻り値  
 画面座標でのポイント。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、画面で、[アラート] ウィンドウの最後の有効な位置を返します。  
  
##  <a name="gettransparency"></a>  CMFCDesktopAlertWnd::GetTransparency  
 透過性レベルを返します。  
  
```  
BYTE GetTransparency() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 ~ 255 の間の透明度レベルです。 値が大きい、不透明度を高くウィンドウです。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用すると、アラートのウィンドウの現在の透明度を取得できます。  
  
##  <a name="hassmallcaption"></a>  CMFCDesktopAlertWnd::HasSmallCaption  
 小さいキャプションまたは標準サイズのキャプションにデスクトップ通知ウィンドウがあるかどうかを判断します。  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` キャプション付きの小さなポップアップ ウィンドウが表示されている場合`FALSE`キャプション付きの通常のサイズは、ポップアップ ウィンドウが表示されている場合。  
  
### <a name="remarks"></a>Remarks  
 小さいキャプションまたは標準サイズのキャプション、ポップアップ ウィンドウがあるかどうかを確認するのにには、このメソッドを使用します。 既定では、小さいキャプションは、高 7 ピクセルです。 標準サイズのキャプションの高さを取得するには、Windows API 関数を呼び出すことによって`GetSystemMetrics(SM_CYCAPTION)`です。  
  
##  <a name="onbeforeshow"></a>  CMFCDesktopAlertWnd::OnBeforeShow  

  
```  
virtual BOOL OnBeforeShow(CPoint&);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*CPoint (& a)*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onclicklinkbutton"></a>  CMFCDesktopAlertWnd::OnClickLinkButton  
 ユーザーがデスクトップの通知 メニューにあるリンク ボタンをクリックしたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmdID*  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE`。  
  
### <a name="remarks"></a>Remarks  
 ユーザーが通知ウィンドウのリンクをクリックしたときに通知する場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="oncommand"></a>  CMFCDesktopAlertWnd::OnCommand  

  
```  
virtual BOOL OnCommand(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*wParam*  
 [in]*lParam*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondraw"></a>  CMFCDesktopAlertWnd::OnDraw  

  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="processcommand"></a>  CMFCDesktopAlertWnd::ProcessCommand  

  
```  
BOOL ProcessCommand(HWND hwnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hwnd*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setanimationspeed"></a>  CMFCDesktopAlertWnd::SetAnimationSpeed  
 新しいアニメーションの速度を設定します。  
  
```  
void SetAnimationSpeed(UINT nSpeed);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nSpeed*  
 新しいアニメーションの速度をミリ秒単位で指定します。  
  
### <a name="remarks"></a>Remarks  
 アラートのウィンドウのアニメーションの速度を設定するには、このメソッドを呼び出します。 既定のアニメーション速度は、30 ミリ秒です。  
  
##  <a name="setanimationtype"></a>  CMFCDesktopAlertWnd::SetAnimationType  
 アニメーションの種類を設定します。  
  
```  
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*型*  
 アニメーションの種類を指定します。  
  
### <a name="remarks"></a>Remarks  
 アニメーションの種類を設定するには、このメソッドを呼び出します。 次のいずれかの値を指定できます。  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="setautoclosetime"></a>  CMFCDesktopAlertWnd::SetAutoCloseTime  
 自動終了のタイムアウトを設定します。  
  
```  
void SetAutoCloseTime(int nTime);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nTime*  
 通知ウィンドウが自動的に閉じるまでの経過する時間 (ミリ秒単位)。  
  
### <a name="remarks"></a>Remarks  
 ウィンドウで、ユーザーが操作できない場合、指定した時間の後に、[アラート] ウィンドウが自動的に閉じます。  
  
##  <a name="setsmallcaption"></a>  CMFCDesktopAlertWnd::SetSmallCaption  
 小規模で標準サイズのキャプションを切り替えます。  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bSmallCaption*  
 `TRUE` 通知ウィンドウが小さいキャプションを表示することを指定するにはそれ以外の場合、`FALSE`通知ウィンドウが標準サイズのキャプションを表示することを指定します。  
  
### <a name="remarks"></a>Remarks  
 または標準サイズの小さいキャプションを表示するには、このメソッドを呼び出します。 既定では、小さいキャプションは、高 7 ピクセルです。 正規のキャプションのサイズを取得するには、Windows API 関数を呼び出すことによって`GetSystemMetrics(SM_CYCAPTION)`です。  
  
##  <a name="settransparency"></a>  CMFCDesktopAlertWnd::SetTransparency  
 ポップアップ ウィンドウの透明度を設定します。  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nTransparency*  
 透明度を指定します。 この値は、0 ~ 255 の範囲にする必要があります。 値が大きい、不透明度を高くウィンドウです。  
  
### <a name="remarks"></a>Remarks  
 ポップアップ ウィンドウの透過性レベルを設定するには、この関数を呼び出します。  
  
##  <a name="getdialogsize"></a>  CMFCDesktopAlertWnd::GetDialogSize  

  
```  
virtual CSize GetDialogSize();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWndInfo クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)
