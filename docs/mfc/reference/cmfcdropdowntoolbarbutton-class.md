---
title: CMFCDropDownToolbarButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c894ff57bbbee59842f56dbfef0ec06a6c7899f
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041696"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton クラス
ツール バー ボタンの一種で、クリックされたときは標準ボタンと同じように動作します。 ただし、ドロップダウン ツールバーを開きます ( [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)ユーザーが押すし、ツール バー ボタンを押したままかどうか。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|`CMFCDropDownToolbarButton` オブジェクトを構築します。|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|現在のボタンに別のツール バー ボタンのプロパティをコピーします。 (上書き[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom))。|  
|`CMFCDropDownToolbarButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|ドロップダウン ツールバーを開きます。|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|メニュー、ツールバーのボタンのテキストをコピーします。 (上書き[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton))。|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|ボタンに関連付けられているドロップダウン ツールバーを取得します。|  
|`CMFCDropDownToolbarButton::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|ドロップダウン ツールバーが現在開いているかどうかを判断します。|  
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|拡張された境界で、ボタンを表示できるかどうかを判断します。 (上書き[CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize))。|  
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|指定したデバイス コンテキストとドッキングの状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))。|  
|`CMFCDropDownToolbarButton::OnCancelMode`|処理するためにフレームワークによって呼び出される、 [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615)メッセージ。 (`CMCToolBarButton::OnCancelMode` をオーバーライドします)。|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd))。|  
|[CMFCDropDownToolbarButton::OnClick](#onclick)|ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick))。|  
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|ユーザーがマウス ボタンを離したときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup))。|  
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|親ツールバーを処理するときに、フレームワークによって呼び出されます、`WM_HELPHITTEST`メッセージ。 (上書き[CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp))。|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|アプリケーションは、親ツールバーのショートカット メニューを表示するときは、指定されたメニューを変更します。 (上書き[CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu))。|  
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw))。|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|ボタンを描画するためにフレームワークによって呼び出される、**コマンド**のペイン、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist))。|  
|[CMFCDropDownToolbarButton::Serialize](#serialize)|アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。 (上書き[CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize))。|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|ユーザーがボタンをクリックしたときにフレームワークによって使用される既定のコマンドを設定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|ユーザー必要がありますを押しながらマウスのボタン、ドロップダウン ツールバーが表示されるまで時間の長さを指定します。|  
  
## <a name="remarks"></a>Remarks  
 A`CMFCDropDownToolBarButton`ボタンの右下隅にある小さい矢印がある点で通常のボタンは異なります。 ユーザーは、ドロップダウン ツールバーからボタンを選択、フレームワークには、トップレベルのツール バー ボタン (右下隅にある小さな矢印の付いたボタン) でそのアイコンが表示されます。  
  
 ドロップダウン ツールバーを実装する方法については、次を参照してください。 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)です。  
  
 `CMFCDropDownToolBarButton`にオブジェクトをエクスポートできる、 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)オブジェクトし、ポップアップ メニューにメニュー ボタンとして表示されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdropdowntoolbar.h  
  
##  <a name="copyfrom"></a>  CMFCDropDownToolbarButton::CopyFrom  
 現在のボタンに別のツール バー ボタンのプロパティをコピーします。  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*src*  
 コピー元のソース ボタンへの参照。  
  
### <a name="remarks"></a>Remarks  
 このツール バー ボタンに別のツール バー ボタンをコピーするには、このメソッドを呼び出します。 *src*型でなければなりません`CMFCDropDownToolbarButton`です。  
  
##  <a name="cmfcdropdowntoolbarbutton"></a>  CMFCDropDownToolbarButton::CMFCDropDownToolbarButton  
 `CMFCDropDownToolbarButton` オブジェクトを構築します。  
  
