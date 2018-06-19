---
title: CWordArray クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf19865b4c11bb8305bea62b3682faebe39bef74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376686"
---
# <a name="cwordarray-class"></a>CWordArray クラス
16 ビットのワードの配列をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CWordArray : public CObject  
```  
  
## <a name="members"></a>メンバー  
 メンバー関数は、`CWordArray`クラスのメンバー関数に似ています[CObArray](../../mfc/reference/cobarray-class.md)です。 メンバー関数については `CObArray` クラスの説明を参照してください。 任意の場所が表示、 [CObject](../../mfc/reference/cobject-class.md)ポインター関数パラメーターまたは戻り値は、置換、 **WORD**です。  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 たとえば、次のように変換します。  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|空の配列を生成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|配列内の要素ポインターへの一時的な参照を返します。|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|指定されたインデックス位置にある値を返します。|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|この配列内の要素の数を取得します。|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|配列内の要素へのアクセスを許可します。 指定できます**NULL**です。|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|この配列内の要素の数を取得します。|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|有効な最大のインデックスを返します。|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|配列が空かどうかを判別します。|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|この配列からすべての要素を削除します。|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|特定のインデックス位置にある要素を削除します。|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|この配列に含まれる要素の数を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::operator&#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|  
  
## <a name="remarks"></a>コメント  
 `CWordArray` 組み込まれており、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロをシリアル化とその要素のダンプをサポートします。 単語の配列がアーカイブか、オーバー ロードされた挿入演算子のいずれかに格納されている場合、 [cobject::serialize](../../mfc/reference/cobject-class.md#serialize)メンバー関数は、各要素は、逆に、シリアル化します。  
  
> [!NOTE]
>  配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。  
  
 配列内の個々 の要素のダンプを必要がある場合は、1 以上ダンプ コンテキストの深さを設定する必要があります。  
  
 使用する方法についての`CWordArray`、記事を参照して[コレクション](../../mfc/collections.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CWordArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
##  <a name="icommandsource_interface"></a>  関数のインターフェイス  
 ユーザー コントロールにコマンド ソース オブジェクトから送信されたコマンドを管理します。  
  
```  
interface class ICommandSource  
```  
  
### <a name="remarks"></a>コメント  
 MFC ビュー内のユーザー コントロールをホストしている場合[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンド (たとえば、フレームのメニュー項目やツールバーのボタン) を処理できるようにします。 実装すると、割り当てるユーザー コントロールへの参照、`ICommandSource`オブジェクト。  
  
 参照してください[する方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)の使用方法の例については`ICommandTarget`します。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
##  <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler  
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
 このメソッドは、コマンド ハンドラーを追加`cmdHandler`コマンド ソース オブジェクトにし、そのハンドラーに`cmdID`です。  
  
 参照してください[する方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)の使用方法の例については`AddCommandHandler`します。  
  
##  <a name="addcommandrangehandler"></a>  ICommandSource::AddCommandRangeHandler  
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
  
##  <a name="addcommandrangeuihandler"></a>  ICommandSource::AddCommandRangeUIHandler  
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
  
##  <a name="addcommanduihandler"></a>  ICommandSource::AddCommandUIHandler  
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
 このメソッドは、ユーザー インターフェイスのコマンドのメッセージ ハンドラーを追加`cmdHandler`コマンド ソース オブジェクトにし、そのハンドラーに`cmdID`です。  
  
##  <a name="postcommand"></a>  ICommandSource::PostCommand  
 処理されるまで待つことがなく、メッセージをポストします。  
  
```  
void PostCommand(unsigned int command);
```  
  
### <a name="parameters"></a>パラメーター  
 `command`  
 メッセージをポストのコマンド ID。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定した ID にマップされているメッセージを非同期的にポスト`command`です。 呼び出す[CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage)ウィンドウのメッセージ キューと返しますに対応するウィンドウ メッセージを処理するを待たず、メッセージを配置します。  
  
##  <a name="removecommandhandler"></a>  ICommandSource::RemoveCommandHandler  
 コマンド ソース オブジェクトから、コマンド ハンドラーを削除します。  
  
```  
void RemoveCommandHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID。  
  
### <a name="remarks"></a>コメント  
 このメソッドにマップされているコマンド ハンドラーを削除する`cmdID`コマンド ソース オブジェクトからです。  
  
