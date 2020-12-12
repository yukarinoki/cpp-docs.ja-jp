---
description: '詳細情報: CMFCRibbonCustomizePropertyPage クラス'
title: CMFCRibbonCustomizePropertyPage クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
ms.openlocfilehash: 93792858cec9d07a73bfec56a282b8d672249cf6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293600"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage クラス

リボンベースのアプリケーションの [ **ユーザー設定** ] ダイアログボックスのカスタムページを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|-|-|
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|`CMFCRibbonCustomizePropertyPage` オブジェクトを構築します。|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[CMFCRibbonCustomizePropertyPage:: AddCustomCategory](#addcustomcategory)|[ **コマンド** ] コンボボックスにカスタムカテゴリを追加します。|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCRibbonCustomizePropertyPage:: OnOK](#onok)|ユーザーが [**カスタマイズ**] ダイアログボックスで **[OK]** をクリックすると、システムによって呼び出されます。|

## <a name="remarks"></a>解説

[ユーザー **設定** ] ダイアログボックスにカスタムコマンドを追加する場合は、AFX_WM_ON_RIBBON_CUSTOMIZE メッセージを処理する必要があります。 メッセージハンドラーで、 `CMFCRibbonCustomizePropertyPage` スタック上のオブジェクトをインスタンス化します。 カスタムコマンドのリストを作成し、を呼び出して `AddCustomCategory` 、[ **カスタマイズ** ] ダイアログボックスに新しいページを追加します。

## <a name="example"></a>例

次の例では、オブジェクトを作成し、カスタムカテゴリを追加する方法を示し `CMFCRibbonCustomizePropertyPage` ます。

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribboncustomizedialog

## <a name="cmfcribboncustomizepropertypageaddcustomcategory"></a><a name="addcustomcategory"></a> CMFCRibbonCustomizePropertyPage:: AddCustomCategory

[ **コマンド** ] コンボボックスにカスタムカテゴリを追加します。

```cpp
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>パラメーター

*lpszName*\
からカスタムカテゴリ名を指定します。

*lstIDS*\
からカスタムカテゴリに表示されるリボンコマンド Id を格納します。

### <a name="remarks"></a>解説

このメソッドは、 *Lpszname* という名前のカテゴリを [ **コマンド** ] コンボボックスに追加します。 ユーザーがカテゴリを選択すると、 *lstIDS* で指定されたコマンドがコマンド一覧に表示されます。

## <a name="cmfcribboncustomizepropertypagecmfcribboncustomizepropertypage"></a><a name="cmfcribboncustomizepropertypage"></a> CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage

`CMFCRibbonCustomizePropertyPage` オブジェクトを構築します。

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>パラメーター

*準備中の Bbonbar*<br/>
からカスタマイズするオプションが設定されているリボンコントロールへのポインター。

## <a name="cmfcribboncustomizepropertypageonok"></a><a name="onok"></a> CMFCRibbonCustomizePropertyPage:: OnOK

ユーザーが [**カスタマイズ**] ダイアログボックスで **[OK]** をクリックしたときに、システムによって calleld を呼び出します。

```
virtual void OnOK();
```

### <a name="remarks"></a>解説

既定の実装では、[ **カスタマイズ** ] ダイアログボックスで選択したオプションがクイックアクセスツールバーに適用されます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
