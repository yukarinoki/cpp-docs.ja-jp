---
description: '詳細情報: CMFCRibbonQuickAccessToolBarDefaultState クラス'
title: CMFCRibbonQuickAccessToolBarDefaultState クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
ms.openlocfilehash: d6cd0c32cd8698259de0a78a6a6a7dc42012e92f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321806"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState クラス

リボンバー ( [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)) に配置されているクイックアクセスツールバーの既定の状態を管理するヘルパークラス。

## <a name="syntax"></a>構文

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|`CMFCRibbonQuickAccessToolbarDefaultState` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState:: AddCommand](#addcommand)|クイックアクセスツールバーの既定の状態にコマンドを追加します。 これによって、ツールバー自体は変更されません。|
|[CMFCRibbonQuickAccessToolBarDefaultState:: CopyFrom](#copyfrom)|クイックアクセスツールバーのプロパティを別のクイックアクセスツールバーにコピーします。|
|[CMFCRibbonQuickAccessToolBarDefaultState:: RemoveAll](#removeall)|クイックアクセスツールバーからすべてのコマンドを削除します。 これによって、ツールバー自体は変更されません。|

## <a name="remarks"></a>解説

アプリケーションにクイックアクセスツールバーを作成した後は、 [CMFCRibbonBar:: SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)を呼び出すことによって、既定の状態を設定することをお勧めします。 この既定の状態は、ユーザーがアプリケーションの [**オプション**] ダイアログボックスの [**カスタマイズ**] ページで [**リセット**] ボタンをクリックしたときに復元されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>例

次の例は、クラスのオブジェクトを構築する方法 `CMFCRibbonQuickAccessToolbarDefaultState` と、クイックアクセスツールバーの既定の状態にコマンドを追加する方法を示しています。

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>要件

**ヘッダー:** afxribbonquickaccesstoolbar

## <a name="cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a> CMFCRibbonQuickAccessToolBarDefaultState:: AddCommand

クイックアクセスツールバーの既定の状態にコマンドを追加します。

```cpp
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>パラメーター

*[入力] uiCmd*<br/>
コマンド ID を指定します。

*[入力] bIsVisible*<br/>
クイックアクセスツールバーが既定の状態の場合に、コマンドの表示を設定します。

### <a name="remarks"></a>解説

CMFCRibbonQuickAccessToolBarDefaultState にコマンドを追加すると、3つの結果が得られます。 最初に、追加した各コマンドがクイックアクセスツールバーの右側のドロップダウンリストに表示されます。 この方法では、ユーザーはクイックアクセスツールバーからコマンドを簡単に追加または削除できます。 次に、クイックアクセスツールバーがリセットされ、ユーザーが [**カスタマイズ**] ダイアログボックスの [**リセット**] ボタンをクリックしたときに、既定の状態で表示されているコマンドのみが表示されます。 第3に、 [CMFCRibbonBar:: SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands)を呼び出していない場合、クイックアクセスツールバーでは、ユーザーが初めてアプリケーションを実行したときに、この一覧から表示されるコマンドが既定の表示されるコマンドとして使用されます。 必要なすべてのコマンドを追加したら、 [CMFCRibbonBar:: SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) を呼び出して、このインスタンスをそのリボンバーのクイックアクセスツールバーの既定の状態として設定します。

## <a name="cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a> CMFCRibbonQuickAccessToolBarDefaultState:: CopyFrom

クイックアクセスツールバーのプロパティを別のクイックアクセスツールバーにコピーします。

```cpp
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
からコピー元のソースオブジェクトへの参照 `CMFCRibbonQuickAccessToolBarDefaultState` 。

### <a name="remarks"></a>解説

このメソッド `CMFCRibbonQuickAccessToolBarDefaultState` は、 [CMFCRibbonQuickAccessToolBarDefaultState:: addcommand](#addcommand) メソッドを使用して、ソースオブジェクトからこのオブジェクトに各コマンドをコピーします。

## <a name="cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a> CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState

クイックアクセスツールバーの既定の状態オブジェクトを構築します。

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>解説

既定では、 [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) の新しいインスタンスに含まれるコマンドの一覧は空です。

## <a name="cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a> CMFCRibbonQuickAccessToolBarDefaultState:: RemoveAll

クイックアクセスツールバーの既定のコマンドの一覧を消去します。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

この関数は、前に [CMFCRibbonQuickAccessToolBarDefaultState:: AddCommand](#addcommand) を呼び出したすべてのコマンドをこのインスタンスから削除します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)