##  <a name="removecommandrangehandler"></a>  ICommandSource::RemoveCommandRangeHandler  
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
 このメソッドによって指定されたコマンド Id にマップされているメッセージ ハンドラーのグループを削除して`cmdIDMin`と`cmdIDMax`、コマンド ソース オブジェクトからです。  
  
##  <a name="removecommandrangeuihandler"></a>  ICommandSource::RemoveCommandRangeUIHandler  
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
 このメソッドによって指定されたコマンド Id にマップされている、ユーザー インターフェイス コマンド メッセージ ハンドラーのグループを削除して`cmdIDMin`と`cmdIDMax`、コマンド ソース オブジェクトからです。  
  
##  <a name="removecommanduihandler"></a>  ICommandSource::RemoveCommandUIHandler  
 コマンド ソース オブジェクトからのユーザー インターフェイスのコマンドのメッセージ ハンドラーを削除します。  
  
```  
void RemoveCommandUIHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ユーザー インターフェイス コマンド メッセージ ハンドラーにマップを削除`cmdID`コマンド ソース オブジェクトからです。  
  
##  <a name="sendcommand"></a>  ICommandSource::SendCommand  
 メッセージを送信し、返す前に処理されるまで待機します。  
  
```  
void SendCommand(unsigned int command);
```  
  
### <a name="parameters"></a>パラメーター  
 `command`  
 送信されるメッセージのコマンド ID。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定した ID に割り当てられたメッセージを同期的に送信する`command`です。 呼び出す[CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage)ウィンドウ プロシージャが返す前に、メッセージが処理されるまでに、ウィンドウのメッセージ キューと待機にメッセージを配置します。  
  
##  <a name="icommandtarget_interface"></a>  ICommandTarget インターフェイス  
 コマンド ソース オブジェクトからのコマンドを受信するインターフェイスを使用するユーザー コントロールを提供します。  
  
```  
interface class ICommandTarget  
```  
  
### <a name="remarks"></a>コメント  
 MFC ビュー内のユーザー コントロールをホストしている場合[CWinFormsView](../../mfc/reference/cwinformsview-class.md)ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンド (たとえば、フレームのメニュー項目やツールバーのボタン) を処理できるようにします。 実装することによって`ICommandTarget`、ユーザー コントロールに、オブジェクトへの参照を提供します。  
  
 参照してください[する方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)の使用方法の例については`ICommandTarget`します。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
##  <a name="initialize"></a>  ICommandTarget::Initialize  
 コマンド ターゲット オブジェクトを初期化します。  
  
```  
void Initialize(ICommandSource^ cmdSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdSource`  
 コマンド ソース オブジェクトへのハンドル。  
  
### <a name="remarks"></a>コメント  
 MFC ビュー内のユーザー コントロールをホストしている場合[CWinFormsView](../../mfc/reference/cwinformsview-class.md)ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンドを処理できるようにします。  
  
 このメソッドは、コマンド ターゲット オブジェクトを初期化し、指定したコマンドのソース オブジェクトに関連付けます`cmdSource`です。 ユーザー コントロール クラスの実装で呼び出す必要があります。 初期化でする必要がありますに登録するコマンド ハンドラー コマンド ソース オブジェクトを呼び出して[ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md)で、`Initialize`実装します。 参照してください[する方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)の使用方法の例については`Initialize`これを行う。  
  
##  <a name="icommandui_interface"></a>  ICommandUI インターフェイス  
 ユーザー インターフェイスのコマンドを管理します。  
  
```  
interface class ICommandUI  
```  
  
### <a name="remarks"></a>コメント  
 このインターフェイスは、ユーザー インターフェイスのコマンドを管理するメソッドとプロパティを提供します。 `ICommandUI` ような[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)する点を除いて、 `ICommandUI` .NET コンポーネントと相互運用可能な MFC アプリケーションのために使用します。  
  
 `ICommandUI` 内で使用される、`ON_UPDATE_COMMAND_UI`ハンドラーの派生クラスでします。 有効になっていると、各メニュー項目、メニューが表示されます (選択またはクリックする) アプリケーションのユーザーがアクティブにしたときまたは無効にします。 各メニュー コマンドのターゲットが実装することでこの情報を提供する`ON_UPDATE_COMMAND_UI`ハンドラー。 アプリケーション内のコマンドのユーザー インターフェイス オブジェクトごとに、[プロパティ] ウィンドウを使用して、メッセージ マップ エントリと各ハンドラーの関数プロトタイプを作成します。  
  
 方法の詳細については`ICommandUI`コマンド ルーティングのインターフェイスを使用してを参照してください[する方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)です。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
 MFC でのユーザー インターフェイスのコマンドを管理する方法の詳細については、次を参照してください。 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)です。  
  
##  <a name="check"></a>  ICommandUI::Check  
 このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。  
  
```  
property UICheckState Check;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態を設定します。 設定`Check`次の値にします。  
  
|用語|定義|  
|----------|----------------|  
|0|オフに|  
|1|チェック|  
|2|不確定な設定します。|  
  
##  <a name="continuerouting"></a>  ICommandUI::ContinueRouting  
 コマンド ルーティング機構、一連のハンドラーを現在のメッセージのルーティングを続行するように指示します。  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>コメント  
 これは、高度なメンバー関数と組み合わせて使用する、 [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex)返すハンドラー`FALSE`です。 詳細については、テクニカル ノートを参照してください。 [TN006: メッセージ マップ](../../mfc/tn006-message-maps.md)です。  
  
##  <a name="enabled"></a>  ICommandUI::Enabled  
 有効またはこのコマンドのユーザー インターフェイス項目を無効にします。  
  
```  
property bool Enabled;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、有効またはこのコマンドのユーザー インターフェイス項目を無効にします。 設定`Enabled`に`TRUE`、項目を有効にする`FALSE`を無効にします。  
  
##  <a name="id"></a>  ICommandUI::ID  
 によって表されるユーザー インターフェイス オブジェクトの ID を取得、`ICommandUI`オブジェクト。  
  
```  
property unsigned int ID;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、ツール バー ボタン、メニュー項目の ID (ハンドル) を取得またはその他のユーザー インターフェイス オブジェクトで表されます、`ICommandUI`オブジェクト。  
  
##  <a name="index"></a>  ICommandUI::Index  
 によって表されるユーザー インターフェイス オブジェクトのインデックスを取得、`ICommandUI`オブジェクト。  
  
```  
property unsigned int Index;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、ツール バー ボタン、メニュー項目のインデックス (ハンドル) を取得またはその他のユーザー インターフェイス オブジェクトで表されます、`ICommandUI`オブジェクト。  
  
##  <a name="radio"></a>  ICommandUI::Radio  
 このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。  
  
```  
property bool Radio;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態を設定します。 設定`Radio`に`TRUE`; 項目を有効にするそれ以外の場合`FALSE`です。  
  
##  <a name="text"></a>  ICommandUI::Text  
 このコマンドのユーザー インターフェイスの項目のテキストを設定します。  
  
```  
property String^ Text;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、このコマンドのユーザー インターフェイスのアイテムのテキストを設定します。 設定`Text`をテキスト文字列のハンドル。  
  
##  <a name="iview_interface"></a>  IView インターフェイス  
 いくつかのメソッドを実装する[CWinFormsView](../../mfc/reference/cwinformsview-class.md)を使用してマネージ コントロールを表示通知を送信します。  
  
```  
interface class IView  
```  
  
### <a name="remarks"></a>コメント  
 `IView` いくつかのメソッドを実装する`CWinFormsView`を使用してホストされるマネージ コントロールに共通の通知の表示を転送します。 これらは[フィルターと並べ替え順序](../../mfc/reference/iview-interface.md)、 [OnUpdate](../../mfc/reference/iview-interface.md)と[OnActivateView](../../mfc/reference/iview-interface.md)です。  
  
 `IView` ような[CView](../../mfc/reference/cview-class.md)が管理対象のビューおよびコントロールでのみ使用されます。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
##  <a name="onactivateview"></a>  IView::OnActivateView  
 ビューがアクティブまたは非アクティブ化されたときに、MFC によって呼び出されます。  
  
```  
void OnActivateView(bool activate);
```  
  
### <a name="parameters"></a>パラメーター  
 `activate`  
 表示されているかどうかを示しますがアクティブまたは非アクティブ化します。  
  
##  <a name="oninitialupdate"></a>  IView::OnInitialUpdate  
 ビューが最初に表示される前に、ビューが最初に、ドキュメントにアタッチされている後に、フレームワークによって呼び出されます。  
  
```  
void OnInitialUpdate();
```  
  
##  <a name="onupdate"></a>  IView::OnUpdate  
 ビューのドキュメントが変更された後に、MFC によって呼び出されます。  
  
```  
void OnUpdate();
```  
  
### <a name="remarks"></a>コメント  
 この機能は、変更を反映するには、その表示を更新するビューを使用します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



