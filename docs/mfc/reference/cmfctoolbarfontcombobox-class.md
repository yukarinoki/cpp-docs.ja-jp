---
title: CMFCToolBarFontComboBox クラス
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
ms.openlocfilehash: 89767a3ed6880703c3c754700ea5669c0cc183e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218364"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox クラス

ユーザーは、システム フォントの一覧からフォントを選択できるコンボ ボックス コントロールを含むツール バー ボタン。

## <a name="syntax"></a>構文

```
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|`CMFCToolBarFontComboBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|ポインターを返します、`CMFCFontInfo`コンボ ボックス内の指定したインデックスのオブジェクト。|
|[CMFCToolBarFontComboBox::SetFont](#setfont)|フォントの名前またはフォントのプレフィックスと文字セットは、いずれかに従ってフォント コンボ ボックスのフォントを選択します。|

### <a name="data-members"></a>データ メンバー

[CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)<br/>
フォント コンボ ボックス内の文字の高さ。

## <a name="remarks"></a>Remarks

フォント コンボ ボックス ボタンをツールバーに追加するには、次の手順を実行します。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。

1. `CMFCToolBarFontComboBox` オブジェクトを構築します。

1. AFX_WM_RESETTOOLBAR メッセージを処理するメッセージ ハンドラーで元のボタンをクリックします。 新しいコンボ ボックス ボタンを使用して置き換える[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)します。

1. 同期を使用して、ドキュメント内のフォントを使用してコンボ ボックスで選択したフォント、 [CMFCToolBarFontComboBox::SetFont](#setfont)メソッド。

ドキュメントのフォント コンボ ボックスで選択したフォントを使用して、同期するを使用して、 [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)メソッドを選択したフォントの属性を取得し、それらの属性を使用して、作成、 [CFont クラス](../../mfc/reference/cfont-class.md)オブジェクト。

フォント コンボ ボックス ボタンは、Win32 関数を呼び出す[EnumFontFamiliesEx](/windows/desktop/api/wingdi/nf-wingdi-enumfontfamiliesexa)をシステムに利用できる画面およびプリンターのフォントを決定します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtoolbarfontcombobox.h

##  <a name="cmfctoolbarfontcombobox"></a>  CMFCToolBarFontComboBox::CMFCToolBarFontComboBox

構築、 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)オブジェクト。

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

*uiID*<br/>
[in]コンボ ボックスのコマンド ID。

*画像を*<br/>
[in]ツール バー イメージの 0 から始まるインデックス。 イメージにある、 [CMFCToolBarImages クラス](../../mfc/reference/cmfctoolbarimages-class.md)オブジェクトを[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)クラスを保持します。

*nFontType*<br/>
[in]コンボ ボックスを含むフォントの種類。 このパラメーターは、次の値の組み合わせ (論理 OR) を指定できます。

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*nCharSet*<br/>
[in]場合 DEFAULT_CHARSET、コンボ ボックスに設定するには、すべての文字セットのフォントすべて一意となる名前にはが含まれています。 (同じ名前の 2 つのフォントがある場合は、コンボ ボックス格納うち 1 つ)。場合は、有効な文字セット値コンボ ボックスに設定するには、指定された文字セット内のフォントのみが含まれています。 参照してください[LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)可能な文字の一覧を設定します。

*dwStyle*<br/>
[in]コンボ ボックスのスタイル。 (を参照してください[コンボ ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))

*iWidth*<br/>
[in]編集コントロールのピクセル単位の幅。

*nPitchAndFamily*<br/>
[in]場合 DEFAULT_PITCH、コンボ ボックスに設定するには、ピッチに関係なくフォントが含まれています。 かどうか FIXED_PITCH または VARIABLE_PITCH に設定すると、コンボ ボックス フォントのみを含む、ピッチ タイプにします。 フォント ファミリに基づくフィルター処理は現在サポートされていません。

*pLstFontsExternal*<br/>
[out]ポインターを[CObList クラス](../../mfc/reference/coblist-class.md)利用可能なフォントを格納するオブジェクトです。

### <a name="remarks"></a>Remarks

通常、`CMFCToolBarFontComboBox`オブジェクトは、単一の共有に利用可能なフォントの一覧を格納`CObList`オブジェクト。 コンス トラクターの 2 つ目のオーバー ロードを使用する有効なポインターを提供していて*pLstFontsExternal*、その`CMFCToolBarFontComboBox`オブジェクトの塗りつぶしが代わりに、`CObList`を*pLstFontsExternal*利用可能なフォントでへのポインター。

### <a name="example"></a>例

次の例は、構築する方法を示します、`CMFCToolBarFontComboBox`オブジェクト。 このコード スニペットは、 [Word パッド サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

##  <a name="getfontdesc"></a>  CMFCToolBarFontComboBox::GetFontDesc

ポインターを返します、`CMFCFontInfo`コンボ ボックス内の指定したインデックスのオブジェクト。

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]コンボ ボックスの項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

`CMFCFontInfo` オブジェクトへのポインター。 場合*iIndex*有効なアイテムのインデックスで指定されていない戻り値は NULL です。

##  <a name="m_nfontheight"></a>  CMFCToolBarFontComboBox::m_nFontHeight

コンボ ボックスのオーナー描画スタイルの場合、フォント コンボ ボックス内の文字のピクセル、高さを指定します。

```
static int m_nFontHeight
```

### <a name="remarks"></a>Remarks

場合、`m_nFontHeight`変数が 0 の高さは、コンボ ボックスの既定のフォントに基づいて自動的に計算されます場合、。 高さには、ベースラインを超えた文字のアセントとベースラインの下にある文字のディセントの両方が含まれます。

##  <a name="setfont"></a>  CMFCToolBarFontComboBox::SetFont

フォント名と文字に従ってフォント コンボ ボックス内のフォント設定を選択しますが、パラメーターで指定されます。

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
[in]フォント名のプレフィックスを指定します。

*nCharSet*<br/>
[in]文字セットを指定します。

*bExact*<br/>
[in]指定するかどうか*lpszName*フォント名またはフォントのプレフィックスが含まれています。

### <a name="return-value"></a>戻り値

フォントが正常に選択された場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

場合*bExact*が true の場合、このメソッドは、として指定した名前を正確に一致するフォントを選択します。 *lpszName*します。 場合*bExact* false で、このメソッドを選択として指定されたテキストで始まるフォント*lpszName*として指定した文字セットを使用して*nCharSet*します。 場合*nCharSet*設定されている DEFAULT_CHARSET、文字セットをして無視*lpszName*フォントを選択するために使用されます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)
