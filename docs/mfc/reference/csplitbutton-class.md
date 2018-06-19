---
title: CSplitButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
dev_langs:
- C++
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac4241bb19c6abc0fbbf489bf4efb43f56ede72e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374225"
---
# <a name="csplitbutton-class"></a>CSplitButton クラス
`CSplitButton`クラスは、分割ボタン コントロールを表します。 分割ボタン コントロールは、ユーザーがボタンのメイン領域をクリックすると既定の動作を実行し、ユーザーがボタンのドロップダウン矢印をクリックするとドロップダウン メニューを表示します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSplitButton : public CButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](#csplitbutton)|`CSplitButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitButton::Create](#create)|指定したスタイルを使用して分割ボタン コントロールを作成し、現在アタッチ`CSplitButton`オブジェクト。|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに表示されるドロップダウン メニューを設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|処理、`BCN_DROPDOWN`システムは、ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに、送信される通知です。|  
  
## <a name="remarks"></a>コメント  
 `CSplitButton`から派生したクラスは、 [CButton](../../mfc/reference/cbutton-class.md)クラスです。 分割ボタン コントロールは、スタイルが button コントロール`BS_SPLITBUTTON`です。 ユーザーがドロップダウン矢印をクリックしたときに、カスタムのメニューが表示されます。 詳細については、次を参照してください。、`BS_SPLITBUTTON`と`BS_DEFSPLITBUTTON`でスタイル[ボタン スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775951)です。  
  
 次の図は、ページャー コントロールと (1) 分割ボタン コントロールを含むダイアログ ボックスを示しています。 既に (2) のドロップダウン矢印をクリックし、(3) のサブメニューを表示します。  
  
 ![Splitbutton およびページャー コントロールを持つダイアログ。] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
 このクラスではサポートされて[!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]およびそれ以降。  
  
 このクラスの追加要件が記載[ビルドの要件の Windows Vista コモン コントロール](../../mfc/build-requirements-for-windows-vista-common-controls.md)です。  
  
##  <a name="create"></a>  CSplitButton::Create  
 指定したスタイルを使用して分割ボタン コントロールを作成し、現在アタッチ`CSplitButton`オブジェクト。  
  
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
|[入力] `dwStyle`|コントロールに適用されるスタイルのビットごとの組み合わせ (OR)。 詳細については、次を参照してください。[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)です。|  
|[入力] `rect`|参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)コントロールのサイズと位置を格納する構造体。|  
|[入力] `pParentWnd`|Null 以外のポインター、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。|  
|[入力] `nID`|コントロールの ID。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
##  <a name="csplitbutton"></a>  CSplitButton::CSplitButton  
 `CSplitButton` オブジェクトを構築します。 コンス トラクターのパラメーターは、ユーザーが分割ボタン コントロールのドロップダウン矢印をクリックしたときに表示されるサブメニューを指定します。  
  
```  
CSplitButton();

 
CSplitButton(
    UINT nMenuId,   
    UINT nSubMenuId)  
CSplitButton(CMenu* pMenu)  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nMenuId`|メニュー バーのリソース ID です。|  
|[入力] `nSubMenuId`|サブメニューのリソース ID です。|  
|[入力] `pMenu`|ポインター、 [CMenu](../../mfc/reference/cmenu-class.md)サブメニューを指定するオブジェクト。 `CSplitButton`オブジェクトの削除、`CMenu`オブジェクトとそれに関連する`HMENU`ときに、`CSplitButton`オブジェクトがスコープから外れます。|  
  
### <a name="remarks"></a>コメント  
 使用して、 [CSplitButton::Create](#create)分割ボタン コントロールを作成しをアタッチする方法、`CSplitButton`オブジェクト。  
  
##  <a name="ondropdown"></a>  CSplitButton::OnDropDown  
 処理、`BCN_DROPDOWN`システムは、ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに、送信される通知です。  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pNMHDR`|ポインター、 [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514)に関する情報を格納する構造体、 [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983)通知します。|  
|[出力] `pResult`|(使用されません。 値は返されません)。値を返す、 [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983)通知します。|  
  
### <a name="remarks"></a>コメント  
 ユーザーは、分割ボタン コントロールのドロップダウン矢印をクリックすると、システムの送信、`BCN_DROPDOWN`通知のメッセージを`OnDropDown`メソッドのハンドル。 ただし、`CSplitButton`オブジェクトを転送しません、`BCN_DROPDOWN`分割ボタン コントロールを含むコントロールに通知します。 その結果、格納しているコントロールは、通知に対する応答でカスタム動作をサポートできません。  
  
 コンテナー コントロールをサポートするカスタム動作を実装するには、使用、 [CButton](../../mfc/reference/cbutton-class.md)のスタイルを持つオブジェクト`BS_SPLITBUTTON`の代わりに、`CSplitButton`オブジェクト。 ハンドラーを実装し、`BCN_DROPDOWN`通知で、`CButton`オブジェクト。 詳細については、次を参照してください。[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)です。  
  
 カスタム動作、分割ボタン コントロール自体でサポートを実装するには、使用[メッセージ リフレクション](../../mfc/tn062-message-reflection-for-windows-controls.md)です。 独自のクラスを派生させる、`CSplitButton`クラスし、名前を付け、CMySplitButton などです。 処理するアプリケーションに、次のメッセージ マップを追加、`BCN_DROPDOWN`通知。  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="setdropdownmenu"></a>  CSplitButton::SetDropDownMenu  
 ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに表示されるドロップダウン メニューを設定します。  
  
```  
void SetDropDownMenu(
    UINT nMenuId,   
    UINT nSubMenuId);  
  
void SetDropDownMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nMenuId`|メニュー バーのリソース ID です。|  
|[入力] `nSubMenuId`|サブメニューのリソース ID です。|  
|[入力] `pMenu`|ポインター、 [CMenu](../../mfc/reference/cmenu-class.md)サブメニューを指定するオブジェクト。 `CSplitButton`オブジェクトの削除、`CMenu`オブジェクトとそれに関連する`HMENU`ときに、`CSplitButton`オブジェクトがスコープから外れます。|  
  
### <a name="remarks"></a>コメント  
 `nMenuId`パラメーターがあるメニュー バー項目の水平方向の一覧、メニュー バーを識別します。 `nSubMenuId`パラメーターは、各メニュー バー項目に関連付けられているメニュー項目のドロップダウン リストである、サブメニューを識別する 0 から始まるインデックス番号します。 たとえば、一般的なアプリケーションが含むメニューがメニュー バー項目、"File"、"Edit"および"Help"です。 "File"メニュー バー項目がメニュー項目を含むサブメニューを「開くには、」「閉じる」および"Exit"です。 分割ボタン コントロールのドロップダウン矢印をクリックすると、コントロールはメニュー バーではなく、指定のサブメニューを表示します。  
  
 次の図は、ページャー コントロールと (1) 分割ボタン コントロールを含むダイアログ ボックスを示しています。 既に (2) のドロップダウン矢印をクリックし、(3) のサブメニューを表示します。  
  
 ![Splitbutton およびページャー コントロールを持つダイアログ。] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
### <a name="example"></a>例  
 次のコード例の最初のステートメントを示しています、 [CSplitButton::SetDropDownMenu](#setdropdownmenu)メソッドです。 お、メニュー、Visual Studio 作成したリソース エディターは、メニュー バー ID を自動的に名前付き、`IDR_MENU1`です。 `nSubMenuId`は 0 で、パラメーターは、メニュー バーの唯一のサブメニューを指します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CSplitButton クラス](../../mfc/reference/csplitbutton-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)
