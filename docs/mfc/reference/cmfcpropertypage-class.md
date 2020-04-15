---
title: CMFCPropertyPage クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: e493f016b6384a768935186c31e3fc71ade6382f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361764"
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage クラス

この`CMFCPropertyPage`クラスは、プロパティ ページのポップアップ メニューの表示をサポートします。

## <a name="syntax"></a>構文

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[プロパティ ページ::CMFC プロパティ ページ](#cmfcpropertypage)|`CMFCPropertyPage` オブジェクトを構築します。|
|`CMFCPropertyPage::~CMFCPropertyPage`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCPropertyPage::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|`CMFCPropertyPage::OnSetActive`|このメンバー関数は、ユーザーがページを選択してアクティブ ページになったときに、フレームワークによって呼び出されます。 (C[プロパティ ページをオーバーライドします。::アクティブです](../../mfc/reference/cpropertypage-class.md#onsetactive)。|
|`CMFCPropertyPage::PreTranslateMessage`|ウィンドウ メッセージが変換メッセージおよびディスパッチ メッセージの Windows 関数にディスパッチされる前に、ウィンドウ[メッセージを](/windows/win32/api/winuser/nf-winuser-dispatchmessage)[変換](/windows/win32/api/winuser/nf-winuser-translatemessage)します。 詳細とメソッド構文については[、「CWnd::P再翻訳メッセージ](../../mfc/reference/cwnd-class.md#pretranslatemessage)」を参照してください。 ( `CPropertyPage::PreTranslateMessage`をオーバーライドします)。|

## <a name="remarks"></a>解説

この`CMFCPropertyPage`クラスは、プロパティ シートの個々のページを表します。

クラスを`CMFCPropertyPage` [CMFC プロパティ シート](../../mfc/reference/cmfcpropertysheet-class.md)クラスと共に使用します。 プロパティ ページのメニューを使用するには、クラスのすべての出現箇所を`CPropertyPage`クラスに`CMFCPropertyPage`置き換えます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx プロパティ ページ.h

## <a name="cmfcpropertypagecmfcpropertypage"></a><a name="cmfcpropertypage"></a>プロパティ ページ::CMFC プロパティ ページ

`CMFCPropertyPage` オブジェクトを構築します。

```
CMFCPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption=0);

CMFCPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption=0);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
このページのテンプレートのリソース ID です。

*nIDキャプション*<br/>
このページのタブに配置するラベルのリソース ID。 0 の場合、このページのダイアログ ボックス テンプレートから名前が取得されます。 既定値は 0 です。

*テンプレート名*<br/>
このページのテンプレートの名前を指定します。 Nll は指定できません。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

コンストラクター パラメーターの詳細については[、「CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)」を参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertySheet クラス](../../mfc/reference/cmfcpropertysheet-class.md)
