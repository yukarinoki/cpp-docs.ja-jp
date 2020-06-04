---
title: プロパティプロパティ
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 0ce3321968f0c29ce3b946f6127e4435b531c422
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360579"
---
# <a name="cmfcpropertygridfileproperty-class"></a>プロパティプロパティ

この`CMFCPropertyGridFileProperty`クラスは、ファイル選択ダイアログ ボックスを開くプロパティ リスト コントロール項目をサポートします。

## <a name="syntax"></a>構文

```
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[プロパティ::プロパティプロパティ](#cmfcpropertygridfileproperty)|`CMFCPropertyGridFileProperty` オブジェクトを構築します。|
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCPropertyGridFileProperty::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|`CMFCPropertyGridFileProperty::OnClickButton`|([プロパティプロパティをオーバーライドします。](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)|

### <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpropertygridctrl.h

## <a name="cmfcpropertygridfilepropertycmfcpropertygridfileproperty"></a><a name="cmfcpropertygridfileproperty"></a>プロパティ::プロパティプロパティ

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

*ファイルダイアログを開く*<br/>
[in][**ファイルを開く**] ダイアログ ボックスを開く場合は TRUE。FALSE を指定すると、[**ファイルの保存**] ダイアログ ボックスが開きます。

*ファイル名*<br/>
[in]初期ファイル名。

*を使用します。*<br/>
[in]1 つ以上のファイル名拡張子の文字列。 既定値は NULL です。

*dwFlags*<br/>
[in]ダイアログ ボックスのフラグ。 既定値は OFN_HIDEREADONLY と OFN_OVERWRITEPROMPT のビットごとの組み合わせ (OR) です。

*Lpszfilter*<br/>
[in]1 つ以上のファイル フィルタの文字列。 既定値は NULL です。

*lpszDescr*<br/>
[in]プロパティ項目の説明。 既定値は NULL です。

*dw データ*<br/>
[in]プロパティ項目に関連付けられているアプリケーション固有のデータ。 たとえば、32 ビット整数またはその他のデータへのポインター。 既定値は 0 です。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

使用可能なフラグの完全なリストについては[、OPENFILENAME 構造体](/windows/win32/api/commdlg/ns-commdlg-openfilenamew)を参照してください。

### <a name="example"></a>例

次の例では、`CMFCPropertyGridFileProperty` クラスのコンストラクターを使用してオブジェクトを作成する方法を示します。 この例は[、Visual Studio のデモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[プロパティプロパティ](../../mfc/reference/cmfcpropertygridproperty-class.md)