```  
CMFCDropDownToolbarButton();

 
CMFCDropDownToolbarButton(
    LPCTSTR lpszName,  
    CMFCDropDownToolBar* pToolBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszName*  
 ボタンの既定のテキスト。  
  
 [in]*pToolBar*  
 ポインター、`CMFCDropDownToolBar`ユーザーがボタンを押したときに表示されるオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 コンス トラクターの 2 番目のオーバー ロードは、ドロップダウン ボタンに最初のボタンからコピー ツールバーを*pToolBar*を指定します。  
  
 通常、ドロップダウン ツールバーのボタンがツールバーに、最近使用したボタンのテキストを使用する*pToolBar*を指定します。 によって指定されたテキストを使用して*lpszName*ボタンがメニュー ボタンに変換またはに表示される、**コマンド**のタブ、**カスタマイズ** ダイアログ ボックス。 詳細については、**カスタマイズ**ダイアログ ボックスを参照してください[CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)です。  
  
### <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCDropDownToolbarButton`クラスです。 このコード スニペットの一部である、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]  
  
##  <a name="dropdowntoolbar"></a>  CMFCDropDownToolbarButton::DropDownToolbar  
 ドロップダウン ツールバーを開きます。  
  
```  
BOOL DropDownToolbar(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWnd*  
 ドロップダウンのフレームの親ウィンドウまたは`NULL`ドロップダウン ツールバーのボタンの親ウィンドウを使用します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 [CMFCDropDownToolbarButton::OnClick](#onclick)メソッドをユーザーがツール バー ボタンを押したまま押し続けたときに、ドロップダウン ツールバーを開くには、このメソッドを呼び出します。  
  
 このメソッドを使用して、ドロップダウン ツールバーを作成する、 [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create)メソッドです。 親ツールバーが垂直方向にドッキングされている場合このメソッドは配置ドロップダウン ツールバーに収まるように応じて、親ツールバーの左側または右側の側のいずれか。 それ以外の場合、このメソッドは、親ツールバーの下にあるドロップダウン ツールバーを配置します。  
  
 このメソッドは失敗*pWnd*は`NULL`し、ドロップダウン ツールバーのボタンには、親ウィンドウはありません。  
  
##  <a name="exporttomenubutton"></a>  CMFCDropDownToolbarButton::ExportToMenuButton  
 メニュー、ツールバーのボタンのテキストをコピーします。  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*メニュー ボタン*  
 対象のメニュー ボタンへの参照。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、基本クラスの実装を呼び出します ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) し、各ツールバーのメニュー項目では、このボタンを含むポップアップ メニューにターゲット メニュー ボタンを追加します。 このメソッドは、ポップアップ メニューにサブメニューを追加しません。  
  
 場合、このメソッドが失敗した親ツールバー`m_pToolBar`は`NULL`基底クラスの実装を返しますまたは`FALSE`です。  
  
##  <a name="getdropdowntoolbar"></a>  CMFCDropDownToolbarButton::GetDropDownToolBar  
 ボタンに関連付けられているドロップダウン ツールバーを取得します。  
  
```  
CMFCToolBar* GetDropDownToolBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンに関連付けられているドロップダウン ツールバー。  
  
### <a name="remarks"></a>Remarks  
 このメソッドが戻る、`m_pToolBar`データ メンバーです。  
  
##  <a name="isdropdown"></a>  CMFCDropDownToolbarButton::IsDropDown  
 ドロップダウン ツールバーが現在開いているかどうかを判断します。  
  
