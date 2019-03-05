---
title: CMFCPropertyGridFileProperty クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 5022063fe7eb8242f01684438e2fdeeeedc80616
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302898"
---
# <a name="cmfcpropertygridfileproperty-class"></a>CMFCPropertyGridFileProperty クラス

`CMFCPropertyGridFileProperty`クラスは、ファイルの選択 ダイアログ ボックスを開くプロパティ リスト コントロール項目をサポートしています。

## <a name="syntax"></a>構文

```
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|`CMFCPropertyGridFileProperty` オブジェクトを構築します。|
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCPropertyGridFileProperty::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|
|`CMFCPropertyGridFileProperty::OnClickButton`|(上書き[cmfcpropertygridproperty::onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton))。|

### <a name="remarks"></a>Remarks

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpropertygridctrl.h

##  <a name="cmfcpropertygridfileproperty"></a>  CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty

`CMFCPropertyGridFileProperty` オブジェクトを構築します。

```
CMFCPropertyGridFileProperty(
    const CString& strName,
    BOOL bOpenFileDialog,
    const CString& strFileName,
    LPCTSTR lpszDefExt=NULL,
    DWORD dwFlags=OFN_HIDEREADONLY|OFN_OVERWRITEPROMPT,
    LPCTSTR lpszFilter=NULL,
    LPCTSTR lpszDescr=NULL,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>パラメーター

*strName*<br/>
[in]プロパティ名。

*bOpenFileDialog*<br/>
[in]オープンする場合は True、**ファイルを開く**; ダイアログ ボックス開く場合は FALSE、**ファイルを保存** ダイアログ ボックス。

*strFileName*<br/>
[in]初期ファイル名。

*lpszDefExt*<br/>
[in]1 つまたは複数のファイル名拡張子の文字列。 既定値は、NULL です。

*dwFlags*<br/>
[in]ダイアログ ボックスのフラグ。 既定値は OFN_HIDEREADONLY と OFN_OVERWRITEPROMPT のビットごとの組み合わせ (OR) です。

*lpszFilter*<br/>
[in]1 つまたは複数のファイル フィルターの文字列。 既定値は、NULL です。

*lpszDescr*<br/>
[in]プロパティ項目の説明。 既定値は、NULL です。

*dwData*<br/>
[in]プロパティ項目に関連付けられているアプリケーションに固有のデータ。 たとえば、32 ビット整数またはその他のデータへのポインター。 既定値は 0 です。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

使用可能なフラグの一覧については、次を参照してください。 [OPENFILENAME 構造体](/windows/desktop/api/commdlg/ns-commdlg-tagofna)します。

### <a name="example"></a>例

次の例では、`CMFCPropertyGridFileProperty` クラスのコンストラクターを使用してオブジェクトを作成する方法を示します。 この例は、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty クラス](../../mfc/reference/cmfcpropertygridproperty-class.md)
