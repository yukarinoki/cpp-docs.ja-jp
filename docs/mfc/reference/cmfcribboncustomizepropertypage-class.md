---
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
ms.openlocfilehash: 57fbd1e1f574beebff8baab014e7ab615f56333f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754176"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage クラス

リボン ベースのアプリケーションの [**カスタマイズ**] ダイアログ ボックスのカスタム ページを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|[プロパティ ページ::CMFC リボンをカスタマイズするプロパティ ページ](#cmfcribboncustomizepropertypage)|`CMFCRibbonCustomizePropertyPage` オブジェクトを構築します。|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[プロパティページ::カスタムカテゴリの追加](#addcustomcategory)|[**コマンド**] コンボ ボックスにカスタム カテゴリを追加します。|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[プロパティページ::オノク](#onok)|ユーザーが [**ユーザー**設定] ダイアログ ボックスで **[OK] を**クリックしたときにシステムによって呼び出されます。|

## <a name="remarks"></a>解説

[**ユーザー設定**] ダイアログ ボックスにカスタム コマンドを追加する場合は、AFX_WM_ON_RIBBON_CUSTOMIZE メッセージを処理する必要があります。 メッセージ ハンドラーで、スタック上`CMFCRibbonCustomizePropertyPage`のオブジェクトをインスタンス化します。 カスタム コマンドの一覧を作成し、`AddCustomCategory`呼び出して [**ユーザー設定**] ダイアログ ボックスに新しいページを追加します。

## <a name="example"></a>例

オブジェクトを構築し、カスタム カテゴリを`CMFCRibbonCustomizePropertyPage`追加する方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[プロパティ ページ](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribbon カスタマイザダイアログ.h

## <a name="cmfcribboncustomizepropertypageaddcustomcategory"></a><a name="addcustomcategory"></a>プロパティページ::カスタムカテゴリの追加

[**コマンド**] コンボ ボックスにカスタム カテゴリを追加します。

```cpp
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*名前を指定します。*|[in]カスタム カテゴリ名を指定します。|
|*lstIDS*|[in]カスタム カテゴリに表示するリボン コマンド ID が含まれています。|

### <a name="remarks"></a>解説

このメソッドは *、lpszName*という名前のカテゴリを **[コマンド**] コンボ ボックスに追加します。 ユーザーがカテゴリを選択すると *、lstIDS*で指定されたコマンドがコマンド・リストに表示されます。

## <a name="cmfcribboncustomizepropertypagecmfcribboncustomizepropertypage"></a><a name="cmfcribboncustomizepropertypage"></a>プロパティ ページ::CMFC リボンをカスタマイズするプロパティ ページ

`CMFCRibbonCustomizePropertyPage` オブジェクトを構築します。

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]カスタマイズするオプションを含むリボン コントロールへのポインター。

## <a name="cmfcribboncustomizepropertypageonok"></a><a name="onok"></a>プロパティページ::オノク

ユーザーが [**カスタマイズ**] ダイアログ ボックスで **[OK] を**クリックしたときに、システムによって呼び出されます。

```
virtual void OnOK();
```

### <a name="remarks"></a>解説

既定の実装では、[**カスタマイズ**] ダイアログ ボックスで選択したオプションがクイック アクセス ツールバーに適用されます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
