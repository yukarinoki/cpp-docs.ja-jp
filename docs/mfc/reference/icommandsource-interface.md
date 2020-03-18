---
title: ICommandSource インターフェイス
ms.date: 03/27/2019
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
ms.openlocfilehash: a57ca6f36546a17b9a35ebea875ff01b43de1332
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445713"
---
# <a name="icommandsource-interface"></a>ICommandSource インターフェイス

コマンドソースオブジェクトからユーザーコントロールに送信されたコマンドを管理します。

## <a name="syntax"></a>構文

```
interface class ICommandSource
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[ICommandSource:: AddCommandHandler](#addcommandhandler)|コマンドソースオブジェクトにコマンドハンドラーを追加します。|
|[ICommandSource:: AddCommandRangeHandler](#addcommandrangehandler)|コマンドソースオブジェクトにコマンドハンドラーのグループを追加します。|
|[ICommandSource:: AddCommandRangeUIHandler](#addcommandrangeuihandler)|コマンドソースオブジェクトに、ユーザーインターフェイスのコマンドメッセージハンドラーのグループを追加します。|
|[ICommandSource:: Add Duihandler](#addcommandrangeuihandler)|コマンドソースオブジェクトにユーザーインターフェイスのコマンドメッセージハンドラーを追加します。|
|[ICommandSource::P ostCommand](#postcommand)|処理されるのを待たずにメッセージをポストします。|
|[ICommandSource:: RemoveCommandHandler](#removecommandhandler)|コマンドソースオブジェクトからコマンドハンドラーを削除します。|
|[ICommandSource:: RemoveCommandRangeHandler](#removecommandrangehandler)|コマンドソースオブジェクトからコマンドハンドラーのグループを削除します。|
|[ICommandSource:: RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|コマンドソースオブジェクトからユーザーインターフェイスのコマンドメッセージハンドラーのグループを削除します。|
|[ICommandSource:: RemoveCommandUIHandler](#removecommandrangeuihandler)|コマンドソースオブジェクトからユーザーインターフェイスのコマンドメッセージハンドラーを削除します。|
|[ICommandSource:: SendCommand](#sendcommand)|メッセージを送信し、が返される前に処理されるのを待機します。|

### <a name="remarks"></a>コメント

MFC ビューでユーザーコントロールをホストする場合、 [CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)は、コマンドをルーティングし、コマンド UI メッセージをユーザーコントロールに更新して、mfc コマンドを処理できるようにします (たとえば、フレームメニュー項目やツールバーボタンなど)。 [ICommandTarget インターフェイス](../../mfc/reference/icommandtarget-interface.md)を実装することにより、ユーザーコントロールに `ICommandSource` オブジェクトへの参照を与えることができます。

`ICommandTarget`の使用方法の例については[、「方法: Windows フォームコントロールにコマンドルーティングを追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)する」を参照してください。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

### <a name="requirements"></a>要件

**ヘッダー:** afxwinforms (アセンブリに定義されています) (アセンブリに定義されています。

## <a name="addcommandhandler"></a>ICommandSource:: AddCommandHandler

コマンドソースオブジェクトにコマンドハンドラーを追加します。

```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID。
*cmdHandler*<br/>
コマンドハンドラーメソッドへのハンドル。

### <a name="remarks"></a>コメント

このメソッドは、コマンドハンドラーの cmdHandler をコマンドソースオブジェクトに追加し、ハンドラーを cmdID にマップします。
AddCommandHandler の使用方法の例については[、「方法: Windows フォームコントロールにコマンドルーティングを追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)する」を参照してください。

## <a name="addcommandrangehandler"></a>ICommandSource:: AddCommandRangeHandler

コマンドソースオブジェクトにコマンドハンドラーのグループを追加します。

```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>パラメーター

*cmdIDMin*<br/>
コマンド ID 範囲の開始インデックス。
*cmdIDMax*<br/>
コマンド ID 範囲の終了インデックス。
*cmdHandler*<br/>
コマンドのマップ先となるメッセージハンドラーメソッドへのハンドル。
### <a name="remarks"></a>コメント

このメソッドは、連続した一連のコマンド Id を1つのメッセージハンドラーにマップして、コマンドソースオブジェクトに追加します。 これは、関連するボタンのグループを1つの方法で処理するために使用されます。

## <a name="addcommandrangeuihandler"></a>ICommandSource:: AddCommandRangeUIHandler

コマンドソースオブジェクトに、ユーザーインターフェイスのコマンドメッセージハンドラーのグループを追加します。

```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>パラメーター

