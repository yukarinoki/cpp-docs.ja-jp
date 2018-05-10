---
title: CDataRecoveryHandler クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
dev_langs:
- C++
helpviewer_keywords:
- CDataRecoveryHandler [MFC], CDataRecoveryHandler
- CDataRecoveryHandler [MFC], AutosaveAllDocumentInfo
- CDataRecoveryHandler [MFC], AutosaveDocumentInfo
- CDataRecoveryHandler [MFC], CreateDocumentInfo
- CDataRecoveryHandler [MFC], DeleteAllAutosavedFiles
- CDataRecoveryHandler [MFC], DeleteAutosavedFile
- CDataRecoveryHandler [MFC], GenerateAutosaveFileName
- CDataRecoveryHandler [MFC], GetAutosaveInterval
- CDataRecoveryHandler [MFC], GetAutosavePath
- CDataRecoveryHandler [MFC], GetDocumentListName
- CDataRecoveryHandler [MFC], GetNormalDocumentTitle
- CDataRecoveryHandler [MFC], GetRecoveredDocumentTitle
- CDataRecoveryHandler [MFC], GetRestartIdentifier
- CDataRecoveryHandler [MFC], GetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], GetShutdownByRestartManager
- CDataRecoveryHandler [MFC], Initialize
- CDataRecoveryHandler [MFC], QueryRestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], ReadOpenDocumentList
- CDataRecoveryHandler [MFC], RemoveDocumentInfo
- CDataRecoveryHandler [MFC], ReopenPreviousDocuments
- CDataRecoveryHandler [MFC], RestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], SaveOpenDocumentList
- CDataRecoveryHandler [MFC], SetAutosaveInterval
- CDataRecoveryHandler [MFC], SetAutosavePath
- CDataRecoveryHandler [MFC], SetRestartIdentifier
- CDataRecoveryHandler [MFC], SetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], SetShutdownByRestartManager
- CDataRecoveryHandler [MFC], UpdateDocumentInfo
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ba9615f583069ec63946fe52840dc5bc4fa545e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler クラス
`CDataRecoveryHandler`自動保存を文書化し、アプリケーションが予期せず終了した場合は、それを復元します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|`CDataRecoveryHandler` オブジェクトを構築します。|  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|登録されている各ファイルの自動保存、`CDataRecoveryHandler`クラスです。|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|自動指定されたドキュメントを保存します。|  
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|開いているドキュメントの一覧にドキュメントを追加します。|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|現在の自動保存されたファイルをすべて削除します。|  
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|指定した自動保存されたファイルを削除します。|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|指定されたドキュメントのファイル名に関連付けられている自動保存ファイルの名前を生成します。|  
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|自動保存の試行間隔を返します。|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|自動保存されたファイルのパスを返します。|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|ドキュメントの名前を取得、`CDocument`オブジェクト。|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|指定されたドキュメントの通常のタイトルを取得します。|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|作成し、復元したドキュメントのタイトルを返します。|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|アプリケーションの一意の再起動の識別子を取得します。|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|示すかどうか、`CDataRecoveryHandler`現在アイドル ループの自動保存を実行します。|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|再起動マネージャーのアプリケーションを終了する原因となったかどうかを示します。|  
|[CDataRecoveryHandler::Initialize](#initialize)|`CDataRecoveryHandler` を初期化します。|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|各ドキュメントをユーザーにダイアログ ボックスを表示、`CDataRecoveryHandler`自動保存します。 ダイアログ ボックスでは、ユーザーが、自動保存されたドキュメントを復元するかどうかを判断します。|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|レジストリから開いているドキュメントのリストを読み込みます。|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|指定されたドキュメントを開いているドキュメントの一覧から削除します。|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|既に開いているドキュメントを開きます。|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|ユーザー入力に基づく自動保存されたドキュメントを復元します。|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|現在開いているドキュメントの一覧を Windows レジストリに保存します。|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|ミリ秒単位での自動保存のサイクルの間隔を設定します。|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|自動保存されたファイルが格納されるディレクトリを設定します。|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|このインスタンスの一意の再起動の識別子を設定、`CDataRecoveryHandler`です。|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|設定するかどうか、`CDataRecoveryHandler`現在アイドル サイクル中に、開いているドキュメントの情報を Windows レジストリに保存します。|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|再起動マネージャーによって、アプリケーションの前回の終了が発生したかどうかを設定します。|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|ユーザーで保存されるため、ドキュメントの情報を更新します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|データ回復のハンドラーが開いていたドキュメントを再度開くかどうかを示します。|  
|m_bSaveDocumentInfoOnIdle|データ回復のハンドラーの自動保存が次のアイドル ループでドキュメントかどうかを示します。|  
|m_bShutdownByRestartManager|再起動マネージャー アプリケーションを終了するかどうかを示します。|  
|m_dwRestartManagerSupportFlags|再起動マネージャーのサポート内容を示すフラグは、アプリケーションを提供します。|  
|m_lstAutosavesToDelete|元のドキュメントを閉じたときに削除されなかった自動保存されたファイルの一覧。 アプリケーションの終了時、ファイルを削除する再起動マネージャー再試行します。|  
|m_mapDocNameToAutosaveName|自動保存されたファイル名にドキュメント名のマップです。|  
|m_mapDocNameToDocumentPtr|ドキュメント名のマップ、 [CDocument](../../mfc/reference/cdocument-class.md)ポインター。|  
|m_mapDocNameToRestoreBool|自動保存されたドキュメントを復元するかどうかを示すブール値パラメーターにドキュメント名のマップです。|  
|m_mapDocumentPtrToDocName|マップ、`CDocument`ドキュメント名へのポインター。|  
|m_mapDocumentPtrToDocTitle|マップ、`CDocument`ドキュメント タイトルへのポインター。 これらのタイトルは、ファイルを保存するために使用されます。|  
|m_nAutosaveInterval|自動保存の間隔をミリ秒で時間です。|  
|m_nTimerID|自動保存タイマーの識別子。|  
|m_strAutosavePath|自動保存されたドキュメントの格納場所。|  
|m_strRestartIdentifier|再起動マネージャーの GUID の文字列表現。|  
  
## <a name="remarks"></a>コメント  
 再起動マネージャーを使用して、`CDataRecoveryHandler`を保持するクラスに追跡をすべての開いているドキュメントと自動保存を必要に応じて、します。 自動保存を有効にするを使用して、 [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)メソッドです。 このメソッドに指示、`CDataRecoveryHandler`を次のアイドル ループの自動保存を実行します。 再起動マネージャー呼び出し`SetSaveDocumentInfoOnIdle`ときに、`CDataRecoveryHandler`自動保存を実行する必要があります。  
  
 すべてのメソッドの`CDataRecoveryHandler`クラスは仮想です。 独自のカスタム データ復旧のハンドラーを作成するには、このクラスのメソッドをオーバーライドします。 独自のデータ回復のハンドラーを作成するマネージャーを再起動するか、しない限りには、CDataRecoveryHandler がインスタンス化できません。 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)を作成、`CDataRecoveryHandler`オブジェクトが必要です。  
  
 使用する前に、`CDataRecoveryHandler`オブジェクトを呼び出す必要があります[CDataRecoveryHandler::Initialize](#initialize)です。  
  
 `CDataRecoveryHandler`クラスは、再起動マネージャーに密接に関連して`CDataRecoveryHandler`グローバル パラメーターに依存する`m_dwRestartManagerSupportFlags`です。 このパラメーターは、再起動マネージャーがどのようなアクセス許可と、アプリケーションとの対話方法を決定します。 再起動マネージャーを既存のアプリケーションに組み込むを割り当てる必要が`m_dwRestartManagerSupportFlags`メイン アプリケーションのコンス トラクターに適切な値です。 再起動マネージャーを使用する方法の詳細については、次を参照してください。[する方法: 再起動マネージャー サポートの追加](../../mfc/how-to-add-restart-manager-support.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdatarecovery.h  
  
##  <a name="autosavealldocumentinfo"></a>  CDataRecoveryHandler::AutosaveAllDocumentInfo  
 登録されている各ファイルの自動保存、`CDataRecoveryHandler`クラスです。  
  
```  
virtual BOOL AutosaveAllDocumentInfo();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合、`CDataRecoveryHandler`すべてのドキュメントを保存`FALSE`任意の文書が保存されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る`TRUE`保存する必要があるドキュメントが存在しない場合。 返します`TRUE`を取得する場合は、すべてのドキュメントを保存せず、`CWinApp`または`CDocManager`のアプリケーションでエラーが生成されます。  
  
 このメソッドのいずれも使用する`AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`または`AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`で設定する必要があります`m_dwRestartManagerSupportFlags`です。 参照してください[m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)詳細についてはします。  
  
##  <a name="autosavedocumentinfo"></a>  CDataRecoveryHandler::AutosaveDocumentInfo  
 自動指定されたドキュメントを保存します。  
  
```  
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,  
    BOOL bResetModifiedFlag = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|ポインター、`CDocument`を保存します。|  
|[入力] `bResetModifiedFlag`|`TRUE` 示します、`CDataRecoveryHandler`考慮`pDocument`を変更できます。`FALSE`フレームワークでは考慮を示す`pDocument`変更できません。 このフラグの効果についての詳細については、「解説」を参照してください。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 適切なフラグが設定されている場合と`pDocument`は有効な`CDocument`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 各`CDocument`オブジェクトは、これが最後に保存してから変更されていないことを示すフラグを持ちます。 使用して[CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified)このフラグの状態を判断します。 場合、`CDocument`が、最後に保存してから変更されていない`AutosaveDocumentInfo`そのドキュメントの自動保存されたファイルを削除します。 ドキュメントが最後に保存されてから変更されている場合に終了する、閉じる前にドキュメントを保存するユーザーがメッセージを表示します。  
  
> [!NOTE]
>  使用して`bResetModifiedFlag`に変更されていないドキュメントの状態を変更する可能性がありますデータが失われる。 フレームワーク、ドキュメントが変更されていない場合、終了するプロンプトが表示されませんを保存します。  
  
 このメソッドで例外をスローする、 [ASSERT](diagnostic-services.md#assert)マクロ場合`pDocument`が無効です`CDocument`オブジェクト。  
  
 このメソッドのいずれも使用する`AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`または`AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL`で設定する必要があります`m_dwRestartManagerSupportFlags`です。   
  
##  <a name="cdatarecoveryhandler"></a>  CDataRecoveryHandler::CDataRecoveryHandler  
 `CDataRecoveryHandler` オブジェクトを構築します。  
  
```  
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,  
    int nAutosaveInterval);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `dwRestartManagerSupportFlags`|再起動マネージャーのオプションがサポートされていることを示します。|  
|[入力] `nAutosaveInterval`|自動保存までの時間。 このパラメーターはミリ秒です。|  
  
### <a name="remarks"></a>コメント  
 MFC フレームワークが自動的に作成、`CDataRecoveryHandler`を使用するときに、アプリケーションのオブジェクト、**新しいプロジェクト**ウィザード。 データの回復の動作をカスタマイズすることも、再起動マネージャーをする場合は、しない限り、作成しないようにする、`CDataRecoveryHandler`オブジェクト。  
  
  
##  <a name="createdocumentinfo"></a>  CDataRecoveryHandler::CreateDocumentInfo  
 開いているドキュメントの一覧にドキュメントを追加します。  
  
```  
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|ポインター、`CDocument`です。 このメソッドには、このドキュメントの情報が作成されます`CDocument`です。|  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、`TRUE` が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは確認場合`pDocument`は、ドキュメントの一覧に既にドキュメントを追加する前にします。 場合`pDocument`は既にこのメソッドの一覧で、自動保存されたファイルに関連付けられている削除`pDocument`です。  
  
 このメソッドのいずれも使用する`AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`または`AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL`で設定する必要があります`m_dwRestartManagerSupportFlags`です。 
  
##  <a name="deleteallautosavedfiles"></a>  CDataRecoveryHandler::DeleteAllAutosavedFiles  
 現在の自動保存されたファイルをすべて削除します。  
  
```  
virtual BOOL DeleteAllAutosavedFiles();
```  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、常に `TRUE` を返します。  
  
##  <a name="deleteautosavedfile"></a>  CDataRecoveryHandler::DeleteAutosavedFile  
 指定した自動保存されたファイルを削除します。  
  
```  
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `strAutosavedFile`|自動保存されたファイル名を表す文字列。|  
  
### <a name="return-value"></a>戻り値  
 常に戻り値の既定の実装`TRUE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、自動保存されたファイルを削除できません、一覧で、ファイルの名前を保存します。 デストラクター、`CDataRecoveryHandler`リストで指定された各自動保存されたファイルを削除しようとしています。  
  
##  <a name="generateautosavefilename"></a>  CDataRecoveryHandler::GenerateAutosaveFileName  
 指定されたドキュメントのファイル名に関連付けられている自動保存ファイルの名前を生成します。  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strDocumentName`  
 ドキュメントの名前を表す文字列。 `GenerateAutosaveFileName` このドキュメントの名前を使用すると、対応する自動保存ファイル名を生成します。  
  
### <a name="return-value"></a>戻り値  
 自動保存ファイル名から生成された`strDocumentName`です。  
  
### <a name="remarks"></a>コメント  
 各ドキュメント名では、自動保存ファイル名を持つ一対一のマッピングを持ちます。  
  
##  <a name="getautosaveinterval"></a>  CDataRecoveryHandler::GetAutosaveInterval  
 自動保存の試行間隔を返します。  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>戻り値  
 自動保存の間隔をミリ秒数を試みます。  
  
##  <a name="getautosavepath"></a>  CDataRecoveryHandler::GetAutosavePath  
 自動保存されたファイルのパスを返します。  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>戻り値  
 自動保存されたドキュメントの格納場所。  
  
##  <a name="getdocumentlistname"></a>  CDataRecoveryHandler::GetDocumentListName  
 ドキュメントの名前を取得、`CDocument`オブジェクト。  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|ポインター、`CDocument`です。 `GetDocumentListName` このドキュメントの名前を取得`CDocument`です。|  
  
### <a name="return-value"></a>戻り値  
 ドキュメント名から`pDocument`です。  
  
### <a name="remarks"></a>コメント  
 `CDataRecoveryHandler`ドキュメント名でキーとして使用`m_mapDocNameToAutosaveName`、 `m_mapDocNameToDocumentPtr`、および`m_mapDocNameToRestoreBool`です。 これらのパラメーターを有効にする、`CDataRecoveryHandler`を監視する`CDocument`オブジェクト、自動保存ファイル名、および自動保存設定します。  
  
##  <a name="getnormaldocumenttitle"></a>  CDataRecoveryHandler::GetNormalDocumentTitle  
 指定されたドキュメントの通常のタイトルを取得します。  
  
```  
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|ポインター、`CDocument`です。|  
  
### <a name="return-value"></a>戻り値  
 指定されたドキュメントの通常のタイトル。  
  
### <a name="remarks"></a>コメント  
 ドキュメントの通常のタイトルは、パスを含まないドキュメントのファイル名では通常です。 これは、タイトル、**ファイル名**のフィールド、**名前を付けて保存** ダイアログ ボックス。  
  
##  <a name="getrecovereddocumenttitle"></a>  CDataRecoveryHandler::GetRecoveredDocumentTitle  
 作成し、復元したドキュメントのタイトルを返します。  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strDocumentTitle`  
 ドキュメントの通常のタイトル。  
  
### <a name="return-value"></a>戻り値  
 回復したドキュメントのタイトル。  
  
### <a name="remarks"></a>コメント  
 既定では、ドキュメントの回復のタイトルは通常のタイトルを **[回復]** が追加されます。 回復したタイトルが、ユーザーに表示されるときに、`CDataRecoveryHandler`自動保存されたドキュメントを復元するユーザーのクエリを実行します。  
  
##  <a name="getrestartidentifier"></a>  CDataRecoveryHandler::GetRestartIdentifier  
 アプリケーションの一意の再起動の識別子を取得します。  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>戻り値  
 一意の識別子を再起動します。  
  
### <a name="remarks"></a>コメント  
 再起動識別子は、アプリケーションの実行ごとに一意です。  
  
 `CDataRecoveryHandler`現在開いているドキュメントはレジストリに情報を格納します。 再起動マネージャーは、アプリケーションを終了して再起動し、する際に再起動識別子が提供、`CDataRecoveryHandler`です。 `CDataRecoveryHandler`再起動識別子を使用して既に開いているドキュメントの一覧を取得します。 これにより、`CDataRecoveryHandler`検索し、自動保存されたファイルを復元しようとします。  
  
##  <a name="getsavedocumentinfoonidle"></a>  CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 示すかどうか、`CDataRecoveryHandler`現在アイドル ループの自動保存を実行します。  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 示します、`CDataRecoveryHandler`現在のアイドル ループの自動保存`FALSE`そうでないことを示します。  
  
##  <a name="getshutdownbyrestartmanager"></a>  CDataRecoveryHandler::GetShutdownByRestartManager  
 再起動マネージャーのアプリケーションを終了する原因となったかどうかを示します。  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 再起動マネージャーのアプリケーションを終了する原因となったことを示します。`FALSE`しないことを示します。  
  
##  <a name="initialize"></a>  CDataRecoveryHandler::Initialize  
 `CDataRecoveryHandler` を初期化します。  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 初期化が成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 初期化プロセスでは、レジストリからの自動保存ファイルを格納するパスを読み込みます。 場合、`Initialize`メソッドには、このディレクトリが見つけられないか、かどうか、パスは`NULL`、`Initialize`失敗し、返します`FALSE`です。  
  
 使用して[CDataRecoveryHandler::SetAutosavePath](#setautosavepath) 、アプリケーションが初期化された後に自動保存パスを変更する、`CDataRecoveryHandler`です。  
  
 `Initialize`メソッドも次の自動保存が発生したときに監視するタイマーを開始します。 使用して[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) 、アプリケーションが初期化された後に自動保存の間隔を変更する、`CDataRecoveryHandler`です。  
  
##  <a name="queryrestoreautosaveddocuments"></a>  CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 各ドキュメントをユーザーにダイアログ ボックスを表示、`CDataRecoveryHandler`自動保存します。 ダイアログ ボックスでは、ユーザーが、自動保存されたドキュメントを復元するかどうかを判断します。  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションが Unicode である場合は、このメソッドが表示されます、 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md)をユーザーにします。 それ以外の場合、フレームワークを使用して[AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox)ユーザーを照会します。  
  
 後に`QueryRestoreAutosavedDocuments`応答をすべて収集メンバー変数に情報を格納、ユーザーから`m_mapDocNameToRestoreBool`です。 このメソッドは、自動保存されたドキュメントを復元できません。  
  
##  <a name="readopendocumentlist"></a>  CDataRecoveryHandler::ReadOpenDocumentList  
 レジストリから開いているドキュメントのリストを読み込みます。  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 示します`ReadOpenDocumentList`には、少なくとも 1 つのドキュメントの情報をレジストリから読み込まれました。`FALSE`ドキュメントの情報が読み込まれていないことを示します。  
  
### <a name="remarks"></a>コメント  
 この関数は、開いているドキュメントの情報をレジストリから読み込むし、メンバー変数に格納`m_mapDocNameToAutosaveName`です。  
  
 後に`ReadOpenDocumentList`すべてのデータが読み込まれるドキュメントについては、レジストリから削除します。  
  
##  <a name="removedocumentinfo"></a>  CDataRecoveryHandler::RemoveDocumentInfo  
 指定されたドキュメントを開いているドキュメントの一覧から削除します。  
  
```  
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|削除するドキュメントへのポインター。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合`pDocument`リストから削除されました`FALSE`場合はエラーが発生しました。  
  
### <a name="remarks"></a>コメント  
 ユーザーがドキュメントを閉じるときに、フレームワークは、開いているドキュメントの一覧から削除するのにこのメソッドを使用します。  
  
 場合`RemoveDocumentInfo`見つかりません`pDocument`、開いているドキュメントの一覧で何も行われません、返します`TRUE`です。  
  
 このメソッドを使用して`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`で設定する必要があります`m_dwRestartManagerSupportFlags`です。   
  
##  <a name="reopenpreviousdocuments"></a>  CDataRecoveryHandler::ReopenPreviousDocuments  
 既に開いているドキュメントを開きます。  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 少なくとも 1 つのドキュメントが開いていた場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、以前開いているドキュメントの最新の保存を開きます。 ドキュメントが保存されていない場合または自動保存、`ReopenPreviousDocuments`そのファイルの種類のテンプレートに基づく、空白のドキュメントを開きます。  
  
 このメソッドを使用して`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`で設定する必要があります`m_dwRestartManagerSupportFlags`です。 このパラメーターが設定されていない場合`ReopenPreviousDocuments`何も実行し、返します`FALSE`です。  
  
 既に開いているドキュメントの一覧に格納されているドキュメントが存在しない場合`ReopenPreviousDocuments`何も実行し、返します`FALSE`です。  
  
##  <a name="restoreautosaveddocuments"></a>  CDataRecoveryHandler::RestoreAutosavedDocuments  
 ユーザー入力に基づく自動保存されたドキュメントを復元します。  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このメソッドは、ドキュメントを正常に復元します。 場合、  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)を復元する必要があるどのドキュメントをユーザーを決定します。 ユーザーが、自動保存されたドキュメントを回復することに決めた場合`RestoreAutosavedDocuments`自動保存ファイルを削除します。 それ以外の場合、`RestoreAutosavedDocuments`開いているドキュメントを自動保存されたバージョンに置き換えます。  
  
 このメソッドのいずれも使用する`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`または`AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`で設定する必要があります`m_dwRestartManagerSupportFlags`です。   
  
##  <a name="saveopendocumentlist"></a>  CDataRecoveryHandler::SaveOpenDocumentList  
 現在開いているドキュメントの一覧を Windows レジストリに保存します。  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 開いているドキュメントを保存するが見つからない場合、または正常に保存された場合は。 `FALSE` 場合は、レジストリに保存するドキュメントがありますが、エラーが発生したため、保存されませんでした。  
  
### <a name="remarks"></a>コメント  
 再起動マネージャー呼び出し`SaveOpenDocumentList`アプリケーションが予期せず終了するときまたはでアップグレードを終了するとします。 使用して、アプリケーションが再起動されると、 [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)開いているドキュメントの一覧を取得します。  
  
 このメソッドは、開いているドキュメントの一覧のみを保存します。 メソッド[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)ドキュメント自体の保存を担当します。  
  
##  <a name="setautosaveinterval"></a>  CDataRecoveryHandler::SetAutosaveInterval  
 ミリ秒単位での自動保存のサイクルの間隔を設定します。  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nAutosaveInterval`  
 ミリ秒単位で新しい自動保存の間隔。  
  
##  <a name="setautosavepath"></a>  CDataRecoveryHandler::SetAutosavePath  
 自動保存されたファイルが格納されるディレクトリを設定します。  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `strAutosavePath`|自動保存ファイルの保存場所のパス。|  
  
### <a name="remarks"></a>コメント  
 自動保存ディレクトリを変更するファイルは移動されません現在自動保存します。  
  
##  <a name="setrestartidentifier"></a>  CDataRecoveryHandler::SetRestartIdentifier  
 このインスタンスの一意の再起動の識別子を設定、`CDataRecoveryHandler`です。  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `strRestartIdentifier`|再起動マネージャーの一意の識別子。|  
  
### <a name="remarks"></a>コメント  
 再起動マネージャーは、レジストリで、開いているドキュメントに関する情報を記録します。 この情報は、一意の再起動の識別子を持つキーとして格納されます。 再起動識別子は、アプリケーションの各インスタンスに対して一意であるため、アプリケーションの複数のインスタンスに予期せず終了した場合し、再起動マネージャーは、それらの各を回復できます。  
  
##  <a name="setsavedocumentinfoonidle"></a>  CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 設定するかどうか、`CDataRecoveryHandler`現在アイドル サイクル中に、開いているドキュメントの情報を Windows レジストリに保存します。  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `bSaveOnIdle`|`TRUE` 現在のアイドル状態サイクル中にドキュメントの情報を保存するには`FALSE to not perform a save`.|  
  
##  <a name="setshutdownbyrestartmanager"></a>  CDataRecoveryHandler::SetShutdownByRestartManager  
 再起動マネージャーによって、アプリケーションの前回の終了が発生したかどうかを設定します。  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `bShutdownByRestartManager`|`TRUE` 再起動マネージャーのアプリケーションを終了する原因となったことを示すために`FALSE`の理由により、アプリケーションが終了していることを示すためにします。|  
  
### <a name="remarks"></a>コメント  
 フレームワークは、前回の終了が予想されるかどうか、または、再起動マネージャーによって開始されたかどうかに基づいて異なる方法では動作します。  
  
##  <a name="updatedocumentinfo"></a>  CDataRecoveryHandler::UpdateDocumentInfo  
 ユーザーで保存されるため、ドキュメントの情報を更新します。  
  
```  
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|保存されたドキュメントへのポインター。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このメソッドは、自動保存されたドキュメントを削除し、文書の情報を更新する場合`FALSE`場合はエラーが発生しました。  
  
### <a name="remarks"></a>コメント  
 ユーザーがドキュメントを保存すると、アプリケーションは、不要になったため、自動保存されたファイルを削除します。 `UpdateDocumentInfo` 呼び出して、自動保存されたファイルを削除[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)です。 `UpdateDocumentInfo` 情報を追加`pDocument`の一覧に現在開いているドキュメント`RemoveDocumentInfo`が保存されている、その情報を削除するドキュメントが開かれたままです。  
  
 このメソッドを使用して`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`で設定する必要があります`m_dwRestartManagerSupportFlags`です。   
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)

