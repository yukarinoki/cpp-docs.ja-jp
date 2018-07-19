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
ms.openlocfilehash: fbced65aa76206d040ff1c13267fe9b7d3c69eca
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122788"
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
|[CSplitButton::OnDropDown](#ondropdown)|システムは、ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに、送信 BCN_DROPDOWN 通知を処理します。|  
  
## <a name="remarks"></a>Remarks  
 `CSplitButton`から派生したクラスは、 [CButton](../../mfc/reference/cbutton-class.md)クラスです。 分割ボタン コントロールは、スタイルが button コントロールです。 ユーザーがドロップダウン矢印をクリックしたときに、カスタムのメニューが表示されます。 詳細についてで BS_SPLITBUTTON と BS_DEFSPLITBUTTON のスタイルを参照してください。[ボタン スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775951)です。  
  
 次の図は、ページャー コントロールと (1) 分割ボタン コントロールを含むダイアログ ボックスを示しています。 既に (2) のドロップダウン矢印をクリックし、(3) のサブメニューを表示します。  
  
 ![Splitbutton およびページャー コントロールを持つダイアログ。] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>必要条件  
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
|[in]*dwStyle*|コントロールに適用されるスタイルのビットごとの組み合わせ (OR)。 詳細については、次を参照してください。[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)です。|  
|[in]*rect*|参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)コントロールのサイズと位置を格納する構造体。|  
|[in]*pParentWnd*|Null 以外のポインター、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。|  
|[in]*nID*|コントロールの ID。|  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は TRUE。それ以外の場合は FALSE です。  
  
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
|[in]*nMenuId*|メニュー バーのリソース ID です。|  
|[in]*nSubMenuId*|サブメニューのリソース ID です。|  
|[in]*pMenu*|ポインター、 [CMenu](../../mfc/reference/cmenu-class.md)サブメニューを指定するオブジェクト。 `CSplitButton`オブジェクトの削除、`CMenu`オブジェクトとその関連付けられた HMENU ときに、`CSplitButton`オブジェクトがスコープから外れます。|  
  
### <a name="remarks"></a>Remarks  
 使用して、 [CSplitButton::Create](#create)分割ボタン コントロールを作成しをアタッチする方法、`CSplitButton`オブジェクト。  
  
##  <a name="ondropdown"></a>  CSplitButton::OnDropDown  
 システムは、ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに、送信 BCN_DROPDOWN 通知を処理します。  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*pNMHDR*|ポインター、 [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514)に関する情報を格納する構造体、 [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983)通知します。|  
|[out]*pResult*|(使用されません。 値は返されません)。値を返す、 [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983)通知します。|  
  
### <a name="remarks"></a>Remarks  
 ユーザーは、分割ボタン コントロールのドロップダウン矢印をクリックすると、システム通知を送信します BCN_DROPDOWN のメッセージを`OnDropDown`メソッドのハンドル。 ただし、`CSplitButton`オブジェクトは、分割ボタン コントロールを含むコントロールへ BCN_DROPDOWN 通知を転送しません。 その結果、格納しているコントロールは、通知に対する応答でカスタム動作をサポートできません。  
  
 コンテナー コントロールをサポートするカスタム動作を実装するには、使用、 [CButton](../../mfc/reference/cbutton-class.md)の代わりに BS_SPLITBUTTON のスタイルを持つオブジェクト、`CSplitButton`オブジェクト。 BCN_DROPDOWN 通知のハンドラーを実装し、`CButton`オブジェクト。 詳細については、次を参照してください。[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)です。  
  
 カスタム動作、分割ボタン コントロール自体でサポートを実装するには、使用[メッセージ リフレクション](../../mfc/tn062-message-reflection-for-windows-controls.md)です。 独自のクラスを派生させる、`CSplitButton`クラスし、名前を付け、CMySplitButton などです。 BCN_DROPDOWN 通知を処理するアプリケーションに、次のメッセージ マップを追加します。  
  
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
|[in]*nMenuId*|メニュー バーのリソース ID です。|  
|[in]*nSubMenuId*|サブメニューのリソース ID です。|  
|[in]*pMenu*|ポインター、 [CMenu](../../mfc/reference/cmenu-class.md)サブメニューを指定するオブジェクト。 `CSplitButton`オブジェクトの削除、`CMenu`オブジェクトとその関連付けられた HMENU ときに、`CSplitButton`オブジェクトがスコープから外れます。|  
  
### <a name="remarks"></a>Remarks  
 *NMenuId*パラメーターがあるメニュー バー項目の水平方向の一覧、メニュー バーを識別します。 *NSubMenuId*パラメーターは、各メニュー バー項目に関連付けられているメニュー項目のドロップダウン リストである、サブメニューを識別する 0 から始まるインデックス番号します。 たとえば、一般的なアプリケーションが含むメニューがメニュー バー項目、"File"、"Edit"および"Help"です。 "File"メニュー バー項目がメニュー項目を含むサブメニューを「開くには、」「閉じる」および"Exit"です。 分割ボタン コントロールのドロップダウン矢印をクリックすると、コントロールはメニュー バーではなく、指定のサブメニューを表示します。  
  
 次の図は、ページャー コントロールと (1) 分割ボタン コントロールを含むダイアログ ボックスを示しています。 既に (2) のドロップダウン矢印をクリックし、(3) のサブメニューを表示します。  
  
 ![Splitbutton およびページャー コントロールを持つダイアログ。] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
### <a name="example"></a>例  
 次のコード例の最初のステートメントを示しています、 [CSplitButton::SetDropDownMenu](#setdropdownmenu)メソッドです。 Visual Studio のリソースがある、メニュー エディターで、メニュー バーの ID、IDR_MENU1 の名前を自動的に作成しました。 *NSubMenuId*は 0 で、パラメーターは、メニュー バーの唯一のサブメニューを指します。  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CSplitButton クラス](../../mfc/reference/csplitbutton-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)
