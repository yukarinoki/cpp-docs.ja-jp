---
title: インターフェイス
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
ms.openlocfilehash: 6a03c46c972f7746f39a3c5c65ca9b5509983d59
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356989"
---
# <a name="icommandsource-interface"></a>インターフェイス

コマンド ソース オブジェクトからユーザー コントロールに送信されるコマンドを管理します。

## <a name="syntax"></a>構文

```cpp
interface class ICommandSource
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[I コマンドソース::コマンドハンドラーの追加](#addcommandhandler)|コマンド ソース オブジェクトにコマンド ハンドラーを追加します。|
|[次のコマンドソース::コマンドレンジハンドラー](#addcommandrangehandler)|コマンド ソース オブジェクトにコマンド ハンドラーのグループを追加します。|
|[I コマンドソース::コマンドレンジUIハンドラ](#addcommandrangeuihandler)|ユーザー インターフェイス コマンド メッセージ ハンドラーのグループをコマンド ソース オブジェクトに追加します。|
|[I コマンドソース::コマンドUIハンドラ](#addcommandrangeuihandler)|ユーザー インターフェイス コマンド メッセージ ハンドラーをコマンド ソース オブジェクトに追加します。|
|[Iコマンドソース::Postコマンド](#postcommand)|メッセージの処理を待たずにメッセージを投稿します。|
|[コマンドソース::コマンドハンドラーの削除](#removecommandhandler)|コマンド ソース オブジェクトからコマンド ハンドラーを削除します。|
|[次のコマンドソース::コマンド範囲ハンドラーの削除](#removecommandrangehandler)|コマンド ソース オブジェクトからコマンド ハンドラーのグループを削除します。|
|[I コマンドソース::コマンド範囲UIハンドラを削除します。](#removecommandrangeuihandler)|コマンド ソース オブジェクトからユーザー インターフェイス コマンド メッセージ ハンドラーのグループを削除します。|
|[I コマンドソース::コマンドUIハンドラの削除](#removecommandrangeuihandler)|コマンド ソース オブジェクトからユーザー インターフェイス コマンド メッセージ ハンドラーを削除します。|
|[Iコマンドソース::コマンドを送ります](#sendcommand)|メッセージを送信し、メッセージが処理されるのを待ってから、戻ります。|

### <a name="remarks"></a>解説

MFC ビューでユーザー コントロールをホストすると[、CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)はコマンドをルーティングし、コマンド UI メッセージをユーザー コントロールに更新して、MFC コマンド (フレーム メニュー項目やツール バー ボタンなど) を処理できるようにします。 [ICommandTarget インターフェイス](../../mfc/reference/icommandtarget-interface.md)を実装することにより、ユーザー コントロールにオブジェクトへの参照`ICommandSource`を与えます。

の使用方法`ICommandTarget`の例については、「[方法 : Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)」を参照してください。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

## <a name="icommandsourceaddcommandhandler"></a><a name="addcommandhandler"></a>I コマンドソース::コマンドハンドラーの追加

コマンド ソース オブジェクトにコマンド ハンドラーを追加します。

```cpp
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID。
*コマンドハンドラー*<br/>
コマンド ハンドラー メソッドへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、コマンド ハンドラー cmdHandler をコマンド ソース オブジェクトに追加し、ハンドラーを cmdID にマップします。
AddCommandHandler の使用方法の例については、「[方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)」を参照してください。

## <a name="icommandsourceaddcommandrangehandler"></a><a name="addcommandrangehandler"></a>次のコマンドソース::コマンドレンジハンドラー

コマンド ソース オブジェクトにコマンド ハンドラーのグループを追加します。

```cpp
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>パラメーター

*cmdIDMin*<br/>
コマンド ID 範囲の開始インデックス。
*コマンドIDマックス*<br/>
コマンド ID 範囲の終了インデックス。
*コマンドハンドラー*<br/>
コマンドがマップされるメッセージ ハンドラー メソッドへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、連続した範囲のコマンド ID を単一のメッセージ ハンドラーにマップし、コマンド ソース オブジェクトに追加します。 これは、1 つのメソッドで関連するボタンのグループを処理するために使用されます。

## <a name="icommandsourceaddcommandrangeuihandler"></a><a name="addcommandrangeuihandler"></a>I コマンドソース::コマンドレンジUIハンドラ

ユーザー インターフェイス コマンド メッセージ ハンドラーのグループをコマンド ソース オブジェクトに追加します。

```cpp
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>パラメーター

