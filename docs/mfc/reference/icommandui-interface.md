---
title: ICommandUI インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70e6f1eb8848c5ee93063877ae036f66584b69c4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[ICommandUI::ContinueRouting](#continuerouting)|コマンド ルーティング メカニズム ハンドラーのチェーンに現在のメッセージのルーティングを続行するように指示します。|  
|[ICommandUI::Enabled](#enabled)|有効またはこのコマンドのユーザー インターフェイス項目を無効にします。|  
|[ICommandUI::ID](#id)|によって表されるユーザー インターフェイス オブジェクトの ID を取得、`ICommandUI`オブジェクト。|  
|[ICommandUI::Index](#index)|によって表されるユーザー インターフェイス オブジェクトのインデックスを取得、`ICommandUI`オブジェクト。|  
|[ICommandUI::Radio](#radio)|このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。|  
|[ICommandUI::Text](#text)|このコマンドのユーザー インターフェイスの項目のテキストを設定します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、ユーザー インターフェイスのコマンドを管理するメソッドとプロパティを提供します。 `ICommandUI` ような[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)する点を除いて、 `ICommandUI` .NET コンポーネントと相互運用可能な MFC アプリケーションのために使用します。  
  
 `ICommandUI` 内で使用される、`ON_UPDATE_COMMAND_UI`ハンドラー、[し、ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-クラスを派生します。 有効になっていると、各メニュー項目、メニューが表示されます (選択またはクリックする) アプリケーションのユーザーがアクティブにしたときまたは無効にします。 各メニュー コマンドのターゲットが実装することでこの情報を提供する`ON_UPDATE_COMMAND_UI`ハンドラー。 アプリケーション内のコマンドのユーザー インターフェイス オブジェクトごとに、[プロパティ] ウィンドウを使用して、メッセージ マップ エントリと各ハンドラーの関数プロトタイプを作成します。  
  
 方法の詳細については`ICommandUI`コマンド ルーティングのインターフェイスを使用してを参照してください[する方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)です。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
 MFC でのユーザー インターフェイスのコマンドを管理する方法の詳細については、次を参照してください。 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)です。  
  
## <a name="check"></a> ICommandUI::Check  
このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。
```
property UICheckState Check;
```
## <a name="remarks"></a>コメント  
このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態を設定します。 チェックを次の値に設定します。  
- 0 をオフにします  
- 1 のチェック  
- 2 が不確定な設定します。  

## <a name="continuerouting"></a> ICommandUI::ContinueRouting   
コマンド ルーティング機構、一連のハンドラーを現在のメッセージのルーティングを続行するように指示します。
```
void ContinueRouting();
```
## <a name="remarks"></a>コメント
これは、FALSE を返す ON_COMMAND_EX ハンドラーと共に使用する高度なメンバー関数です。 詳細については、テクニカル ノート TN006 を参照してください: メッセージ マップです。

## <a name="enabled"></a> ICommandUI::Enabled 
有効またはこのコマンドのユーザー インターフェイス項目を無効にします。
```
property bool Enabled;
```
## <a name="remarks"></a>コメント
このプロパティは、有効またはこのコマンドのユーザー インターフェイス項目を無効にします。 有効を有効にする項目を無効にする場合は FALSE を true に設定します。

## <a name="id"></a> ICommandUI::ID  
ICommandUI オブジェクトによって表されるユーザー インターフェイス オブジェクトの ID を取得します。
```
property unsigned int ID;
```
## <a name="remarks"></a>コメント
このプロパティは、メニュー項目、ツール バー ボタンまたは ICommandUI オブジェクトによって表されるその他のユーザー インターフェイス オブジェクトの ID (ハンドル) を取得します。

## <a name="index"></a> ICommandUI::Index   
ICommandUI オブジェクトによって表されるユーザー インターフェイス オブジェクトのインデックスを取得します。
```
property unsigned int Index;
```
## <a name="remarks"></a>コメント
このプロパティは、メニュー項目、ツール バー ボタンまたは ICommandUI オブジェクトによって表されるその他のユーザー インターフェイス オブジェクトのインデックス (ハンドル) を取得します。

## <a name="radio"></a> ICommandUI::Radio 
このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。
```
property bool Radio;
```
## <a name="remarks"></a>コメント
このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態を設定します。 無線を有効にするアイテムです。 true に設定します。それ以外の場合は FALSE。

## <a name="text"></a> ICommandUI::Text 
このコマンドのユーザー インターフェイスの項目のテキストを設定します。
```
property String^ Text;
```
## <a name="remarks"></a>コメント
このプロパティは、このコマンドのユーザー インターフェイスのアイテムのテキストを設定します。 テキストをテキスト文字列のハンドルに設定します。

## <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  
  
## <a name="see-also"></a>関連項目  
 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)
