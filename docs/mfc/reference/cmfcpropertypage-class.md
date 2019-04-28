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
ms.openlocfilehash: 62e33da998f1e5332436d887c38d3fd65526561b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310490"
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage クラス

`CMFCPropertyPage`クラスは、[プロパティ] ページのポップアップ メニューの表示をサポートしています。

## <a name="syntax"></a>構文

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|`CMFCPropertyPage` オブジェクトを構築します。|
|`CMFCPropertyPage::~CMFCPropertyPage`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCPropertyPage::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|
|`CMFCPropertyPage::OnSetActive`|このメンバー関数は、ページは、ユーザーが選択され、アクティブになったときにフレームワークによって呼び出されます。 (上書き[CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive))。|
|`CMFCPropertyPage::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 関数。 詳細とメソッド構文は、次を参照してください。 [cwnd::pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)します。 ( `CPropertyPage::PreTranslateMessage`をオーバーライドします)。|

## <a name="remarks"></a>Remarks

`CMFCPropertyPage`クラスは、[タブ] ダイアログ ボックスとも呼ばれる、プロパティ シートの各ページを表します。

使用して、`CMFCPropertyPage`クラスと組み合わせて、 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)クラス。 プロパティ ページ メニューを使用するには、すべての出現箇所を置き換えます、`CPropertyPage`クラス、`CMFCPropertyPage`クラス。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpropertypage.h

##  <a name="cmfcpropertypage"></a>  CMFCPropertyPage::CMFCPropertyPage

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

*nIDTemplate*<br/>
このページのテンプレートのリソース ID。

*nIDCaption*<br/>
このページのタブに配置する、ラベルのリソース ID。 0 の場合、名前は、このページのダイアログ ボックス テンプレートから取得されます。 既定値は 0 です。

*lpszTemplateName*<br/>
このページのテンプレートの名前を指します。 Nll は指定できません。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

コンス トラクターのパラメーターの詳細については、次を参照してください。 [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertySheet クラス](../../mfc/reference/cmfcpropertysheet-class.md)
