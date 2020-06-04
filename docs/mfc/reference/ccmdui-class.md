---
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
ms.openlocfilehash: 3e167d9e305481e05808f5e553222c10abbc88de
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752726"
---
# <a name="ccmdui-class"></a>CCmdUI クラス

派生クラスの`ON_UPDATE_COMMAND_UI`ハンドラー内`CCmdTarget`でのみ使用されます。

## <a name="syntax"></a>構文

```
class CCmdUI
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ルーティングの続行](#continuerouting)|現在のメッセージをハンドラーのチェーンにルーティングし続けるコマンド ルーティング メカニズムを指示します。|
|[を有効にします。](#enable)|このコマンドのユーザー インターフェイス項目を有効または無効にします。|
|[を設定します。](#setcheck)|このコマンドのユーザー インターフェイス項目のチェック状態を設定します。|
|[CCmdUI::セットラジオ](#setradio)|メンバー関数`SetCheck`と同様に、無線グループで動作します。|
|[を設定します。](#settext)|このコマンドのユーザー インターフェイスアイテムのテキストを設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CCmdUI::m_nID](#m_nid)|ユーザー インターフェイス オブジェクトの ID。|
|[CCmdUI::m_nIndex](#m_nindex)|ユーザー インターフェイス オブジェクトのインデックス。|
|[CCmdUI::m_pMenu](#m_pmenu)|オブジェクトが表すメニューへの`CCmdUI`ポイント。|
|[CCmdUI::m_pOther](#m_pother)|通知を送信したウィンドウ オブジェクトへのポイント。|
|[CCmdUI:m_pSubMenu](#m_psubmenu)|オブジェクトによって表される含まれているサブメニューへの`CCmdUI`ポイント。|

## <a name="remarks"></a>解説

`CCmdUI`は基本クラスを持っていません。

アプリケーションのユーザーがメニューをプル ダウンする場合、各メニュー項目は、有効または無効として表示するかどうかを知る必要があります。 メニュー コマンドのターゲットは、ON_UPDATE_COMMAND_UI ハンドラーを実装することによって、この情報を提供します。 アプリケーションのコマンド ユーザー インターフェイス オブジェクトごとに、クラス ウィザードまたは **[プロパティ]** ウィンドウ **([クラス ビュー**] ) を使用して、各ハンドラーのメッセージ マップ エントリと関数プロトタイプを作成します。 [Class Wizard](mfc-class-wizard.md)

メニューがプル ダウンされると、フレームワークは各ON_UPDATE_COMMAND_UI ハンドラを検索して呼び出し`CCmdUI`、各ハンドラは`Enable``Check`メンバー関数を呼び出します ( および など) を、フレームワークは各メニュー項目を適切に表示します。

メニュー項目は、ハンドラー内のコードを変更せずに、コントロール バー ボタンまたはその他のコマンド ユーザー インターフェイス`ON_UPDATE_COMMAND_UI`オブジェクトに置き換えることができます。

次の表は、さまざまなコマンド`CCmdUI`ユーザー インターフェイス項目に対するメンバー関数の効果をまとめたものです。

|ユーザー インターフェイス項目|有効化|セットチェック|セットラジオ|Settext|
|--------------------------|------------|--------------|--------------|-------------|
|メニュー項目|有効または無効にする|チェックまたはチェックを解除|ドットを使用してチェックする|アイテムテキストを設定します|
|ツール バー ボタン|有効または無効にする|選択、選択解除、または不確定|`SetCheck` と同じ|(該当なし)|
|ステータス バー ペイン|テキストを表示または非表示にする|ポップアウトまたは通常の境界線を設定します。|`SetCheck` と同じ|ペインテキストを設定する|
|標準ボタン`CDialogBar`|有効または無効にする|チェックボックスをオンまたはオフにする|`SetCheck` と同じ|ボタンテキストを設定します|
|の通常の制御`CDialogBar`|有効または無効にする|(該当なし)|(該当なし)|ウィンドウテキストを設定します。|

このクラスの使用方法の詳細については、「[ユーザー インターフェイス オブジェクトを更新する方法](../../mfc/how-to-update-user-interface-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CCmdUI`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="ccmduicontinuerouting"></a><a name="continuerouting"></a>ルーティングの続行

