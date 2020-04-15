---
title: クラス
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
ms.openlocfilehash: bdfcbea6c345235358384691388afcdbbd2d0a42
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321938"
---
# <a name="cdatarecoveryhandler-class"></a>クラス

アプリケーション`CDataRecoveryHandler`が予期せず終了した場合、ドキュメントは自動保存され、復元されます。

## <a name="syntax"></a>構文

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|||
|-|-|
|[次の処理を行います。](#cdatarecoveryhandler)|`CDataRecoveryHandler` オブジェクトを構築します。|

### <a name="methods"></a>メソッド

|||
|-|-|
|[を切り取るハンドラー::オートセーブオールドキュメントインフォ](#autosavealldocumentinfo)|クラスに登録されている各ファイルを`CDataRecoveryHandler`自動保存します。|
|[を使用します。](#autosavedocumentinfo)|指定したドキュメントを自動保存します。|
|[をクリックします。](#createdocumentinfo)|開いているドキュメントの一覧にドキュメントを追加します。|
|[を切り:Dファイルを自動保存します。](#deleteallautosavedfiles)|現在の自動保存ファイルをすべて削除します。|
|[ファイル:D](#deleteautosavedfile)|指定した自動保存ファイルを削除します。|
|[を生成します。](#generateautosavefilename)|指定されたドキュメント ファイル名に関連付けられた自動保存ファイルの名前を生成します。|
|[を取得します。](#getautosaveinterval)|自動保存の試行間隔を返します。|
|[を取得します。](#getautosavepath)|自動保存されたファイルのパスを返します。|
|[を使用します。](#getdocumentlistname)|オブジェクトからドキュメント名を`CDocument`取得します。|
|[を取得します。](#getnormaldocumenttitle)|指定されたドキュメントの標準タイトルを取得します。|
|[を取得します。](#getrecovereddocumenttitle)|回復されたドキュメントのタイトルを作成して返します。|
|[を取得します。](#getrestartidentifier)|アプリケーションの一意の再起動識別子を取得します。|
|[をクリックします。](#getsavedocumentinfoonidle)|現在の`CDataRecoveryHandler`アイドル ループで自動保存を実行するかどうかを示します。|
|[を実行します。](#getshutdownbyrestartmanager)|再起動マネージャーがアプリケーションを終了させたかどうかを示します。|
|[を初期化します。](#initialize)|`CDataRecoveryHandler` を初期化します。|
|[::クエリ復元自動保存されたドキュメント](#queryrestoreautosaveddocuments)|自動保存したドキュメントごとにダイアログ ボックスを表示します`CDataRecoveryHandler`。 このダイアログ ボックスでは、ユーザーが自動保存されたドキュメントを復元するかどうかを指定します。|
|[ドキュメントリストを開きます。](#readopendocumentlist)|開いているドキュメント リストをレジストリから読み込みます。|
|[をクリックします。](#removedocumentinfo)|指定されたドキュメントを開いているドキュメント リストから削除します。|
|[::再オープン前のドキュメント](#reopenpreviousdocuments)|以前に開いたドキュメントを開きます。|
|[::自動保存されたドキュメントを復元します。](#restoreautosaveddocuments)|ユーザー入力に基づいて、自動保存されたドキュメントを復元します。|
|[をクリックします。](#saveopendocumentlist)|開いているドキュメントの現在の一覧を Windows レジストリに保存します。|
|[を切り取る](#setautosaveinterval)|自動保存サイクルの時間をミリ秒単位で設定します。|
|[を切り取るハンドラー::自動保存パスを設定します。](#setautosavepath)|自動保存ファイルが保存されるディレクトリを設定します。|
|[を切り取るハンドラー::セットリスタート識別子](#setrestartidentifier)|のこのインスタンスの一意の再起動識別子を`CDataRecoveryHandler`設定します。|
|[を切り取るハンドラー:::保存ドキュメントインフォオンアイドル](#setsavedocumentinfoonidle)|現在のアイドル`CDataRecoveryHandler`サイクル中に、 が開いているドキュメント情報を Windows レジストリに保存するかどうかを設定します。|
|[を実行します。](#setshutdownbyrestartmanager)|アプリケーションの直前の終了が再起動マネージャーによって発生したかどうかを設定します。|
|[をクリックします。](#updatedocumentinfo)|ユーザーがドキュメントを保存したために、ドキュメントの情報を更新します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|m_bRestoringPreviousOpenDocs|データ回復ハンドラーが、以前に開いたドキュメントを再度開くかどうかを示します。|
|m_bSaveDocumentInfoOnIdle|データ回復ハンドラーが次のアイドル ループでドキュメントを自動保存するかどうかを示します。|
|m_bShutdownByRestartManager|再起動マネージャーによってアプリケーションが終了するかどうかを示します。|
|m_dwRestartManagerSupportFlags|再起動マネージャーがアプリケーションに提供するサポートを示すフラグ。|
|m_lstAutosavesToDelete|元のドキュメントを閉じたときに削除されなかった自動保存ファイルのリスト。 アプリケーションが終了すると、再始動マネージャーはファイルの削除を再試行します。|
|m_mapDocNameToAutosaveName|自動保存されたファイル名にドキュメント名をマップします。|
|m_mapDocNameToDocumentPtr|ドキュメント名と[CDocument](../../mfc/reference/cdocument-class.md)ポインターのマップ。|
|m_mapDocNameToRestoreBool|ドキュメント名を、自動保存されたドキュメントを復元するかどうかを示すブール値パラメーターにマップします。|
|m_mapDocumentPtrToDocName|ドキュメント名への`CDocument`ポインターのマップ。|
|m_mapDocumentPtrToDocTitle|ドキュメント タイトル`CDocument`へのポインターのマップ。 これらのタイトルは、ファイルの保存に使用されます。|
|m_nAutosaveInterval|自動保存の間隔 (ミリ秒単位)。|
|m_nTimerID|自動保存タイマーの識別子。|
|m_strAutosavePath|自動保存されたドキュメントが保存される場所。|
|m_strRestartIdentifier|再起動マネージャーの GUID の文字列表現。|

## <a name="remarks"></a>解説

再起動マネージャーは、クラス`CDataRecoveryHandler`を使用して、開いているすべてのドキュメントを追跡し、必要に応じて自動保存します。 自動保存を有効にするには、メソッドを使用[します](#setsavedocumentinfoonidle)。 このメソッドは、次`CDataRecoveryHandler`のアイドル ループで自動保存を実行するように指示します。 再起動マネージャーは、`SetSaveDocumentInfoOnIdle`自動保存`CDataRecoveryHandler`を実行する必要があるときに呼び出します。

クラスのすべてのメソッドは`CDataRecoveryHandler`仮想です。 独自のカスタム データ回復ハンドラーを作成するには、このクラスのメソッドをオーバーライドします。 独自のデータ回復ハンドラーを作成するか、マネージャーを再起動しない限り、CDataRecoveryHandler をインスタンス化しないでください。 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)は、`CDataRecoveryHandler`必要に応じてオブジェクトを作成します。

オブジェクトを使用する前`CDataRecoveryHandler`に[、CDataRecoveryHandler::初期化](#initialize)を呼び出す必要があります。

クラスは`CDataRecoveryHandler`再起動マネージャに密接に接続されているため、`CDataRecoveryHandler`グローバル パラメータに依存します。 `m_dwRestartManagerSupportFlags` このパラメーターは、再起動マネージャーが持つアクセス許可と、アプリケーションとの対話方法を決定します。 既存のアプリケーションに再起動マネージャーを組み込むには、メイン`m_dwRestartManagerSupportFlags`アプリケーションのコンストラクターで適切な値を割り当てる必要があります。 再起動マネージャーの使用方法の詳細については、「方法 :[再起動マネージャー サポートを追加する](../../mfc/how-to-add-restart-manager-support.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdatarecovery.h

## <a name="cdatarecoveryhandlerautosavealldocumentinfo"></a><a name="autosavealldocumentinfo"></a>を切り取るハンドラー::オートセーブオールドキュメントインフォ

クラスに登録されている各ファイルを`CDataRecoveryHandler`自動保存します。

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>戻り値

すべてのドキュメントを`CDataRecoveryHandler`保存した場合は TRUE。文書が保存されなかった場合は FALSE。

### <a name="remarks"></a>解説

保存する必要があるドキュメントがない場合、このメソッドは TRUE を返します。 また、アプリケーションの`CWinApp`を`CDocManager`取得してエラーが発生した場合は、ドキュメントを保存せずに TRUE を返します。

このメソッドを使用するには、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTARTまたはAFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVALを に`m_dwRestartManagerSupportFlags`設定する必要があります。 詳細については、「[方法 : 再起動マネージャー サポートを追加](../../mfc/how-to-add-restart-manager-support.md)する 」を参照してください。

## <a name="cdatarecoveryhandlerautosavedocumentinfo"></a><a name="autosavedocumentinfo"></a>を使用します。

指定したドキュメントを自動保存します。

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ドキュメント*|[in]保存するへの`CDocument`ポインター。|
|*変更されたフラグを設定します。*|[in]TRUE は`CDataRecoveryHandler`*、pDocument*が変更されることを考慮することを示します。FALSE は、フレームワークが*pDocument*を変更していないものと見なすことを示します。 このフラグの効果の詳細については、「解説」を参照してください。|

### <a name="return-value"></a>戻り値

適切なフラグが設定され *、pDocument*が有効な`CDocument`オブジェクトである場合は TRUE。

### <a name="remarks"></a>解説

各`CDocument`オブジェクトには、最後の保存以降に変更されたかどうかを示すフラグがあります。 このフラグの状態を確認するには[、CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified)を使用します。 最後の`CDocument`保存以降に変更されていない場合は、`AutosaveDocumentInfo`そのドキュメントの自動保存ファイルを削除します。 ドキュメントが最後に保存した後に変更されている場合、ドキュメントを閉じると、閉じる前にドキュメントを保存するように求められます。

> [!NOTE]
> *bResetModifiedFlag*を使用してドキュメントの状態を変更せずに変更すると、ユーザーが保存されていないデータを失う可能性があります。 フレームワークがドキュメントを変更していないと見なしても、閉じるとユーザーに保存を求めるメッセージは表示されません。

このメソッドは *、pDocument*が有効な`CDocument`オブジェクトでない場合に[、ASSERT](diagnostic-services.md#assert)マクロを使用して例外をスローします。

このメソッドを使用するには、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTARTまたはAFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVALを*m_dwRestartManagerSupportFlags*で設定する必要があります。

## <a name="cdatarecoveryhandlercdatarecoveryhandler"></a><a name="cdatarecoveryhandler"></a>次の処理を行います。

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
|*サポートフラグ*|[in]再起動マネージャーのどのオプションがサポートされているかを示します。|
|*n自動保存間隔*|[in]自動保存の間隔。 このパラメータはミリ秒単位です。|

### <a name="remarks"></a>解説

MFC フレームワークは、`CDataRecoveryHandler`**新しいプロジェクト**ウィザードを使用すると、アプリケーションのオブジェクトを自動的に作成します。 データ回復動作または再起動マネージャーをカスタマイズする場合を除き、オブジェクトを`CDataRecoveryHandler`作成しないでください。

## <a name="cdatarecoveryhandlercreatedocumentinfo"></a><a name="createdocumentinfo"></a>をクリックします。

開いているドキュメントの一覧にドキュメントを追加します。

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ドキュメント*|[in]へのポインター。 `CDocument` このメソッドは、この`CDocument`ドキュメント情報を作成します。|

### <a name="return-value"></a>戻り値

既定の実装では TRUE が返されます。

### <a name="remarks"></a>解説

このメソッドは、ドキュメントを追加する前に *、pDocument*が既にドキュメントの一覧に含まれるかどうかをチェックします。 *pDocument が*既にリストに含まれる場合、このメソッドは*pDocument*に関連付けられた自動保存ファイルを削除します。

このメソッドを使用するには、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTARTまたはAFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVALを*m_dwRestartManagerSupportFlags*で設定する必要があります。

## <a name="cdatarecoveryhandlerdeleteallautosavedfiles"></a><a name="deleteallautosavedfiles"></a>を切り:Dファイルを自動保存します。

現在の自動保存ファイルをすべて削除します。

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>戻り値

既定の実装では、常に TRUE が返されます。

## <a name="cdatarecoveryhandlerdeleteautosavedfile"></a><a name="deleteautosavedfile"></a>ファイル:D

指定した自動保存ファイルを削除します。

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ストオート保存ファイル*|[in]自動保存されたファイル名を含む文字列。|

### <a name="return-value"></a>戻り値

既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

このメソッドが自動保存ファイルを削除できない場合は、ファイルの名前が一覧に保存されます。 のデストラクターは、`CDataRecoveryHandler`そのリストで指定された自動保存された各ファイルを削除しようとします。

## <a name="cdatarecoveryhandlergenerateautosavefilename"></a><a name="generateautosavefilename"></a>を生成します。

指定されたドキュメント ファイル名に関連付けられた自動保存ファイルの名前を生成します。

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>パラメーター

*ドキュメント名*<br/>
[in]ドキュメント名を含む文字列。 `GenerateAutosaveFileName`は、このドキュメント名を使用して、対応する自動保存ファイル名を生成します。

### <a name="return-value"></a>戻り値

から生成された自動保存ファイル*名*。

### <a name="remarks"></a>解説

各ドキュメント名には、自動保存ファイル名を持つ 1 対 1 のマッピングがあります。

## <a name="cdatarecoveryhandlergetautosaveinterval"></a><a name="getautosaveinterval"></a>を取得します。

自動保存の試行間隔を返します。

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>戻り値

自動保存の試行間隔 (ミリ秒単位)。

## <a name="cdatarecoveryhandlergetautosavepath"></a><a name="getautosavepath"></a>を取得します。

自動保存されたファイルのパスを返します。

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>戻り値

自動保存されたドキュメントが保存される場所。

## <a name="cdatarecoveryhandlergetdocumentlistname"></a><a name="getdocumentlistname"></a>を使用します。

オブジェクトからドキュメント名を`CDocument`取得します。

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ドキュメント*|[in]へのポインター。 `CDocument` `GetDocumentListName`は、この ドキュメント名を`CDocument`取得します。|

### <a name="return-value"></a>戻り値

ドキュメント名は*pDocument から取得します*。

### <a name="remarks"></a>解説

では`CDataRecoveryHandler`*、*、 、 、 m_mapDocNameToDocumentPtr 、 および*m_mapDocNameToRestoreBool* *m_mapDocNameToAutosaveName*のキーとしてドキュメント名を使用します。 これらのパラメータを使用`CDataRecoveryHandler`すると、`CDocument`オブジェクト、自動保存ファイル名、自動保存設定を監視できます。

## <a name="cdatarecoveryhandlergetnormaldocumenttitle"></a><a name="getnormaldocumenttitle"></a>を取得します。

指定されたドキュメントの標準タイトルを取得します。

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ドキュメント*|[in]へのポインター。 `CDocument`|

### <a name="return-value"></a>戻り値

指定されたドキュメントの標準タイトル。

### <a name="remarks"></a>解説

通常、ドキュメントの通常のタイトルは、パスのないドキュメントのファイル名です。 これは、[**名前を付けて保存**] ダイアログ ボックスの **[ファイル名**] フィールドのタイトルです。

## <a name="cdatarecoveryhandlergetrecovereddocumenttitle"></a><a name="getrecovereddocumenttitle"></a>を取得します。

回復されたドキュメントのタイトルを作成して返します。

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>パラメーター

*タイトル*<br/>
[in]ドキュメントの通常のタイトル。

### <a name="return-value"></a>戻り値

回復されたドキュメントのタイトル。

### <a name="remarks"></a>解説

既定では、ドキュメントの回復されたタイトルは、通常のタイトルで **[回復] が**追加されます。 回復されたタイトルは、ユーザーが自動保存された`CDataRecoveryHandler`ドキュメントを復元するクエリを実行したときに表示されます。

## <a name="cdatarecoveryhandlergetrestartidentifier"></a><a name="getrestartidentifier"></a>を取得します。

アプリケーションの一意の再起動識別子を取得します。

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>戻り値

一意の再起動識別子。

### <a name="remarks"></a>解説

再起動識別子は、アプリケーションの実行ごとに一意です。

現在`CDataRecoveryHandler`開いているドキュメントに関する情報がレジストリに格納されます。 再起動マネージャがアプリケーションを終了して再起動すると、 に再起動識別子が提供されます`CDataRecoveryHandler`。 は`CDataRecoveryHandler`、再起動識別子を使用して、以前に開いたドキュメントの一覧を取得します。 これにより、自動`CDataRecoveryHandler`保存されたファイルを検索して復元することができます。

## <a name="cdatarecoveryhandlergetsavedocumentinfoonidle"></a><a name="getsavedocumentinfoonidle"></a>をクリックします。

現在の`CDataRecoveryHandler`アイドル ループで自動保存を実行するかどうかを示します。

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>戻り値

TRUE は`CDataRecoveryHandler`、現在のアイドル ループの自動保存を示します。FALSE は、それがないことを示します。

## <a name="cdatarecoveryhandlergetshutdownbyrestartmanager"></a><a name="getshutdownbyrestartmanager"></a>を実行します。

再起動マネージャーがアプリケーションを終了させたかどうかを示します。

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>戻り値

TRUE は、再起動マネージャーがアプリケーションを終了させた場合を示します。FALSE は、それがなかったことを示します。

## <a name="cdatarecoveryhandlerinitialize"></a><a name="initialize"></a>を初期化します。

`CDataRecoveryHandler` を初期化します。

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>戻り値

初期化が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

初期化プロセスは、レジストリから自動保存ファイルを格納するためのパスを読み込みます。 メソッドがこの`Initialize`ディレクトリを見つけられない場合、またはパスが NULL`Initialize`の場合`FALSE`は、失敗して返します。

アプリケーションが初期化された後、自動保存パスを変更するには[、CDataRecoveryHandler::SetAutosavePath](#setautosavepath)を使用します`CDataRecoveryHandler`。

この`Initialize`メソッドは、次の自動保存が発生したときに監視するタイマーも開始します。 アプリケーションが初期化された後、自動保存間隔を変更するには[、CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)を使用します`CDataRecoveryHandler`。

## <a name="cdatarecoveryhandlerqueryrestoreautosaveddocuments"></a><a name="queryrestoreautosaveddocuments"></a>::クエリ復元自動保存されたドキュメント

自動保存したドキュメントごとにダイアログ ボックスを表示します`CDataRecoveryHandler`。 このダイアログ ボックスでは、ユーザーが自動保存されたドキュメントを復元するかどうかを指定します。

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>解説

アプリケーションが Unicode の場合、このメソッドは、ユーザーに[CTaskDialog](../../mfc/reference/ctaskdialog-class.md)を表示します。 それ以外の場合、フレームワークは[AfxMessageBox を](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox)使用してユーザーにクエリを実行します。

ユーザー`QueryRestoreAutosavedDocuments`からすべての応答を収集した後、メンバー変数*m_mapDocNameToRestoreBool*に情報を格納します。 このメソッドは、自動保存されたドキュメントを復元しません。

## <a name="cdatarecoveryhandlerreadopendocumentlist"></a><a name="readopendocumentlist"></a>ドキュメントリストを開きます。

開いているドキュメント リストをレジストリから読み込みます。

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>戻り値

TRUE は`ReadOpenDocumentList`、レジストリから少なくとも 1 つのドキュメントの情報を読み込んだことを示します。FALSE は、ドキュメント情報が読み込まれなかった場合を示します。

### <a name="remarks"></a>解説

この関数は、レジストリから開いているドキュメント情報を読み込み、メンバ変数*m_mapDocNameToAutosaveName*に格納します。

すべての`ReadOpenDocumentList`データを読み込んだ後、レジストリからドキュメント情報を削除します。

## <a name="cdatarecoveryhandlerremovedocumentinfo"></a><a name="removedocumentinfo"></a>をクリックします。

指定されたドキュメントを開いているドキュメント リストから削除します。

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ドキュメント*|[in]削除するドキュメントへのポインター。|

### <a name="return-value"></a>戻り値

true*を指定すると、pDocument*がリストから削除されました。エラーが発生した場合は FALSE。

### <a name="remarks"></a>解説

ユーザーがドキュメントを閉じると、フレームワークはこのメソッドを使用して、開いているドキュメントの一覧からドキュメントを削除します。

開`RemoveDocumentInfo`いているドキュメントの一覧で*pDocument*が見つからない場合は、何も実行されず、TRUE を返します。

このメソッドを使用するには、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES*をm_dwRestartManagerSupportFlags*で設定する必要があります。

## <a name="cdatarecoveryhandlerreopenpreviousdocuments"></a><a name="reopenpreviousdocuments"></a>::再オープン前のドキュメント

以前に開いたドキュメントを開きます。

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>戻り値

1 つ以上のドキュメントが開かれた場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、以前に開いたドキュメントの最新の保存を開きます。 文書が保存または自動保存されていない場合は、`ReopenPreviousDocuments`そのファイルの種類のテンプレートに基づいて空白の文書を開きます。

このメソッドを使用するには、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES*をm_dwRestartManagerSupportFlags*で設定する必要があります。 このパラメータが設定されていない場合は`ReopenPreviousDocuments`、何も行わないので、FALSE を返します。

以前に開いたドキュメントの一覧にドキュメントが保存されていない場合`ReopenPreviousDocuments`は、何も行われず、FALSE を返します。

## <a name="cdatarecoveryhandlerrestoreautosaveddocuments"></a><a name="restoreautosaveddocuments"></a>::自動保存されたドキュメントを復元します。

ユーザー入力に基づいて、自動保存されたドキュメントを復元します。

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>戻り値

このメソッドがドキュメントを正常に復元する場合は TRUE。

### <a name="remarks"></a>解説

このメソッドは、ユーザーが復元するドキュメントを決定するために[、CDataRecoveryHandler::QueryRestoreAutosavedドキュメント](#queryrestoreautosaveddocuments)を呼び出します。 ユーザーが自動保存されたドキュメントを復元しない場合は、`RestoreAutosavedDocuments`自動保存ファイルを削除します。 それ以外`RestoreAutosavedDocuments`の場合は、開いているドキュメントを自動保存されたバージョンに置き換えます。

このメソッドを使用するには、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILESまたはAFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILESを に`m_dwRestartManagerSupportFlags`設定する必要があります。

## <a name="cdatarecoveryhandlersaveopendocumentlist"></a><a name="saveopendocumentlist"></a>をクリックします。

開いているドキュメントの現在の一覧を Windows レジストリに保存します。

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>戻り値

開いているドキュメントが保存されていない場合、または正常に保存された場合は TRUE。 レジストリに保存するドキュメントがある場合は FALSE ですが、エラーが発生したため保存されませんでした。

### <a name="remarks"></a>解説

アプリケーションが予期せず`SaveOpenDocumentList`終了したとき、またはアップグレードのためにアプリケーションが終了すると、再起動マネージャーが呼び出されます。 アプリケーションが再起動すると、開いているドキュメントの一覧を取得するために[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)を使用します。

このメソッドは、開いているドキュメントの一覧のみを保存します。 メソッド[CDataRecoveryHandler::自動保存ドキュメント情報](#autosavedocumentinfo)は、ドキュメント自体を保存する責任があります。

## <a name="cdatarecoveryhandlersetautosaveinterval"></a><a name="setautosaveinterval"></a>を切り取る

自動保存サイクルの時間をミリ秒単位で設定します。

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>パラメーター

*n自動保存間隔*<br/>
[in]新しい自動保存間隔 (ミリ秒単位)。

## <a name="cdatarecoveryhandlersetautosavepath"></a><a name="setautosavepath"></a>を切り取るハンドラー::自動保存パスを設定します。

自動保存ファイルが保存されるディレクトリを設定します。

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*パスを自動保存する*|[in]自動保存ファイルが保存されるパス。|

### <a name="remarks"></a>解説

自動保存ディレクトリを変更しても、現在自動保存されているファイルは移動しません。

## <a name="cdatarecoveryhandlersetrestartidentifier"></a><a name="setrestartidentifier"></a>を切り取るハンドラー::セットリスタート識別子

のこのインスタンスの一意の再起動識別子を`CDataRecoveryHandler`設定します。

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*を使用します。*|[in]再起動マネージャーの一意の識別子。|

### <a name="remarks"></a>解説

再起動マネージャーは、レジストリで開いているドキュメントに関する情報を記録します。 この情報は、キーとして一意の再起動識別子と共に格納されます。 再起動識別子はアプリケーションの各インスタンスで一意であるため、アプリケーションの複数のインスタンスが予期せず終了し、再起動マネージャーが各インスタンスを回復できます。

## <a name="cdatarecoveryhandlersetsavedocumentinfoonidle"></a><a name="setsavedocumentinfoonidle"></a>を切り取るハンドラー:::保存ドキュメントインフォオンアイドル

現在のアイドル`CDataRecoveryHandler`サイクル中に、 が開いているドキュメント情報を Windows レジストリに保存するかどうかを設定します。

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*アイドル状態*|[in]現在のアイドル サイクル中にドキュメント情報を保存する場合は TRUE。保存を実行しない場合は FALSE。|

## <a name="cdatarecoveryhandlersetshutdownbyrestartmanager"></a><a name="setshutdownbyrestartmanager"></a>を実行します。

アプリケーションの直前の終了が再起動マネージャーによって発生したかどうかを設定します。

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*マネージャーマネージャー*|[in]再起動マネージャーがアプリケーションを終了させたことを示す場合は TRUE。別の理由でアプリケーションが終了したことを示す場合は FALSE。|

### <a name="remarks"></a>解説

フレームワークは、前の出口が予期しないものであったか、または再起動マネージャーによって開始されたかに基づいて、異なる動作をします。

## <a name="cdatarecoveryhandlerupdatedocumentinfo"></a><a name="updatedocumentinfo"></a>をクリックします。

ユーザーがドキュメントを保存したために、ドキュメントの情報を更新します。

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ドキュメント*|[in]保存されたドキュメントへのポインター。|

### <a name="return-value"></a>戻り値

このメソッドが自動保存されたドキュメントを削除し、ドキュメント情報を更新した場合は TRUE。エラーが発生した場合は FALSE。

### <a name="remarks"></a>解説

ユーザーがドキュメントを保存すると、自動保存されたファイルは不要になったため、アプリケーションによって削除されます。 `UpdateDocumentInfo`を呼び出すことによって自動保存されたファイルを[削除](#removedocumentinfo)します。 `UpdateDocumentInfo`その後、現在開いているドキュメント`RemoveDocumentInfo`の一覧に*pDocument*の情報を追加します。

このメソッドを使用するには、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES*をm_dwRestartManagerSupportFlags*で設定する必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)
