---
title: CMFCRibbonMainPanel クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05257749c95b619c479538a1322746ae2b487b6a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel クラス
クリックしたときに表示されるリボン パネルを実装、 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|既定のコンストラクター|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonMainPanel::Add](#add)|アプリケーション ボタン パネルの左側のウィンドウにリボン要素を追加します。 (上書き[cmfcribbonpanel::add](../../mfc/reference/cmfcribbonpanel-class.md#add))。|  
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|最近使用したファイル リスト メニューにテキスト文字列を追加します。|  
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|アプリケーションのリボン パネルの下のウィンドウにリボン要素を追加します。|  
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|アプリケーション ボタン パネルの右側のウィンドウにリボン要素を追加します。|  
|`CMFCRibbonMainPanel::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|リボンのメイン パネルの領域を表す四角形を返します。|  
|`CMFCRibbonMainPanel::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 フレームワークは、表示、`CMFCRibbonMainPanel`アプリケーションのパネルを開くとします。 3 つのペインが含まれています。  
  
-   左側のウィンドウには、コマンドに関連付けられているファイルなどが含まれています。**開く**、**保存**、**印刷**、および**閉じる**です。 このウィンドウにコマンドを追加するには、呼び出す[CMFCRibbonMainPanel::Add](#add)です。  
  
-   右側のペインには、左側のウィンドウでをクリックするコマンドを変更するオプションが含まれています。 たとえばをクリックする**名前を付けて保存**左側のペインから右側のウィンドウが使用可能なファイルの種類を表示できます。 このペインにアイテムを追加するには、呼び出す[CMFCRibbonMainPanel::AddToRight](#addtoright)です。  
  
-   下のペインには、アプリケーションの設定を変更して、プログラムを終了できるボタンが含まれています。 このペインにアイテムを追加するには、呼び出す[CMFCRibbonMainPanel::AddToBottom](#addtobottom)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonMainPanel.h  
  
##  <a name="add"></a>  CMFCRibbonMainPanel::Add  
 アプリケーション ボタン パネルの左側のウィンドウにリボン要素を追加します。  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pElem`  
 メイン パネルに追加するリボン要素へのポインター。  
  
### <a name="remarks"></a>コメント  
 パネルにリボン要素を追加します。 このメソッドを使用して追加された要素は、メイン パネルの左側の列に格納されます。  
  
##  <a name="addrecentfileslist"></a>  CMFCRibbonMainPanel::AddRecentFilesList  
 最近使用したファイル リスト メニューにテキスト文字列を追加します。  
  
```  
void AddRecentFilesList(
    LPCTSTR lpszLabel,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszLabel`  
 最近使ったファイルの一覧に追加する文字列を指定します。  
  
 `nWidth`  
 最近使ったファイルの一覧 パネルのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addtobottom"></a>  CMFCRibbonMainPanel::AddToBottom  
 アプリケーションのリボン パネルの下のウィンドウにリボン要素を追加します。  
  
```  
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pElem`  
 メイン パネルの下に追加するリボン要素へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addtoright"></a>  CMFCRibbonMainPanel::AddToRight  
 アプリケーション ボタン パネルの右側のウィンドウにリボン要素を追加します。  
  
```  
void AddToRight(
    CMFCRibbonBaseElement* pElem,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>パラメーター  
 `pElem`  
 メイン パネルの右側に追加するリボン要素へのポインター。  
  
 `nWidth`  
 右側のパネルのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
 右側のパネルをリボン要素を追加するのにには、この関数を使用します。 右側のパネルには、最近使ったファイル で、通常が表示されますが、リボンの要素を追加することができます。  
  
##  <a name="getcommandsframe"></a>  CMFCRibbonMainPanel::GetCommandsFrame  
 リボンのメイン パネルの領域を表す四角形を返します。  
  
```  
CRect GetCommandsFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボンのメイン パネルの領域を表す四角形。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel クラス](../../mfc/reference/cmfcribbonpanel-class.md)
