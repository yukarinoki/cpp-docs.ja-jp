---
title: CMFCFontInfo クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
ms.openlocfilehash: 606d70176e93de6f5526c30f182cee6f8c05499f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522370"
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo クラス

`CMFCFontInfo`クラスは、名とフォントの他の属性について説明します。

## <a name="syntax"></a>構文

```
class CMFCFontInfo : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCFontInfo`|`CMFCFontInfo` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCFontInfo::GetFullName](#getfullname)|フォントとその文字の連結された名前のセット (スクリプト) を取得します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|フォントに関連付けられている文字セット (スクリプト) を指定する値。|
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|ピッチとファミリのフォントを指定する値。|
|[CMFCFontInfo::m_nType](#m_ntype)|フォントの種類を指定する値。|
|[CMFCFontInfo::m_strName](#m_strname)|フォントの名前たとえば、 **Arial**します。|
|[CMFCFontInfo::m_strScript](#m_strscript)|フォントに関連付けられている文字セット (スクリプト) の名前。|

## <a name="remarks"></a>Remarks

アタッチすることができます、`CMFCFontInfo`オブジェクトの項目を[CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)クラス。 呼び出す、 [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc)へのポインターを取得するメソッドを`CMFCFontInfo`オブジェクト。

## <a name="example"></a>例

次の例では、さまざまなメンバーを使用する方法、`CMFCFontInfo`クラス。 例では、取得する方法を示します、`CMFCFontInfo`オブジェクトから、 `CMFCRibbonFontComboBox`、およびそのローカル変数にアクセスする方法。 この例は、 [MSOffice 2007 デモのサンプル](../../visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtoolbarfontcombobox.h

##  <a name="cmfcfontinfo"></a>  CMFCFontInfo::CMFCFontInfo

`CMFCFontInfo` オブジェクトを構築します。

```
CMFCFontInfo(
    LPCTSTR lpszName,
    LPCTSTR lpszScript,
    BYTE nCharSet,
    BYTE nPitchAndFamily,
    int nType);

CMFCFontInfo(const CMFCFontInfo& src);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
[in]フォントの名前。 詳細については、次を参照してください。、`lfFaceName`のメンバー、 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)構造体。

*lpszScript*<br/>
[in]フォントのスクリプト (文字セット) の名前。

*nCharSet*<br/>
[in]フォントの文字セット (スクリプト) を指定する値。 詳細については、次を参照してください。、`lfCharSet`のメンバー、 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)構造体。

*nPitchAndFamily*<br/>
[in]ピッチとファミリのフォントを指定する値。 詳細については、次を参照してください。、`lfPitchAndFamily`のメンバー、 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)構造体。

*%n タイプ*<br/>
[in]フォントの種類を指定する値。 このパラメーターは、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE のビットごとの組み合わせ (OR) を指定できます。

*src*<br/>
[in]既存の`CMFCFontInfo`オブジェクト メンバーがこれを構築するため`CMFCFontInfo`オブジェクト。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

このドキュメントでは、用語*文字セット*と*スクリプト*同じ意味で。 A*スクリプト*文字と 1 つまたは複数の言語でこれらの文字を書き込むための規則のコレクションでは書記体系であるとも呼ばれます。 文字のコレクションには、アルファベットとそのスクリプトで使用される区切り記号が含まれています。 など、米国で話されていることと、そのアルファベットには a ~ Z の文字が含まれています、ラテン文字は英語に使用します。`lfCharSet`のメンバー、 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)構造体は、文字セットを指定します。 たとえば、ANSI_CHARSET 値には、ラテン文字のアルファベットを含む、ANSI 文字セットを指定します。

##  <a name="getfullname"></a>  CMFCFontInfo::GetFullName

フォントとその文字の連結された名前のセット (スクリプト) を取得します。

```
CString GetFullName() const;
```

### <a name="return-value"></a>戻り値

スクリプトとフォントの名前を含む文字列。

### <a name="remarks"></a>Remarks

このメソッドを使用すると、フォントの完全な名前を取得できます。 たとえば、フォント名が**Arial** 、およびフォント スクリプトが**キリル**、このメソッドは、"Arial (キリル)"を返します。

##  <a name="m_ncharset"></a>  CMFCFontInfo::m_nCharSet

フォントに関連付けられている文字セット (スクリプト) を指定する値。

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。、 *nCharSet*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクター。

##  <a name="m_npitchandfamily"></a>  CMFCFontInfo::m_nPitchAndFamily

声の高さ (ポイント サイズ) とフォントのファミリ (serif、sans serif, および monospace など) を指定する値。

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。、 *nPitchAndFamily*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクター。

##  <a name="m_ntype"></a>  CMFCFontInfo::m_nType

フォントの種類を指定する値。

```
const int m_nType;
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。、 *%n タイプ*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクター。

##  <a name="m_strname"></a>  CMFCFontInfo::m_strName

フォントの名前。 たとえば、 **Arial**します。

```
const CString m_strName;
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。、 *lpszName*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクター。

##  <a name="m_strscript"></a>  CMFCFontInfo::m_strScript

フォントに関連付けられている文字セット (スクリプト) の名前。

```
const CString m_strScript;
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。、 *lpszScript*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクター。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox クラス](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