*cmdIDMin*<br/>
コマンド ID 範囲の開始インデックス。
*コマンドIDマックス*<br/>
コマンド ID 範囲の終了インデックス。
*コマンドハンドラー*<br/>
コマンドがマップされるメッセージ ハンドラー メソッドへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、連続した範囲のコマンド ID を単一のユーザー インターフェイス コマンド メッセージ ハンドラーにマップし、コマンド ソース オブジェクトに追加します。 これは、1 つのメソッドで関連するボタンのグループを処理するために使用されます。

## <a name="icommandsourceaddcommanduihandler"></a><a name="addcommanduihandler"></a>I コマンドソース::コマンドUIハンドラ

ユーザー インターフェイス コマンド メッセージ ハンドラーをコマンド ソース オブジェクトに追加します。

```cpp
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID。
*コマンドハンドラー*<br/>
ユーザー インターフェイス コマンド メッセージ ハンドラー メソッドへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、ユーザー インターフェイス コマンド メッセージ ハンドラー cmdHandler をコマンド ソース オブジェクトに追加し、ハンドラーを cmdID にマップします。

## <a name="icommandsourcepostcommand"></a><a name="postcommand"></a>Iコマンドソース::Postコマンド

メッセージの処理を待たずにメッセージを投稿します。

```cpp
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>パラメーター

*コマンド*<br/>
投稿するメッセージのコマンド ID。

### <a name="remarks"></a>解説

このメソッドは、コマンドによって指定された ID にマップされたメッセージを非同期にポストします。 CWnd::PostMessage を呼び出してメッセージをウィンドウのメッセージ キューに配置し、対応するウィンドウがメッセージを処理するのを待たずに戻ります。

## <a name="icommandsourceremovecommandhandler"></a><a name="removecommandhandler"></a>コマンドソース::コマンドハンドラーの削除

コマンド ソース オブジェクトからコマンド ハンドラーを削除します。

```cpp
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID。

### <a name="remarks"></a>解説

このメソッドは、コマンド ソース オブジェクトから cmdID にマップされたコマンド ハンドラーを削除します。

## <a name="icommandsourceremovecommandrangehandler"></a><a name="removecommandrangehandler"></a>次のコマンドソース::コマンド範囲ハンドラーの削除

コマンド ソース オブジェクトからコマンド ハンドラーのグループを削除します。

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>パラメーター

*cmdIDMin*<br/>
コマンド ID 範囲の開始インデックス。
*コマンドIDマックス*<br/>
コマンド ID 範囲の終了インデックス。

### <a name="remarks"></a>解説

このメソッドは、cmdIDMin および cmdIDMax で指定されたコマンド ID にマップされたメッセージ ハンドラーのグループをコマンド ソース オブジェクトから削除します。

## <a name="icommandsourceremovecommandrangeuihandler"></a><a name="removecommandrangeuihandler"></a>I コマンドソース::コマンド範囲UIハンドラを削除します。

コマンド ソース オブジェクトからユーザー インターフェイス コマンド メッセージ ハンドラーのグループを削除します。

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>パラメーター

*cmdIDMin*<br/>
コマンド ID 範囲の開始インデックス。
*コマンドIDマックス*<br/>
コマンド ID 範囲の終了インデックス。

### <a name="remarks"></a>解説

このメソッドは、コマンド ソース オブジェクトから cmdIDMin および cmdIDMax で指定されたコマンド ID にマップされた、ユーザー インターフェイス コマンド メッセージ ハンドラーのグループを削除します。

## <a name="icommandsourceremovecommanduihandler"></a><a name="removecommanduihandler"></a>I コマンドソース::コマンドUIハンドラの削除

コマンド ソース オブジェクトからユーザー インターフェイス コマンド メッセージ ハンドラーを削除します。

```cpp
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID。

### <a name="remarks"></a>解説

このメソッドは、コマンド ソース オブジェクトから cmdID にマップされたユーザー インターフェイス コマンド メッセージ ハンドラーを削除します。

## <a name="icommandsourcesendcommand"></a><a name="sendcommand"></a>Iコマンドソース::コマンドを送ります

メッセージを送信し、メッセージが処理されるのを待ってから、戻ります。

```cpp
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>パラメーター

*コマンド*<br/>
送信されるメッセージのコマンド ID。

### <a name="remarks"></a>解説

このメソッドは、コマンドによって指定された ID にマップされたメッセージを同期的に送信します。 CWnd::SendMessage を呼び出してウィンドウのメッセージ キューにメッセージを配置し、そのウィンドウ プロシージャがメッセージを処理してから戻るまで待機します。

## <a name="see-also"></a>関連項目

[方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[インターフェイス](../../mfc/reference/icommandtarget-interface.md)
