---
title: CAtlTransactionManager クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1217fe9c7bbb43b578a7f7236c69531f04464a44
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755922"
---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager クラス

CAtlTransactionManager クラスは、カーネル トランザクション マネージャー (KTM) 関数のラッパーを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlTransactionManager;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[~ CAtlTransactionManager](#dtor)|CAtlTransactionManager デストラクターです。|
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager コンス トラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[閉じる](#close)|1 つのトランザクション ハンドルを閉じます。|
|[コミット](#commit)|トランザクションをコミットすることを要求します。|
|[作成します。](#create)|トランザクション ハンドルを作成します。|
|[CreateFile](#createfile)|作成するか、ファイル、ファイル ストリーム、またはトランザクション処理された操作とディレクトリを開きます。|
|[DeleteFile](#deletefile)|トランザクション処理された操作として、既存のファイルを削除します。|
|[FindFirstFile](#findfirstfile)|トランザクション処理された操作としては、ディレクトリのファイルまたはサブディレクトリを検索します。|
|[GetFileAttributes](#getfileattributes)|トランザクション処理された操作として指定したファイルまたはディレクトリのファイル システム属性を取得します。|
|[GetFileAttributesEx](#getfileattributesex)|トランザクション処理された操作として指定したファイルまたはディレクトリのファイル システム属性を取得します。|
|[このインターフェイスの GetHandle](#gethandle)|トランザクション ハンドルを返します。|
|[IsFallback](#isfallback)|フォールバックの呼び出しが有効になっているかどうかを判断します。|
|[MoveFile](#movefile)|既存のファイルまたはトランザクション処理された操作として、その子を含む、ディレクトリに移動します。|
|[RegCreateKeyEx](#regcreatekeyex)|指定されたレジストリ キーを作成し、トランザクションに関連付けます。 キーが既に存在する場合は、関数が開きます。|
|[RegDeleteKey](#regdeletekey)|トランザクション処理された操作として、レジストリの指定したプラットフォームに固有のビューからサブキーとその値を削除します。|
|[RegOpenKeyEx](#regopenkeyex)|指定されたレジストリ キーを開き、トランザクションに関連付けます。|
|[ロールバック](#rollback)|トランザクションをロールバックするように要求します。|
|[SetFileAttributes](#setfileattributes)|トランザクション処理された操作として、ファイルまたはディレクトリの属性を設定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|TRUE の場合、フォールバックがサポートされています。FALSE それ以外の場合。|
|[m_hTransaction](#m_htransaction)|トランザクションのハンドルです。|

## <a name="remarks"></a>Remarks

## <a name="inheritance-hierarchy"></a>継承階層

[ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** atltransactionmanager.h

##  <a name="dtor"></a>  ~ CAtlTransactionManager

CAtlTransactionManager デストラクターです。

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>Remarks

通常の処理でトランザクションが自動的にコミットされ終了します。 例外のアンワインド中にデストラクターが呼び出される場合、トランザクションがロールバックされ、閉じられました。

##  <a name="catltransactionmanager"></a>  CAtlTransactionManager

CAtlTransactionManager コンス トラクターです。

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>パラメーター

*bFallback*  
TRUE は、フォールバックのサポートを示します。 トランザクション処理された関数が失敗した場合、クラスは自動的に「非トランザクション」関数を呼び出します。 FALSE は、「予備」の呼び出しがないことを示します。

*bAutoCreateTransaction*  
TRUE は、コンス トラクターでトランザクション ハンドラーが自動的に作成されたことを示します。 FALSE ではないことを示します。

### <a name="remarks"></a>Remarks

##  <a name="close"></a>  閉じる

トランザクション ハンドルを閉じます。

```
inline BOOL Close();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`CloseHandle`関数。 メソッドは、デストラクターで自動的に呼び出されます。

##  <a name="commit"></a>  コミット

トランザクションをコミットすることを要求します。

```
inline BOOL Commit();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`CommitTransaction`関数。 メソッドは、デストラクターで自動的に呼び出されます。

##  <a name="create"></a>  作成します。

トランザクション ハンドルを作成します。

```
inline BOOL Create();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`CreateTransaction`関数。 チェックしてください。

##  <a name="createfile"></a>  CreateFile

作成するか、ファイル、ファイル ストリーム、またはトランザクション処理された操作とディレクトリを開きます。

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

*lpFileName*  
作成または開くオブジェクトの名前。

*dwDesiredAccess*  
読み取り、書き込み、またはどちらも、両方 (ゼロ) としてまとめることができるオブジェクトへのアクセス。 最もよく使用される値は、GENERIC_READ、GENERIC_WRITE、またはその両方: GENERIC_READ &#124; GENERIC_WRITE します。

*dwShareMode*  
読み取り、書き込み、両方が、削除、または、これらのすべてのオブジェクトの共有モード: FILE_SHARE_DELETE、FILE_SHARE_READ、FILE_SHARE_WRITE は 0。

*lpSecurityAttributes*  
オプションのセキュリティ記述子を含み、また、返されたハンドルを子プロセスに継承できるかどうかを判断します SECURITY_ATTRIBUTES 構造体へのポインター。 パラメーターは、NULL にすることができます。

*dwCreationDisposition*  
ファイルが存在し、存在しないを実行するアクション。 このパラメーターは、組み合わせることはできません、次の値のいずれかを指定する必要があります: CREATE_ALWAYS、CREATE_NEW、OPEN_ALWAYS、OPEN_EXISTING の場合、または TRUNCATE_EXISTING します。

*dwFlagsAndAttributes*  
ファイルの属性とフラグ。 このパラメーターは、使用可能なファイル属性 (FILE_ATTRIBUTE_ *) の任意の組み合わせを含めることができます。 その他のすべてのファイル属性は、FILE_ATTRIBUTE_NORMAL をオーバーライドします。 このパラメーターは、フラグの組み合わせを含めることも (file_flag _\*) バッファリング動作の制御、アクセス モード、およびその他の特殊なフラグ。 これらを組み合わせて、任意 FILE_ATTRIBUTE_ で\*値。

*hTemplateFile*  
GENERIC_READ アクセス権を持つテンプレート ファイルに有効なハンドル。 テンプレート ファイルは、ファイルの属性と作成されるファイルの拡張属性を提供します。 このパラメーターは、NULL を指定できます。

### <a name="return-value"></a>戻り値

オブジェクトへのアクセスに使用できるハンドルを返します。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`CreateFileTransacted`関数。

##  <a name="deletefile"></a>  DeleteFile

トランザクション処理された操作として、既存のファイルを削除します。

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>パラメーター

*lpFileName*  
削除するファイルの名前。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`DeleteFileTransacted`関数。

##  <a name="findfirstfile"></a>  FindFirstFile

トランザクション処理された操作としては、ディレクトリのファイルまたはサブディレクトリを検索します。

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>パラメーター

*lpFileName*  
ディレクトリまたはパス、およびファイル名を検索します。 このパラメーターは、アスタリスク (*) や疑問符 () などのワイルドカード文字を含めることができます。

*pNextInfo*  
見つかったファイルまたはサブディレクトリに関する情報を受け取る WIN32_FIND_DATA 構造体へのポインター。

### <a name="return-value"></a>戻り値

戻り値が後続の呼び出しで使用される検索のハンドルには、関数が成功すると、`FindNextFile`または`FindClose`します。 または関数は、失敗するファイルの検索文字列からの検索に失敗したかどうか、 *lpFileName*パラメーター、戻り値は、INVALID_HANDLE_VALUE です。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`FindFirstFileTransacted`関数。

##  <a name="getfileattributes"></a>  GetFileAttributes

トランザクション処理された操作として指定したファイルまたはディレクトリのファイル システム属性を取得します。

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>パラメーター

*lpFileName*  
ファイルまたはディレクトリの名前。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`GetFileAttributesTransacted`関数。

##  <a name="getfileattributesex"></a>  GetFileAttributesEx

トランザクション処理された操作として指定したファイルまたはディレクトリのファイル システム属性を取得します。

```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>パラメーター

*lpFileName*  
ファイルまたはディレクトリの名前。

*fInfoLevelId*  
取得する属性の情報のレベル。

*lpFileInformation*  
属性の情報を受け取るバッファーへのポインター。 このバッファーに格納されている属性情報の種類の値によって決まります*fInfoLevelId*します。 場合、 *fInfoLevelId*パラメーターが GetFileExInfoStandard し、このパラメーター WIN32_FILE_ATTRIBUTE_DATA 構造体を指します。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`GetFileAttributesTransacted`関数。

##  <a name="gethandle"></a>  このインターフェイスの GetHandle

トランザクション ハンドルを返します。

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>戻り値

クラスのトランザクション ハンドルを返します。 場合 NULL を返します、`CAtlTransactionManager`ハンドルにアタッチされていません。

### <a name="remarks"></a>Remarks

##  <a name="isfallback"></a>  IsFallback

フォールバックの呼び出しが有効になっているかどうかを判断します。

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>戻り値

TRUE を返しますが、クラスのサポートのフォールバック呼び出しです。 FALSE それ以外の場合。

### <a name="remarks"></a>Remarks

##  <a name="m_bfallback"></a>  m_bFallback

TRUE の場合、フォールバックがサポートされています。FALSE それ以外の場合。

```
BOOL m_bFallback;
```

### <a name="remarks"></a>Remarks

##  <a name="m_htransaction"></a>  m_hTransaction

トランザクションのハンドルです。

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>Remarks

##  <a name="movefile"></a>  MoveFile

既存のファイルまたはトランザクション処理された操作として、その子を含む、ディレクトリに移動します。

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>パラメーター

*lpOldFileName*  
既存のファイルまたはローカル コンピューター上のディレクトリの現在の名前。

*lpNewFileName*  
ファイルまたはディレクトリの新しい名前。 この名前がまだ存在しない必要があります。 別のファイル システムまたはドライブに新しいファイルがあります。 新しいディレクトリは、同じドライブ上にある必要があります。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`MoveFileTransacted`関数。

##  <a name="regcreatekeyex"></a>  RegCreateKeyEx

指定されたレジストリ キーを作成し、トランザクションに関連付けます。 キーが既に存在する場合は、関数が開きます。

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

*hKey*  
開いているレジストリ キーへのハンドル。

*いったん*  
この関数を開くか作成するサブキーの名前。

*dwReserved*  
このパラメーターは予約されており、0 にする必要があります。

*lpClass*  
このキーのユーザー定義のクラス。 このパラメーターは無視できます。 このパラメーターは、NULL を指定できます。

*dwOptions*  
このパラメーターは、次の値のいずれかを指定できます: REG_OPTION_BACKUP_RESTORE、REG_OPTION_NON_VOLATILE、または REG_OPTION_VOLATILE します。

*samDesired*  
キーのアクセス権を指定するマスク。

*lpSecurityAttributes*  
子プロセスが、返されたハンドルを継承できるかどうかを決定する SECURITY_ATTRIBUTES 構造体へのポインター。 場合*lpSecurityAttributes*が null の場合、ハンドルを継承することはできません。

*phkResult*  
開くか、作成したキーを識別するハンドルを受け取る変数へのポインター。 キーが定義済みのレジストリ キーの 1 つでない場合は、呼び出し、`RegCloseKey`ハンドルの使用が完了した後に機能します。

*lpdwDisposition*  
廃棄値は次のいずれかを受け取る変数へのポインター: ポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は、ERROR_SUCCESS を返します。 関数が失敗した場合は、Winerror.h で定義されている 0 以外のエラー コードは、戻り値。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`RegCreateKeyTransacted`関数。

##  <a name="regdeletekey"></a>  RegDeleteKey

トランザクション処理された操作として、レジストリの指定したプラットフォームに固有のビューからサブキーとその値を削除します。

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*hKey*|開いているレジストリ キーへのハンドル。|
|*いったん*|削除するキーの名前。|

### <a name="return-value"></a>戻り値

関数が成功した場合は、ERROR_SUCCESS を返します。 関数が失敗した場合は、Winerror.h で定義されている 0 以外のエラー コードは、戻り値。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`RegDeleteKeyTransacted`関数。

##  <a name="regopenkeyex"></a>  RegOpenKeyEx

指定されたレジストリ キーを開き、トランザクションに関連付けます。

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>パラメーター

*hKey*  
開いているレジストリ キーへのハンドル。

*いったん*  
開かれているレジストリ サブキーの名前。

*ulOptions*  
このパラメーターは予約されており、0 にする必要があります。

*samDesired*  
キーのアクセス権を指定するマスク。

*phkResult*  
開くか、作成したキーを識別するハンドルを受け取る変数へのポインター。 キーが定義済みのレジストリ キーの 1 つでない場合は、呼び出し、`RegCloseKey`ハンドルの使用が完了した後に機能します。

### <a name="return-value"></a>戻り値

関数が成功した場合は、ERROR_SUCCESS を返します。 戻り値は、0 以外のエラー コードを Winerror.h で定義されている、関数が失敗した場合、します。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`RegOpenKeyTransacted`関数。

##  <a name="rollback"></a>  ロールバック

トランザクションをロールバックするように要求します。

```
inline BOOL Rollback();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`RollbackTransaction`関数。

##  <a name="setfileattributes"></a>  SetFileAttributes

トランザクション処理された操作として、ファイルまたはディレクトリの属性を設定します。

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>パラメーター

*lpFileName*  
ファイルまたはディレクトリの名前。

*dwAttributes*  
ファイルに設定するファイル属性。 詳細については、次を参照してください。 [SetFileAttributesTransacted](/windows/desktop/api/winbase/nf-winbase-setfileattributestransacteda)します。

### <a name="remarks"></a>Remarks

このラッパーの呼び出し、`SetFileAttributesTransacted`関数。

## <a name="see-also"></a>関連項目

[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
