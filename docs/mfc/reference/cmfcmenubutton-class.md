---
title: CMFCMenuButton クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aae4caaa73970818a4c3deee9a82b94260629e17
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700914"
---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton クラス
ポップアップ メニューを表示してユーザーのメニュー選択を報告するボタンです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|`CMFCMenuButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|ディスパッチされる前に、ウィンドウ メッセージを変換するためにフレームワークによって呼び出されます。 (`CMFCButton::PreTranslateMessage` をオーバーライドします)。|  
|[CMFCMenuButton::SizeToContent](#sizetocontent)|そのテキストとイメージのサイズに応じてボタンのサイズを変更します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|使用するか、既定のシステムのポップアップ メニューを表示するかどうかを指定します[CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)します。|  
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|下にあるか、ボタンの右側に、ポップアップ メニューに表示されるかどうかを指定します。|  
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|メニュー ボタンが、ボタンを離した後に、状態を変更するかどうかを指定します。|  
|[CMFCMenuButton::m_hMenu](#m_hmenu)|関連付けられた Windows メニューへのハンドル。|  
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|項目を示す識別子、ユーザーは、ポップアップ メニューから選択します。|  
  
## <a name="remarks"></a>Remarks  
 `CMFCMenuButton`から派生したクラスは、 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)からさらに、派生元が、 [CButton クラス](../../mfc/reference/cbutton-class.md)します。 したがって、使用できる`CMFCMenuButton`、コードを使用する場合と同じ方法で`CButton`します。  
  
 作成するときに、 `CMFCMenuButton`、関連付けられたポップアップ メニューへのハンドルで渡す必要があります。 次に、関数を呼び出して`CMFCMenuButton::SizeToContent`します。 `CMFCMenuButton::SizeToContent` ボタンのサイズが、ポップアップ ウィンドウが表示される場所の下に具体的には、または、ボタンの右側に場所を指す矢印に含められることを確認します。  
  
## <a name="example"></a>例  
 次の例では、ボタン メニューのハンドルを設定し、テキストとイメージのサイズに応じてボタンのサイズを変更して、フレームワークによって表示されるポップアップ メニューを設定する方法を示します。 このコード スニペットの一部、[新しいコントロール サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmenubutton.h  
  
##  <a name="cmfcmenubutton"></a>  CMFCMenuButton::CMFCMenuButton  
 新しい[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)オブジェクト。  
  
```  
CMFCMenuButton();
```  
  
##  <a name="m_bosmenu"></a>  CMFCMenuButton::m_bOSMenu  
 ポップアップ メニューを示すブール型のメンバー変数、framework が表示されます。  
  
```  
BOOL m_bOSMenu;  
```  
  
### <a name="remarks"></a>Remarks  
 場合`m_bOSMenu`が true の場合、フレームワークは、継承された呼び出します`TrackPopupMenu`のこのオブジェクトのメソッド。 それ以外の場合、フレームワーク[CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)します。  
  
##  <a name="m_brightarrow"></a>  CMFCMenuButton::m_bRightArrow  
 ポップアップ メニューの場所を示すブール型のメンバー変数。  
  
```  
BOOL m_bRightArrow;  
```  
  
### <a name="remarks"></a>Remarks  
 ユーザーは、メニュー ボタンを押すと、アプリケーションには、ポップアップ メニューが表示されます。 フレームワークは、ボタンの下、または、ボタンの右側に、ポップアップ メニューに表示されます。 ボタンには、ポップアップ メニューが表示される場所を示す小さな矢印もあります。 場合`m_bRightArrow`が true の場合、フレームワーク、ボタンの右側に、ポップアップ メニューが表示されます。 それ以外の場合、ボタンの下のポップアップ メニューが表示されます。  
  
##  <a name="m_bstaypressed"></a>  CMFCMenuButton::m_bStayPressed  
 メニュー ボタンが表示されるかどうかを示すブール型のメンバー変数を押した、ユーザーは、ポップアップ メニューから選択します。  
  
```  
BOOL m_bStayPressed;  
```  
  
### <a name="remarks"></a>Remarks  
 場合、`m_bStayPressed`メンバーが FALSE で、メニュー ボタンが押されていないになる状態ときに、使用がボタンをクリックします。 この場合、フレームワークには、ポップアップ メニューのみが表示されます。  
  
 場合、`m_bStayPressed`メンバーは TRUE、ユーザーがボタンをクリックすると、メニュー ボタンが押されたになります。 ユーザーがいずれか、選択を行ったか、取り消すことによって、ポップアップ メニューを閉じた後まで押されたままです。  
  
##  <a name="m_hmenu"></a>  CMFCMenuButton::m_hMenu  
 関連付けられたメニューへのハンドル。  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="remarks"></a>Remarks  
 フレームワークには、ユーザーがメニュー ボタンをクリックすると、このメンバー変数によって示されるメニューが表示されます。  
  
##  <a name="m_nmenuresult"></a>  CMFCMenuButton::m_nMenuResult  
 どの項目を示す整数をユーザーは、ポップアップ メニューから選択します。  
  
```  
int m_nMenuResult;  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー変数の値は、メニューを選択せずに取り消された場合、またはエラーが発生した場合、0 です。  
  
##  <a name="pretranslatemessage"></a>  CMFCMenuButton::PreTranslateMessage  
 ディスパッチされる前に、ウィンドウ メッセージを変換するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
*pMsg*<br/>
[in]指す、 [MSG](../../mfc/reference/msg-structure1.md)処理するメッセージを含む構造体。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、メッセージが変換されたおよびディスパッチできないする必要があります。メッセージが変換されていないと、ディスパッチする必要がある場合は 0。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="sizetocontent"></a>  CMFCMenuButton::SizeToContent  
 テキストのサイズとイメージのサイズに応じてボタンのサイズを変更します。  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
*bCalcOnly*<br/>
[in]このメソッドが、ボタンをサイズ変更するかどうかを示すブール値パラメーター。  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)ボタンの新しいサイズを指定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この関数を呼び出す場合と*bCalcOnly*が true の場合、`SizeToContent`ボタンの新しいサイズのみが計算されます。  
  
 ボタンのテキスト、イメージ、および矢印に合わせてボタンの新しいサイズが計算されます。 フレームワークは、水平方向の端に 10 ピクセルおよび垂直方向の端の 5 ピクセルの定義済みのマージンでも追加します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)