現在のメッセージをハンドラーのチェーンにルーティングし続けるコマンド ルーティング 機構に指示するには、このメンバー関数を呼び出します。

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>解説

これは、FALSE を返すON_COMMAND_EX ハンドラーと共に使用する高度なメンバー関数です。 詳細については、テクニカル[ノート 6](../../mfc/tn006-message-maps.md)を参照してください。

## <a name="ccmduienable"></a><a name="enable"></a>を有効にします。

このコマンドのユーザー インターフェイス項目を有効または無効にします。

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>パラメーター

*ボン*<br/>
TRUE を指定すると項目が有効になり、FALSE を指定して無効になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

## <a name="ccmduim_nid"></a><a name="m_nid"></a>CCmdUI::m_nID

オブジェクトによって表されるメニュー項目、ツール バー ボタン、またはその他のユーザー インターフェイス`CCmdUI`オブジェクトの ID。

```
UINT m_nID;
```

## <a name="ccmduim_nindex"></a><a name="m_nindex"></a>CCmdUI::m_nIndex

オブジェクトによって表されるメニュー項目、ツール バー ボタン、またはその他のユーザー インターフェイス`CCmdUI`オブジェクトのインデックス。

```
UINT m_nIndex;
```

## <a name="ccmduim_pmenu"></a><a name="m_pmenu"></a>CCmdUI::m_pMenu

`CCmdUI`オブジェクトが`CMenu`表すメニューへのポインタ (型)。

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>解説

項目がメニューでない場合は NULL。

## <a name="ccmduim_psubmenu"></a><a name="m_psubmenu"></a>CCmdUI:m_pSubMenu

オブジェクトによって表`CMenu`される、格納されているサブメニューへのポインター (型`CCmdUI`)。

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>解説

項目がメニューでない場合は NULL。 サブメニューがポップアップの場合 *、m_nID*にはポップアップメニューの最初の項目の ID が含まれます。 詳細については、テクニカル[ノート 21](../../mfc/tn021-command-and-message-routing.md)を参照してください。

## <a name="ccmduim_pother"></a><a name="m_pother"></a>CCmdUI::m_pOther

通知を送信した`CWnd`ツールやステータス バーなどのウィンドウ オブジェクトへのポインター ( 型 ) です。

```
CWnd* m_pOther;
```

### <a name="remarks"></a>解説

項目がメニューまたは非`CWnd`オブジェクトの場合は NULL。

## <a name="ccmduisetcheck"></a><a name="setcheck"></a>を設定します。

このメンバー関数を呼び出して、このコマンドのユーザー インターフェイス項目を適切なチェック状態に設定します。

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>パラメーター

*nチェック*<br/>
設定するチェック状態を指定します。 0 の場合は、チェックを解除します。1 の場合は、チェックします。2 の場合は、不確定を設定します。

### <a name="remarks"></a>解説

このメンバー関数は、メニュー項目とツール バー ボタンに対して機能します。 不確定状態は、ツール バー ボタンにのみ適用されます。

## <a name="ccmduisetradio"></a><a name="setradio"></a>CCmdUI::セットラジオ

このメンバー関数を呼び出して、このコマンドのユーザー インターフェイス項目を適切なチェック状態に設定します。

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>パラメーター

*ボン*<br/>
アイテムを有効にする場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメンバー関数は、`SetCheck`無線グループの一部として機能するユーザー インターフェイス項目に対して動作する点を除いて、 のように動作します。 項目自体が無線グループの動作を維持しない限り、グループ内の他の項目のチェックを外しても自動ではありません。

## <a name="ccmduisettext"></a><a name="settext"></a>を設定します。

このコマンドのユーザー インターフェイス項目のテキストを設定します。

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
テキスト文字列へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>関連項目

[MDI のサンプル](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
