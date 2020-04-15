---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
ms.openlocfilehash: 5c2814f963ea4814e0d7585e0e4d6dda26c1f04d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321323"
---
# <a name="catltransactionmanager-class"></a>クラス

クラスはカーネル トランザクション マネージャー (KTM) 関数のラッパーを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlTransactionManager;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コトルトランザクションマネージャー](#dtor)|デストラクタ。|
|[をクリックします。](#catltransactionmanager)|コンストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[閉じる](#close)|トランザクション ハンドルを閉じます。|
|[Commit](#commit)|トランザクションのコミットを要求します。|
|[作成](#create)|トランザクション ハンドルを作成します。|
|[CreateFile](#createfile)|トランザクション操作としてファイル、ファイル ストリーム、またはディレクトリを作成または開きます。|
|[DeleteFile](#deletefile)|トランザクション操作として既存のファイルを削除します。|
|[ファイルを検索する](#findfirstfile)|トランザクション操作として、ディレクトリでファイルまたはサブディレクトリを検索します。|
|[ファイル属性を取得します。](#getfileattributes)|指定したファイルまたはディレクトリのファイル システム属性をトランザクション操作として取得します。|
|[ファイル属性の取得](#getfileattributesex)|指定したファイルまたはディレクトリのファイル システム属性をトランザクション操作として取得します。|
|[ハンドルを取得します。](#gethandle)|トランザクション ハンドルを返します。|
|[イスフォールバック](#isfallback)|フォールバック呼び出しが有効かどうかを判断します。|
|[MoveFile](#movefile)|既存のファイルまたはディレクトリ (子を含む) をトランザクション操作として移動します。|
|[キーエックス](#regcreatekeyex)|指定したレジストリ キーを作成し、トランザクションに関連付けます。 キーが既に存在する場合は、そのキーが開きます。|
|[レジストリキー](#regdeletekey)|トランザクション操作として、指定されたプラットフォーム固有のレジストリ ビューからサブキーとその値を削除します。|
|[キーエックスを開く](#regopenkeyex)|指定したレジストリ キーを開き、トランザクションに関連付けます。|
|[ロールバック](#rollback)|トランザクションのロールバックを要求します。|
|[ファイル属性の設定](#setfileattributes)|ファイルまたはディレクトリの属性をトランザクション操作として設定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|フォールバックがサポートされている場合は TRUE。それ以外の場合は FALSE。|
|[m_hTransaction](#m_htransaction)|トランザクション ハンドル。|

## <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

[ATL::カトルトランザクションマネージャー](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** atltransactionmanager.h

## <a name="catltransactionmanager"></a><a name="dtor"></a>コトルトランザクションマネージャー

デストラクタ。

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>解説

通常の処理では、トランザクションは自動的にコミットされ、クローズされます。 例外アンワインド中にデストラクターが呼び出されると、トランザクションはロールバックされ、閉じられます。

## <a name="catltransactionmanager"></a><a name="catltransactionmanager"></a>をクリックします。

コンストラクター。

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>パラメーター

*bフォールバック*<br/>
TRUE は、サポート フォールバックを示します。 トランザクション関数が失敗すると、クラスは自動的に「非トランザクション」関数を呼び出します。 FALSE は「フォールバック」呼び出しがないことを示します。

*トランザクションを自動作成します。*<br/>
TRUE は、トランザクション ハンドラーがコンストラクターで自動的に作成されることを示します。 FALSE は、それがないことを示します。

### <a name="remarks"></a>解説

## <a name="close"></a><a name="close"></a>閉じる

トランザクション ハンドルを閉じます。

```
inline BOOL Close();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このラッパーは関数`CloseHandle`を呼び出します。 メソッドはデストラクターで自動的に呼び出されます。

## <a name="commit"></a><a name="commit"></a>コミット

トランザクションのコミットを要求します。

```
inline BOOL Commit();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このラッパーは関数`CommitTransaction`を呼び出します。 メソッドはデストラクターで自動的に呼び出されます。

## <a name="create"></a><a name="create"></a>作成

トランザクション ハンドルを作成します。

```
inline BOOL Create();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このラッパーは関数`CreateTransaction`を呼び出します。 チェックする

## <a name="createfile"></a><a name="createfile"></a>Createfile

トランザクション操作としてファイル、ファイル ストリーム、またはディレクトリを作成または開きます。

```
inline HANDLE CreateFile(
    LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
作成または開くオブジェクトの名前。

*アクセスを許可*<br/>
読み取り、書き込み、両方、またはどちらも (ゼロ) として要約できるオブジェクトへのアクセス。 最もよく使用される値は、GENERIC_READ、GENERIC_WRITE、またはその両方 GENERIC_WRITE &#124; GENERIC_READです。

*を使用します。*<br/>
オブジェクトの共有モード (読み取り、書き込み、両方、削除、これらすべて、またはなし: 0、FILE_SHARE_DELETE、FILE_SHARE_READ、FILE_SHARE_WRITE。

*属性*<br/>
省略可能なセキュリティ記述子を含み、返されたハンドルを子プロセスによって継承できるかどうかを決定するSECURITY_ATTRIBUTES構造体へのポインター。 パラメーターは NULL にすることができます。

*dwクリエーションディスポジション*<br/>
存在するファイルに対して実行するアクション。 このパラメーターは、CREATE_ALWAYS、CREATE_NEW、OPEN_ALWAYS、OPEN_EXISTING、またはTRUNCATE_EXISTINGの値のいずれかでなければなりません。

*属性*<br/>
ファイルの属性とフラグ。 このパラメーターには、使用可能なファイル属性 (FILE_ATTRIBUTE_*) の任意の組み合わせを組み合わせて指定できます。 その他のファイル属性はすべてFILE_ATTRIBUTE_NORMAL上書きされます。 このパラメーターには、バッファリング動作、アクセス モード\*、およびその他の特殊目的フラグを制御するためのフラグ (FILE_FLAG_ ) の組み合わせを含めることもできます。 これらは、FILE_ATTRIBUTE_\*値と組み合わせます。

*ファイル*<br/>
GENERIC_READアクセス権を持つテンプレート ファイルへの有効なハンドル。 テンプレート・ファイルは、作成されるファイルのファイル属性および拡張属性を提供します。 このパラメーターは NULL にすることができます。

### <a name="return-value"></a>戻り値

オブジェクトへのアクセスに使用できるハンドルを返します。

### <a name="remarks"></a>解説

このラッパーは関数`CreateFileTransacted`を呼び出します。

## <a name="deletefile"></a><a name="deletefile"></a>ファイルの削除

トランザクション操作として既存のファイルを削除します。

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
削除するファイルの名前。

### <a name="remarks"></a>解説

このラッパーは関数`DeleteFileTransacted`を呼び出します。

## <a name="findfirstfile"></a><a name="findfirstfile"></a>ファイルを検索する

トランザクション操作として、ディレクトリでファイルまたはサブディレクトリを検索します。

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
検索するディレクトリまたはパス、およびファイル名。 このパラメーターには、アスタリスク (*) や疑問符 ()などのワイルドカード文字を含めることができます。

*次の情報*<br/>
見つかったファイルまたはサブディレクトリに関する情報を受け取るWIN32_FIND_DATA構造体へのポインタ。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は、後続の or の呼び`FindNextFile`出`FindClose`しで使用される検索ハンドルです。 関数が*lpFileName*パラメーターの検索文字列からファイルを検索できない場合、戻り値はINVALID_HANDLE_VALUE。

### <a name="remarks"></a>解説

このラッパーは関数`FindFirstFileTransacted`を呼び出します。

## <a name="getfileattributes"></a><a name="getfileattributes"></a>ファイル属性を取得します。

指定したファイルまたはディレクトリのファイル システム属性をトランザクション操作として取得します。

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
ファイルまたはディレクトリの名前。

### <a name="remarks"></a>解説

このラッパーは関数`GetFileAttributesTransacted`を呼び出します。

## <a name="getfileattributesex"></a><a name="getfileattributesex"></a>ファイル属性の取得

指定したファイルまたはディレクトリのファイル システム属性をトランザクション操作として取得します。

```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
ファイルまたはディレクトリの名前。

*をクリックします。*<br/>
取得する属性情報のレベル。

*ファイル情報*<br/>
属性情報を受け取るバッファーへのポインター。 このバッファーに格納される属性情報の種類は、 *fInfoLevelId*の値によって決まります。 パラメーター*が*GetFileExInfoStandard の場合、このパラメーターはWIN32_FILE_ATTRIBUTE_DATA構造体を指します。

### <a name="remarks"></a>解説

このラッパーは関数`GetFileAttributesTransacted`を呼び出します。

## <a name="gethandle"></a><a name="gethandle"></a>ハンドルを取得します。

トランザクション ハンドルを返します。

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>戻り値

クラスのトランザクション ハンドルを返します。 ハンドルに`CAtlTransactionManager`アタッチされていない場合は NULL を返します。

### <a name="remarks"></a>解説

## <a name="isfallback"></a><a name="isfallback"></a>イスフォールバック

フォールバック呼び出しが有効かどうかを判断します。

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>戻り値

TRUE を返すクラスは、フォールバック呼び出しをサポートします。 それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="m_bfallback"></a><a name="m_bfallback"></a>m_bFallback

フォールバックがサポートされている場合は TRUE。それ以外の場合は FALSE。

```
BOOL m_bFallback;
```

### <a name="remarks"></a>解説

## <a name="m_htransaction"></a><a name="m_htransaction"></a>m_hTransaction

トランザクション ハンドル。

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>解説

## <a name="movefile"></a><a name="movefile"></a>ファイルの移動

既存のファイルまたはディレクトリ (子を含む) をトランザクション操作として移動します。

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>パラメーター

*ファイル名を指定します。*<br/>
ローカル コンピュータ上の既存のファイルまたはディレクトリの現在の名前。

*ファイル名を指定します。*<br/>
ファイルまたはディレクトリの新しい名前。 この名前は既に存在してはなりません。 新しいファイルが別のファイル システムまたはドライブ上にある可能性があります。 新しいディレクトリは同じドライブになければなりません。

### <a name="remarks"></a>解説

このラッパーは関数`MoveFileTransacted`を呼び出します。

## <a name="regcreatekeyex"></a><a name="regcreatekeyex"></a>キーエックス

指定したレジストリ キーを作成し、トランザクションに関連付けます。 キーが既に存在する場合は、そのキーが開きます。

```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```

### <a name="parameters"></a>パラメーター

*Hkey*<br/>
開いているレジストリ キーへのハンドル。

*サブキー*<br/>
この関数が開く、または作成するサブキーの名前。

*dw予約済み*<br/>
このパラメーターは予約済みで、0 である必要があります。

*クラス*<br/>
このキーのユーザー定義クラス。 このパラメータは無視できます。 このパラメーターは NULL にすることができます。

*dw オプション*<br/>
このパラメーターには、REG_OPTION_BACKUP_RESTORE、REG_OPTION_NON_VOLATILE、またはREG_OPTION_VOLATILEのいずれかの値を指定できます。

*サム必要に応じて*<br/>
キーのアクセス権を指定するマスク。

*属性*<br/>
SECURITY_ATTRIBUTES 構造体へのポインター。この構造体は、返されたハンドルを子プロセスが継承できるかどうかを決定します。 *場合は、NULL、* ハンドルを継承できません。

*フク結果*<br/>
開かれたキーまたは作成されたキーへのハンドルを受け取る変数へのポインター。 キーが定義済みのレジストリ キーの 1 つでない場合は`RegCloseKey`、ハンドルの使用が完了した後で関数を呼び出します。

*lpdwディスポジション*<br/>
REG_CREATED_NEW_KEYまたはREG_OPENED_EXISTING_KEYのいずれかの破棄値を受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はERROR_SUCCESS。 関数が失敗した場合、戻り値は Winerror.h で定義された 0 以外のエラー コードです。

### <a name="remarks"></a>解説

このラッパーは関数`RegCreateKeyTransacted`を呼び出します。

## <a name="regdeletekey"></a><a name="regdeletekey"></a>レジストリキー

トランザクション操作として、指定されたプラットフォーム固有のレジストリ ビューからサブキーとその値を削除します。

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Hkey*|開いているレジストリ キーへのハンドル。|
|*サブキー*|削除するキーの名前。|

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はERROR_SUCCESS。 関数が失敗した場合、戻り値は Winerror.h で定義された 0 以外のエラー コードです。

### <a name="remarks"></a>解説

このラッパーは関数`RegDeleteKeyTransacted`を呼び出します。

## <a name="regopenkeyex"></a><a name="regopenkeyex"></a>キーエックスを開く

指定したレジストリ キーを開き、トランザクションに関連付けます。

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>パラメーター

*Hkey*<br/>
開いているレジストリ キーへのハンドル。

*サブキー*<br/>
開くレジストリ サブキーの名前。

*ウルオプション*<br/>
このパラメーターは予約済みで、0 である必要があります。

*サム必要に応じて*<br/>
キーのアクセス権を指定するマスク。

*フク結果*<br/>
開かれたキーまたは作成されたキーへのハンドルを受け取る変数へのポインター。 キーが定義済みのレジストリ キーの 1 つでない場合は`RegCloseKey`、ハンドルの使用が完了した後で関数を呼び出します。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はERROR_SUCCESS。 関数が失敗した場合、戻り値は Winerror.h で定義された 0 以外のエラー コードです。

### <a name="remarks"></a>解説

このラッパーは関数`RegOpenKeyTransacted`を呼び出します。

## <a name="rollback"></a><a name="rollback"></a>ロールバック

トランザクションのロールバックを要求します。

```
inline BOOL Rollback();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このラッパーは関数`RollbackTransaction`を呼び出します。

## <a name="setfileattributes"></a><a name="setfileattributes"></a>ファイル属性の設定

ファイルまたはディレクトリの属性をトランザクション操作として設定します。

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
ファイルまたはディレクトリの名前。

*dw属性*<br/>
ファイルに設定するファイル属性。 詳細については、「[トランスフォームを実行するファイル属性」を参照してください。](/windows/win32/api/winbase/nf-winbase-setfileattributestransactedw)

### <a name="remarks"></a>解説

このラッパーは関数`SetFileAttributesTransacted`を呼び出します。

## <a name="see-also"></a>関連項目

[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
