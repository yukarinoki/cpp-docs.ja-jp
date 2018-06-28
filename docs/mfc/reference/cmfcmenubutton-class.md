---
title: CMFCMenuButton クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 09d68cd7c0e4796b3368e1167888d703d37a8cf8
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040169"
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
|[CMFCMenuButton::SizeToContent](#sizetocontent)|そのテキストおよびイメージのサイズに応じてボタンのサイズを変更します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|既定のシステムのポップアップ メニューを表示するか、使用するかどうかを示す[CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)です。|  
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|下にあるか、ボタンの右側に、ポップアップ メニューに表示されるかどうかを指定します。|  
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|メニュー ボタンがボタンを離す後に、状態を変更するかどうかを指定します。|  
|[CMFCMenuButton::m_hMenu](#m_hmenu)|関連付けられた Windows メニューへのハンドル。|  
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|項目を示す識別子、ユーザーは、ポップアップ メニューから選択します。|  
  
## <a name="remarks"></a>Remarks  
 `CMFCMenuButton`から派生したクラスは、 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)から派生した、さらに、 [CButton クラス](../../mfc/reference/cbutton-class.md)です。 したがって、使用することができます`CMFCMenuButton`、コードを使用すると同じ方法で`CButton`です。  
  
 作成するときに、 `CMFCMenuButton`、関連付けられたポップアップ メニューへのハンドルに渡す必要があります。 次に、関数を呼び出す`CMFCMenuButton::SizeToContent`です。 `CMFCMenuButton::SizeToContent` ボタンのサイズは、ポップアップ ウィンドウが表示される場所、つまり、下にあるか、ボタンの右側に場所を指す矢印を含めるための十分なことを確認します。  
  
## <a name="example"></a>例  
 次の例では、ボタン メニューのハンドルを設定し、テキストおよびイメージのサイズに応じてボタンのサイズを変更して、フレームワークによって表示されるポップアップ メニューを設定する方法を示します。 このコード スニペットの一部である、[新しいコントロール サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxmenubutton.h  
  
##  <a name="cmfcmenubutton"></a>  CMFCMenuButton::CMFCMenuButton  
 新しい[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)オブジェクト。  
  
```  
CMFCMenuButton();
```  
  
##  <a name="m_bosmenu"></a>  CMFCMenuButton::m_bOSMenu  
 ポップアップ メニューを示すブール型のメンバー変数、フレームワークが表示されます。  
  
```  
BOOL m_bOSMenu;  
```  
  
### <a name="remarks"></a>Remarks  
 場合`m_bOSMenu`は`TRUE`、フレームワーク、継承された`TrackPopupMenu`このオブジェクトのメソッドです。 それ以外の場合、フレームワークによって呼び出されます[CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)です。  
  
##  <a name="m_brightarrow"></a>  CMFCMenuButton::m_bRightArrow  
 ポップアップ メニューの場所を示すブール型のメンバー変数。  
  
```  
BOOL m_bRightArrow;  
```  
  
### <a name="remarks"></a>Remarks  
 ユーザーは、メニュー ボタンを押すと、アプリケーションは、ポップアップ メニューを表示します。 フレームワークは、ボタンの下、または、ボタンの右側に、ポップアップ メニューに表示されます。 ボタンは、ポップアップ メニューが表示される場所を示す小さな矢印もあります。 場合`m_bRightArrow`は`TRUE`フレームワークは、ボタンの右側にポップアップ メニューを表示します。 それ以外の場合、ボタンの下のポップアップ メニューが表示されます。  
  
##  <a name="m_bstaypressed"></a>  CMFCMenuButton::m_bStayPressed  
 メニュー ボタンが表示されるかどうかを示すブール型のメンバー変数を押した、ユーザーは、ポップアップ メニューから選択します。  
  
```  
BOOL m_bStayPressed;  
```  
  
### <a name="remarks"></a>Remarks  
 場合、`m_bStayPressed`メンバーは`FALSE`、メニュー ボタンになる押されていない場合に使用 をクリックします。 この場合、フレームワークには、ポップアップ メニューのみが表示されます。  
  
 場合、`m_bStayPressed`メンバーは`TRUE`ユーザーがボタンをクリックしたときに、メニュー ボタンが押されたになります。 ユーザーがいずれか、選択を行ったか、取り消すことによって、ポップアップ メニューを閉じた後まで押されたままです。  
  
##  <a name="m_hmenu"></a>  CMFCMenuButton::m_hMenu  
 関連付けられたメニューのハンドルです。  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、ユーザーがメニュー ボタンをクリックしたときに、このメンバー変数によって示されるメニューを表示します。  
  
##  <a name="m_nmenuresult"></a>  CMFCMenuButton::m_nMenuResult  
 どの項目を示す整数をユーザーは、ポップアップ メニューから選択します。  
  
```  
int m_nMenuResult;  
```  
  
### <a name="remarks"></a>Remarks  
 ユーザーは選択せず、メニューをキャンセルするか、エラーが発生した場合、このメンバー変数の値は 0 です。  
  
##  <a name="pretranslatemessage"></a>  CMFCMenuButton::PreTranslateMessage  
 ディスパッチされる前に、ウィンドウ メッセージを変換するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pMsg*  
 指す、 [MSG](../../mfc/reference/msg-structure1.md)を処理するメッセージを含む構造体。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、メッセージが変換されていて、ディスパッチいない必要があります。メッセージが変換されていないと、ディスパッチする必要がある場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="sizetocontent"></a>  CMFCMenuButton::SizeToContent  
 テキストのサイズ、イメージのサイズに応じてボタンのサイズを変更します。  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bCalcOnly*  
 このメソッド、ボタンのサイズを変更するかどうかを示すブール値パラメーターです。  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)ボタンの新しいサイズを指定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この関数を呼び出す場合と*bCalcOnly*は`TRUE`、`SizeToContent`ボタンの新しいサイズのみが計算されます。  
  
 ボタンの新しいサイズは、ボタンのテキスト、イメージ、および矢印に合わせて計算されます。 フレームワークは、10 のピクセルの水平方向のエッジと 5 のピクセルの垂直方向のエッジの定義済みの余白にも追加されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)
