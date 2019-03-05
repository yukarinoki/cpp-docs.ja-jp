---
title: ICommandUI インターフェイス
ms.date: 11/04/2016
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
ms.openlocfilehash: 31157ba2445a432af274650011b839fb3df9b3c2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268175"
---
# <a name="icommandui-interface"></a>ICommandUI インターフェイス

ユーザー インターフェイスのコマンドを管理します。

## <a name="syntax"></a>構文

```
interface class ICommandUI
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[icommandui__Check](#check)|このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。|
|[ICommandUI::ContinueRouting](#continuerouting)|ハンドラーのチェーンに現在のメッセージのルーティングを続行するコマンド ルーティング メカニズムに指示します。|
|[ICommandUI::Enabled](#enabled)|有効またはこのコマンドのユーザー インターフェイス項目を無効にします。|
|[ICommandUI::ID](#id)|によって表されるユーザー インターフェイス オブジェクトの ID を取得、`ICommandUI`オブジェクト。|
|[ICommandUI::Index](#index)|によって表されるユーザー インターフェイス オブジェクトのインデックスを取得、`ICommandUI`オブジェクト。|
|[ICommandUI::Radio](#radio)|このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。|
|[ICommandUI::Text](#text)|このコマンドのユーザー インターフェイスの項目のテキストを設定します。|

## <a name="remarks"></a>Remarks

このインターフェイスは、ユーザー インターフェイスのコマンドを管理するメソッドとプロパティを提供します。 `ICommandUI` ような[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)ことを除いて、`ICommandUI`の .NET コンポーネントと相互運用可能な MFC アプリケーションで使用します。

`ICommandUI` ON_UPDATE_COMMAND_UI ハンドラー内で使用されて、[し、ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-クラスを派生します。 有効になっている、各メニュー項目、メニューが表示されます (選択または数回のクリック)、アプリケーションのユーザーがアクティブ化または無効にします。 各メニュー コマンドのターゲットは、ON_UPDATE_COMMAND_UI ハンドラーを実装することでこの情報を提供します。 アプリケーション内のコマンドのユーザー インターフェイス オブジェクトごとに、[プロパティ] ウィンドウを使用して、メッセージ マップ エントリと各ハンドラーの関数プロトタイプを作成します。

方法の詳細については`ICommandUI`コマンド ルーティングのインターフェイスを使用してを参照してください[方法。コマンドの追加フォーム コントロールを Windows へのルーティング](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)します。

Windows フォームの使用に関する詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。

MFC でのユーザー インターフェイスのコマンドを管理する方法の詳細については、次を参照してください。 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)します。

## <a name="check"></a> ICommandUI::Check

このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。
```
property UICheckState Check;
```

## <a name="remarks"></a>Remarks

このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。 チェックは、次の値に設定します。
- 0 をオフにします
- 1 つのチェック
- 不確定な設定 2

## <a name="continuerouting"></a> ICommandUI::ContinueRouting

ハンドラーのチェーンに現在のメッセージのルーティングを続行するコマンドのルーティング メカニズムに指示します。
```
void ContinueRouting();
```

## <a name="remarks"></a>Remarks

これは、高度なメンバー関数は FALSE を返す ON_COMMAND_EX ハンドラーと組み合わせて使用する必要があります。 詳細については、テクニカル ノート TN006 を参照してください。メッセージ マップです。

## <a name="enabled"></a> ICommandUI::Enabled

有効またはこのコマンドのユーザー インターフェイス項目を無効にします。
```
property bool Enabled;
```

## <a name="remarks"></a>Remarks

このプロパティは、有効または、このコマンドのユーザー インターフェイス項目を無効にします。 有効には、有効にする項目を無効にする場合は FALSE true に設定されます。

## <a name="id"></a> ICommandUI::ID

ICommandUI オブジェクトによって表されるユーザー インターフェイス オブジェクトの ID を取得します。
```
property unsigned int ID;
```

## <a name="remarks"></a>Remarks

このプロパティは、メニュー項目、ツール バー ボタン、または ICommandUI オブジェクトによって表されるその他のユーザー インターフェイス オブジェクトの ID (ハンドル) を取得します。

## <a name="index"></a> ICommandUI::Index

ICommandUI オブジェクトによって表されるユーザー インターフェイス オブジェクトのインデックスを取得します。
```
property unsigned int Index;
```

## <a name="remarks"></a>Remarks

このプロパティは、メニュー項目、ツール バー ボタン、または ICommandUI オブジェクトによって表されるその他のユーザー インターフェイス オブジェクトのインデックス (ハンドル) を取得します。

## <a name="radio"></a> ICommandUI::Radio

このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。
```
property bool Radio;
```

## <a name="remarks"></a>Remarks

このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。 アイテムを有効にする場合は true にセット オプションそれ以外の場合は FALSE です。

## <a name="text"></a> ICommandUI::Text

このコマンドのユーザー インターフェイスの項目のテキストを設定します。
```
property String^ Text;
```

## <a name="remarks"></a>Remarks

このプロパティは、このコマンドのユーザー インターフェイスの項目のテキストを設定します。 テキストをテキスト文字列のハンドルに設定します。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

## <a name="see-also"></a>関連項目

[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)
