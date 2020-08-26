---
title: CDataRecoveryHandler クラス
ms.date: 03/27/2019
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
ms.openlocfilehash: 4bb4d4ddf291cb1efc01b887c54a6573c52df8dc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842924"
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler クラス

`CDataRecoveryHandler`アプリケーションが予期せず終了した場合、は自動でドキュメントを保存し、復元します。

## <a name="syntax"></a>構文

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|-|-|
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|`CDataRecoveryHandler` オブジェクトを構築します。|

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[CDataRecoveryHandler:: AutosaveAllDocumentInfo](#autosavealldocumentinfo)|クラスに登録されている各ファイルを自動保存 `CDataRecoveryHandler` します。|
|[CDataRecoveryHandler:: AutosaveDocumentInfo](#autosavedocumentinfo)|指定されたドキュメントを自動保存します。|
|[CDataRecoveryHandler:: CreateDocumentInfo](#createdocumentinfo)|開いているドキュメントの一覧にドキュメントを追加します。|
|[CDataRecoveryHandler::D eleteAllAutosavedFiles](#deleteallautosavedfiles)|現在の自動保存ファイルをすべて削除します。|
|[CDataRecoveryHandler::D eleteAutosavedFile](#deleteautosavedfile)|指定された自動保存ファイルを削除します。|
|[CDataRecoveryHandler:: GenerateAutosaveFileName](#generateautosavefilename)|指定されたドキュメントファイル名に関連付けられている自動保存ファイルの名前を生成します。|
|[CDataRecoveryHandler:: GetAutosaveInterval](#getautosaveinterval)|自動保存の試行間隔を返します。|
|[CDataRecoveryHandler:: GetAutosavePath](#getautosavepath)|自動保存されたファイルのパスを返します。|
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|オブジェクトからドキュメント名を取得し `CDocument` ます。|
|[CDataRecoveryHandler:: GetNormalDocumentTitle](#getnormaldocumenttitle)|指定されたドキュメントの通常のタイトルを取得します。|
|[CDataRecoveryHandler:: Get Eddocumenttitle](#getrecovereddocumenttitle)|回復されたドキュメントのタイトルを作成して返します。|
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|アプリケーションの一意の再起動 id を取得します。|
|[CDataRecoveryHandler:: GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|が現在の `CDataRecoveryHandler` アイドルループで自動保存を実行するかどうかを示します。|
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|再起動マネージャーによってアプリケーションの終了が発生したかどうかを示します。|
|[CDataRecoveryHandler:: Initialize](#initialize)|`CDataRecoveryHandler` を初期化します。|
|[CDataRecoveryHandler:: QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|が自動保存された各ドキュメントについて、ユーザーにダイアログボックスを表示 `CDataRecoveryHandler` します。 ダイアログボックスに、ユーザーが自動保存されたドキュメントを復元するかどうかが決定されます。|
|[CDataRecoveryHandler:: ReadOpenDocumentList](#readopendocumentlist)|開いているドキュメントの一覧をレジストリから読み込みます。|
|[CDataRecoveryHandler:: RemoveDocumentInfo](#removedocumentinfo)|開いているドキュメントリストから、指定されたドキュメントを削除します。|
|[CDataRecoveryHandler:: Reopenの前のドキュメント](#reopenpreviousdocuments)|以前開いたドキュメントを開きます。|
|[CDataRecoveryHandler:: RestoreAutosavedDocuments](#restoreautosaveddocuments)|ユーザー入力に基づいて、自動保存されたドキュメントを復元します。|
|[CDataRecoveryHandler:: SaveOpenDocumentList](#saveopendocumentlist)|開いているドキュメントの現在の一覧を Windows レジストリに保存します。|
|[CDataRecoveryHandler:: SetAutosaveInterval](#setautosaveinterval)|自動保存サイクルの間隔をミリ秒単位で設定します。|
|[CDataRecoveryHandler:: SetAutosavePath](#setautosavepath)|自動保存ファイルが格納されるディレクトリを設定します。|
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|のこのインスタンスの一意の再起動識別子を設定 `CDataRecoveryHandler` します。|
|[CDataRecoveryHandler:: SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|現在のアイドルサイクル中に、が開いている `CDataRecoveryHandler` ドキュメント情報を Windows レジストリに保存するかどうかを設定します。|
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|アプリケーションの前の終了が再起動マネージャーによって発生したかどうかを設定します。|
|[CDataRecoveryHandler:: UpdateDocumentInfo](#updatedocumentinfo)|ユーザーがドキュメントを保存したため、ドキュメントの情報を更新します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|-|-|
|m_bRestoringPreviousOpenDocs|データ回復ハンドラーが以前に開いたドキュメントを再び開くかどうかを示します。|
|m_bSaveDocumentInfoOnIdle|データ復旧ハンドラーが、次のアイドルループでドキュメントを自動保存するかどうかを示します。|
|m_bShutdownByRestartManager|再起動マネージャーによってアプリケーションが終了するかどうかを示します。|
|m_dwRestartManagerSupportFlags|再起動マネージャーによってアプリケーションに提供されるサポートを示すフラグ。|
|m_lstAutosavesToDelete|元のドキュメントが閉じられたときに削除されなかった、自動保存されたファイルの一覧。 アプリケーションが終了すると、再起動マネージャーによってファイルの削除が再試行されます。|
|m_mapDocNameToAutosaveName|自動保存されるファイル名へのドキュメント名のマップ。|
|m_mapDocNameToDocumentPtr|[CDocument](../../mfc/reference/cdocument-class.md)ポインターへのドキュメント名のマップ。|
|m_mapDocNameToRestoreBool|自動保存されたドキュメントを復元するかどうかを示すブール型パラメーターへのドキュメント名のマップ。|
|m_mapDocumentPtrToDocName|`CDocument`ドキュメント名へのポインターのマップ。|
|m_mapDocumentPtrToDocTitle|`CDocument`ドキュメントタイトルへのポインターのマップ。 これらのタイトルは、ファイルの保存に使用されます。|
|m_nAutosaveInterval|自動保存の間隔 (ミリ秒単位)。|
|m_nTimerID|自動保存タイマーの識別子。|
|m_strAutosavePath|自動保存されたドキュメントが格納される場所。|
|m_strRestartIdentifier|再起動マネージャーの GUID の文字列形式。|

## <a name="remarks"></a>解説

再起動マネージャーは、クラスを使用して、開いている `CDataRecoveryHandler` すべてのドキュメントを追跡し、必要に応じてそれらを自動保存します。 自動保存を有効にするには、 [CDataRecoveryHandler:: SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) メソッドを使用します。 このメソッドは、を、 `CDataRecoveryHandler` 次のアイドルループで自動保存を実行するように指示します。 再起動マネージャーは `SetSaveDocumentInfoOnIdle` 、が `CDataRecoveryHandler` 自動保存を実行するときにを呼び出します。

クラスのすべてのメソッド `CDataRecoveryHandler` は virtual です。 このクラスのメソッドをオーバーライドして、独自のカスタムデータ回復ハンドラーを作成します。 独自のデータ復旧ハンドラーまたは再起動マネージャーを作成しない限り、CDataRecoveryHandler をインスタンス化しないでください。 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)は、 `CDataRecoveryHandler` 必要に応じてオブジェクトを作成します。

オブジェクトを使用するには `CDataRecoveryHandler` 、 [CDataRecoveryHandler:: Initialize](#initialize)を呼び出す必要があります。

クラスは `CDataRecoveryHandler` 再起動マネージャーに密接に接続されているため、は `CDataRecoveryHandler` グローバルパラメーターに依存し `m_dwRestartManagerSupportFlags` ます。 このパラメーターは、再起動マネージャーが持つアクセス許可と、アプリケーションとの対話方法を決定します。 再起動マネージャーを既存のアプリケーションに組み込むには、 `m_dwRestartManagerSupportFlags` メインアプリケーションのコンストラクターに適切な値を割り当てる必要があります。 再起動マネージャーの使用方法の詳細については、「 [方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdatarecovery

## <a name="cdatarecoveryhandlerautosavealldocumentinfo"></a><a name="autosavealldocumentinfo"></a> CDataRecoveryHandler:: AutosaveAllDocumentInfo

クラスに登録されている各ファイルを自動保存 `CDataRecoveryHandler` します。

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>戻り値

がすべての `CDataRecoveryHandler` ドキュメントを保存した場合は TRUE。ドキュメントが保存されていない場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、保存する必要のあるドキュメントがない場合に TRUE を返します。 また、アプリケーションのを取得する `CWinApp` とエラーが生成される場合に、ドキュメントを保存せずに TRUE を返し `CDocManager` ます。

このメソッドを使用するには、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART または AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL のいずれかをで設定する必要があり `m_dwRestartManagerSupportFlags` ます。 詳細については、「 [方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)」を参照してください。

## <a name="cdatarecoveryhandlerautosavedocumentinfo"></a><a name="autosavedocumentinfo"></a> CDataRecoveryHandler:: AutosaveDocumentInfo

指定されたドキュメントを自動保存します。

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>パラメーター

*pDocument*\
から保存するへのポインター `CDocument` 。

*bResetModifiedFlag*\
からTRUE は、によって `CDataRecoveryHandler` *pdocument* が変更されると見なされることを示します。FALSE は、フレームワークが *Pdocument* を変更せずに考慮することを示します。 このフラグの効果の詳細については、「解説」を参照してください。

### <a name="return-value"></a>戻り値

適切なフラグが設定され、 *Pdocument* が有効なオブジェクトである場合は TRUE `CDocument` 。

### <a name="remarks"></a>解説

各 `CDocument` オブジェクトには、最後の保存以降に変更されたかどうかを示すフラグが付いています。 このフラグの状態を確認するには、 [CDocument:: IsModified](../../mfc/reference/cdocument-class.md#ismodified) を使用します。 最後に `CDocument` 保存した後にが変更されていない場合は、 `AutosaveDocumentInfo` そのドキュメントの自動保存ファイルを削除します。 最後の保存以降にドキュメントが変更された場合は、閉じる前にドキュメントを保存するようにユーザーに要求します。

> [!NOTE]
> *BResetModifiedFlag*を使用してドキュメントの状態を変更なしに変更すると、ユーザーが保存されていないデータを失う可能性があります。 フレームワークでドキュメントが変更されていないと見なされた場合、閉じると、ユーザーに保存するプロンプトは表示されません。

*Pdocument*が有効なオブジェクトでない場合、このメソッドは[ASSERT](diagnostic-services.md#assert)マクロを使用して例外をスロー `CDocument` します。

この方法を使用するには、 *m_dwRestartManagerSupportFlags*で AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART または AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL のいずれかを設定する必要があります。

## <a name="cdatarecoveryhandlercdatarecoveryhandler"></a><a name="cdatarecoveryhandler"></a> CDataRecoveryHandler::CDataRecoveryHandler

`CDataRecoveryHandler` オブジェクトを構築します。

```
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,
    int nAutosaveInterval);
```

### <a name="parameters"></a>パラメーター

*dwRestartManagerSupportFlags*\
から再起動マネージャーのどのオプションがサポートされているかを示します。

*nAutosaveInterval*\
から自動保存の間隔。 このパラメーターは、ミリ秒単位で指定します。

### <a name="remarks"></a>解説

新しいプロジェクトウィザードを使用すると、MFC フレームワークによってアプリケーションのオブジェクトが自動的に作成され `CDataRecoveryHandler` ます。 **New Project** データ回復動作または再起動マネージャーをカスタマイズする場合を除き、オブジェクトを作成しないでください `CDataRecoveryHandler` 。

## <a name="cdatarecoveryhandlercreatedocumentinfo"></a><a name="createdocumentinfo"></a> CDataRecoveryHandler:: CreateDocumentInfo

開いているドキュメントの一覧にドキュメントを追加します。

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>パラメーター

*pDocument*\
からへのポインター `CDocument` 。 このメソッドは、こののドキュメント情報を作成し `CDocument` ます。

### <a name="return-value"></a>戻り値

既定の実装では、TRUE が返されます。

### <a name="remarks"></a>解説

このメソッドは、ドキュメントを追加する前に、ドキュメントのリストに *Pdocument* が既に存在するかどうかを確認します。 *Pdocument*が既に一覧に含まれている場合、このメソッドは*pdocument*に関連付けられている自動保存ファイルを削除します。

この方法を使用するには、 *m_dwRestartManagerSupportFlags*で AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART または AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL のいずれかを設定する必要があります。

## <a name="cdatarecoveryhandlerdeleteallautosavedfiles"></a><a name="deleteallautosavedfiles"></a> CDataRecoveryHandler::D eleteAllAutosavedFiles

現在の自動保存ファイルをすべて削除します。

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>戻り値

既定の実装では、常に TRUE が返されます。

## <a name="cdatarecoveryhandlerdeleteautosavedfile"></a><a name="deleteautosavedfile"></a> CDataRecoveryHandler::D eleteAutosavedFile

指定された自動保存ファイルを削除します。

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>パラメーター

*strAutosavedFile*\
から自動保存されたファイル名を含む文字列。

### <a name="return-value"></a>戻り値

既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

このメソッドで自動保存ファイルを削除できない場合は、ファイルの名前が一覧に保存されます。 のデストラクターは、 `CDataRecoveryHandler` そのリストで指定された各自動保存ファイルを削除しようとします。

## <a name="cdatarecoveryhandlergenerateautosavefilename"></a><a name="generateautosavefilename"></a> CDataRecoveryHandler:: GenerateAutosaveFileName

指定されたドキュメントファイル名に関連付けられている自動保存ファイルの名前を生成します。

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>パラメーター

*strDocumentName*<br/>
からドキュメント名を格納している文字列。 `GenerateAutosaveFileName` は、このドキュメント名を使用して、対応する自動保存ファイル名を生成します。

### <a name="return-value"></a>戻り値

*StrDocumentName*から生成された自動保存ファイル名。

### <a name="remarks"></a>解説

各ドキュメント名には、自動保存ファイル名を使用した1対1のマッピングがあります。

## <a name="cdatarecoveryhandlergetautosaveinterval"></a><a name="getautosaveinterval"></a> CDataRecoveryHandler:: GetAutosaveInterval

自動保存の試行間隔を返します。

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>戻り値

自動保存を試行する間隔 (ミリ秒単位)。

## <a name="cdatarecoveryhandlergetautosavepath"></a><a name="getautosavepath"></a> CDataRecoveryHandler:: GetAutosavePath

自動保存されたファイルのパスを返します。

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>戻り値

自動保存されたドキュメントが格納される場所。

## <a name="cdatarecoveryhandlergetdocumentlistname"></a><a name="getdocumentlistname"></a> CDataRecoveryHandler::GetDocumentListName

オブジェクトからドキュメント名を取得し `CDocument` ます。

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>パラメーター

*pDocument*\
からへのポインター `CDocument` 。 `GetDocumentListName` このからドキュメント名を取得し `CDocument` ます。

### <a name="return-value"></a>戻り値

*Pdocument*のドキュメント名。

### <a name="remarks"></a>解説

では、 `CDataRecoveryHandler` *m_mapDocNameToAutosaveName*、 *m_mapDocNameToDocumentPtr*、および *m_mapDocNameToRestoreBool*のキーとしてドキュメント名が使用されます。 これらのパラメーターを使用すると、 `CDataRecoveryHandler` `CDocument` オブジェクト、自動保存ファイル名、および自動保存設定を監視できます。

## <a name="cdatarecoveryhandlergetnormaldocumenttitle"></a><a name="getnormaldocumenttitle"></a> CDataRecoveryHandler:: GetNormalDocumentTitle

指定されたドキュメントの通常のタイトルを取得します。

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>パラメーター

*pDocument*\
からへのポインター `CDocument` 。

### <a name="return-value"></a>戻り値

指定されたドキュメントの通常のタイトル。

### <a name="remarks"></a>解説

通常、ドキュメントの通常のタイトルは、パスを含まないドキュメントのファイル名です。 これは、[名前**を付けて保存**] ダイアログボックスの [**ファイル名**] フィールドのタイトルです。

## <a name="cdatarecoveryhandlergetrecovereddocumenttitle"></a><a name="getrecovereddocumenttitle"></a> CDataRecoveryHandler:: Get Eddocumenttitle

回復されたドキュメントのタイトルを作成して返します。

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>パラメーター

*strDocumentTitle*<br/>
からドキュメントの通常のタイトル。

### <a name="return-value"></a>戻り値

回復されたドキュメントタイトル。

### <a name="remarks"></a>解説

既定では、ドキュメントの回復されたタイトルは、 **[回復]** が追加された通常のタイトルです。 回復したタイトルは、が自動保存されたドキュメントをユーザーに照会するときに、ユーザーに表示され `CDataRecoveryHandler` ます。

## <a name="cdatarecoveryhandlergetrestartidentifier"></a><a name="getrestartidentifier"></a> CDataRecoveryHandler::GetRestartIdentifier

アプリケーションの一意の再起動 id を取得します。

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>戻り値

一意の再起動識別子。

### <a name="remarks"></a>解説

再起動識別子は、アプリケーションの実行ごとに一意です。

は、 `CDataRecoveryHandler` 現在開いているドキュメントに関する情報をレジストリに格納します。 再起動マネージャーは、アプリケーションを終了して再起動すると、に再起動識別子を渡し `CDataRecoveryHandler` ます。 は、 `CDataRecoveryHandler` 再起動識別子を使用して、既に開いているドキュメントの一覧を取得します。 これにより、が自動保存さ `CDataRecoveryHandler` れたファイルの検索と復元を試みることができます。

## <a name="cdatarecoveryhandlergetsavedocumentinfoonidle"></a><a name="getsavedocumentinfoonidle"></a> CDataRecoveryHandler:: GetSaveDocumentInfoOnIdle

が現在の `CDataRecoveryHandler` アイドルループで自動保存を実行するかどうかを示します。

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>戻り値

TRUE は、現在のアイドルループの自動保存を示し `CDataRecoveryHandler` ます。FALSE は、そうでないことを示します。

## <a name="cdatarecoveryhandlergetshutdownbyrestartmanager"></a><a name="getshutdownbyrestartmanager"></a> CDataRecoveryHandler::GetShutdownByRestartManager

再起動マネージャーによってアプリケーションの終了が発生したかどうかを示します。

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、再起動マネージャーによってアプリケーションが終了したことを示します。FALSE は、そうでないことを示します。

## <a name="cdatarecoveryhandlerinitialize"></a><a name="initialize"></a> CDataRecoveryHandler:: Initialize

`CDataRecoveryHandler` を初期化します。

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>戻り値

初期化が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

初期化プロセスは、レジストリから自動保存ファイルを格納するためのパスを読み込みます。 メソッドが `Initialize` このディレクトリを見つけられない場合、またはパスが NULL の場合、は失敗し、を `Initialize` 返し `FALSE` ます。

アプリケーションがを初期化した後で、 [CDataRecoveryHandler:: SetAutosavePath](#setautosavepath) を使用して、自動保存パスを変更し `CDataRecoveryHandler` ます。

また、メソッドは、 `Initialize` 次の自動保存が行われるタイミングを監視するタイマーを開始します。 [CDataRecoveryHandler:: SetAutosaveInterval](#setautosaveinterval)を使用して、アプリケーションがを初期化した後で、自動保存間隔を変更し `CDataRecoveryHandler` ます。

## <a name="cdatarecoveryhandlerqueryrestoreautosaveddocuments"></a><a name="queryrestoreautosaveddocuments"></a> CDataRecoveryHandler:: QueryRestoreAutosavedDocuments

が自動保存された各ドキュメントについて、ユーザーにダイアログボックスを表示 `CDataRecoveryHandler` します。 ダイアログボックスに、ユーザーが自動保存されたドキュメントを復元するかどうかが決定されます。

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>解説

アプリケーションが Unicode の場合、このメソッドはユーザーに [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) を表示します。 それ以外の場合、フレームワークは [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) を使用してユーザーを照会します。

は、 `QueryRestoreAutosavedDocuments` ユーザーからのすべての応答を収集した後、 *m_mapDocNameToRestoreBool*メンバー変数に情報を格納します。 このメソッドは、自動保存されたドキュメントを復元しません。

## <a name="cdatarecoveryhandlerreadopendocumentlist"></a><a name="readopendocumentlist"></a> CDataRecoveryHandler:: ReadOpenDocumentList

開いているドキュメントの一覧をレジストリから読み込みます。

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>戻り値

TRUE は、が `ReadOpenDocumentList` レジストリから少なくとも1つのドキュメントの情報を読み込んだことを示します。FALSE は、ドキュメント情報が読み込まれていないことを示します。

### <a name="remarks"></a>解説

この関数は、開いているドキュメントの情報をレジストリから読み込み、 *m_mapDocNameToAutosaveName*メンバー変数に格納します。

`ReadOpenDocumentList`は、すべてのデータを読み込んだ後、ドキュメントの情報をレジストリから削除します。

## <a name="cdatarecoveryhandlerremovedocumentinfo"></a><a name="removedocumentinfo"></a> CDataRecoveryHandler:: RemoveDocumentInfo

開いているドキュメントリストから、指定されたドキュメントを削除します。

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>パラメーター

*pDocument*\
から削除するドキュメントへのポインター。

### <a name="return-value"></a>戻り値

リストから *Pdocument* が削除された場合は TRUE。エラーが発生した場合は FALSE。

### <a name="remarks"></a>解説

ユーザーがドキュメントを閉じると、フレームワークはこのメソッドを使用して、開いているドキュメントの一覧からドキュメントを削除します。

開いている `RemoveDocumentInfo` ドキュメントの一覧に *pdocument* が見つからない場合は、何も実行されず、TRUE が返されます。

このメソッドを使用するには、 *m_dwRestartManagerSupportFlags*で AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES を設定する必要があります。

## <a name="cdatarecoveryhandlerreopenpreviousdocuments"></a><a name="reopenpreviousdocuments"></a> CDataRecoveryHandler:: Reopenの前のドキュメント

以前開いたドキュメントを開きます。

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>戻り値

少なくとも1つのドキュメントが開かれている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、以前開いたドキュメントの最新の保存を開きます。 ドキュメントが保存されていない、または自動保存されていない場合は、 `ReopenPreviousDocuments` そのファイルの種類のテンプレートに基づいて空のドキュメントが開きます。

このメソッドを使用するには、 *m_dwRestartManagerSupportFlags*で AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES を設定する必要があります。 このパラメーターが設定されていない場合、は何も実行せず、 `ReopenPreviousDocuments` FALSE を返します。

以前に開いていたドキュメントの一覧にドキュメントが格納されていない場合、は何も実行せず、 `ReopenPreviousDocuments` FALSE を返します。

## <a name="cdatarecoveryhandlerrestoreautosaveddocuments"></a><a name="restoreautosaveddocuments"></a> CDataRecoveryHandler:: RestoreAutosavedDocuments

ユーザー入力に基づいて、自動保存されたドキュメントを復元します。

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>戻り値

このメソッドがドキュメントを正常に復元した場合は TRUE。

### <a name="remarks"></a>解説

このメソッドは、 [CDataRecoveryHandler:: QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) を呼び出して、ユーザーがどのドキュメントを復元するかを決定します。 自動保存されたドキュメントを復元しないことをユーザーが決定した場合、は `RestoreAutosavedDocuments` 自動保存ファイルを削除します。 それ以外の場合は、開いているドキュメントを自動保存された `RestoreAutosavedDocuments` バージョンに置き換えます。

このメソッドを使用するには、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES または AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES のいずれかをで設定する必要があり `m_dwRestartManagerSupportFlags` ます。

## <a name="cdatarecoveryhandlersaveopendocumentlist"></a><a name="saveopendocumentlist"></a> CDataRecoveryHandler:: SaveOpenDocumentList

開いているドキュメントの現在の一覧を Windows レジストリに保存します。

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>戻り値

保存する開いているドキュメントがない場合、または正常に保存された場合は TRUE。 レジストリに保存するドキュメントが存在するが、エラーが発生したために保存されなかった場合は FALSE。

### <a name="remarks"></a>解説

再起動マネージャーは、 `SaveOpenDocumentList` アプリケーションが予期せず終了したとき、またはアップグレードのために終了したときに、を呼び出します。 アプリケーションが再起動すると、 [CDataRecoveryHandler:: ReadOpenDocumentList](#readopendocumentlist) を使用して、開いているドキュメントの一覧が取得されます。

このメソッドは、開いているドキュメントの一覧のみを保存します。 メソッド [CDataRecoveryHandler:: AutosaveDocumentInfo](#autosavedocumentinfo) は、ドキュメント自体を保存します。

## <a name="cdatarecoveryhandlersetautosaveinterval"></a><a name="setautosaveinterval"></a> CDataRecoveryHandler:: SetAutosaveInterval

自動保存サイクルの間隔をミリ秒単位で設定します。

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>パラメーター

*nAutosaveInterval*<br/>
から新しい自動保存間隔 (ミリ秒単位)。

## <a name="cdatarecoveryhandlersetautosavepath"></a><a name="setautosavepath"></a> CDataRecoveryHandler:: SetAutosavePath

自動保存ファイルが格納されるディレクトリを設定します。

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>パラメーター

*strAutosavePath*\
から自動保存ファイルが格納されるパス。

### <a name="remarks"></a>解説

自動保存ディレクトリを変更しても、現在自動保存されているファイルは移動されません。

## <a name="cdatarecoveryhandlersetrestartidentifier"></a><a name="setrestartidentifier"></a> CDataRecoveryHandler::SetRestartIdentifier

のこのインスタンスの一意の再起動識別子を設定 `CDataRecoveryHandler` します。

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>パラメーター

*strRestartIdentifier*\
から再起動マネージャーの一意の識別子。

### <a name="remarks"></a>解説

再起動マネージャーは、開いているドキュメントに関する情報をレジストリに記録します。 この情報は、一意の再起動識別子と共にキーとして格納されます。 再起動識別子はアプリケーションの各インスタンスに対して一意であるため、アプリケーションの複数のインスタンスが予期せずに終了し、再起動マネージャーがそれぞれを回復できます。

## <a name="cdatarecoveryhandlersetsavedocumentinfoonidle"></a><a name="setsavedocumentinfoonidle"></a> CDataRecoveryHandler:: SetSaveDocumentInfoOnIdle

現在のアイドルサイクル中に、が開いている `CDataRecoveryHandler` ドキュメント情報を Windows レジストリに保存するかどうかを設定します。

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>パラメーター

*bSaveOnIdle*\
から現在のアイドルサイクル中にドキュメント情報を保存する場合は TRUE。保存を実行しない場合は FALSE。

## <a name="cdatarecoveryhandlersetshutdownbyrestartmanager"></a><a name="setshutdownbyrestartmanager"></a> CDataRecoveryHandler::SetShutdownByRestartManager

アプリケーションの前の終了が再起動マネージャーによって発生したかどうかを設定します。

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>パラメーター

*bShutdownByRestartManager*\
から再起動マネージャーによってアプリケーションの終了が発生したことを示す場合は TRUE。アプリケーションが別の理由で終了したことを示す場合は FALSE。

### <a name="remarks"></a>解説

フレームワークの動作は、前の終了が予期しないものかどうか、または再起動マネージャーによって開始されたかどうかによって異なります。

## <a name="cdatarecoveryhandlerupdatedocumentinfo"></a><a name="updatedocumentinfo"></a> CDataRecoveryHandler:: UpdateDocumentInfo

ユーザーがドキュメントを保存したため、ドキュメントの情報を更新します。

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>パラメーター

*pDocument*\
から保存されたドキュメントへのポインター。

### <a name="return-value"></a>戻り値

このメソッドが自動保存されたドキュメントを削除し、ドキュメント情報を更新した場合は TRUE です。エラーが発生した場合は FALSE。

### <a name="remarks"></a>解説

ユーザーがドキュメントを保存すると、アプリケーションは不要になったため、自動保存されたファイルを削除します。 `UpdateDocumentInfo`[CDataRecoveryHandler:: RemoveDocumentInfo](#removedocumentinfo)を呼び出して、自動保存されたファイルを削除します。 `UpdateDocumentInfo` は情報を削除するが、保存されたドキュメントは開いたままであるため、現在開いているドキュメントの一覧に *Pdocument* から情報を追加し `RemoveDocumentInfo` ます。

このメソッドを使用するには、 *m_dwRestartManagerSupportFlags*で AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES を設定する必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)
