---
description: ': CCmdUI クラスに関する詳細情報'
title: CCmdUI クラス
ms.date: 09/06/2019
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
ms.openlocfilehash: d868c0dc3c9915f5300f56e5bfa5f1971d4ec3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132991"
---
# <a name="ccmdui-class"></a>CCmdUI クラス

は `ON_UPDATE_COMMAND_UI` 、派生クラスのハンドラー内でのみ使用され `CCmdTarget` ます。

## <a name="syntax"></a>構文

```
class CCmdUI
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCmdUI:: ContinueRouting](#continuerouting)|は、現在のメッセージのルーティングをハンドラーのチェーンの下位にルーティングするようにコマンドルーティング機構に指示します。|
|[CCmdUI:: Enable](#enable)|このコマンドのユーザーインターフェイス項目を有効または無効にします。|
|[CCmdUI:: SetCheck](#setcheck)|このコマンドのユーザーインターフェイス項目のチェックの状態を設定します。|
|[CCmdUI:: SetRadio](#setradio)|`SetCheck`メンバー関数と同様ですが、ラジオグループで動作します。|
|[CCmdUI:: SetText](#settext)|このコマンドのユーザーインターフェイス項目のテキストを設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CCmdUI:: m_nID](#m_nid)|ユーザーインターフェイスオブジェクトの ID。|
|[CCmdUI:: m_nIndex](#m_nindex)|ユーザーインターフェイスオブジェクトのインデックス。|
|[CCmdUI:: m_pMenu](#m_pmenu)|オブジェクトによって表されるメニューをポイントし `CCmdUI` ます。|
|[CCmdUI:: m_pOther](#m_pother)|通知を送信したウィンドウオブジェクトを指します。|
|[CCmdUI:: m_pSubMenu](#m_psubmenu)|オブジェクトによって表される、含まれているサブメニューを指し `CCmdUI` ます。|

## <a name="remarks"></a>解説

`CCmdUI` に基底クラスがありません。

アプリケーションのユーザーがメニューを取得すると、各メニュー項目は、[有効] または [無効] と表示されているかどうかを確認する必要があります。 メニューコマンドのターゲットは、ON_UPDATE_COMMAND_UI ハンドラーを実装することによってこの情報を提供します。 アプリケーションの各コマンドユーザーインターフェイスオブジェクトに対して、 [クラスウィザード](mfc-class-wizard.md) または **プロパティ** ウィンドウ ( **クラスビュー**) を使用して、各ハンドラーのメッセージマップエントリと関数プロトタイプを作成します。

メニューがプルダウンされると、フレームワークは各 ON_UPDATE_COMMAND_UI ハンドラーを検索して呼び出します。各ハンドラーはやなどのメンバー関数を呼び出し、 `CCmdUI` `Enable` `Check` フレームワークは各メニュー項目を適切に表示します。

メニュー項目は、ハンドラー内のコードを変更することなく、コントロールバーボタンまたはその他のコマンドユーザーインターフェイスオブジェクトに置き換えることができ `ON_UPDATE_COMMAND_UI` ます。

次の表は、 `CCmdUI` さまざまなコマンドユーザーインターフェイス項目に対する効果のメンバー関数の概要を示しています。

|User-Interface 項目|有効にする|SetCheck|SetRadio|SetText|
|--------------------------|------------|--------------|--------------|-------------|
|メニュー項目|有効または無効にする|確認またはオフにする|ドットを使用したチェック|項目のテキストを設定します|
|ツール バー ボタン|有効または無効にする|選択、選択解除、または不確定|`SetCheck` と同じ|(該当なし)|
|ステータスバーウィンドウ|テキストを表示または非表示にします|ポップアウトまたは通常の罫線を設定します|`SetCheck` と同じ|ペインテキストの設定|
|の通常のボタン `CDialogBar`|有効または無効にする|チェックボックスをオンまたはオフにします。|`SetCheck` と同じ|ボタンのテキストを設定します|
|通常のコントロール `CDialogBar`|有効または無効にする|(該当なし)|(該当なし)|ウィンドウテキストを設定します|

このクラスの使用の詳細については、「 [How To Update User-Interface Objects](../../mfc/how-to-update-user-interface-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CCmdUI`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="ccmduicontinuerouting"></a><a name="continuerouting"></a> CCmdUI:: ContinueRouting

