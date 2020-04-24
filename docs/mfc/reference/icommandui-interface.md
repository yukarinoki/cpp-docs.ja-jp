---
title: IコマンドUIインターフェイス
ms.date: 09/07/2019
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
ms.openlocfilehash: b75509beb7287fad5e51dc9d15fc3e47cacf6854
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751309"
---
# <a name="icommandui-interface"></a>IコマンドUIインターフェイス

ユーザー インターフェイス コマンドを管理します。

## <a name="syntax"></a>構文

```
interface class ICommandUI
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[icommandui__Check](#check)|このコマンドのユーザー インターフェイス項目を適切なチェック状態に設定します。|
|[IコマンドUI::ルーティングを続行](#continuerouting)|現在のメッセージをハンドラーのチェーンにルーティングし続けるコマンド ルーティング メカニズムを指示します。|
|[IコマンドUI::有効](#enabled)|このコマンドのユーザー インターフェイス項目を有効または無効にします。|
|[Iコマンドイイ::ID](#id)|オブジェクトによって表されるユーザー インターフェイス オブジェクトの`ICommandUI`ID を取得します。|
|[IコマンドUI::インデックス](#index)|オブジェクトによって表されるユーザー インターフェイス オブジェクトのインデックス`ICommandUI`を取得します。|
|[Iコマンドイ::ラジオ](#radio)|このコマンドのユーザー インターフェイス項目を適切なチェック状態に設定します。|
|[IコマンドUI::テキスト](#text)|このコマンドのユーザー インターフェイスアイテムのテキストを設定します。|

## <a name="remarks"></a>解説

このインターフェイスには、ユーザー インターフェイス コマンドを管理するメソッドとプロパティが用意されています。 `ICommandUI`は、.NET コンポーネントと相互運用する`ICommandUI`MFC アプリケーションで使用される点を除き[、CCmdUI クラス](../../mfc/reference/ccmdui-class.md)に似ています。

`ICommandUI`は[、ICommandTarget](../../mfc/reference/icommandtarget-interface.md)派生クラスのON_UPDATE_COMMAND_UI ハンドラー内で使用されます。 アプリケーションのユーザーがメニューをアクティブ (選択またはクリック) すると、各メニュー項目は有効または無効として表示されます。 各メニュー コマンドのターゲットは、ON_UPDATE_COMMAND_UI ハンドラーを実装することによって、この情報を提供します。 アプリケーション内のコマンド ユーザー インターフェイス オブジェクトごとに、クラス[ウィザード](mfc-class-wizard.md)を使用して、各ハンドラーのメッセージ マップ エントリと関数プロトタイプを作成します。

コマンド ルーティングでのインターフェイス`ICommandUI`の使用方法の詳細については、「方法[: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)」を参照してください。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

MFC でユーザー インターフェイス コマンドを管理する方法の詳細については、「 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)」を参照してください。

## <a name="icommanduicheck"></a><a name="check"></a>IコマンドUI::チェック

このコマンドのユーザー インターフェイス項目を適切なチェック状態に設定します。

```
property UICheckState Check;
```

## <a name="remarks"></a>解説

このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェック状態に設定します。 [チェック] を次の値に設定します。

- 0 チェックを外す
- 1 チェック
- 2 不確定の設定

## <a name="icommanduicontinuerouting"></a><a name="continuerouting"></a>IコマンドUI::ルーティングを続行

現在のメッセージをハンドラーのチェーンにルーティングし続けるコマンド ルーティング メカニズムを指示します。

```cpp
void ContinueRouting();
```

## <a name="remarks"></a>解説

これは、FALSE を返すON_COMMAND_EX ハンドラーと共に使用する高度なメンバー関数です。 詳細については、テクニカル ノート TN006: メッセージ マップを参照してください。

## <a name="icommanduienabled"></a><a name="enabled"></a>IコマンドUI::有効

このコマンドのユーザー インターフェイス項目を有効または無効にします。

```
property bool Enabled;
```

## <a name="remarks"></a>解説

このプロパティは、このコマンドのユーザー インターフェイス項目を有効または無効にします。 項目を無効にするには、有効に設定して TRUE を、FALSE に設定します。

## <a name="icommanduiid"></a><a name="id"></a>Iコマンドイイ::ID

ICommandUI オブジェクトによって表されるユーザー インターフェイス オブジェクトの ID を取得します。

```
property unsigned int ID;
```

## <a name="remarks"></a>解説

このプロパティは、メニュー項目、ツール バー ボタン、または ICommandUI オブジェクトによって表されるその他のユーザー インターフェイス オブジェクトの ID (ハンドル) を取得します。

## <a name="icommanduiindex"></a><a name="index"></a>IコマンドUI::インデックス

ICommandUI オブジェクトによって表されるユーザー インターフェイス オブジェクトのインデックスを取得します。

```
property unsigned int Index;
```

## <a name="remarks"></a>解説

このプロパティは、メニュー項目、ツール バー ボタン、または ICommandUI オブジェクトによって表される他のユーザー インターフェイス オブジェクトのインデックス (ハンドル) を取得します。

## <a name="icommanduiradio"></a><a name="radio"></a>Iコマンドイ::ラジオ

このコマンドのユーザー インターフェイス項目を適切なチェック状態に設定します。

```
property bool Radio;
```

## <a name="remarks"></a>解説

このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェック状態に設定します。 ラジオを TRUE に設定すると、アイテムが有効になります。それ以外の場合は FALSE。

## <a name="icommanduitext"></a><a name="text"></a>IコマンドUI::テキスト

このコマンドのユーザー インターフェイスアイテムのテキストを設定します。

```
property String^ Text;
```

## <a name="remarks"></a>解説

このプロパティは、このコマンドのユーザー インターフェイスアイテムのテキストを設定します。 テキストをテキスト文字列ハンドルに設定します。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

## <a name="see-also"></a>関連項目

[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)
