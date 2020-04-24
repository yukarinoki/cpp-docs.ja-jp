---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
ms.openlocfilehash: dbf28787e0c0f7d89586fbf98632bd9172c12eed
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754157"
---
# <a name="cmfcribbonfontcombobox-class"></a>クラス

フォントの一覧を含むコンボ ボックスを実装します。 このコンボ ボックスをリボン パネルに配置できます。

## <a name="syntax"></a>構文

```
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|デストラクターです。|

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|`CMFCRibbonFontComboBox` オブジェクトを構築して初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|リボンのフォント コンボ ボックスに、指定されたフォントの種類、文字セット、ピッチ、ファミリのフォントを設定します。|
|`CMFCRibbonFontComboBox::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|指定された文字セットを返します。|
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|コンボ ボックスに表示するフォントの種類を返します。 有効なオプションは、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE、またはそのビットごとの任意の組み合わせです。|
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|コンボ ボックスに表示されるフォントのピッチとファミリを返します。|
|`CMFCRibbonFontComboBox::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|リボンのフォント コンボ ボックスに、以前に指定されたフォントの種類、文字セット、ピッチ、ファミリのフォントを設定します。|
|[CMFCRibbonFontComboBox::SetFont](#setfont)|コンボ ボックスで、指定されたフォントを選択します。|

## <a name="remarks"></a>解説

作成したオブジェクトは`CMFCRibbonFontComboBox`[、CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add)を呼び出して、リボン パネルに追加します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

[CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxリボンコンボボックス.h

## <a name="cmfcribbonfontcomboboxbuildfonts"></a><a name="buildfonts"></a>コンボボックス::ビルドフォント

リボンのコンボ ボックスにフォントを設定します。

```cpp
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```

### <a name="parameters"></a>パラメーター

*nフォントタイプ*<br/>
[in]追加するフォントのフォントの種類を指定します。

*nCharセット*<br/>
[in]追加するフォントの文字セットを指定します。

*アンドファミリー*<br/>
[in]追加するフォントのピッチとファミリを指定します。

## <a name="cmfcribbonfontcomboboxcmfcribbonfontcombobox"></a><a name="cmfcribbonfontcombobox"></a>コンボボックス::CMFCリボンフォントコンボボックス

[オブジェクトを](../../mfc/reference/cmfcribbonfontcombobox-class.md)構築して初期化します。

```
CMFCRibbonFontComboBox(
    UINT nID,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH,
    int nWidth = -1);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]ユーザーがコンボ ボックスから項目を選択したときに実行されるコマンドのコマンド ID。

*nフォントタイプ*<br/>
[in]コンボ ボックスに表示するフォントの種類を指定します。 有効なオプションは、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE、またはそのビットごとの任意の組み合わせです。

*nCharセット*<br/>
[in]コンボ ボックス内のフォントを、指定した文字セットに属するフォントにフィルターします。

*アンドファミリー*<br/>
[in]コンボ ボックスに表示されるフォントのピッチとファミリを指定します。

*n幅*<br/>
[in]コンボ ボックスの幅をピクセル単位で指定します。

### <a name="remarks"></a>解説

可能な*nFontType*パラメーター値の詳細については、Windows SDK のドキュメントの[「列挙フォントファムプロ」](/previous-versions/dd162621\(v=vs.85\))を参照してください。

*nCharSet*に割り当てることができる有効な文字セットと*nPitchAndFamily*に割り当てることができる有効な値の詳細については、Windows SDK ドキュメントの[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)を参照してください。

## <a name="cmfcribbonfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>コンボボックス::フォントを取得します。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonfontcomboboxrebuildfonts"></a><a name="rebuildfonts"></a>コンボボックス::リビルドフォント

リボンのコンボ ボックスに、以前に指定したフォントの種類、文字セット、ピッチとファミリのフォントを設定します。

```cpp
void RebuildFonts();
```

### <a name="remarks"></a>解説

このクラスの[コンストラクター](#cmfcribbonfontcombobox)のリボン フォント コンボ ボックスに含めるフォントの種類、文字セット、ピッチ、およびフォント ファミリを指定するか[、CMFCRibbonFontComboBox::BuildFonts](#buildfonts)を呼び出します。

## <a name="cmfcribbonfontcomboboxsetfont"></a><a name="setfont"></a>コンボボックス::フォントを設定します。

コンボ ボックスで、指定されたフォントを選択します。

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet = DEFAULT_CHARSET,
    BOOL bExact = FALSE);
```

### <a name="parameters"></a>パラメーター

'lpszName* 選択するフォントの名前を指定します。

*nCharセット*<br/>
選択したフォントの文字セットを指定します。

*b正確な情報*<br/>
フォントを選択するときに文字セットが一致する必要があることを指定する場合は TRUE。FALSE を指定すると、フォントの選択時に文字セットを無視できます。

### <a name="return-value"></a>戻り値

指定したフォントが見つかり、選択されている場合は 0 以外の値を指定します。それ以外の場合は、ゼロ。

### <a name="remarks"></a>解説

## <a name="cmfcribbonfontcomboboxgetcharset"></a><a name="getcharset"></a>コンボボックス::取得文字セット

指定された文字セットを返します。

```
BYTE GetCharSet() const;
```

### <a name="return-value"></a>戻り値

文字セット (Windows SDK のドキュメントのログフォントを参照)。

### <a name="remarks"></a>解説

## <a name="cmfcribbonfontcomboboxgetfonttype"></a><a name="getfonttype"></a>コンボボックス::フォントタイプを取得します。

コンボ ボックスに表示するフォントの種類を返します。 有効なオプションは、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE、またはそのビットごとの任意の組み合わせです。

```
int GetFontType() const;
```

### <a name="return-value"></a>戻り値

フォントの種類 (Windows SDK のドキュメントの列挙フォントファムプロを参照してください)。

### <a name="remarks"></a>解説

## <a name="cmfcribbonfontcomboboxgetpitchandfamily"></a><a name="getpitchandfamily"></a>コンボボックス::ゲットピッチアンドファミリー

コンボ ボックスに表示されるフォントのピッチとファミリを返します。

```
BYTE GetPitchAndFamily() const;
```

### <a name="return-value"></a>戻り値

ピッチとファミリ (Windows SDK のドキュメントのログフォントを参照)。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonComboBox クラス](../../mfc/reference/cmfcribboncombobox-class.md)