このメンバー関数を呼び出して、現在のメッセージのルーティングを続行するようにコマンドルーティング機構に指示します。

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>解説

これは、FALSE を返す ON_COMMAND_EX ハンドラーと組み合わせて使用する必要がある高度なメンバー関数です。 詳細については、「 [テクニカルノート 6](../../mfc/tn006-message-maps.md)」を参照してください。

## <a name="ccmduienable"></a><a name="enable"></a> CCmdUI:: Enable

このメンバー関数を呼び出して、このコマンドのユーザーインターフェイス項目を有効または無効にします。

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>パラメーター

*楽しい*<br/>
項目を有効にする場合は TRUE、無効にする場合は FALSE。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

## <a name="ccmduim_nid"></a><a name="m_nid"></a> CCmdUI:: m_nID

オブジェクトによって表されるメニュー項目、ツールバーボタン、またはその他のユーザーインターフェイスオブジェクトの ID `CCmdUI` 。

```
UINT m_nID;
```

## <a name="ccmduim_nindex"></a><a name="m_nindex"></a> CCmdUI:: m_nIndex

オブジェクトによって表されるメニュー項目、ツールバーボタン、またはその他のユーザーインターフェイスオブジェクトのインデックス `CCmdUI` 。

```
UINT m_nIndex;
```

## <a name="ccmduim_pmenu"></a><a name="m_pmenu"></a> CCmdUI:: m_pMenu

`CMenu`オブジェクトによって表されるメニューへのポインター (型) `CCmdUI` 。

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>解説

項目がメニューでない場合は NULL。

## <a name="ccmduim_psubmenu"></a><a name="m_psubmenu"></a> CCmdUI:: m_pSubMenu

`CMenu`オブジェクトによって表される、格納されているサブメニューへのポインター (型) `CCmdUI` 。

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>解説

項目がメニューでない場合は NULL。 サブメニューがポップアップの場合、 *m_nID* には、ポップアップメニューの最初の項目の ID が含まれます。 詳細については、「 [テクニカルノート 21](../../mfc/tn021-command-and-message-routing.md)」を参照してください。

## <a name="ccmduim_pother"></a><a name="m_pother"></a> CCmdUI:: m_pOther

通知を送信し `CWnd` たウィンドウオブジェクトに対する (型の) ポインター (ツールやステータスバーなど)。

```
CWnd* m_pOther;
```

### <a name="remarks"></a>解説

項目がメニューまたは非オブジェクトである場合は NULL `CWnd` 。

## <a name="ccmduisetcheck"></a><a name="setcheck"></a> CCmdUI:: SetCheck

このメンバー関数を呼び出して、このコマンドのユーザーインターフェイス項目を適切なチェック状態に設定します。

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>パラメーター

*n*<br/>
設定するチェック状態を指定します。 0の場合は、オフにします。1の場合、をチェックします。2の場合、は不確定を設定します。

### <a name="remarks"></a>解説

このメンバー関数は、メニュー項目とツールバーボタンに対して機能します。 不確定状態は、ツールバーボタンにのみ適用されます。

## <a name="ccmduisetradio"></a><a name="setradio"></a> CCmdUI:: SetRadio

このメンバー関数を呼び出して、このコマンドのユーザーインターフェイス項目を適切なチェック状態に設定します。

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>パラメーター

*楽しい*<br/>
項目を有効にする場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメンバー関数はと同じように動作し `SetCheck` ますが、ラジオグループの一部として機能するユーザーインターフェイス項目で動作する点が異なります。 グループ内の他の項目をオフにすることは、項目自体がラジオグループの動作を維持していない限り、自動ではありません。

## <a name="ccmduisettext"></a><a name="settext"></a> CCmdUI:: SetText

このメンバー関数を呼び出して、このコマンドのユーザーインターフェイス項目のテキストを設定します。

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
テキスト文字列へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>関連項目

[MFC のサンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
