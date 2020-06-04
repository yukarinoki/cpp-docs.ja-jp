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
ms.openlocfilehash: 41a958c78719f6aedf1cc02f8e3ff5a2dbbf0e1b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368849"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator クラス

リボンの区切り記号を実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|[CMFC リボンセパレータ::CMFC リボンセパレータ](#cmfcribbonseparator)|`CMFCRibbonSeparator` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[をクリックします。](#addtolistbox)|[**ユーザー設定**] ダイアログ ボックスの **[コマンド] ボックス**に区切り記号を追加します。 (オーバーライドします[。](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox)|
|`CMFCRibbonSeparator::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCRibbonSeparator::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|

### <a name="protected-methods"></a>プロテクト メソッド

|||
|-|-|
|名前|説明|
|[セパレータ::コピー元](#copyfrom)|別のオブジェクトから区切り記号のメンバー変数を設定するコピー メソッド。|
|[セパレータ::取得レギュラーサイズ](#getregularsize)|区切り記号のサイズを返します。|
|[を指定します。](#isseparator)|これが区切り文字であるかどうかを示します。|
|[を切り取る](#istabstop)|これがタブストップであるかどうかを示します。|
|[CMFCリボンセパレータ::オンドロー](#ondraw)|リボンまたはクイック アクセス ツール バーに区切り記号を描画するために、システムによって呼び出されます。|
|[を使用します。](#ondrawonlist)|**コマンド**リストに区切り記号を描画するためにシステムによって呼び出されます。|

## <a name="remarks"></a>解説

リボンの区分線は、リボン要素を論理的に区切る垂直線または水平線です。 区分線は、リボン コントロール、メイン アプリケーション メニュー、リボン ステータス バー、およびクイック アクセス ツールバーに描画できます。

アプリケーションで区切り記号を使用するには、次に示すように、新しいオブジェクトを構築し、メイン アプリケーション メニューに追加します。

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```

リボン パネルに区切り記号を追加するには[、CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator)を呼び出します。 区切り記号はメソッドによって内部的に割り当てられ`AddSeparator`、追加されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[セパレータ](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxbaseribbonelement.h

## <a name="cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a>をクリックします。

[**ユーザー設定**] ダイアログ ボックスの **[コマンド] ボックス**に区切り記号を追加します。

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>パラメーター

*リストボックス*<br/>
[in]区切り記号が追加される**コマンド**リストへのポインター。

*bディープ*<br/>
[in]無視。

### <a name="return-value"></a>戻り値

*pWndListBox*で指定されたリスト ボックス内の文字列に対する 0 から始まるインデックス。

## <a name="cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a>CMFC リボンセパレータ::CMFC リボンセパレータ

`CMFCRibbonSeparator` オブジェクトを構築します。

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>パラメーター

*ビショリス*<br/>
[in]TRUE の場合、区切り記号は水平です。FALSE の場合、区切り記号は垂直です。

### <a name="remarks"></a>解説

水平セパレータは、アプリケーションメニューで使用されます。 縦区切り記号は、ツールバーで使用されます。

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に`CMFCRibbonSeparator`示します。

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

## <a name="cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a>セパレータ::コピー元

別のオブジェクトから区切り記号のメンバー変数を設定するコピー メソッド。

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>パラメーター

*Src*<br/>
[in]コピー元のリボン要素。

## <a name="cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a>セパレータ::取得レギュラーサイズ

区切り記号のサイズを返します。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイスコンテンツへのポインタ。

### <a name="return-value"></a>戻り値

指定されたデバイス コンテキストの区切り記号のサイズ。

## <a name="cmfcribbonseparatorisseparator"></a><a name="isseparator"></a>を指定します。

これが区切り文字であるかどうかを示します。

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>戻り値

このクラスでは常に TRUE です。

## <a name="cmfcribbonseparatoristabstop"></a><a name="istabstop"></a>を切り取る

これがタブストップであるかどうかを示します。

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>戻り値

このクラスでは常に FALSE。

### <a name="remarks"></a>解説

リボンの区切り記号はタブストップではありません。

## <a name="cmfcribbonseparatorondraw"></a><a name="ondraw"></a>CMFCリボンセパレータ::オンドロー

リボンまたはクイック アクセス ツール バーに区切り記号を描画するために、システムによって呼び出されます。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

## <a name="cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a>を使用します。

**コマンド**リストに区切り記号を描画するためにシステムによって呼び出されます。

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

|||
|-|-|
|パラメーター|説明|
|*pDC*|[in]デバイス コンテキストへのポインター。|
|*str テキスト*|[in]リストに表示されるテキスト。|
|*オフセット*|[in]テキストと外接する四角形の左側の間隔。|
|*Rect*|[in]外接する四角形を指定します。|
|*bIsSelected*|[in]無視。|
|*b強調表示*|[in]無視。|

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
