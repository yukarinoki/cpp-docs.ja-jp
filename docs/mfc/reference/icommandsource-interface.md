---
title: 関数のインターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ff57ec9deea4ff8b39e572d720ad7e0fdaa15dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="icommandsource-interface"></a>関数のインターフェイス
ユーザー コントロールにコマンド ソース オブジェクトから送信されたコマンドを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
interface class ICommandSource  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ICommandSource::AddCommandHandler](#addcommandhandler)|コマンド ソース オブジェクトに、コマンド ハンドラーを追加します。|  
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|コマンド ソース オブジェクトを一連のコマンド ハンドラーを追加します。|  
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|コマンド ソース オブジェクトを一連のユーザー インターフェイスのコマンドのメッセージ ハンドラーを追加します。|  
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|コマンド ソース オブジェクトには、ユーザー インターフェイスのコマンドのメッセージ ハンドラーを追加します。|  
|[ICommandSource::PostCommand](#postcommand)|処理されるまで待つことがなく、メッセージをポストします。|  
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|コマンド ソース オブジェクトから、コマンド ハンドラーを削除します。|  
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|コマンド ソース オブジェクトから一連のコマンド ハンドラーを削除します。|  
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|コマンド ソース オブジェクトからのユーザー インターフェイスのコマンドのメッセージ ハンドラーのグループを削除します。|  
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|コマンド ソース オブジェクトからのユーザー インターフェイスのコマンドのメッセージ ハンドラーを削除します。|  
|[ICommandSource::SendCommand](#sendcommand)|メッセージを送信し、返す前に処理されるまで待機します。|  
  
### <a name="remarks"></a>コメント  
 MFC ビュー内のユーザー コントロールをホストしている場合[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンド (たとえば、フレームのメニュー項目やツールバーのボタン) を処理できるようにします。 実装することによって[し、ICommandTarget インターフェイス](../../mfc/reference/icommandtarget-interface.md)、ユーザー コントロールへの参照を提供する、`ICommandSource`オブジェクト。  
  
 参照してください[する方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)の使用方法の例については`ICommandTarget`します。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  
  
## <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler
コマンド ソース オブジェクトに、コマンド ハンドラーを追加します。
```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>パラメーター  
`cmdID`  
コマンド ID。  
`cmdHandler`  
コマンド ハンドラー メソッドへのハンドル。

### <a name="remarks"></a>コメント
このメソッドは、コマンド ソース オブジェクトにコマンド ハンドラー cmdHandler を追加し、cmdID ハンドラーにマップします。
参照してください[する方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)AddCommandHandler を使用する方法の例についてはします。

## <a name="addcommandrangehandler"></a> ICommandSource::AddCommandRangeHandler

コマンド ソース オブジェクトを一連のコマンド ハンドラーを追加します。
```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```
### <a name="parameters"></a>パラメーター  
`cmdIDMin`  
コマンド ID 範囲の開始インデックス。
`cmdIDMax`  
コマンド ID 範囲の終了インデックスです。
`cmdHandler`  
コマンドがマップされているメッセージ ハンドラー メソッドへのハンドル。
### <a name="remarks"></a>コメント
このメソッドは、1 つのメッセージ ハンドラーに連続した範囲のコマンド Id をマップし、コマンド ソース オブジェクトに追加します。 これは、は、1 つのメソッドを使用して関連するボタンのグループを処理するために使用されます。

## <a name="addcommandrangeuihandler"></a> ICommandSource::AddCommandRangeUIHandler
コマンド ソース オブジェクトを一連のユーザー インターフェイスのコマンドのメッセージ ハンドラーを追加します。
```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin, 
    unsigned int cmdIDMax, 
    CommandUIHandler^ cmdUIHandler);
```
### <a name="parameters"></a>パラメーター  
`cmdIDMin`  
コマンド ID 範囲の開始インデックス。
`cmdIDMax`  
コマンド ID 範囲の終了インデックスです。
`cmdHandler`  
コマンドがマップされているメッセージ ハンドラー メソッドへのハンドル。

### <a name="remarks"></a>コメント
このメソッドは、1 人のユーザー インターフェイスのコマンドのメッセージ ハンドラーに連続した範囲のコマンド Id をマップし、コマンド ソース オブジェクトに追加します。 これは、は、1 つのメソッドを使用して関連するボタンのグループを処理するために使用されます。

## <a name="addcommanduihandler"></a> ICommandSource::AddCommandUIHandler
コマンド ソース オブジェクトには、ユーザー インターフェイスのコマンドのメッセージ ハンドラーを追加します。
```
void AddCommandUIHandler(
    unsigned int cmdID, 
    CommandUIHandler^ cmdUIHandler);
```
### <a name="parameters"></a>パラメーター
`cmdID`  
コマンド ID。  
`cmdUIHandler`  
ユーザー インターフェイスのコマンドのメッセージ ハンドラー メソッドへのハンドル。

### <a name="remarks"></a>コメント
このメソッドは、コマンド ソース オブジェクトにユーザー インターフェイスのコマンドのメッセージ ハンドラー cmdHandler を追加し、cmdID ハンドラーにマップします。

## <a name="postcommand"></a> ICommandSource::PostCommand
処理されるまで待つことがなく、メッセージをポストします。
```
void PostCommand(unsigned int command);
```
### <a name="parameters"></a>パラメーター
`command`  
メッセージをポストのコマンド ID。
### <a name="remarks"></a>コメント
このメソッドは、コマンドで指定した ID に割り当てられたメッセージを非同期的にポストします。 ウィンドウのメッセージ キューにメッセージを配置する CWnd::PostMessage を呼び出すし、対応するウィンドウ メッセージを処理するを待たずに戻ります。


## <a name="removecommandhandler"></a> ICommandSource::RemoveCommandHandler
コマンド ソース オブジェクトから、コマンド ハンドラーを削除します。
```
void RemoveCommandHandler(unsigned int cmdID);
```
### <a name="parameters"></a>パラメーター
`cmdID`  
コマンド ID。
### <a name="remarks"></a>コメント
このメソッドは、コマンド ソース オブジェクトから cmdID に割り当てられたコマンド ハンドラーを削除します。


## <a name="removecommandrangecommandhandler"></a> ICommandSource::RemoveCommandRangeHandler 
コマンド ソース オブジェクトから一連のコマンド ハンドラーを削除します。
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```
### <a name="parameters"></a>パラメーター
`cmdIDMin`  
コマンド ID 範囲の開始インデックス。
`cmdIDMax`  
コマンド ID 範囲の終了インデックスです。
### <a name="remarks"></a>コメント
このメソッドは、一連のコマンド ソース オブジェクトから cmdIDMin および cmdIDMax で指定されたコマンド Id を割り当て、メッセージのハンドラーを削除します。

## <a name="removecommandrangeuihandler"></a> ICommandSource::RemoveCommandRangeUIHandler 
コマンド ソース オブジェクトからのユーザー インターフェイスのコマンドのメッセージ ハンドラーのグループを削除します。
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```
### <a name="parameters"></a>パラメーター
`cmdIDMin`  
コマンド ID 範囲の開始インデックス。
`cmdIDMax`  
コマンド ID 範囲の終了インデックスです。
### <a name="remarks"></a>コメント
このメソッドは、一連のコマンド ソース オブジェクトから cmdIDMin および cmdIDMax で指定されたコマンド Id を割り当て、ユーザー インターフェイス コマンド メッセージ ハンドラーを削除します。

## <a name="removecommanduihandler"></a> ICommandSource::RemoveCommandUIHandler 
コマンド ソース オブジェクトからのユーザー インターフェイスのコマンドのメッセージ ハンドラーを削除します。
```
void RemoveCommandUIHandler(unsigned int cmdID);
```
### <a name="parameters"></a>パラメーター
`cmdID`  
コマンド ID。
### <a name="remarks"></a>コメント
このメソッドは、コマンド ソース オブジェクトから cmdID に割り当てられたユーザー インターフェイスのコマンドのメッセージ ハンドラーを削除します。

## <a name="sendcommand"></a> ICommandSource::SendCommand 
メッセージを送信し、返す前に処理されるまで待機します。
```
void SendCommand(unsigned int command);
```
### <a name="parameters"></a>パラメーター
`command`  
送信されるメッセージのコマンド ID。
### <a name="remarks"></a>コメント
このメソッドは、コマンドで指定した ID に割り当てられたメッセージを同期的に送信します。 ウィンドウのメッセージ キューにメッセージを配置する CWnd::SendMessage を呼び出すし、そのウィンドウ プロシージャが返す前にメッセージを処理するまで待機します。
## <a name="see-also"></a>関連項目  
 [方法: コマンドの追加にルーティングする Windows フォーム コントロール](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget インターフェイス](../../mfc/reference/icommandtarget-interface.md)
