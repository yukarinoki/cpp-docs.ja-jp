---
title: クラスを既定の状態にします。
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
ms.openlocfilehash: 56219e8ed1833f4b448ec6ffd3c16e9db3c66ada
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368874"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>クラスを既定の状態にします。

リボン バー [(CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)クラス) に配置されているクイック アクセス ツール バーの既定の状態を管理するヘルパー クラス。

## <a name="syntax"></a>構文

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[既定の状態:::CMFC リボン クイック アクセス ツールバーの既定の状態](#cmfcribbonquickaccesstoolbardefaultstate)|`CMFCRibbonQuickAccessToolbarDefaultState` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[既定の状態::コマンドの追加](#addcommand)|クイック アクセス ツールバーの既定の状態にコマンドを追加します。 この方法では、ツールバー自体は変更されません。|
|[既定の状態::コピーから](#copyfrom)|クイック アクセス ツールバーのプロパティを別のクイック アクセス ツールバーにコピーします。|
|[既定の状態::すべて削除](#removeall)|クイック アクセス ツールバーからすべてのコマンドを削除します。 この方法では、ツールバー自体は変更されません。|

## <a name="remarks"></a>解説

アプリケーションでクイック アクセス ツール バーを作成した後[、CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)を呼び出して既定の状態を設定することをお勧めします。 この既定の状態は、ユーザーがアプリケーションの **[オプション]** ダイアログ ボックスの [**カスタマイズ**] ページの [**リセット**] ボタンをクリックすると復元されます。

## <a name="inheritance-hierarchy"></a>継承階層

[既定の状態](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>例

次の例は、`CMFCRibbonQuickAccessToolbarDefaultState`クラスのオブジェクトを構築する方法と、クイック アクセス ツール バーの既定の状態にコマンドを追加する方法を示しています。

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribbon クイックアクセスツールバー.h

## <a name="cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a>既定の状態::コマンドの追加

クイック アクセス ツールバーの既定の状態にコマンドを追加します。

```
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>パラメーター

*[in] uiCmd*<br/>
コマンド ID を指定します。

*[in] ビズブル*<br/>
クイック アクセス ツールバーが既定の状態の場合に、コマンドの表示/非表示を設定します。

### <a name="remarks"></a>解説

コマンドを追加すると、3 つの結果が得られます。 まず、追加した各コマンドがクイック アクセス ツールバーの右側のドロップダウンリストに表示されます。 この方法で、ユーザーはクイック アクセス ツール バーにコマンドを簡単に追加または削除できます。 次に、クイック アクセス ツール バーがリセットされ、ユーザーが [**カスタマイズ]** ダイアログ ボックスの [**リセット**] ボタンをクリックしたときに、既定の状態で表示されているコマンドのみが表示されます。 3 つ目は[、CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands)を呼び出していない場合、クイック アクセス ツール バーは、ユーザーがアプリケーションを初めて実行するときに、この一覧から表示されるコマンドを既定の表示コマンドとして使用します。 必要なすべてのコマンドを追加したら[、CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)を呼び出して、このインスタンスをリボン バーのクイック アクセス ツール バーの既定の状態に設定します。

## <a name="cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a>既定の状態::コピーから

クイック アクセス ツールバーのプロパティを別のクイック アクセス ツールバーにコピーします。

```
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]コピー元のソース`CMFCRibbonQuickAccessToolBarDefaultState`オブジェクトへの参照。

### <a name="remarks"></a>解説

このメソッドは、`CMFCRibbonQuickAccessToolBarDefaultState`[ソース](#addcommand)オブジェクトからこのオブジェクトに各コマンドをコピーします。

## <a name="cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a>既定の状態:::CMFC リボン クイック アクセス ツールバーの既定の状態

クイック アクセス ツール バーの既定の状態オブジェクトを作成します。

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>解説

既定では、[新](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)しいインスタンスに含まれるコマンドの一覧は空です。

## <a name="cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a>既定の状態::すべて削除

クイック アクセス ツールバーの既定のコマンドの一覧をクリアします。

```
void RemoveAll();
```

### <a name="remarks"></a>解説

この関数は、このインスタンスから、以前に呼び出されたコマンドをすべて[削除します](#addcommand)。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcribbonbar-class.md)
