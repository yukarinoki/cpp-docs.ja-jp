---
title: CMFCDesktopAlertWndInfo クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b775b06f605edc68c6f1dbe47035d9ecf214b396
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo クラス
`CMFCDesktopAlertWndInfo`クラスが使用されて、 [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)です。 デスクトップ通知ウィンドウがポップアップする場合に表示されるコントロールを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[アイコン](#m_hicon)|表示されるアイコンへのハンドル。|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|デスクトップ通知ウィンドウ上のリンクに関連付けられているコマンド ID。|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|デスクトップ通知ウィンドウに表示されるテキストです。|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|デスクトップ通知ウィンドウに表示されるリンク。|  
  
## <a name="remarks"></a>コメント  
 `CMFCDesktopAlertWndInfo`クラスに渡される、 [cmfcdesktopalertwnd::create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)デスクトップ通知ウィンドウの既定のダイアログ ボックスに表示される要素を指定します。 既定のダイアログ ボックスでは、3 つの項目を含めることができます。  
  
-   アイコンは、呼び出すことによって設定されている[アイコン](#m_hicon)です。  
  
-   ラベル、またはテキスト メッセージは、呼び出すことによって設定されている[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)です。  
  
-   呼び出して設定されているリンク[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)です。 リンクがクリックされたときに実行されるコマンドを設定するには、呼び出す[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)です。  
  
 既定のダイアログ ボックスが十分でない場合は、カスタム ダイアログを作成し、渡すこと、 [cmfcdesktopalertwnd::create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)メソッドをこのクラスを使用する代わりにします。 詳細については、次を参照してください。 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)です。  
  
## <a name="example"></a>例  
 次の例でさまざまなメンバーを使用して、`CMFCDesktopAlertWndInfo`クラスです。 例では、デスクトップ通知ウィンドウ、デスクトップの通知ウィンドウに表示されているリンクおよびデスクトップ通知ウィンドウ上のリンクに関連付けられているコマンド ID で表示されるテキスト、アイコン、表示されるハンドルを設定する方法を示します。 この例の一部である、[デスクトップ アラート デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxDesktopAlertDialog.h  
  
##  <a name="operator_eq"></a>  CMFCDesktopAlertWndInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_hicon"></a>  アイコン  
 表示されるアイコンへのハンドル。  
  
```  
HICON m_hIcon;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_nurlcmdid"></a>  CMFCDesktopAlertWndInfo::m_nURLCmdID  
 デスクトップ通知ウィンドウ上のリンクに関連付けられているコマンド ID。  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>コメント  
 コマンド ID で指定されたリンクをクリックするユーザーのポップアップ ウィンドウの所有者に送信される[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)です。  
  
##  <a name="m_strtext"></a>  CMFCDesktopAlertWndInfo::m_strText  
 デスクトップ通知ウィンドウに表示されるテキストです。  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_strurl"></a>  CMFCDesktopAlertWndInfo::m_strURL  
 デスクトップ通知ウィンドウに表示されるリンク。  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>コメント  
 ユーザーは、リンクをクリックすると、コマンドを含む、 [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)コマンド ID は、ポップアップ ウィンドウの所有者に送信されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [Cmfcdesktopalertwnd::create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)
