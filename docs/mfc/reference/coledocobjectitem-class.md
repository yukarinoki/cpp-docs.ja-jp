---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
dev_langs:
- C++
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af2b13b8da5f70cf55b47ddf3b7864f9f9151a40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373580"
---
# <a name="coledocobjectitem-class"></a>関数クラス
Active ドキュメント コンテインメントを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|構築、`COleDocObject`項目。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[:Dodefaultprinting](#dodefaultprinting)|既定のプリンター設定を使用して、コンテナー アプリケーションのドキュメントを印刷します。|  
|[COleDocObjectItem::ExecCommand](#execcommand)|ユーザーによって指定されたコマンドを実行します。|  
|[COleDocObjectItem::GetActiveView](#getactiveview)|ドキュメントのアクティブなビューを取得します。|  
|[COleDocObjectItem::GetPageCount](#getpagecount)|コンテナー アプリケーションのドキュメント内のページの数を取得します。|  
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|コンテナー アプリケーションのドキュメントは、印刷用に準備します。|  
|[前述](#onprint)|コンテナー アプリケーションのドキュメントを印刷します。|  
|[COleDocObjectItem::QueryCommand](#querycommand)|ユーザー インターフェイスのイベントによって生成された 1 つ以上のコマンドの状態を調べるためにクエリを実行します。|  
|[COleDocObjectItem::Release](#release)|OLE 項目にリンクへの接続を解放しが開いていた場合に終了します。 クライアント アイテムは破棄されません。|  
  
## <a name="remarks"></a>コメント  
 MFC では、アクティブなドキュメントは、通常、一括編集可能な埋め込み、違いは次のと同様に処理します。  
  
-   `COleDocument`-派生クラスは、埋め込まれた現在のアイテムの一覧を維持できます。 ただし、これらの項目があります`COleDocObjectItem`-項目を派生します。  
  
-   アクティブ ドキュメントがアクティブである場合は、インプレース アクティブになる場合、ビューの全体のクライアント領域を占有します。  
  
-   Active ドキュメント コンテナーがのフル コントロール、**ヘルプ**メニュー。  
  
-   **ヘルプ**メニューには、Active ドキュメント コンテナーとサーバーの両方のメニュー項目が含まれています。  
  
 Active ドキュメント コンテナーが所有しているため、**ヘルプ**] メニューの [コンテナーがサーバーに転送します**ヘルプ**] メニューの [メッセージをサーバーにします。 この統合によって処理`COleDocObjectItem`です。  
  
 概要を参照してください メニューのマージとアクティブなドキュメントのライセンス認証に関する詳細については、 [Active ドキュメント コンテインメント](../../mfc/active-document-containment.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="coledocobjectitem"></a>  COleDocObjectItem::COleDocObjectItem  
 初期化するためにこのメンバー関数を呼び出す、`COleDocObjectItem`オブジェクト。  
  
```  
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pContainerDoc`  
 ポインター、 `COleDocument` active ドキュメント コンテナーとして機能するオブジェクト。 このパラメーターを指定する必要があります**NULL**を有効にする**IMPLEMENT_SERIALIZE**です。 以外の OLE 項目を構築する通常**NULL**ドキュメント ポインター。  
  
##  <a name="dodefaultprinting"></a>  :Dodefaultprinting  
 既定の設定を使用してドキュメントに、フレームワークによって呼び出されます。  
  
```  
static HRESULT DoDefaultPrinting(
    CView* pCaller,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCaller`  
 ポインター、 [CView](../../mfc/reference/cview-class.md)印刷コマンドを送信しているオブジェクト。  
  
 `pInfo`  
 ポインター、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)を印刷するジョブを記述するオブジェクト。  
  
##  <a name="execcommand"></a>  COleDocObjectItem::ExecCommand  
 ユーザーによって指定されたコマンドを実行するには、このメンバー関数を呼び出します。  
  
```  
HRESULT ExecCommand(
    DWORD nCmdID,  
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,  
    const GUID* pguidCmdGroup = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCmdID`  
 実行するコマンドの識別子。 識別されるグループである必要があります`pguidCmdGroup`です。  
  
 `nCmdExecOpt`  
 コマンドの実行オプションを指定します。 既定では、ユーザーに確認しないでコマンドの実行に設定します。 参照してください[する](http://msdn.microsoft.com/library/windows/desktop/ms683930)の値の一覧です。  
  
 `pguidCmdGroup`  
 コマンド グループの一意の識別子。 既定では、 **NULL**、標準的なグループを指定します。 コマンドは、渡された`nCmdID`グループに属している必要があります。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合返しますそれ以外の場合、次のエラー コードのいずれか。  
  
|[値]|説明|  
|-----------|-----------------|  
|**E_UNEXPECTED**|予期しないエラーが発生しました。|  
|**E_FAIL**|エラーが発生しました。|  
|**E_NOTIMPL**|MFC を示す自体が変換およびコマンドのディスパッチを試行します。|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup` 非**NULL**認識されているコマンド グループが指定されていません。|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID` グループ pGroup で有効なコマンドとして認識されません。|  
|**OLECMDERR_DISABLED**|によって識別されるコマンド`nCmdID`は無効になり、実行することはできません。|  
|**OLECMDERR_NOHELP**|呼び出し元によって識別されるコマンドのヘルプの要望`nCmdID`しますが、利用可能なヘルプはありません。|  
|**OLECMDERR_CANCELLED**|ユーザーには、実行が取り消されました。|  
  
### <a name="remarks"></a>コメント  
 `pguidCmdGroup`と`nCmdID`パラメーターを一緒に呼び出すコマンドを一意に識別します。 `nCmdExecOpt`パラメーターを実行する正確なアクションを指定します。  
  
##  <a name="getactiveview"></a>  COleDocObjectItem::GetActiveView  
 ポインターを取得するには、このメンバー関数を呼び出す、`IOleDocumentView`現在アクティブなビューのインターフェイスです。  
  
```  
LPOLEDOCUMENTVIEW GetActiveView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [IOleDocumentView](http://msdn.microsoft.com/library/windows/desktop/ms678455)現在アクティブなビューのインターフェイスです。 返すかどうか、現在のビューはありません、 **NULL**です。  
  
### <a name="remarks"></a>コメント  
 参照カウントを返された`IOleDocumentView`ポインターは、この関数によって返される前に加算されません。  
  
##  <a name="getpagecount"></a>  COleDocObjectItem::GetPageCount  
 ドキュメントのページの数を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetPageCount(
    LPLONG pnFirstPage,  
    LPLONG pcPages);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnFirstPage*  
 ドキュメントの最初のページの数へのポインター。 指定できます**NULL**、この番号は必要ありません、呼び出し元を示します。  
  
 *pcPages*  
 ドキュメント内のページの総数へのポインター。 指定できます**NULL**、この番号は必要ありません、呼び出し元を示します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="onprepareprinting"></a>  COleDocObjectItem::OnPreparePrinting  
 このメンバー関数は、印刷用のドキュメントを用意するためにフレームワークによって呼び出されます。  
  
```  
static BOOL OnPreparePrinting(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCaller`  
 ポインター、 [CView](../../mfc/reference/cview-class.md)印刷コマンドを送信しているオブジェクト。  
  
 `pInfo`  
 ポインター、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)を印刷するジョブを記述するオブジェクト。  
  
 `bPrintAll`  
 ドキュメント全体を印刷するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="onprint"></a>  前述  
 このメンバー関数は、ドキュメントを印刷するためにフレームワークによって呼び出されます。  
  
```  
static void OnPrint(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCaller`  
 印刷コマンドを送信している CView オブジェクトへのポインター。  
  
 `pInfo`  
 ポインター、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)を印刷するジョブを記述するオブジェクト。  
  
 `bPrintAll`  
 ドキュメント全体を印刷するかどうかを指定します。  
  
##  <a name="querycommand"></a>  COleDocObjectItem::QueryCommand  
 ユーザー インターフェイスのイベントによって生成された 1 つ以上のコマンドの状態を調べるためにクエリを実行します。  
  
```  
HRESULT QueryCommand(
    ULONG nCmdID,  
    DWORD* pdwStatus,  
    OLECMDTEXT* pCmdText =NULL,  
    const GUID* pguidCmdGroup =NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCmdID`  
 照会するコマンドの識別子。  
  
 `pdwStatus`  
 クエリの結果として返されたフラグへのポインター。 使用可能な値の一覧は、次を参照してください。 [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237)です。  
  
 `pCmdText`  
 ポインター、 [OLECMDTEXT](http://msdn.microsoft.com/library/windows/desktop/ms693314)構造を 1 つのコマンドの名前と状態情報を返します。 指定できます**NULL**を呼び出し元がこの情報を必要としないことを示します。  
  
 `pguidCmdGroup`  
 コマンド グループの一意の識別子指定できます**NULL**標準グループを指定します。  
  
### <a name="return-value"></a>戻り値  
 戻り値の完全な一覧については、次を参照してください。 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) Windows SDK に含まれています。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491)メソッドを Windows SDK で説明します。  
  
##  <a name="release"></a>  COleDocObjectItem::Release  
 OLE 項目にリンクへの接続を解放しが開いていた場合に終了します。 クライアント アイテムは破棄されません。  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCloseOption`  
 読み込み済み状態に戻ったときに、OLE 項目を保存どのような状況を指定するフラグを設定します。 使用可能な値の一覧は、次を参照してください。 [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close)です。  
  
### <a name="remarks"></a>コメント  
 クライアント アイテムは破棄されません。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCBIND](../../visual-cpp-samples.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [CDocObjectServerItem クラス](../../mfc/reference/cdocobjectserveritem-class.md)
