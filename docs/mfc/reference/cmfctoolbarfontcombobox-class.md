---
title: コンボボックス クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
ms.openlocfilehash: 7b31f4b725a6983171162d9805d08224ad787808
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360458"
---
# <a name="cmfctoolbarfontcombobox-class"></a>コンボボックス クラス

ユーザーがシステム フォントの一覧からフォントを選択できるようにするコンボ ボックス コントロールを含むツール バー ボタン。

## <a name="syntax"></a>構文

```
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[コンボボックス::CMFCツールバーフォントコンボボックス](#cmfctoolbarfontcombobox)|`CMFCToolBarFontComboBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コンボボックス::フォントを取得します。](#getfontdesc)|コンボ ボックス内の`CMFCFontInfo`指定したインデックスのオブジェクトへのポインターを返します。|
|[コンボボックス::フォントを設定します。](#setfont)|フォントの名前、またはフォントのプレフィックスと文字セットのいずれかに従って、フォントコンボボックス内のフォントを選択します。|

### <a name="data-members"></a>データ メンバー

[コンボボックス::m_nFontHeight](#m_nfontheight)<br/>
フォント コンボ ボックスの文字の高さ。

## <a name="remarks"></a>解説

ツールバーにフォントコンボボックスボタンを追加するには、次の手順を実行します。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。

1. `CMFCToolBarFontComboBox` オブジェクトを構築します。

1. AFX_WM_RESETTOOLBAR メッセージを処理するメッセージ ハンドラーで[、CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)を使用して、元のボタンを新しいコンボ ボックス ボタンに置き換えます。

1. コンボ ボックスで選択されているフォントを[、CMFCToolBarFontComboBox::SetFont](#setfont)メソッドを使用してドキュメント内のフォントと同期させます。

コンボ ボックスで選択したフォントとドキュメントのフォントを同期するには[、CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)メソッドを使用して、選択したフォントの属性を取得し、それらの属性を使用して[CFont クラス](../../mfc/reference/cfont-class.md)オブジェクトを作成します。

フォントコンボボックスボタンは、Win32 関数[EnumFontFamilyEx](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesexw)を呼び出して、システムで使用できる画面フォントとプリンタ フォントを決定します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[コンボボックスボタン](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[コンボボックス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxツールバーフォントコンボボックス.h

## <a name="cmfctoolbarfontcomboboxcmfctoolbarfontcombobox"></a><a name="cmfctoolbarfontcombobox"></a>コンボボックス::CMFCツールバーフォントコンボボックス

[オブジェクトを](../../mfc/reference/cmfctoolbarfontcombobox-class.md)構築します。

```
public:
CMFCToolBarFontComboBox(
    UINT uiID,
    int iImage,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    DWORD dwStyle = CBS_DROPDOWN,
    int iWidth = 0,
    BYTE nPitchAndFamily = DEFAULT_PITCH);

protected:
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,
    int nFontType,
    BYTE nCharSet,
    BYTE nPitchAndFamily);

CMFCToolBarFontComboBox();
```

### <a name="parameters"></a>パラメーター

*Uiid*<br/>
[in]コンボ ボックスのコマンド ID。

*iイメージ*<br/>
[in]ツール バー イメージの 0 から始まるインデックス。 イメージは、[クラスクラス](../../mfc/reference/cmfctoolbarimages-class.md)が保持するクラス のクラスのクラス[に](../../mfc/reference/cmfctoolbar-class.md)配置されます。

*nフォントタイプ*<br/>
[in]コンボ ボックスに含まれるフォントの種類。 このパラメーターは、次の値の組み合わせ (論理 OR) にすることができます。

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*nCharセット*<br/>
[in]DEFAULT_CHARSETに設定すると、コンボ ボックスには、すべての文字セットに一意のフォントがすべて含まれます。 (同じ名前のフォントが 2 つある場合、コンボ ボックスには 1 つのフォントが含まれます)。有効な文字セット値に設定すると、指定した文字セットのフォントのみがコンボ ボックスに表示されます。 可能な文字セットのリストについては[、LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)を参照してください。

*Dwstyle*<br/>
[in]コンボ ボックスのスタイル。 ([コンボボックススタイルを](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)参照)

*幅*<br/>
[in]エディット コントロールの幅 (ピクセル単位)。

*アンドファミリー*<br/>
[in]DEFAULT_PITCHに設定すると、コンボ ボックスにはピッチに関係なくフォントが含まれます。 FIXED_PITCHまたはVARIABLE_PITCHに設定すると、コンボ ボックスには、そのピッチタイプのフォントのみが含まれます。 フォント ファミリに基づくフィルター処理は現在サポートされていません。

*外部フォント*<br/>
[アウト]使用可能なフォントを格納する[CObList クラス](../../mfc/reference/coblist-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

通常、`CMFCToolBarFontComboBox`オブジェクトは、使用可能なフォントのリストを単一`CObList`の共有オブジェクトに格納します。 コンストラクタの 2 番目のオーバーロードを使用し *、pLstFontsExternal*への有効なポインタ`CMFCToolBarFontComboBox`を指定すると、その`CObList`オブジェクトは代わりに、その*pLstFontsExternal*ポイントに使用可能なフォントを設定します。

### <a name="example"></a>例

オブジェクトを構築する方法を次の例`CMFCToolBarFontComboBox`に示します。 このコード スニペットは、 [Word パッド サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

## <a name="cmfctoolbarfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>コンボボックス::フォントを取得します。

コンボ ボックス内の`CMFCFontInfo`指定したインデックスのオブジェクトへのポインターを返します。

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]コンボ ボックス項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

`CMFCFontInfo` オブジェクトを指すポインターです。 *iIndex が*有効な項目インデックスを指定しない場合、戻り値は NULL になります。

## <a name="cmfctoolbarfontcomboboxm_nfontheight"></a><a name="m_nfontheight"></a>コンボボックス::m_nFontHeight

コンボ ボックスにオーナー描画スタイルがある場合に、フォント コンボ ボックスの文字の高さをピクセル単位で指定します。

```
static int m_nFontHeight
```

### <a name="remarks"></a>解説

変数が`m_nFontHeight`0 の場合、コンボ ボックスの既定のフォントに従って高さが自動的に計算されます。 高さには、ベースラインの上の文字の上昇と、ベースラインの下の文字の降下の両方が含まれます。

## <a name="cmfctoolbarfontcomboboxsetfont"></a><a name="setfont"></a>コンボボックス::フォントを設定します。

フォントコンボボックスで、パラメータで指定されているフォント名と文字セットに従ってフォントを選択します。

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]フォント名または接頭辞を指定します。

*nCharセット*<br/>
[in]文字セットを指定します。

*b正確な情報*<br/>
[in]*lpszName*にフォント名またはフォント接頭辞が含まれているかどうかを指定します。

### <a name="return-value"></a>戻り値

フォントが正常に選択された場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*bExact*が TRUE の場合、このメソッドは *、lpszName*として指定した名前と完全に一致するフォントを選択します。 *bExact*が FALSE の場合、このメソッドは *、lpszName*で指定されたテキストで始まり *、nCharSet*として指定した文字セットを使用するフォントを選択します。 *nCharSet*を DEFAULT_CHARSET に設定すると、文字セットは無視され *、lpszName*のみが使用されてフォントが選択されます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[ボタンを置き換える](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)
