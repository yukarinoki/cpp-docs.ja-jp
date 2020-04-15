---
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
ms.openlocfilehash: 1458039c25f2379b3c3db553b2010e9391df28db
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375103"
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel クラス

をクリックすると表示されるリボン パネルを実装[します](../../mfc/reference/cmfcribbonapplicationbutton-class.md)。

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
|[CMFCリボンメインパネル::追加](#add)|アプリケーション ボタン パネルの左側のペインにリボン要素を追加します。 [(CMFCリボンパネルをオーバーライドします。:追加](../../mfc/reference/cmfcribbonpanel-class.md#add).)|
|[次の項目一覧を追加します。](#addrecentfileslist)|最近使ったファイルの一覧メニューにテキスト文字列を追加します。|
|[CMFCリボンメインパネル::下へ](#addtobottom)|リボン アプリケーション パネルの下部ペインにリボン要素を追加します。|
|[CMFCリボンメインパネル::右に追加](#addtoright)|アプリケーション ボタン パネルの右側のペインにリボン要素を追加します。|
|`CMFCRibbonMainPanel::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[コマンド フレームを取得します。](#getcommandsframe)|リボンのメイン パネルの領域を表す四角形を返します。|
|`CMFCRibbonMainPanel::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|

## <a name="remarks"></a>解説

フレームワークは、アプリケーション`CMFCRibbonMainPanel`パネルを開くと表示されます。 このウィンドウには、次の 3 つのペインが含まれています。

- 左側のウィンドウには、ファイルに関連付けられたコマンド **([開く**]、[**保存**]、[**印刷**]、[閉じる]など) が**表示されます**。 このウィンドウにコマンドを追加するには[、CMFCRibbonMainPanel::Add](#add)を呼び出します。

- 右側のペインには、左側のペインでクリックしたコマンドを変更するオプションが含まれています。 たとえば、左側のウィンドウで **[名前を付けて保存**] をクリックすると、右側のペインに使用可能なファイルの種類が表示されます。 このウィンドウに項目を追加するには[、CMFCRibbonMainPanel::AddToRight](#addtoright)を呼び出します。

- 下部ペインには、アプリケーションの設定を変更し、プログラムを終了するためのボタンがあります。 このウィンドウに項目を追加するには[、CMFCRibbonMainPanel::AddToBottom](#addtobottom)を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRibbonメインパネル.h

## <a name="cmfcribbonmainpaneladd"></a><a name="add"></a>CMFCリボンメインパネル::追加

アプリケーション ボタン パネルの左側のペインにリボン要素を追加します。

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>パラメーター

*ペレム*<br/>
[イン、アウト]メイン パネルに追加するリボン要素へのポインター。

### <a name="remarks"></a>解説

パネルにリボン要素を追加します。 このメソッドを使用して追加された要素は、メイン パネルの左の列にあります。

## <a name="cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a>次の項目一覧を追加します。

最近使ったファイルの一覧メニューにテキスト文字列を追加します。

```
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
最近使ったファイルの一覧に追加する文字列を指定します。

*n幅*<br/>
最近使ったファイルのリスト パネルの幅をピクセル単位で指定します。

### <a name="remarks"></a>解説

## <a name="cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a>CMFCリボンメインパネル::下へ

リボン アプリケーション パネルの下部ペインにリボン要素を追加します。

```
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>パラメーター

*ペレム*<br/>
[イン、アウト]メイン パネルの下部に追加するリボン要素へのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a>CMFCリボンメインパネル::右に追加

アプリケーション ボタン パネルの右側のペインにリボン要素を追加します。

```
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>パラメーター

*ペレム*<br/>
メイン パネルの右側に追加するリボン要素へのポインター。

*n幅*<br/>
右側のパネルの幅をピクセル単位で指定します。

### <a name="remarks"></a>解説

この関数を使用して、右側のパネルにリボン要素を追加します。 通常、右側のパネルには最近使用したファイルの一覧が表示されますが、ここで他のリボン要素を追加することもできます。

## <a name="cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a>コマンド フレームを取得します。

リボンのメイン パネルの領域を表す四角形を返します。

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>戻り値

リボンのメイン パネルの領域を表す四角形。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcribbonpanel-class.md)
