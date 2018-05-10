---
title: CPagerCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
dev_langs:
- C++
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d22aa408fe2933803083adc784c2dbf3a85dd4df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cpagerctrl-class"></a>CPagerCtrl クラス
`CPagerCtrl` クラスは、Windows のページャー コントロールをラップします。ページャー コントロールには、外側のウィンドウに収まらない内側のウィンドウをスクロールによって表示する機能があります。  
  
## <a name="syntax"></a>構文  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|`CPagerCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPagerCtrl::Create](#create)|指定したスタイルを使用してページャー コントロールを作成し、現在アタッチ`CPagerCtrl`オブジェクト。|  
|[CPagerCtrl::CreateEx](#createex)|指定された拡張スタイルを使用してページャー コントロールを作成し、現在アタッチ`CPagerCtrl`オブジェクト。|  
|[CPagerCtrl::ForwardMouse](#forwardmouse)|有効または無効に転送[WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616)メッセージを現在のページャー コントロールに含まれているウィンドウ。|  
|[CPagerCtrl::GetBkColor](#getbkcolor)|現在のページャー コントロールの背景色を取得します。|  
|[CPagerCtrl::GetBorder](#getborder)|現在のページャー コントロールの境界線のサイズを取得します。|  
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|現在のページャー コントロールのボタンのサイズを取得します。|  
|[CPagerCtrl::GetButtonState](#getbuttonstate)|現在のページャー コントロールの指定したボタンの状態を取得します。|  
|[CPagerCtrl::GetDropTarget](#getdroptarget)|取得、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)現在のページャー コントロールのインターフェイスです。|  
|[CPagerCtrl::GetScrollPos](#getscrollpos)|現在のページャー コントロールのスクロール位置を取得します。|  
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|現在のページャー コントロールの指定したボタンがかどうかを示す`pressed`状態です。|  
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|現在のページャー コントロールの指定したボタンがかどうかを示す`grayed`状態です。|  
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|現在のページャー コントロールの指定したボタンがかどうかを示す`hot`状態です。|  
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|現在のページャー コントロールの指定したボタンがかどうかを示す`invisible`状態です。|  
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|現在のページャー コントロールの指定したボタンがかどうかを示す`normal`状態です。|  
|[CPagerCtrl::RecalcSize](#recalcsize)|コンテナー内のウィンドウのサイズを再計算する現在のページャー コントロールをによりします。|  
|[CPagerCtrl::SetBkColor](#setbkcolor)|現在のページャー コントロールの背景色を設定します。|  
|[CPagerCtrl::SetBorder](#setborder)|現在のページャー コントロールの境界線のサイズを設定します。|  
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|現在のページャー コントロールのボタンのサイズを設定します。|  
|[CPagerCtrl::SetChild](#setchild)|現在のページャー コントロールの内側のウィンドウを設定します。|  
|[CPagerCtrl::SetScrollPos](#setscrollpos)|現在のページャー コントロールのスクロール位置を設定します。|  
  
## <a name="remarks"></a>コメント  
 ページャー コントロールは、コンテナー内のウィンドウでは、線形と外側のウィンドウよりも大きい別のウィンドウを含むウィンドウです。 ページャー コントロールは、端まで達する、コンテナー内のウィンドウをスクロールするときに自動的に消滅する 2 つのスクロール ボタンを表示し、それ以外の場合に再表示します。 水平方向または垂直方向にスクロールするページャー コントロールを作成できます。  
  
 たとえば、アプリケーションのツールバーがすべての項目を表示するのに十分な幅がない場合は、ページャー コントロールにツールバーを割り当てることができ、ユーザーが左または右のすべてのアイテムにアクセスするには、ツールバーをスクロールできます。 Microsoft Internet Explorer バージョン 4.0 (commctrl.dll バージョン 4.71) には、ページャー コントロールが導入されています。  
  
 `CPagerCtrl`から派生したクラスは、 [CWnd](../../mfc/reference/cwnd-class.md)クラスです。 ページャー コントロールの例および詳細については、次を参照してください。[ページャー コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760855)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPagerCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="cpagerctrl"></a>  CPagerCtrl::CPagerCtrl  
 `CPagerCtrl` オブジェクトを構築します。  
  
```  
CPagerCtrl();
```  
  
### <a name="remarks"></a>コメント  
 使用して、 [CPagerCtrl::Create](#create)または[CPagerCtrl::CreateEx](#createex)ページャー コントロールを作成しをアタッチする方法、`CPagerCtrl`オブジェクト。  
  
##  <a name="create"></a>  CPagerCtrl::Create  
 指定したスタイルを使用してページャー コントロールを作成し、現在アタッチ`CPagerCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwStyle`|ビットごとの組み合わせ (OR)[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)をコントロールに適用できます。|  
|[入力] `rect`|参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)クライアント座標で表したコントロールのサイズと位置を格納する構造体。|  
|[入力] `pParentWnd`|ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。 このパラメーターを指定できません`NULL`です。|  
|[入力] `nID`|コントロールの ID。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ページャー コントロールを作成するには、宣言、`CPagerCtrl`変数、まず、 [CPagerCtrl::Create](#create)または[CPagerCtrl::CreateEx](#createex)その変数にメソッドです。  
  
### <a name="example"></a>例  
 次の例は、ページャー コントロールを作成しを使用して、 [CPagerCtrl::SetChild](#setchild)に非常に長いボタン コントロールをページャー コントロールに関連付けるメソッド。 使用して、 [CPagerCtrl::SetButtonSize](#setbuttonsize)に 20 ピクセルのページャー コントロールの高さを設定するメソッドを[CPagerCtrl::SetBorder](#setborder) 1 ピクセルに境界線の太さを設定するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CPagerCtrl::CreateEx  
 指定された拡張スタイルを使用してページャー コントロールを作成し、現在アタッチ`CPagerCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwExStyle`|コントロールに適用する拡張スタイルのビットごとの組み合わせ。 詳細については、次を参照してください。、`dwExStyle`のパラメーター、[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)関数。|  
|[入力] `dwStyle`|ビットごとの組み合わせ (OR)[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)をコントロールに適用できます。|  
|[入力] `rect`|参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)クライアント座標で表したコントロールのサイズと位置を格納する構造体。|  
|[入力] `pParentWnd`|ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。 このパラメーターを指定できません`NULL`です。|  
|[入力] `nID`|コントロールの ID。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ページャー コントロールを作成するには、宣言、`CPagerCtrl`変数、まず、 [CPagerCtrl::Create](#create)または[CPagerCtrl::CreateEx](#createex)その変数にメソッドです。  
  
##  <a name="forwardmouse"></a>  CPagerCtrl::ForwardMouse  
 有効または無効に転送[WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616)メッセージを現在のページャー コントロールに含まれているウィンドウ。  
  
```  
void ForwardMouse(BOOL bForward);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `bForward`|`true` マウスのメッセージを転送または`false`マウス メッセージを転送しません。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_FORWARDMOUSE](http://msdn.microsoft.com/library/windows/desktop/bb760867) Windows SDK で説明するメッセージ。  
  
##  <a name="getborder"></a>  CPagerCtrl::GetBorder  
 現在のページャー コントロールの境界線のサイズを取得します。  
  
```  
int GetBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の境界線のサイズはピクセル単位で測定されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_GETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760869) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::GetBorder](#getborder)ページャー コントロールの境界線の太さを取得します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]  
  
##  <a name="getbkcolor"></a>  CPagerCtrl::GetBkColor  
 現在のページャー コントロールの背景色を取得します。  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)のページャー コントロールの現在の背景色を表す値です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760868) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::SetBkColor](#setbkcolor)赤にページャー コントロールの背景色を設定するメソッドと[CPagerCtrl::GetBkColor](#getbkcolor)変更が行われたことを確認するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="getbuttonsize"></a>  CPagerCtrl::GetButtonSize  
 現在のページャー コントロールのボタンのサイズを取得します。  
  
```  
int GetButtonSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のボタンのサイズはピクセル単位で測定されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_GETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760870) Windows SDK で説明するメッセージ。  
  
 ページャー コントロールがある場合、`PGS_HORZ`ボタンのサイズのスタイル、ページャー ボタンの幅を決定するページャー コントロールがある場合と、`PGS_VERT`スタイル、ボタンのサイズは、ページャー ボタンの高さを決定します。 詳細については、次を参照してください。[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)です。  
  
##  <a name="getbuttonstate"></a>  CPagerCtrl::GetButtonState  
 現在のページャー コントロールに指定されたスクロール ボタンの状態を取得します。  
  
```  
DWORD GetButtonState(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iButton`|状態を取得するボタンを示します。 ページャー コントロール スタイルがの場合`PGS_HORZ`、指定`PGB_TOPORLEFT`、左ボタンのおよび`PGB_BOTTOMORRIGHT`右ボタンのです。 ページャー コントロール スタイルがの場合`PGS_VERT`を指定`PGB_TOPORLEFT`の一番上のボタンと`PGB_BOTTOMORRIGHT`の下部にあるボタンです。 詳細については、次を参照してください。[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)です。|  
  
### <a name="return-value"></a>戻り値  
 指定されたボタンの状態、`iButton`パラメーター。 いずれかの状態が`PGF_INVISIBLE`、 `PGF_NORMAL`、 `PGF_GRAYED`、 `PGF_DEPRESSED`、または`PGF_HOT`です。 詳細については、戻り値の参照、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK で説明するメッセージ。  
  
##  <a name="getdroptarget"></a>  CPagerCtrl::GetDropTarget  
 取得、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)現在のページャー コントロールのインターフェイスです。  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`IDropTarget`現在のページャー コントロールのインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 `IDropTarget` 実装するインターフェイスの 1 つは、アプリケーションでドラッグ アンド ドロップ操作をサポートします。  
  
 このメソッドは、送信、 [PGM_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb760872) Windows SDK で説明するメッセージ。 このメソッドの呼び出し元が通話を担当する、`Release`のメンバー、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)インターフェイスのインターフェイスが不要になったとき。  
  
##  <a name="getscrollpos"></a>  CPagerCtrl::GetScrollPos  
 現在のページャー コントロールのスクロール位置を取得します。  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のスクロール位置をピクセル単位で計測します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_GETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760874) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::GetScrollPos](#getscrollpos)のページャー コントロールの現在のスクロール位置を取得します。 この例では左端の位置の 0 にページャー コントロールが既にスクロールいない場合、 [CPagerCtrl::SetScrollPos](#setscrollpos)スクロール位置を 0 に設定するメソッドをします。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]  
  
##  <a name="isbuttondepressed"></a>  CPagerCtrl::IsButtonDepressed  
 現在のページャー コントロールの指定されたスクロール ボタンが押された状態かどうかを示します。  
  
```  
BOOL IsButtonDepressed(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iButton`|状態を取得するボタンを示します。 ページャー コントロール スタイルがの場合`PGS_HORZ`、指定`PGB_TOPORLEFT`、左ボタンのおよび`PGB_BOTTOMORRIGHT`右ボタンのです。 ページャー コントロール スタイルがの場合`PGS_VERT`を指定`PGB_TOPORLEFT`の一番上のボタンと`PGB_BOTTOMORRIGHT`の下部にあるボタンです。 詳細については、次を参照してください。[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)です。|  
  
### <a name="return-value"></a>戻り値  
 `true` 指定したボタンが押された状態である場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK で説明するメッセージ。 返される状態があるかどうかをテストし、`PGF_DEPRESSED`です。 詳細については、戻り値の参照、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
##  <a name="isbuttongrayed"></a>  CPagerCtrl::IsButtonGrayed  
 現在のページャー コントロールの指定されたスクロール ボタンが淡色表示の状態かどうかを示します。  
  
```  
BOOL IsButtonGrayed(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iButton`|状態を取得するボタンを示します。 ページャー コントロール スタイルがの場合`PGS_HORZ`、指定`PGB_TOPORLEFT`、左ボタンのおよび`PGB_BOTTOMORRIGHT`右ボタンのです。 ページャー コントロール スタイルがの場合`PGS_VERT`を指定`PGB_TOPORLEFT`の一番上のボタンと`PGB_BOTTOMORRIGHT`の下部にあるボタンです。 詳細については、次を参照してください。[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)です。|  
  
### <a name="return-value"></a>戻り値  
 `true` 指定したボタンが淡色表示の状態の場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK で説明するメッセージ。 返される状態があるかどうかをテストし、`PGF_GRAYED`です。 詳細については、戻り値の参照、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
##  <a name="isbuttonhot"></a>  CPagerCtrl::IsButtonHot  
 現在のページャー コントロールの指定されたスクロール ボタンがホットな状態かどうかを示します。  
  
```  
BOOL IsButtonHot(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iButton`|状態を取得するボタンを示します。 ページャー コントロール スタイルがの場合`PGS_HORZ`、指定`PGB_TOPORLEFT`、左ボタンのおよび`PGB_BOTTOMORRIGHT`右ボタンのです。 ページャー コントロール スタイルがの場合`PGS_VERT`を指定`PGB_TOPORLEFT`の一番上のボタンと`PGB_BOTTOMORRIGHT`の下部にあるボタンです。 詳細については、次を参照してください。[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)です。|  
  
### <a name="return-value"></a>戻り値  
 `true` 指定したボタンがホットな状態の場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK で説明するメッセージ。 返される状態があるかどうかをテストし、`PGF_HOT`です。 詳細については、戻り値の参照、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
##  <a name="isbuttoninvisible"></a>  CPagerCtrl::IsButtonInvisible  
 現在のページャー コントロールの指定されたスクロール ボタンが非表示の状態があるかどうかを示します。  
  
```  
BOOL IsButtonInvisible(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iButton`|状態を取得するボタンを示します。 ページャー コントロール スタイルがの場合`PGS_HORZ`、指定`PGB_TOPORLEFT`、左ボタンのおよび`PGB_BOTTOMORRIGHT`右ボタンのです。 ページャー コントロール スタイルがの場合`PGS_VERT`を指定`PGB_TOPORLEFT`の一番上のボタンと`PGB_BOTTOMORRIGHT`の下部にあるボタンです。 詳細については、次を参照してください。[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)です。|  
  
### <a name="return-value"></a>戻り値  
 `true` 指定したボタンが非表示の状態の場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 Windows では、スクロール ボタン、特定の方向に非表示コンテナー内のウィンドウは、スクロールし、端まで達する、さらにボタンをクリックするとできないウィンドウの詳細を表示させます。  
  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK で説明するメッセージ。 返される状態があるかどうかをテストし、`PGF_INVISIBLE`です。 詳細については、戻り値の参照、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)ページャー コントロールの左し、右スクロール ボタンが表示されているかどうかを判断するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]  
  
##  <a name="isbuttonnormal"></a>  CPagerCtrl::IsButtonNormal  
 現在のページャー コントロールの指定されたスクロール ボタンが通常の状態かどうかを示します。  
  
```  
BOOL IsButtonNormal(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iButton`|状態を取得するボタンを示します。 ページャー コントロール スタイルがの場合`PGS_HORZ`、指定`PGB_TOPORLEFT`、左ボタンのおよび`PGB_BOTTOMORRIGHT`右ボタンのです。 ページャー コントロール スタイルがの場合`PGS_VERT`を指定`PGB_TOPORLEFT`の一番上のボタンと`PGB_BOTTOMORRIGHT`の下部にあるボタンです。 詳細については、次を参照してください。[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)です。|  
  
### <a name="return-value"></a>戻り値  
 `true` 指定したボタンは、通常の状態がある場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK で説明するメッセージ。 返される状態があるかどうかをテストし、`PGF_NORMAL`です。 詳細については、戻り値の参照、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
##  <a name="recalcsize"></a>  CPagerCtrl::RecalcSize  
 コンテナー内のウィンドウのサイズを再計算する現在のページャー コントロールをによりします。  
  
```  
void RecalcSize();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_RECALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760876) Windows SDK で説明するメッセージ。 その結果、ページャー コントロールは、 [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864)コンテナー内のウィンドウのスクロール可能なディメンションを取得する通知。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::RecalcSize](#recalcsize)のサイズを再計算する現在のページャー コントロールを要求するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]  
  
### <a name="example"></a>例  
 次の例で[メッセージ リフレクション](../../mfc/tn062-message-reflection-for-windows-controls.md)計算を実行するコントロールの親ダイアログを必要とするのではなく、独自のサイズを再計算するページャー コントロールを有効にします。 例では、`MyPagerCtrl`クラス、 [CPagerCtrl クラス](../../mfc/reference/cpagerctrl-class.md)に関連付けるには、メッセージ マップを使用して、 [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864)を使用した通知、`OnCalcsize`通知ハンドラー。 この例では、通知ハンドラーは、固定値のページャー コントロールの高さと幅を設定します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]  
  
##  <a name="setbkcolor"></a>  CPagerCtrl::SetBkColor  
 現在のページャー コントロールの背景色を設定します。  
  
```  
COLORREF SetBkColor(COLORREF clrBk);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `clrBk`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)のページャー コントロールの新しい背景色を表す値です。|  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)のページャー コントロールの直前の背景色を表す値です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760878) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::SetBkColor](#setbkcolor)赤にページャー コントロールの背景色を設定するメソッドと[CPagerCtrl::GetBkColor](#getbkcolor)変更が行われたことを確認するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="setborder"></a>  CPagerCtrl::SetBorder  
 現在のページャー コントロールの境界線のサイズを設定します。  
  
```  
int SetBorder(int iBorder);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iBorder`|新しい境界線のサイズはピクセル単位で測定されます。 場合、`iBorder`パラメーターが負の場合、境界線のサイズは 0 に設定します。|  
  
### <a name="return-value"></a>戻り値  
 以前の境界線のサイズはピクセル単位で測定されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_SETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760880) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次の例は、ページャー コントロールを作成しを使用して、 [CPagerCtrl::SetChild](#setchild)に非常に長いボタン コントロールをページャー コントロールに関連付けるメソッド。 使用して、 [CPagerCtrl::SetButtonSize](#setbuttonsize)に 20 ピクセルのページャー コントロールの高さを設定するメソッドを[CPagerCtrl::SetBorder](#setborder) 1 ピクセルに境界線の太さを設定するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setbuttonsize"></a>  CPagerCtrl::SetButtonSize  
 現在のページャー コントロールのボタンのサイズを設定します。  
  
```  
int SetButtonSize(int iButtonSize);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iButtonSize`|新しいボタンのサイズはピクセル単位で測定されます。|  
  
### <a name="return-value"></a>戻り値  
 以前のボタンのサイズはピクセル単位で測定されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_SETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760886) Windows SDK で説明するメッセージ。  
  
 ページャー コントロールがある場合、`PGS_HORZ`ボタンのサイズのスタイル、ページャー ボタンの幅を決定するページャー コントロールがある場合と、`PGS_VERT`スタイル、ボタンのサイズは、ページャー ボタンの高さを決定します。 既定のボタンのサイズが 4 分の 3 つ、スクロール バーの幅と、ボタンの最小サイズは 12 ピクセルです。 詳細については、次を参照してください。[ページャー コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)です。  
  
### <a name="example"></a>例  
 次の例は、ページャー コントロールを作成しを使用して、 [CPagerCtrl::SetChild](#setchild)に非常に長いボタン コントロールをページャー コントロールに関連付けるメソッド。 使用して、 [CPagerCtrl::SetButtonSize](#setbuttonsize)に 20 ピクセルのページャー コントロールの高さを設定するメソッドを[CPagerCtrl::SetBorder](#setborder) 1 ピクセルに境界線の太さを設定するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setchild"></a>  CPagerCtrl::SetChild  
 現在のページャー コントロールの内側のウィンドウを設定します。  
  
```  
void SetChild(HWND hwndChild);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `hwndChild`|含まれているウィンドウをハンドルします。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_SETCHILD](http://msdn.microsoft.com/library/windows/desktop/bb760884) Windows SDK で説明するメッセージ。  
  
 このメソッドが含まれているウィンドウの親を変更していません。のみ、スクロールするためのページャー コントロールにウィンドウ ハンドルを割り当てます。 ほとんどの場合は、ページャー コントロールの子ウィンドウがコンテナー内のウィンドウになります。  
  
### <a name="example"></a>例  
 次の例は、ページャー コントロールを作成しを使用して、 [CPagerCtrl::SetChild](#setchild)に非常に長いボタン コントロールをページャー コントロールに関連付けるメソッド。 使用して、 [CPagerCtrl::SetButtonSize](#setbuttonsize)に 20 ピクセルのページャー コントロールの高さを設定するメソッドを[CPagerCtrl::SetBorder](#setborder) 1 ピクセルに境界線の太さを設定するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setscrollpos"></a>  CPagerCtrl::SetScrollPos  
 現在のページャー コントロールのスクロール位置を設定します。  
  
```  
void SetScrollPos(int iPos);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iPos`|新しいスクロール位置をピクセル単位で計測します。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PGM_SETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760886) Windows SDK で説明するメッセージ。  
  
## <a name="see-also"></a>関連項目  
 [CPagerCtrl クラス](../../mfc/reference/cpagerctrl-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [複数のページャー コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760855)



