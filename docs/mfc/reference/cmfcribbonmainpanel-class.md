---
description: '詳細情報: CMFCRibbonMainPanel クラス'
title: CMFCRibbonMainPanel クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
ms.openlocfilehash: 823a1ce8a8684ca791f838346a1fb50727096a62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321813"
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel クラス

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)をクリックしたときに表示されるリボンパネルを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|既定のコンストラクターです。|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonMainPanel:: Add](#add)|アプリケーションのボタンパネルの左ペインにリボン要素を追加します。 ( [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)をオーバーライドします)。|
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|[最近使ったファイル] リストメニューにテキスト文字列を追加します。|
|[CMFCRibbonMainPanel:: AddToBottom](#addtobottom)|リボンアプリケーションパネルの下部ペインにリボン要素を追加します。|
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|アプリケーションのボタンパネルの右ペインにリボン要素を追加します。|
|`CMFCRibbonMainPanel::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCRibbonMainPanel:: Getコマンドフレーム](#getcommandsframe)|リボンのメインパネルの領域を表す四角形を返します。|
|`CMFCRibbonMainPanel::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|

## <a name="remarks"></a>解説

アプリケーションパネルを開いたときに、フレームワークによってが表示され `CMFCRibbonMainPanel` ます。 次の3つのペインがあります。

- 左側のウィンドウには、ファイルに関連付けられているコマンド ([ **開く**]、[ **保存**]、[ **印刷**]、[ **閉じる**] など) が表示されます。 このウィンドウにコマンドを追加するには、 [CMFCRibbonMainPanel:: add](#add)を呼び出します。

- 右ペインには、左側のウィンドウでクリックしたコマンドを変更するオプションが表示されます。 たとえば、左側のウィンドウから [ **名前を付けて保存** ] をクリックすると、右側のウィンドウに使用可能なファイルの種類が表示されます。 このペインに項目を追加するには、 [CMFCRibbonMainPanel:: AddToRight](#addtoright)を呼び出します。

- 下部のペインには、アプリケーションの設定を変更したり、プログラムを終了したりするためのボタンがあります。 このペインに項目を追加するには、 [CMFCRibbonMainPanel:: AddToBottom](#addtobottom)を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxRibbonMainPanel

## <a name="cmfcribbonmainpaneladd"></a><a name="add"></a> CMFCRibbonMainPanel:: Add

アプリケーションのボタンパネルの左ペインにリボン要素を追加します。

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>パラメーター

*pElem*<br/>
[入力、出力]メインパネルに追加するリボン要素へのポインター。

### <a name="remarks"></a>解説

リボン要素をパネルに追加します。 このメソッドを使用して追加された要素は、メインパネルの左側の列に配置されます。

## <a name="cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a> CMFCRibbonMainPanel::AddRecentFilesList

[最近使ったファイル] リストメニューにテキスト文字列を追加します。

```cpp
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
最近使ったファイルの一覧に追加する文字列を指定します。

*nWidth*<br/>
[最近使ったファイル] リストパネルの幅をピクセル単位で指定します。

### <a name="remarks"></a>解説

## <a name="cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a> CMFCRibbonMainPanel:: AddToBottom

リボンアプリケーションパネルの下部ペインにリボン要素を追加します。

```cpp
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>パラメーター

*pElem*<br/>
[入力、出力]メインパネルの下部に追加するリボン要素へのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a> CMFCRibbonMainPanel::AddToRight

アプリケーションのボタンパネルの右ペインにリボン要素を追加します。

```cpp
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>パラメーター

*pElem*<br/>
メインパネルの右側に追加するリボン要素へのポインター。

*nWidth*<br/>
右側のパネルの幅をピクセル単位で指定します。

### <a name="remarks"></a>解説

この関数を使用すると、リボン要素を右側のパネルに追加できます。 通常、右側のパネルには最近使用したファイルの一覧が表示されますが、その他のリボン要素を追加することもできます。

## <a name="cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a> CMFCRibbonMainPanel:: Getコマンドフレーム

リボンのメインパネルの領域を表す四角形を返します。

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>戻り値

リボンのメインパネルの領域を表す四角形。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel クラス](../../mfc/reference/cmfcribbonpanel-class.md)
