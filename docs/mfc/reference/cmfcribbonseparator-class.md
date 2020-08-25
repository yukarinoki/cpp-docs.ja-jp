---
title: CMFCRibbonSeparator クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
ms.openlocfilehash: f435dc5ae8821a6d5626af2f93710a1672fd374c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831802"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator クラス

リボンの区切り記号を実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|-|-|
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|`CMFCRibbonSeparator` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[CMFCRibbonSeparator:: AddToListBox](#addtolistbox)|[**カスタマイズ**] ダイアログボックスの [**コマンド**] ボックスの一覧に区切り記号を追加します。 ( [CMFCRibbonBaseElement:: AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox)をオーバーライドします)。|
|`CMFCRibbonSeparator::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCRibbonSeparator::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|-|-|
|[CMFCRibbonSeparator:: CopyFrom](#copyfrom)|区切り記号のメンバー変数を別のオブジェクトから設定するコピーメソッド。|
|[CMFCRibbonSeparator:: GetRegularSize](#getregularsize)|区切り記号のサイズを返します。|
|[CMFCRibbonSeparator:: IsSeparator](#isseparator)|区切り記号かどうかを示します。|
|[CMFCRibbonSeparator:: IsTabStop](#istabstop)|このがタブストップであるかどうかを示します。|
|[CMFCRibbonSeparator:: OnDraw](#ondraw)|リボンまたはクイックアクセスツールバーのいずれかに区分線を描画するために、システムによって呼び出されます。|
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|**コマンド**リストの区切り記号を描画するためにシステムによって呼び出されます。|

## <a name="remarks"></a>解説

リボンの区切り記号は、リボン要素を論理的に分離する垂直方向または水平方向の線です。 区切り記号は、リボンコントロール、メインアプリケーションメニュー、リボンステータスバー、およびクイックアクセスツールバーに描画できます。

アプリケーションで区切り記号を使用するには、次に示すように、新しいオブジェクトを作成し、メインアプリケーションメニューに追加します。

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```

[CMFCRibbonPanel:: AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator)を呼び出して、リボンパネルに区切り記号を追加します。 区切り記号は、メソッドによって内部的に割り当てられ、追加され `AddSeparator` ます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxbaseribbonelement.h

## <a name="cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a> CMFCRibbonSeparator:: AddToListBox

[**カスタマイズ**] ダイアログボックスの [**コマンド**] ボックスの一覧に区切り記号を追加します。

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>パラメーター

*pWndListBox*<br/>
から区切り記号が追加された **コマンド** 一覧へのポインター。

*bDeep*<br/>
から無効.

### <a name="return-value"></a>戻り値

*PWndListBox*によって指定されたリストボックス内の文字列の0から始まるインデックス。

## <a name="cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a> CMFCRibbonSeparator::CMFCRibbonSeparator

`CMFCRibbonSeparator` オブジェクトを構築します。

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>パラメーター

*bIsHoriz*<br/>
からTRUE の場合、区切り記号は水平です。FALSE の場合、区切り記号は vertical です。

### <a name="remarks"></a>解説

横方向の区切り記号は、アプリケーションメニューで使用されます。 垂直方向の区切り記号は、ツールバーで使用します。

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に示し `CMFCRibbonSeparator` ます。

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

## <a name="cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a> CMFCRibbonSeparator:: CopyFrom

区切り記号のメンバー変数を別のオブジェクトから設定するコピーメソッド。

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>パラメーター

*Src*<br/>
からコピー元のリボン要素。

## <a name="cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonSeparator:: GetRegularSize

区切り記号のサイズを返します。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテンツへのポインター。

### <a name="return-value"></a>戻り値

指定されたデバイスコンテキストの区切り記号のサイズ。

## <a name="cmfcribbonseparatorisseparator"></a><a name="isseparator"></a> CMFCRibbonSeparator:: IsSeparator

区切り記号かどうかを示します。

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>戻り値

このクラスでは常に TRUE です。

## <a name="cmfcribbonseparatoristabstop"></a><a name="istabstop"></a> CMFCRibbonSeparator:: IsTabStop

このがタブストップであるかどうかを示します。

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>戻り値

このクラスでは常に FALSE です。

### <a name="remarks"></a>解説

リボンの区切り記号はタブストップではありません。

## <a name="cmfcribbonseparatorondraw"></a><a name="ondraw"></a> CMFCRibbonSeparator:: OnDraw

リボンまたはクイックアクセスツールバーのいずれかに区分線を描画するために、システムによって呼び出されます。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

## <a name="cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a> CMFCRibbonSeparator::OnDrawOnList

**コマンド**リストの区切り記号を描画するためにシステムによって呼び出されます。

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>パラメーター

*pDC*\
からデバイスコンテキストへのポインター。

*strText*\
から一覧に表示されるテキスト。

*nTextOffset*\
からテキストと外接する四角形の左側との間隔。

*rect*\
から外接する四角形を指定します。

*bIsSelected*\
から無効.

*bHighlighted 表示*\
から無効.

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