```  
BOOL IsDropDown() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドロップダウン ツールバーが現在開いている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 フレームワークを使用して、ドロップダウン ツールバーを開き、 [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)メソッドです。 フレームワークは、ユーザーは、ドロップダウン ツールバーの非クライアント領域でマウスの左ボタンを押したときに、ドロップダウン ツールバーを閉じます。  
  
##  <a name="isextrasize"></a>  CMFCDropDownToolbarButton::IsExtraSize  
 拡張された境界で、ボタンを表示できるかどうかを判断します。  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 拡張境界で、ツール バー ボタンを表示できる場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 拡張の罫線の詳細については、次を参照してください。 [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize)です。  
  
##  <a name="m_uishowbardelay"></a>  CMFCDropDownToolbarButton::m_uiShowBarDelay  
 ユーザー必要がありますを押しながらマウスのボタン、ドロップダウン ツールバーが表示されるまで時間の長さを指定します。  
  
```  
static UINT m_uiShowBarDelay;  
```  
  
### <a name="remarks"></a>Remarks  
 遅延時間はミリ秒単位で測定されます。 既定値は 500 です。 別の遅延を設定するには、この共有のデータ メンバーの値を変更します。  
  
##  <a name="oncalculatesize"></a>  CMFCDropDownToolbarButton::OnCalculateSize  
 指定したデバイス コンテキストとドッキングの状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 ボタンを表示しているデバイス コンテキスト。  
  
 [in]*sizeDefault*  
 ボタンの既定のサイズ。  
  
 [in]*bHorz*  
 親ツールバーのドッキング状態です。 このパラメーターは`TRUE`か、ツールバーが水平にドッキングされているが浮動小数点型、または`FALSE`ツールバーが垂直方向にドッキングされている場合。  
  
### <a name="return-value"></a>戻り値  
 A `SIZE` (ピクセル単位)、ボタンのサイズを格納する構造体。  
  
### <a name="remarks"></a>Remarks  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))、ボタンのサイズの水平方向にドロップダウンの矢印の幅を追加しています。  
  
##  <a name="onchangeparentwnd"></a>  CMFCDropDownToolbarButton::OnChangeParentWnd  
 新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndParent*  
 新しい親ウィンドウです。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) をテキスト ラベルをオフにして ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) と設定、 [CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext)と[CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton)データ メンバーに`FALSE`です。  
  
##  <a name="onclick"></a>  CMFCDropDownToolbarButton::OnClick  
 ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWnd*  
 ツール バー ボタンの親ウィンドウです。  
  
 [in]*bDelay*  
 `TRUE` 場合は、メッセージは、遅延で処理する必要があります。  
  
### <a name="return-value"></a>戻り値  
 ボタンをクリックしてメッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドが基底クラスの実装を拡張[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)、ドロップダウン ツールバーの状態を更新しています。  
  
 このメソッドがで指定した時間の長さが待機するタイマーを作成するユーザーには、ツールバーのボタンがクリックすると、ときに、 [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)データ メンバーとし、を使用して開き、ドロップダウンツールバー[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)メソッドです。 このメソッドは、ユーザーがツール バー ボタンをクリックした 2 回目に、ドロップダウン ツールバーを閉じます。  
  
##  <a name="onclickup"></a>  CMFCDropDownToolbarButton::OnClickUp  
 ユーザーがマウス ボタンを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>戻り値  
 ボタンをクリックしてメッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドが基底クラスの実装を拡張[CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)、ドロップダウン ツールバーの状態を更新しています。  
  
 このメソッドは、アクティブである場合、ドロップダウン ツールバー タイマーを停止します。 開いている場合は、ドロップダウン ツールバーを閉じます。  
  
 詳細について、ドロップダウン ツールバーとツールバーのドロップダウン タイマーは、次を参照してください。 [CMFCDropDownToolbarButton::OnClick](#onclick)です。  
  
##  <a name="oncontexthelp"></a>  CMFCDropDownToolbarButton::OnContextHelp  
 親ツールバーを処理するときに、フレームワークによって呼び出されます、`WM_HELPHITTEST`メッセージ。  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWnd*  
 ツール バー ボタンの親ウィンドウです。  
  
### <a name="return-value"></a>戻り値  
 ボタンは、のヘルプ メッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) を呼び出して、 [CMFCDropDownToolbarButton::OnClick](#onclick)メソッドを*bDelay*'éý'`FALSE`です。 このメソッドによって返される値を返します[CMFCDropDownToolbarButton::OnClick](#onclick)です。  
  
 詳細については、 `WM_HELPHITTEST message, see` [TN028: 状況依存ヘルプ サポート](../../mfc/tn028-context-sensitive-help-support.md)です。  
  
##  <a name="oncustomizemenu"></a>  CMFCDropDownToolbarButton::OnCustomizeMenu  
 アプリケーションは、親ツールバーのショートカット メニューを表示するときは、指定されたメニューを変更します。  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pMenu*  
 メニューをカスタマイズします。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは `TRUE` を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) を次のメニュー項目を無効にします。  
  
- **ボタン イメージのコピー**  
  
- **ボタンの外観**  
  
- **イメージ**  
  
- **[テキスト]**  
  
- **イメージとテキスト**  
  
 カスタマイズ モードに、フレームワークによって表示されるショートカット メニューを変更するには、このメソッドをオーバーライドします。  
  
##  <a name="ondraw"></a>  CMFCDropDownToolbarButton::OnDraw  
 指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 ボタンを表示しているデバイス コンテキスト。  
  
 [in]*rect*  
 ボタンの外接する四角形。  
  
 [in]*pImages*  
 ボタンに関連付けられているツール バー イメージのコレクション。  
  
 [in]*bHorz*  
 親ツールバーのドッキング状態です。 このパラメーターは`TRUE`ボタンが水平にドッキングされているときと`FALSE`ボタンが垂直方向にドッキングされているとき。  
  
 [in]*bCustomizeMode*  
 ツールバーをカスタマイズ モードであるかどうかを指定します。 このパラメーターは`TRUE`ツールバーがカスタマイズ モードの場合と`FALSE`ときに、ツールバー モードではないカスタマイズします。  
  
 [in]*bHighlight*  
 ボタンが強調表示されているかどうかを指定します。 このパラメーターは`TRUE`ボタンが強調表示されていると`FALSE`ときに、ボタンが強調表示されません。  
  
 [in]*bDrawBorder*  
 ボタンの境界線を表示する必要があるかどうかを指定します。 このパラメーターは`TRUE`ボタンが枠線を表示する場合と`FALSE`ときに、ボタンを表示しないでの境界線です。  
  
 [in]*bGrayDisabledButtons*  
 無効なボタンに影を付けるか、無効なイメージのコレクションを使用するかどうかを指定します。 このパラメーターは`TRUE`無効なボタンが淡色表示されている必要がありますの場合と`FALSE`このメソッドが、無効なイメージのコレクションを使用するとします。  
  
### <a name="remarks"></a>Remarks  
 ツールバーのボタンの描画をカスタマイズするには、このメソッドをオーバーライドします。  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCDropDownToolbarButton::OnDrawOnCustomizeList  
 ボタンを描画するためにフレームワークによって呼び出される、**コマンド**のペイン、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 ボタンを表示しているデバイス コンテキスト。  
  
 [in]*rect*  
 ボタンの外接する四角形。  
  
 [in]*bSelected*  
 かどうか、ボタンが選択されます。 このパラメーターが場合`TRUE`ボタンが選択されています。 このパラメーターが場合`FALSE`ボタンが選択されていません。  
  
### <a name="return-value"></a>戻り値  
 指定したデバイス コンテキストにあるボタンのピクセル単位の幅。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、カスタマイズ ダイアログ ボックス (**コマンド** タブ)、ボタンがオーナー描画リスト ボックスに表示するために必要な場合です。  
  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist))、ボタンの名前に、ボタンのテキスト ラベルを変更することで (つまりの値に、`lpszName`渡されたパラメーターコンス トラクターに)。  
  
##  <a name="serialize"></a>  CMFCDropDownToolbarButton::Serialize  
 アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ar*  
 `CArchive`元またはシリアル化するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) の親ツールバー リソース ID をシリアル化しています。 アーカイブの読み込み時 ([場合](../../mfc/reference/carchive-class.md#isloading)0 以外の値を返します)、このメソッドを設定、`m_pToolBar`データ メンバーをシリアル化されたリソース ID を含むツールバー  
  
##  <a name="setdefaultcommand"></a>  CMFCDropDownToolbarButton::SetDefaultCommand  
 ユーザーがボタンをクリックしたときにフレームワークによって使用される既定のコマンドを設定します。  
  
```  
void SetDefaultCommand(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiCmd*  
 既定のコマンドの ID です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出して、ユーザーがボタンをクリックしたときに、フレームワークが実行される既定のコマンドを指定します。 指定されたコマンド ID を持つ項目*uiCmd*親ドロップダウン ツールバーにある必要があります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)



