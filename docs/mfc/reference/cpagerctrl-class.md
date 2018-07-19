---
title: CPagerCtrl クラス |Microsoft Docs
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
ms.openlocfilehash: 56b00604f57c67ba2555f667e41501451d06fed4
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853824"
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
|[CPagerCtrl::Create](#create)|指定したスタイルを使用してページャー コントロールを作成し、現在結び付けます`CPagerCtrl`オブジェクト。|  
|[CPagerCtrl::CreateEx](#createex)|指定された拡張スタイルを使用してページャー コントロールを作成し、現在結び付けます`CPagerCtrl`オブジェクト。|  
|[CPagerCtrl::ForwardMouse](#forwardmouse)|有効または転送を無効に[WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616)メッセージを現在のページャー コントロールに含まれているウィンドウ。|  
|[CPagerCtrl::GetBkColor](#getbkcolor)|現在のページャー コントロールの背景色を取得します。|  
|[CPagerCtrl::GetBorder](#getborder)|現在のページャー コントロールの境界線のサイズを取得します。|  
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|現在のページャー コントロールのボタンのサイズを取得します。|  
|[CPagerCtrl::GetButtonState](#getbuttonstate)|現在のページャー コントロールの指定したボタンの状態を取得します。|  
|[CPagerCtrl::GetDropTarget](#getdroptarget)|取得、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)現在ページャー コントロールのインターフェイス。|  
|[CPagerCtrl::GetScrollPos](#getscrollpos)|現在のページャー コントロールのスクロール位置を取得します。|  
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|現在のページャー コントロールの指定したボタンがかどうかを示す`pressed`状態。|  
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|現在のページャー コントロールの指定したボタンがかどうかを示す`grayed`状態。|  
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|現在のページャー コントロールの指定したボタンがかどうかを示す`hot`状態。|  
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|現在のページャー コントロールの指定したボタンがかどうかを示す`invisible`状態。|  
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|現在のページャー コントロールの指定したボタンがかどうかを示す`normal`状態。|  
|[CPagerCtrl::RecalcSize](#recalcsize)|現在のページャー コントロールのウィンドウのサイズを再計算させます。|  
|[CPagerCtrl::SetBkColor](#setbkcolor)|現在のページャー コントロールの背景色を設定します。|  
|[CPagerCtrl::SetBorder](#setborder)|現在のページャー コントロールの境界線のサイズを設定します。|  
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|現在のページャー コントロールのボタンのサイズを設定します。|  
|[CPagerCtrl::SetChild](#setchild)|現在のページャー コントロールの内側のウィンドウを設定します。|  
|[CPagerCtrl::SetScrollPos](#setscrollpos)|現在のページャー コントロールのスクロール位置を設定します。|  
  
## <a name="remarks"></a>Remarks  
 ページャー コントロールは、コンテナー内のウィンドウで線形と外側のウィンドウよりも大きいは、別のウィンドウを含むウィンドウです。 ページャー コントロールは端まで達する、含まれているウィンドウをスクロールするときは自動的に消滅する 2 つのスクロール ボタンを表示し、再び表示します。 水平方向または垂直方向にスクロールするページャー コントロールを作成することができます。  
  
 など、アプリケーションのすべての項目を表示するのに十分な幅がツールバーにある場合は、ページャー コントロールにツールバーを割り当てることができ、ユーザーは、ツールバーを左またはすべての項目へのアクセス権をスクロールできます。 Microsoft Internet Explorer バージョン 4.0 (commctrl.dll バージョン 4.71) には、ページャー コントロールが導入されています。  
  
 `CPagerCtrl`から派生したクラスは、 [CWnd](../../mfc/reference/cwnd-class.md)クラス。 ページャー コントロールの例と詳細については、次を参照してください。[ページャー コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760855)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPagerCtrl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="cpagerctrl"></a>  CPagerCtrl::CPagerCtrl  
 `CPagerCtrl` オブジェクトを構築します。  
  
```  
CPagerCtrl();
```  
  
### <a name="remarks"></a>Remarks  
 使用して、 [CPagerCtrl::Create](#create)または[CPagerCtrl::CreateEx](#createex)ページャー コントロールを作成し、アタッチ先メソッドを`CPagerCtrl`オブジェクト。  
  
##  <a name="create"></a>  CPagerCtrl::Create  
 指定したスタイルを使用してページャー コントロールを作成し、現在結び付けます`CPagerCtrl`オブジェクト。  
  
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
|[in]*dwStyle*|ビットごとの組み合わせ (OR)[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)をコントロールに適用できます。|  
|[in]*rect*|参照を[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)クライアント座標で、コントロールのサイズと位置を含む構造体。|  
|[in]*pParentWnd*|ポインターを[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。 このパラメーターは、NULL にすることはできません。|  
|[in]*nID*|コントロールの ID。|  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 ページャー コントロールを作成するには、宣言、`CPagerCtrl`変数を呼び出して、 [CPagerCtrl::Create](#create)または[CPagerCtrl::CreateEx](#createex)その変数のメソッド。  
  
### <a name="example"></a>例  
 次の例は、ページャー コントロールを作成しを使用して、 [CPagerCtrl::SetChild](#setchild)に非常に長いボタン コントロールにページャー コントロールを関連付けるメソッド。 使用して、 [CPagerCtrl::SetButtonSize](#setbuttonsize)に 20 ピクセルのページャー コントロールの高さを設定するメソッドを[CPagerCtrl::SetBorder](#setborder) 1 ピクセルに枠線の太さを設定します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CPagerCtrl::CreateEx  
 指定された拡張スタイルを使用してページャー コントロールを作成し、現在結び付けます`CPagerCtrl`オブジェクト。  
  
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
|[in]*dwExStyle*|コントロールに適用する拡張スタイルのビットごとの組み合わせ。 詳細については、次を参照してください。、 *dwExStyle*のパラメーター、 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)関数。|  
|[in]*dwStyle*|ビットごとの組み合わせ (OR)[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)をコントロールに適用できます。|  
|[in]*rect*|参照を[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)クライアント座標で、コントロールのサイズと位置を含む構造体。|  
|[in]*pParentWnd*|ポインターを[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。 このパラメーターは、NULL にすることはできません。|  
|[in]*nID*|コントロールの ID。|  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 ページャー コントロールを作成するには、宣言、`CPagerCtrl`変数を呼び出して、 [CPagerCtrl::Create](#create)または[CPagerCtrl::CreateEx](#createex)その変数のメソッド。  
  
##  <a name="forwardmouse"></a>  CPagerCtrl::ForwardMouse  
 有効または転送を無効に[WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616)メッセージを現在のページャー コントロールに含まれているウィンドウ。  
  
```  
void ForwardMouse(BOOL bForward);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*bForward*|True の場合、マウス メッセージを転送しないマウス メッセージを転送または FALSE。|  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_FORWARDMOUSE](http://msdn.microsoft.com/library/windows/desktop/bb760867)メッセージは、Windows SDK で説明します。  
  
##  <a name="getborder"></a>  CPagerCtrl::GetBorder  
 現在のページャー コントロールの境界線のサイズを取得します。  
  
```  
int GetBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の境界線のサイズは、ピクセル単位で測定されます。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_GETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760869)メッセージは、Windows SDK で説明します。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::GetBorder](#getborder)ページャー コントロールの境界線の太さを取得します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]  
  
##  <a name="getbkcolor"></a>  CPagerCtrl::GetBkColor  
 現在のページャー コントロールの背景色を取得します。  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)ページャー コントロールの現在の背景色を表す値です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760868)メッセージは、Windows SDK で説明します。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::SetBkColor](#setbkcolor)ページャー コントロールの背景色を赤に設定する方法と、 [CPagerCtrl::GetBkColor](#getbkcolor)メソッドを変更が行われたことを確認します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="getbuttonsize"></a>  CPagerCtrl::GetButtonSize  
 現在のページャー コントロールのボタンのサイズを取得します。  
  
```  
int GetButtonSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のボタンのサイズは、ピクセル単位で測定されます。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_GETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760870)メッセージは、Windows SDK で説明します。  
  
 ボタンのサイズが、ページャー ボタンの幅を決定します、ページャー コントロールがスタイルの PGS_HORZ し、ボタンのサイズがページャー ボタンの高さを決定します、ページャー コントロールが PGS_VERT スタイル。 詳細については、次を参照してください。[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)します。  
  
##  <a name="getbuttonstate"></a>  CPagerCtrl::GetButtonState  
 現在のページャー コントロールの指定されたスクロール ボタンの状態を取得します。  
  
```  
DWORD GetButtonState(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*名前*|ボタンの状態を取得することを示します。 ページャー コントロールのスタイルが PGS_HORZ の場合は、右側のボタンの左ボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 ページャー コントロールのスタイルが PGS_VERT の場合は、下のボタンの上部にボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 詳細については、次を参照してください。[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)します。|  
  
### <a name="return-value"></a>戻り値  
 指定されたボタンの状態、*名前*パラメーター。 状態は PGF_INVISIBLE、PGF_NORMAL、PGF_GRAYED、PGF_DEPRESSED、または PGF_HOT です。 詳細については、の戻り値のセクションを参照してください、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージは、Windows SDK で説明します。  
  
##  <a name="getdroptarget"></a>  CPagerCtrl::GetDropTarget  
 取得、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)現在ページャー コントロールのインターフェイス。  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`IDropTarget`現在ページャー コントロールのインターフェイス。  
  
### <a name="remarks"></a>Remarks  
 `IDropTarget` 実装するインターフェイスの 1 つは、アプリケーションでドラッグ アンド ドロップ操作をサポートします。  
  
 このメソッドは、送信、 [PGM_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb760872)メッセージは、Windows SDK で説明します。 このメソッドの呼び出し元が通話を担当、`Release`のメンバー、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)インターフェイスのインターフェイスが不要になったとき。  
  
##  <a name="getscrollpos"></a>  CPagerCtrl::GetScrollPos  
 現在のページャー コントロールのスクロール位置を取得します。  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のスクロール位置はピクセル単位で測定されます。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_GETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760874)メッセージは、Windows SDK で説明します。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::GetScrollPos](#getscrollpos)ページャー コントロールの現在のスクロール位置を取得します。 この例では 0、左端の位置にページャー コントロールが既にスクロールいない場合、 [CPagerCtrl::SetScrollPos](#setscrollpos)スクロール位置を 0 に設定するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]  
  
##  <a name="isbuttondepressed"></a>  CPagerCtrl::IsButtonDepressed  
 現在のページャー コントロールの指定されたスクロール ボタンが押された状態かどうかを示します。  
  
```  
BOOL IsButtonDepressed(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*名前*|ボタンの状態を取得することを示します。 ページャー コントロールのスタイルが PGS_HORZ の場合は、右側のボタンの左ボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 ページャー コントロールのスタイルが PGS_VERT の場合は、下のボタンの上部にボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 詳細については、次を参照してください。[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)します。|  
  
### <a name="return-value"></a>戻り値  
 指定されたボタンが押された状態の場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージは、Windows SDK で説明します。 返される状態が PGF_DEPRESSED かどうかをテストします。 詳細については、の戻り値のセクションを参照してください、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
##  <a name="isbuttongrayed"></a>  CPagerCtrl::IsButtonGrayed  
 現在のページャー コントロールの指定されたスクロール ボタンが淡色表示の状態かどうかを示します。  
  
```  
BOOL IsButtonGrayed(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*名前*|ボタンの状態を取得することを示します。 ページャー コントロールのスタイルが PGS_HORZ の場合は、右側のボタンの左ボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 ページャー コントロールのスタイルが PGS_VERT の場合は、下のボタンの上部にボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 詳細については、次を参照してください。[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)します。|  
  
### <a name="return-value"></a>戻り値  
 指定したボタンが淡色表示の状態の場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージは、Windows SDK で説明します。 返される状態が PGF_GRAYED かどうかをテストします。 詳細については、の戻り値のセクションを参照してください、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
##  <a name="isbuttonhot"></a>  CPagerCtrl::IsButtonHot  
 現在のページャー コントロールの指定されたスクロール ボタンがホットな状態かどうかを示します。  
  
```  
BOOL IsButtonHot(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*名前*|ボタンの状態を取得することを示します。 ページャー コントロールのスタイルが PGS_HORZ の場合は、右側のボタンの左ボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 ページャー コントロールのスタイルが PGS_VERT の場合は、下のボタンの上部にボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 詳細については、次を参照してください。[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)します。|  
  
### <a name="return-value"></a>戻り値  
 指定したボタンがホットな状態の場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージは、Windows SDK で説明します。 返される状態が PGF_HOT かどうかをテストします。 詳細については、の戻り値のセクションを参照してください、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
##  <a name="isbuttoninvisible"></a>  CPagerCtrl::IsButtonInvisible  
 現在のページャー コントロールの指定されたスクロール ボタンが非表示の状態かどうかを示します。  
  
```  
BOOL IsButtonInvisible(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*名前*|ボタンの状態を取得することを示します。 ページャー コントロールのスタイルが PGS_HORZ の場合は、右側のボタンの左ボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 ページャー コントロールのスタイルが PGS_VERT の場合は、下のボタンの上部にボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 詳細については、次を参照してください。[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)します。|  
  
### <a name="return-value"></a>戻り値  
 指定したボタンが非表示の状態の場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 Windows、スクロール ボタン特定の方向に表示されない場合に、スクロールが端まで達するので、さらにボタンをクリックすることはできませんウィンドウの詳細を表示させます。  
  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージは、Windows SDK で説明します。 返される状態が PGF_INVISIBLE かどうかをテストします。 詳細については、の戻り値のセクションを参照してください、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)ページャー コントロールの左し、右スクロール ボタンが表示されるかどうかを判断するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]  
  
##  <a name="isbuttonnormal"></a>  CPagerCtrl::IsButtonNormal  
 現在のページャー コントロールの指定されたスクロール ボタンが通常の状態かどうかを示します。  
  
```  
BOOL IsButtonNormal(int iButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*名前*|ボタンの状態を取得することを示します。 ページャー コントロールのスタイルが PGS_HORZ の場合は、右側のボタンの左ボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 ページャー コントロールのスタイルが PGS_VERT の場合は、下のボタンの上部にボタンと PGB_BOTTOMORRIGHT PGB_TOPORLEFT を指定します。 詳細については、次を参照してください。[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)します。|  
  
### <a name="return-value"></a>戻り値  
 指定したボタンが通常の状態の場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージは、Windows SDK で説明します。 返される状態が PGF_NORMAL かどうかをテストします。 詳細については、の戻り値のセクションを参照してください、 [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871)メッセージ。  
  
##  <a name="recalcsize"></a>  CPagerCtrl::RecalcSize  
 現在のページャー コントロールのウィンドウのサイズを再計算させます。  
  
```  
void RecalcSize();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_RECALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760876)メッセージは、Windows SDK で説明します。 その結果、ページャー コントロールの送信、 [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864)通知ウィンドウのスクロール可能なディメンションを取得します。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::RecalcSize](#recalcsize)のサイズを再計算する現在のページャー コントロールを要求するメソッド。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]  
  
### <a name="example"></a>例  
 次の例では[メッセージ リフレクション](../../mfc/tn062-message-reflection-for-windows-controls.md)計算を実行するコントロールの親のダイアログを必要とするのではなく、独自のサイズを再計算するページャー コントロールを有効にします。 例では、`MyPagerCtrl`からクラス、 [CPagerCtrl クラス](../../mfc/reference/cpagerctrl-class.md)に関連付けるメッセージ マップを使用し、 [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864)通知と共に、`OnCalcsize`通知ハンドラー。 この例では、通知ハンドラーは、固定値にページャー コントロールの高さと幅を設定します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]  
  
##  <a name="setbkcolor"></a>  CPagerCtrl::SetBkColor  
 現在のページャー コントロールの背景色を設定します。  
  
```  
COLORREF SetBkColor(COLORREF clrBk);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*clrBk*|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)ページャー コントロールの新しい背景色を表す値です。|  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)ページャー コントロールの前の背景色を表す値です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760878)メッセージは、Windows SDK で説明します。  
  
### <a name="example"></a>例  
 次の例では、 [CPagerCtrl::SetBkColor](#setbkcolor)ページャー コントロールの背景色を赤に設定する方法と、 [CPagerCtrl::GetBkColor](#getbkcolor)メソッドを変更が行われたことを確認します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="setborder"></a>  CPagerCtrl::SetBorder  
 現在のページャー コントロールの境界線のサイズを設定します。  
  
```  
int SetBorder(int iBorder);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*iBorder*|新しい境界線のサイズは、ピクセル単位で測定されます。 場合、 *iBorder*パラメーターが負の値、境界線のサイズが 0 に設定されます。|  
  
### <a name="return-value"></a>戻り値  
 前の境界線のサイズは、ピクセル単位で測定されます。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_SETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760880)メッセージは、Windows SDK で説明します。  
  
### <a name="example"></a>例  
 次の例は、ページャー コントロールを作成しを使用して、 [CPagerCtrl::SetChild](#setchild)に非常に長いボタン コントロールにページャー コントロールを関連付けるメソッド。 使用して、 [CPagerCtrl::SetButtonSize](#setbuttonsize)に 20 ピクセルのページャー コントロールの高さを設定するメソッドを[CPagerCtrl::SetBorder](#setborder) 1 ピクセルに枠線の太さを設定します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setbuttonsize"></a>  CPagerCtrl::SetButtonSize  
 現在のページャー コントロールのボタンのサイズを設定します。  
  
```  
int SetButtonSize(int iButtonSize);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*iButtonSize*|新しいボタンのサイズは、ピクセル単位で測定されます。|  
  
### <a name="return-value"></a>戻り値  
 以前のボタンのサイズは、ピクセル単位で測定されます。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_SETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760886)メッセージは、Windows SDK で説明します。  
  
 ボタンのサイズが、ページャー ボタンの幅を決定します、ページャー コントロールがスタイルの PGS_HORZ し、ボタンのサイズがページャー ボタンの高さを決定します、ページャー コントロールが PGS_VERT スタイル。 既定のボタンのサイズは、スクロール バーの幅の 4 分の 3 つと、ボタンの最小サイズは 12 ピクセルです。 詳細については、次を参照してください。[ページャー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760859)します。  
  
### <a name="example"></a>例  
 次の例は、ページャー コントロールを作成しを使用して、 [CPagerCtrl::SetChild](#setchild)に非常に長いボタン コントロールにページャー コントロールを関連付けるメソッド。 使用して、 [CPagerCtrl::SetButtonSize](#setbuttonsize)に 20 ピクセルのページャー コントロールの高さを設定するメソッドを[CPagerCtrl::SetBorder](#setborder) 1 ピクセルに枠線の太さを設定します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setchild"></a>  CPagerCtrl::SetChild  
 現在のページャー コントロールの内側のウィンドウを設定します。  
  
```  
void SetChild(HWND hwndChild);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*hwndChild*|含まれるウィンドウへのハンドルします。|  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_SETCHILD](http://msdn.microsoft.com/library/windows/desktop/bb760884)メッセージは、Windows SDK で説明します。  
  
 このメソッドが含まれているウィンドウの親を変更していません。だけ、スクロールのページャー コントロールにウィンドウ ハンドルを割り当てます。 ほとんどの場合、コンテナー内のウィンドウは、ページャー コントロールの子ウィンドウになります。  
  
### <a name="example"></a>例  
 次の例は、ページャー コントロールを作成しを使用して、 [CPagerCtrl::SetChild](#setchild)に非常に長いボタン コントロールにページャー コントロールを関連付けるメソッド。 使用して、 [CPagerCtrl::SetButtonSize](#setbuttonsize)に 20 ピクセルのページャー コントロールの高さを設定するメソッドを[CPagerCtrl::SetBorder](#setborder) 1 ピクセルに枠線の太さを設定します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setscrollpos"></a>  CPagerCtrl::SetScrollPos  
 現在のページャー コントロールのスクロール位置を設定します。  
  
```  
void SetScrollPos(int iPos);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*iPos*|新しいスクロール位置はピクセル単位で測定されます。|  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [PGM_SETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760886)メッセージは、Windows SDK で説明します。  
  
## <a name="see-also"></a>関連項目  
 [CPagerCtrl クラス](../../mfc/reference/cpagerctrl-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ページャー コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760855)



