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
ms.openlocfilehash: 6e87971e2afefc9cf1574abe951920c254dcd2ae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367479"
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo クラス

この`CMFCFontInfo`クラスは、フォントの名前とその他の属性を記述します。

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
|[を取得します。](#getfullname)|フォントとその文字セット (スクリプト) の連結名を取得します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[フォント情報::m_nCharSet](#m_ncharset)|フォントに関連付けられている文字セット (スクリプト) を指定する値。|
|[フォント情報::m_nPitchAndFamily](#m_npitchandfamily)|フォントのピッチとファミリを指定する値。|
|[フォント情報::m_nType](#m_ntype)|フォントの種類を指定する値。|
|[m_strName](#m_strname)|フォントの名前。たとえば、 **Arial**.|
|[フォント情報::m_strScript](#m_strscript)|フォントに関連付けられた文字セット (スクリプト) の名前。|

## <a name="remarks"></a>解説

`CMFCFontInfo`[クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)クラスの項目にオブジェクトをアタッチできます。 オブジェクトへの[ポインターを取得](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc)するには、メソッドを`CMFCFontInfo`呼び出します。

## <a name="example"></a>例

クラスのさまざまなメンバーを使用する方法を次の例に`CMFCFontInfo`示します。 この例では、`CMFCFontInfo``CMFCRibbonFontComboBox`からオブジェクトを取得する方法と、そのローカル変数にアクセスする方法を示します。 この例は[MSOffice 2007 デモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxツールバーフォントコンボボックス.h

## <a name="cmfcfontinfocmfcfontinfo"></a><a name="cmfcfontinfo"></a>をクリックします。

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

*名前を指定します。*<br/>
[in]フォントの名前。 詳しくは[、LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) `lfFaceName`構造体のメンバーを参照してください。

*スクリプト*<br/>
[in]フォントのスクリプト (文字セット) の名前。

*nCharセット*<br/>
[in]フォントの文字セット (スクリプト) を指定する値。 詳しくは[、LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) `lfCharSet`構造体のメンバーを参照してください。

*アンドファミリー*<br/>
[in]フォントのピッチとファミリを指定する値。 詳しくは[、LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) `lfPitchAndFamily`構造体のメンバーを参照してください。

*nType*<br/>
[in]フォントの種類を指定する値。 このパラメーターは、DEVICE_FONTTYPE、RASTER_FONTTYPE、およびTRUETYPE_FONTTYPEのビットごとの組み合わせ (OR) にすることができます。

*src*<br/>
[in]この`CMFCFontInfo`オブジェクト`CMFCFontInfo`の構築に使用されるメンバーを持つ既存のオブジェクト。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

このドキュメントでは、*文字セット*と*スクリプト*という用語を同じ意味で使用します。 *スクリプト*は、書記システムとも呼ばれ、1 つ以上の言語で文字を書き込む文字とルールの集まりです。 文字のコレクションには、そのスクリプトで使用されるアルファベットと句読点が含まれます。 たとえば、ラテン文字は米国で話されている英語に使用され、アルファベットには A ~ Z の文字が含まれます。`lfCharSet` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体のメンバーは、文字セットを指定します。 たとえば、ANSI_CHARSET値は、ラテン文字のアルファベットを含む ANSI 文字セットを指定します。

## <a name="cmfcfontinfogetfullname"></a><a name="getfullname"></a>を取得します。

フォントとその文字セット (スクリプト) の連結名を取得します。

```
CString GetFullName() const;
```

### <a name="return-value"></a>戻り値

フォント名とスクリプトを含む文字列。

### <a name="remarks"></a>解説

このメソッドは、フォントの完全な名前を取得するために使います。 たとえば、フォント名が**Arial**で、フォント スクリプトが**キリル文字**の場合、このメソッドは "Arial (キリル文字)" を返します。

## <a name="cmfcfontinfom_ncharset"></a><a name="m_ncharset"></a>フォント情報::m_nCharSet

フォントに関連付けられている文字セット (スクリプト) を指定する値。

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>解説

詳細については[、コンストラクターの](#cmfcfontinfo) *nCharSet*パラメーターを参照してください。

## <a name="cmfcfontinfom_npitchandfamily"></a><a name="m_npitchandfamily"></a>フォント情報::m_nPitchAndFamily

フォントのピッチ (ポイント サイズ) とファミリ (セリフ、sans-serif、およびモノスペースなど) を指定する値。

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>解説

詳細については[、コンストラクターの](#cmfcfontinfo) *nPitchAndFamily*パラメーターを参照してください。

## <a name="cmfcfontinfom_ntype"></a><a name="m_ntype"></a>フォント情報::m_nType

フォントの種類を指定する値。

```
const int m_nType;
```

### <a name="remarks"></a>解説

詳細については[、コンストラクターの](#cmfcfontinfo) *nType*パラメーターを参照してください。

## <a name="cmfcfontinfom_strname"></a><a name="m_strname"></a>m_strName

フォントの名前 : たとえば、 **Arial**.

```
const CString m_strName;
```

### <a name="remarks"></a>解説

詳細については[、コンストラクターの](#cmfcfontinfo) *lpszName*パラメーターを参照してください。

## <a name="cmfcfontinfom_strscript"></a><a name="m_strscript"></a>フォント情報::m_strScript

フォントに関連付けられた文字セット (スクリプト) の名前。

```
const CString m_strScript;
```

### <a name="remarks"></a>解説

詳細については[、コンストラクターの](#cmfcfontinfo) *lpszScript*パラメーターを参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[コンボボックス クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[コンボボックス クラス](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