*cmdIDMin*<br/>
コマンド ID 範囲の開始インデックス。
*cmdIDMax*<br/>
コマンド ID 範囲の終了インデックス。
*cmdHandler*<br/>
コマンドのマップ先となるメッセージハンドラーメソッドへのハンドル。

### <a name="remarks"></a>コメント

このメソッドは、コマンド Id の連続した範囲を1つのユーザーインターフェイスのコマンドメッセージハンドラーにマップして、コマンドソースオブジェクトに追加します。 これは、関連するボタンのグループを1つの方法で処理するために使用されます。

## <a name="addcommanduihandler"></a>ICommandSource:: Add Duihandler

コマンドソースオブジェクトにユーザーインターフェイスのコマンドメッセージハンドラーを追加します。

```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID。
*cmdUIHandler*<br/>
ユーザーインターフェイスコマンドメッセージハンドラーメソッドへのハンドル。

### <a name="remarks"></a>コメント

このメソッドは、コマンドソースオブジェクトにユーザーインターフェイスのコマンドメッセージハンドラー cmdHandler を追加し、そのハンドラーを cmdID にマップします。

## <a name="postcommand"></a>ICommandSource::P ostCommand

処理されるのを待たずにメッセージをポストします。

```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>パラメーター

*command*<br/>
ポストされるメッセージのコマンド ID。
### <a name="remarks"></a>コメント

このメソッドは、コマンドで指定された ID にマップされたメッセージを非同期にポストします。 CWnd::P ostMessage を呼び出して、ウィンドウのメッセージキューにメッセージを配置し、対応するウィンドウがメッセージを処理するのを待たずに制御を戻します。

## <a name="removecommandhandler"></a>ICommandSource:: RemoveCommandHandler

コマンドソースオブジェクトからコマンドハンドラーを削除します。

```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID。
### <a name="remarks"></a>コメント

このメソッドは、コマンドソースオブジェクトから、cmdID にマップされたコマンドハンドラーを削除します。

## <a name="removecommandrangehandler"></a>ICommandSource:: RemoveCommandRangeHandler

コマンドソースオブジェクトからコマンドハンドラーのグループを削除します。

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>パラメーター

*cmdIDMin*<br/>
コマンド ID 範囲の開始インデックス。
*cmdIDMax*<br/>
コマンド ID 範囲の終了インデックス。
### <a name="remarks"></a>コメント

このメソッドは、cmdIDMin および cmdIDMax によって指定されたコマンド Id にマップされたメッセージハンドラーのグループを、コマンドソースオブジェクトから削除します。

## <a name="removecommandrangeuihandler"></a>ICommandSource:: RemoveCommandRangeUIHandler

コマンドソースオブジェクトからユーザーインターフェイスのコマンドメッセージハンドラーのグループを削除します。

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>パラメーター

*cmdIDMin*<br/>
コマンド ID 範囲の開始インデックス。
*cmdIDMax*<br/>
コマンド ID 範囲の終了インデックス。
### <a name="remarks"></a>コメント

このメソッドは、コマンドソースオブジェクトから、cmdIDMin および cmdIDMax によって指定されたコマンド Id にマップされた、ユーザーインターフェイスのコマンドメッセージハンドラーのグループを削除します。

## <a name="removecommanduihandler"></a>ICommandSource:: RemoveCommandUIHandler

コマンドソースオブジェクトからユーザーインターフェイスのコマンドメッセージハンドラーを削除します。

```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID。
### <a name="remarks"></a>コメント

このメソッドは、コマンドソースオブジェクトから、cmdID にマップされたユーザーインターフェイスのコマンドメッセージハンドラーを削除します。

## <a name="sendcommand"></a>ICommandSource:: SendCommand

メッセージを送信し、が返される前に処理されるのを待機します。

```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>パラメーター

*command*<br/>
送信されるメッセージのコマンド ID。
### <a name="remarks"></a>コメント

このメソッドは、コマンドで指定された ID にマップされたメッセージを同期的に送信します。 CWnd:: SendMessage を呼び出して、メッセージをウィンドウのメッセージキューに配置し、ウィンドウプロシージャがメッセージを処理してから制御が戻るまで待機します。
## <a name="see-also"></a>参照

[方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandTarget インターフェイス](../../mfc/reference/icommandtarget-interface.md)
