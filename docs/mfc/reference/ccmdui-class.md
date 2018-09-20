---
title: CCmdUI クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
dev_langs:
- C++
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 288dbaa5bb3c0d7f1731d996e6f4b1daed93d14e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411379"
---
# <a name="ccmdui-class"></a>CCmdUI クラス

内でのみ使用、`ON_UPDATE_COMMAND_UI`でハンドラーを`CCmdTarget`-クラスを派生します。

## <a name="syntax"></a>構文

```
class CCmdUI
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCmdUI::ContinueRouting](#continuerouting)|ハンドラーのチェーンに現在のメッセージのルーティングを続行するコマンド ルーティング メカニズムに指示します。|
|[関数](#enable)|有効またはこのコマンドのユーザー インターフェイス項目を無効にします。|
|[CCmdUI::SetCheck](#setcheck)|このコマンドのユーザー インターフェイスの項目のチェックの状態を設定します。|
|[CCmdUI::SetRadio](#setradio)|ように、`SetCheck`メンバー関数では、オプション ボタン グループが動作します。|
|[CCmdUI::SetText](#settext)|このコマンドのユーザー インターフェイスの項目のテキストを設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CCmdUI::m_nID](#m_nid)|ユーザー インターフェイス オブジェクトの ID。|
|[CCmdUI::m_nIndex](#m_nindex)|ユーザー インターフェイス オブジェクトのインデックス。|
|[CCmdUI::m_pMenu](#m_pmenu)|によって表されるメニューを指す、`CCmdUI`オブジェクト。|
|[CCmdUI::m_pOther](#m_pother)|通知を送信したウィンドウ オブジェクトへのポインター。|
|[CCmdUI::m_pSubMenu](#m_psubmenu)|によって表される包含のサブメニューを指す、`CCmdUI`オブジェクト。|

## <a name="remarks"></a>Remarks

`CCmdUI` 基本クラスはありません。

ときに、アプリケーションのユーザーは、メニューの各メニュー項目のニーズを知るかどうか、表示するか有効になっているまたは無効になっています。 メニュー コマンドのターゲットは、ON_UPDATE_COMMAND_UI ハンドラーを実装することでこの情報を提供します。 アプリケーション内のコマンドのユーザー インターフェイス オブジェクトごとに、[プロパティ] ウィンドウを使用して、ハンドラーごとのメッセージ マップ エントリと関数のプロトタイプを作成します。

各ハンドラーが呼び出す、メニューがプルダウンときに、フレームワークを検索し、各 ON_UPDATE_COMMAND_UI ハンドラーを呼び出す`CCmdUI`などの関数メンバー`Enable`と`Check`、し、フレームワーク、適切に、各メニュー項目を表示します。

メニュー項目は、内のコードを変更することがなく、コントロール バー ボタンやその他のコマンドのユーザー インターフェイス オブジェクトに置き換えることが、`ON_UPDATE_COMMAND_UI`ハンドラー。

次の表に、効果`CCmdUI`'s、さまざまなコマンドのユーザー インターフェイスのアイテムがあるメンバー関数。

|ユーザー インターフェイス項目|[有効化]|SetCheck|SetRadio|SetText|
|--------------------------|------------|--------------|--------------|-------------|
|メニュー項目|有効または無効にします。|オンまたはオフに|ドットを使用したチェックします。|項目テキストの設定|
|ツール バー ボタン|有効または無効にします。|選択、未選択、または中間|`SetCheck` と同じ|(適用なし)|
|ステータス バー ペイン|テキストは、表示または非表示|セットのポップアウトまたは通常の境界線|`SetCheck` と同じ|ウィンドウのテキストを設定します。|
|通常のボタン `CDialogBar`|有効または無効にします。|オンまたはチェック ボックスをオフに|`SetCheck` と同じ|ボタン テキストの設定|
|通常の制御 `CDialogBar`|有効または無効にします。|(適用なし)|(適用なし)|ウィンドウのテキストを設定します。|

このクラスの使用方法の詳細は、次を参照してください。[ユーザー インターフェイス オブジェクトを更新する方法](../../mfc/how-to-update-user-interface-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`CCmdUI`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

##  <a name="continuerouting"></a>  CCmdUI::ContinueRouting

ハンドラーのチェーンに現在のメッセージのルーティングを続行するコマンド ルーティング メカニズムを確認するには、このメンバー関数を呼び出します。

```
void ContinueRouting();
```

### <a name="remarks"></a>Remarks

これは、高度なメンバー関数は FALSE を返す ON_COMMAND_EX ハンドラーと組み合わせて使用する必要があります。 詳細については、次を参照してください。[テクニカル ノート 6](../../mfc/tn006-message-maps.md)します。

##  <a name="enable"></a>  関数

有効またはこのコマンドのユーザー インターフェイス項目を無効にするには、このメンバー関数を呼び出します。

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>パラメーター

*bOn*<br/>
無効にする false の場合、項目を有効にする場合は TRUE。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

##  <a name="m_nid"></a>  CCmdUI::m_nID

メニュー項目、ツールバーのボタンによって表されるその他のユーザー インターフェイス オブジェクトの ID、`CCmdUI`オブジェクト。

```
UINT m_nID;
```

##  <a name="m_nindex"></a>  CCmdUI::m_nIndex

メニュー項目やツールバーのボタンによって表されるその他のユーザー インターフェイス オブジェクトのインデックス、`CCmdUI`オブジェクト。

```
UINT m_nIndex;
```

##  <a name="m_pmenu"></a>  CCmdUI::m_pMenu

ポインター (の`CMenu`型) で表されるメニューに、`CCmdUI`オブジェクト。

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>Remarks

項目がメニューではない場合は NULL です。

##  <a name="m_psubmenu"></a>  CCmdUI::m_pSubMenu

ポインター (の`CMenu`型) で表される包含のサブメニューを`CCmdUI`オブジェクト。

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>Remarks

項目がメニューではない場合は NULL です。 場合、サブメニューは、ポップアップ*サブメニュー*ポップアップ メニューの最初の項目の ID が含まれています。 詳細については、次を参照してください。[テクニカル ノート 21](../../mfc/tn021-command-and-message-routing.md)します。

##  <a name="m_pother"></a>  CCmdUI::m_pOther

ポインター (型の`CWnd`)、通知を送信したツールバーやステータス バーなど、ウィンドウ オブジェクト。

```
CWnd* m_pOther;
```

### <a name="remarks"></a>Remarks

項目がメニューまたは以外の場合は NULL`CWnd`オブジェクト。

##  <a name="setcheck"></a>  CCmdUI::SetCheck

このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定するには、このメンバー関数を呼び出します。

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>パラメーター

*確認してください。*<br/>
設定をチェックの状態を指定します。 場合は、0 がオフにします。場合 1 を確認します。2 の場合は、不確定な設定とします。

### <a name="remarks"></a>Remarks

このメンバー関数は、メニュー項目とツールバーのボタンに対して機能します。 中間の状態は、ツールバーのボタンにのみ適用されます。

##  <a name="setradio"></a>  CCmdUI::SetRadio

このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定するには、このメンバー関数を呼び出します。

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>パラメーター

*bOn*<br/>
アイテムを有効にする場合は TRUEそれ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

このメンバー関数のように動作する`SetCheck`ラジオ グループの一部として機能するユーザー インターフェイス項目上で動作する点を除いて、します。 項目自体は、オプション ボタン グループの動作を維持している場合、グループ内の他の項目をオフにする自動はありません。

##  <a name="settext"></a>  CCmdUI::SetText

このコマンドのユーザー インターフェイスの項目のテキストを設定するには、このメンバー関数を呼び出します。

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
テキスト文字列へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル MDI](../../visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
