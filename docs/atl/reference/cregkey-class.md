---
title: クラスを指定します。
ms.date: 11/04/2016
f1_keywords:
- CRegKey
- ATLBASE/ATL::CRegKey
- ATLBASE/ATL::CRegKey::CRegKey
- ATLBASE/ATL::CRegKey::Attach
- ATLBASE/ATL::CRegKey::Close
- ATLBASE/ATL::CRegKey::Create
- ATLBASE/ATL::CRegKey::DeleteSubKey
- ATLBASE/ATL::CRegKey::DeleteValue
- ATLBASE/ATL::CRegKey::Detach
- ATLBASE/ATL::CRegKey::EnumKey
- ATLBASE/ATL::CRegKey::Flush
- ATLBASE/ATL::CRegKey::GetKeySecurity
- ATLBASE/ATL::CRegKey::NotifyChangeKeyValue
- ATLBASE/ATL::CRegKey::Open
- ATLBASE/ATL::CRegKey::QueryBinaryValue
- ATLBASE/ATL::CRegKey::QueryDWORDValue
- ATLBASE/ATL::CRegKey::QueryGUIDValue
- ATLBASE/ATL::CRegKey::QueryMultiStringValue
- ATLBASE/ATL::CRegKey::QueryQWORDValue
- ATLBASE/ATL::CRegKey::QueryStringValue
- ATLBASE/ATL::CRegKey::QueryValue
- ATLBASE/ATL::CRegKey::RecurseDeleteKey
- ATLBASE/ATL::CRegKey::SetBinaryValue
- ATLBASE/ATL::CRegKey::SetDWORDValue
- ATLBASE/ATL::CRegKey::SetGUIDValue
- ATLBASE/ATL::CRegKey::SetKeySecurity
- ATLBASE/ATL::CRegKey::SetKeyValue
- ATLBASE/ATL::CRegKey::SetMultiStringValue
- ATLBASE/ATL::CRegKey::SetQWORDValue
- ATLBASE/ATL::CRegKey::SetStringValue
- ATLBASE/ATL::CRegKey::SetValue
- ATLBASE/ATL::CRegKey::m_hKey
- ATLBASE/ATL::CRegKey::m_pTM
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
ms.openlocfilehash: d3bdb2e7c3ab0ef56ef7f6fba5d43f1ba0bb7fc6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746512"
---
# <a name="cregkey-class"></a>クラスを指定します。

このクラスは、システム レジストリのエントリを操作するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CRegKey
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クレキー::CRegKey](#cregkey)|コンストラクターです。|
|[キー::~CRegキー](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRegKey::添付](#attach)|m_hKey メンバー ハンドルを に設定して`CRegKey`、HKEY[m_hKey](#m_hkey)をオブジェクトにアタッチ`hKey`します。|
|[クレジキー::閉じる](#close)|[m_hKey](#m_hkey)メンバ ハンドルを解放し、NULL に設定します。|
|[CRegKey::作成](#create)|のサブキーとして存在しない場合、指定したキーを作成`hKeyParent`します。|
|[:Dエレテサブキー](#deletesubkey)|指定したキーをレジストリから削除します。|
|[:Dエレテバリュー](#deletevalue)|値フィールドを[m_hKey](#m_hkey)から削除します。|
|[クレキー::Dエタッハ](#detach)|m_hKey メンバー ハンドルをオブジェクトからデタッチし、NULL`m_hKey`に設定します。 [m_hKey](#m_hkey) `CRegKey`|
|[キー::列挙キー](#enumkey)|開いているレジストリ キーのサブキーを列挙します。|
|[クレジキー::フラッシュ](#flush)|開いているレジストリ キーのすべての属性をレジストリに書き込みます。|
|[キー::ゲットキーセキュリティ](#getkeysecurity)|開いているレジストリ キーを保護するセキュリティ記述子のコピーを取得します。|
|[キー::キーの値を変更します。](#notifychangekeyvalue)|このメソッドは、開いているレジストリ キーの属性または内容の変更を呼び出し元に通知します。|
|[CRegKey::オープン](#open)|指定したキーを開き、このキーのハンドル[m_hKey](#m_hkey)設定します。|
|[次の値を返します。](#querybinaryvalue)|指定した値名のバイナリ データを取得します。|
|[キー::クエリドワードバリュー](#querydwordvalue)|指定した値の名前の DWORD データを取得します。|
|[キー:クエリGUID 値](#queryguidvalue)|指定した値の名前の GUID データを取得します。|
|[次の文字列値](#querymultistringvalue)|指定した値名の複数文字列データを取得します。|
|[キー::クエリQワードバリュー](#queryqwordvalue)|指定した値名の QWORD データを取得します。|
|[次の文字列を指定します。](#querystringvalue)|指定した値名の文字列データを取得します。|
|[クエリキー::クエリ値](#queryvalue)|m_hKeyの指定された値フィールドのデータを[取得します。](#m_hkey) このメソッドの以前のバージョンはサポートされなくなり、ATL_DEPRECATEDとしてマークされています。|
|[キー::再呪い削除キー](#recursedeletekey)|指定したキーをレジストリから削除し、サブキーを明示的に削除します。|
|[を設定します。](#setbinaryvalue)|レジストリ キーのバイナリ値を設定します。|
|[キー::セットドワードバリュー](#setdwordvalue)|レジストリ キーの DWORD 値を設定します。|
|[キー::セットGUID 値](#setguidvalue)|レジストリ キーの GUID 値を設定します。|
|[キー::セットキーセキュリティ](#setkeysecurity)|レジストリ キーのセキュリティを設定します。|
|[キー::セットキー値](#setkeyvalue)|指定したキーの指定した値フィールドにデータを格納します。|
|[を設定します。](#setmultistringvalue)|レジストリ キーの複数文字列値を設定します。|
|[キー::セットクワードバリュー](#setqwordvalue)|レジストリ キーの QWORD 値を設定します。|
|[キー::セット文字列値](#setstringvalue)|レジストリ キーの文字列値を設定します。|
|[キー::セットバリュー](#setvalue)|m_hKeyの指定した値フィールドにデータを[格納します。](#m_hkey) このメソッドの以前のバージョンはサポートされなくなり、ATL_DEPRECATEDとしてマークされています。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[キー::オペレーター HKEY](#operator_hkey)|オブジェクトを`CRegKey`HKEY に変換します。|
|[キー::演算子 =](#operator_eq)|代入演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[クレキー::m_hKey](#m_hkey)|オブジェクトに関連付けられたレジストリ キーのハンドル`CRegKey`を格納します。|
|[クレキー::m_pTM](#m_ptm)|オブジェクトへの`CAtlTransactionManager`ポインタ|

## <a name="remarks"></a>解説

`CRegKey`には、システム レジストリ内のキーと値を作成および削除するためのメソッドが用意されています。 レジストリには、ソフトウェア のバージョン番号、インストールされているハードウェアの論理対物理マッピング、COM オブジェクトなど、システム コンポーネントのインストール固有の定義セットが含まれています。

`CRegKey`は、特定のマシンのシステム レジストリへのプログラミング インターフェイスを提供します。 たとえば、特定のレジストリ キーを開くには、`CRegKey::Open`を呼び出します。 データ値を取得または変更するには、`CRegKey::QueryValue`または`CRegKey::SetValue`をそれぞれ呼び出します。 キーを閉じるには、`CRegKey::Close`を呼び出します。

キーを閉じると、そのレジストリ データがハード ディスクに書き込まれます ( フラッシュされます ) 。 このプロセスには数分かかる場合があります。 アプリケーションでハード ディスクにレジストリ データを明示的に書き込む必要がある場合は[、RegFlushKey](/windows/win32/api/winreg/nf-winreg-regflushkey) Win32 関数を呼び出すことができます。 ただし、`RegFlushKey`多くのシステム リソースを使用するため、必要な場合にのみ呼び出す必要があります。

> [!IMPORTANT]
> 呼び出し元がレジストリの場所を指定できるようにするメソッドは、信頼できないデータを読み取る可能性があります。 [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)を使用するメソッドは、この関数が明示的に NULL で終了した文字列を処理しないことを考慮する必要があります。 両方の条件は、呼び出し元のコードによってチェックする必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="cregkeyattach"></a><a name="attach"></a>CRegKey::添付

[m_hKey](#m_hkey)メンバ ハンドルを*hKey*`CRegKey`に設定して、HKEY をオブジェクトにアタッチします。

```cpp
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>パラメーター

*Hkey*<br/>
レジストリ キーのハンドル。

### <a name="remarks"></a>解説

`Attach`は NULL`m_hKey`以外の場合にアサートします。

## <a name="cregkeyclose"></a><a name="close"></a>クレジキー::閉じる

[m_hKey](#m_hkey)メンバ ハンドルを解放し、NULL に設定します。

```
LONG Close() throw();
```

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESSを返します。それ以外の場合はエラー値を返します。

## <a name="cregkeycreate"></a><a name="create"></a>CRegKey::作成

指定したキーが*hKeyParent*のサブキーとして存在しない場合は、このメソッドを呼び出して、キーを作成します。

```
LONG Create(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPTSTR lpszClass = REG_NONE,
    DWORD dwOptions = REG_OPTION_NON_VOLATILE,
    REGSAM samDesired = KEY_READ | KEY_WRITE,
    LPSECURITY_ATTRIBUTES lpSecAttr = NULL,
    LPDWORD lpdwDisposition = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*キーペアレント*<br/>
開いているキーのハンドル。

*名前を変更します。*<br/>
作成または開くキーの名前を指定します。 この名前は *、hKeyParent*のサブキーである必要があります。

*クラス*<br/>
作成または開くキーのクラスを指定します。 既定値はREG_NONEです。

*dw オプション*<br/>
キーのオプション。 既定値は REG_OPTION_NON_VOLATILE です。 使用可能な値と説明の一覧については、Windows SDK[の「RegCreateKeyEx」](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw)を参照してください。

*サム必要に応じて*<br/>
キーのセキュリティ アクセス。 既定値は&#124;KEY_WRITEKEY_READ。 使用可能な値と説明の一覧については、を`RegCreateKeyEx`参照してください。

*lpSecAttr*<br/>
キーのハンドルを子プロセスが継承できるかどうかを示す[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体へのポインター。 既定では、このパラメーターは NULL です (つまり、ハンドルを継承することはできません)。

*lpdwディスポジション*<br/>
[アウト]NULL 以外の場合は、キーが存在せず、作成されたREG_CREATED_NEW_KEY、またはREG_OPENED_EXISTING_KEY (キーが存在し、開かれた場合) のいずれかを取得します。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESSを返し、キーを開きます。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

`Create`[m_hKey](#m_hkey)メンバーをこのキーのハンドルに設定します。

## <a name="cregkeycregkey"></a><a name="cregkey"></a>クレキー::CRegKey

コンストラクターです。

```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
`CRegKey` オブジェクトへの参照です。

*Hkey*<br/>
レジストリ キーへのハンドル。

*Ptm*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="remarks"></a>解説

新しい `CRegKey` オブジェクトを作成します。 オブジェクトは、既存`CRegKey`のオブジェクトから作成することも、レジストリ キーへのハンドルから作成することもできます。

## <a name="cregkeycregkey"></a><a name="dtor"></a>キー::~CRegキー

デストラクターです。

```
~CRegKey() throw();
```

### <a name="remarks"></a>解説

デストラクターがリリース`m_hKey`されます。

## <a name="cregkeydeletesubkey"></a><a name="deletesubkey"></a>:Dエレテサブキー

指定したキーをレジストリから削除します。

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>パラメーター

*サブキー*<br/>
削除するキーの名前を指定します。 この名前は、 のサブキー [m_hKey](#m_hkey)する必要があります。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESSを返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

`DeleteSubKey`サブキーを持たないキーのみを削除できます。 キーにサブキーがある場合は、代わりに[RecurseDeleteKey を](#recursedeletekey)呼び出します。

## <a name="cregkeydeletevalue"></a><a name="deletevalue"></a>:Dエレテバリュー

値フィールドを[m_hKey](#m_hkey)から削除します。

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>パラメーター

*値*<br/>
削除する値フィールドを指定します。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESSを返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

## <a name="cregkeydetach"></a><a name="detach"></a>クレキー::Dエタッハ

m_hKey メンバー ハンドルをオブジェクトからデタッチし、NULL`m_hKey`に設定します。 [m_hKey](#m_hkey) `CRegKey`

```
HKEY Detach() throw();
```

### <a name="return-value"></a>戻り値

`CRegKey`オブジェクトに関連付けられている HKEY。

## <a name="cregkeyenumkey"></a><a name="enumkey"></a>キー::列挙キー

開いているレジストリ キーのサブキーを列挙します。

```
LONG EnumKey(
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
サブキー インデックス。 このパラメータは、最初の呼び出しでは 0 にする必要があり、その後の呼び出しではインクリメントされます。

*名前*<br/>
終了 NULL 文字を含む、サブキーの名前を受け取るバッファーへのポインター。 完全なキー階層ではなく、サブキーの名前だけがバッファーにコピーされます。

*長さ*<br/>
*pszName*パラメーターで指定されたバッファーのサイズを TCHARs で指定する変数へのポインター。 このサイズには、終端の NULL 文字を含める必要があります。 メソッドが戻るとき *、pnNameLength*によって指される変数には、バッファーに格納されている文字数が含まれます。 返されるカウントには、終端の NULL 文字は含まれません。

*書き込み時間*<br/>
列挙されたサブキーが最後に書き込まれた時刻を受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

サブキーを列挙するには、インデックス`CRegKey::EnumKey`を 0 で呼び出します。 インデックス値をインクリメントし、メソッドがERROR_NO_MORE_ITEMSを返すまで繰り返します。 詳細については、Windows SDK[の「レジストリキー」](/windows/win32/api/winreg/nf-winreg-regenumkeyexw)を参照してください。

## <a name="cregkeyflush"></a><a name="flush"></a>クレジキー::フラッシュ

開いているレジストリ キーのすべての属性をレジストリに書き込みます。

```
LONG Flush() throw();
```

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

詳細については、Windows SDK[の「レグ列挙フラッシュ](/windows/win32/api/winreg/nf-winreg-regflushkey)」を参照してください。

## <a name="cregkeygetkeysecurity"></a><a name="getkeysecurity"></a>キー::ゲットキーセキュリティ

開いているレジストリ キーを保護するセキュリティ記述子のコピーを取得します。

```
LONG GetKeySecurity(
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>パラメーター

*Si*<br/>
要求されたセキュリティ情報を示す[SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information)値。

*Psd*<br/>
要求されたセキュリティ記述子のコピーを受け取るバッファーへのポインター。

*pn バイト*<br/>
*psd*が指すバッファのサイズ (バイト単位)

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 メソッドが失敗した場合、戻り値は、WINERROR で定義されている 0 以外のエラー コードです。H。

### <a name="remarks"></a>解説

詳細については、「[レジストリ キー セキュリティ](/windows/win32/api/winreg/nf-winreg-reggetkeysecurity)」を参照してください。

## <a name="cregkeym_hkey"></a><a name="m_hkey"></a>クレキー::m_hKey

オブジェクトに関連付けられたレジストリ キーのハンドル`CRegKey`を格納します。

```
HKEY m_hKey;
```

## <a name="cregkeym_ptm"></a><a name="m_ptm"></a>クレキー::m_pTM

`CAtlTransactionManager`オブジェクトへのポインター。

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>解説

## <a name="cregkeynotifychangekeyvalue"></a><a name="notifychangekeyvalue"></a>キー::キーの値を変更します。

このメソッドは、開いているレジストリ キーの属性または内容の変更を呼び出し元に通知します。

```
LONG NotifyChangeKeyValue(
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```

### <a name="parameters"></a>パラメーター

*ビウォッチサブツリー*<br/>
指定したキーとそのすべてのサブキーの変更を報告するか、指定したキーのみに変更を報告するかを示すフラグを指定します。 このパラメーターが TRUE の場合、メソッドはキーとそのサブキーの変更を報告します。 パラメータが FALSE の場合、メソッドはキー内の変更のみを報告します。

*をフィルター処理します。*<br/>
報告する変更を制御するフラグのセットを指定します。 このパラメーターは、次の値の組み合わせにすることができます。

|値|意味|
|-----------|-------------|
|REG_NOTIFY_CHANGE_NAME|サブキーが追加または削除された場合に、呼び出し元に通知します。|
|REG_NOTIFY_CHANGE_ATTRIBUTES|セキュリティ記述子情報など、キーの属性に対する変更を呼び出し元に通知します。|
|REG_NOTIFY_CHANGE_LAST_SET|キーの値に対する変更を呼び出し元に通知します。 これには、値の追加や削除、既存の値の変更などがあります。|
|REG_NOTIFY_CHANGE_SECURITY|キーのセキュリティ記述子に対する変更を呼び出し元に通知します。|

*Hevent*<br/>
イベントに対するハンドル。 *bAsync*パラメーターが TRUE の場合、メソッドはすぐに戻り、このイベントを通知することによって変更が報告されます。 *bAsync*が FALSE の場合 *、h イベント*は無視されます。

*同期*<br/>
メソッドが変更を報告する方法を示すフラグを指定します。 このパラメーターが TRUE の場合、メソッドはすぐに戻り、指定されたイベントを通知することによって変更を報告します。 このパラメーターが FALSE の場合、メソッドは変更が発生するまで戻りません。 *hEvent が*有効なイベントを指定しない場合 *、bAsync*パラメーターを TRUE にすることはできません。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

> [!NOTE]
> このメソッドは、指定されたキーが削除された場合、呼び出し元に通知しません。

詳細とサンプル プログラムについては、「[キー値の変更」](/windows/win32/api/winreg/nf-winreg-regnotifychangekeyvalue)を参照してください。

## <a name="cregkeyopen"></a><a name="open"></a>CRegKey::オープン

指定したキーを開き、このキーのハンドル[m_hKey](#m_hkey)設定します。

```
LONG Open(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```

### <a name="parameters"></a>パラメーター

*キーペアレント*<br/>
開いているキーのハンドル。

*名前を変更します。*<br/>
作成または開くキーの名前を指定します。 この名前は *、hKeyParent*のサブキーである必要があります。

*サム必要に応じて*<br/>
キーのセキュリティ アクセス。 既定値は KEY_ALL_ACCESS です。 使用可能な値と説明の一覧については、Windows SDK[の「RegCreateKeyEx」](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw)を参照してください。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESSを返します。それ以外の場合は、WINERROR で定義された 0 以外のエラー値。H。

### <a name="remarks"></a>解説

*lpszKeyName*パラメーターが NULL または空の文字列を指`Open`している場合は *、hKeyParent*で識別されるキーの新しいハンドルを開きますが、以前に開いたハンドルは閉じられません。

[CRegKey::Create](#create)と`Open`は異なり、指定されたキーが存在しない場合は作成されません。

## <a name="cregkeyoperator-hkey"></a><a name="operator_hkey"></a>キー::オペレーター HKEY

オブジェクトを`CRegKey`HKEY に変換します。

```
operator HKEY() const throw();
```

## <a name="cregkeyoperator-"></a><a name="operator_eq"></a>キー::演算子 =

代入演算子。

```
CRegKey& operator= (CRegKey& key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
コピーするキー。

### <a name="return-value"></a>戻り値

新しいキーへの参照を返します。

### <a name="remarks"></a>解説

この演算子は、現在のオブジェクトから*キー*をデタッチし、代`CRegKey`わりにオブジェクトに割り当てます。

## <a name="cregkeyquerybinaryvalue"></a><a name="querybinaryvalue"></a>次の値を返します。

指定した値名のバイナリ データを取得します。

```
LONG QueryBinaryValue(
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
照会する値の名前を含む null で終わる文字列へのポインター。

*pValue*<br/>
値のデータを受け取るバッファーへのポインター。

*pn バイト*<br/>
*pValue*パラメーターによって指されるバッファーのサイズをバイト単位で指定する変数へのポインター。 メソッドが返されるときに、この変数には、バッファーにコピーされるデータのサイズが格納されます。

### <a name="return-value"></a>戻り値

メソッドが成功すると、ERROR_SUCCESSが返されます。 メソッドが値の読み取りに失敗した場合、WINERROR で定義された 0 以外のエラー コードを返します。H。 参照されるデータがREG_BINARY型でない場合は、ERROR_INVALID_DATAが返されます。

### <a name="remarks"></a>解説

このメソッドは、データ`RegQueryValueEx`の正しい型が返されることを使用し、確認します。 詳細については、[次を](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)参照してください。

> [!IMPORTANT]
> このメソッドを使用すると、呼び出し元は、信頼できないデータを読み取る可能性のあるレジストリの場所を指定できます。 また、このメソッドで使用される[RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)関数は、NULL で終了した文字列を明示的に処理しません。 両方の条件は、呼び出し元のコードによってチェックする必要があります。

## <a name="cregkeyquerydwordvalue"></a><a name="querydwordvalue"></a>キー::クエリドワードバリュー

指定した値の名前の DWORD データを取得します。

```
LONG QueryDWORDValue(
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
照会する値の名前を含む null で終わる文字列へのポインター。

*値*<br/>
DWORD を受け取るバッファーへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功すると、ERROR_SUCCESSが返されます。 メソッドが値の読み取りに失敗した場合、WINERROR で定義された 0 以外のエラー コードを返します。H。 参照されるデータが型REG_DWORDでない場合は、ERROR_INVALID_DATAが返されます。

### <a name="remarks"></a>解説

このメソッドは、データ`RegQueryValueEx`の正しい型が返されることを使用し、確認します。 詳細については、[次を](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)参照してください。

> [!IMPORTANT]
> このメソッドを使用すると、呼び出し元は、信頼できないデータを読み取る可能性のあるレジストリの場所を指定できます。 また、このメソッドで使用される[RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)関数は、NULL で終了した文字列を明示的に処理しません。 両方の条件は、呼び出し元のコードによってチェックする必要があります。

## <a name="cregkeyqueryguidvalue"></a><a name="queryguidvalue"></a>キー:クエリGUID 値

指定した値の名前の GUID データを取得します。

```
LONG QueryGUIDValue(
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
照会する値の名前を含む null で終わる文字列へのポインター。

*guid値*<br/>
GUID を受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功すると、ERROR_SUCCESSが返されます。 メソッドが値の読み取りに失敗した場合、WINERROR で定義された 0 以外のエラー コードを返します。H。 参照されるデータが有効な GUID でない場合は、ERROR_INVALID_DATAが返されます。

### <a name="remarks"></a>解説

このメソッドは、文字列`CRegKey::QueryStringValue`を使用して[、CLSIDFromString](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)を使用して GUID に変換します。

> [!IMPORTANT]
> このメソッドを使用すると、呼び出し元は、信頼できないデータを読み取る可能性のあるレジストリの場所を指定できます。

## <a name="cregkeyquerymultistringvalue"></a><a name="querymultistringvalue"></a>次の文字列値

指定した値名の複数文字列データを取得します。

```
LONG QueryMultiStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
照会する値の名前を含む null で終わる文字列へのポインター。

*値*<br/>
マルチストリング データを受け取るバッファーへのポインター。 複数文字列は、NULL で終わる文字列の配列で、2 つの NULL 文字で終わるものです。

*pnChars*<br/>
*pszValue*が指すバッファのサイズ (TCHARs 単位) です。 メソッドが返されるときに *、pnChars*には、取得した複数文字列のサイズ (終端の null 文字を含む) が TCHARs で格納されます。

### <a name="return-value"></a>戻り値

メソッドが成功すると、ERROR_SUCCESSが返されます。 メソッドが値の読み取りに失敗した場合、WINERROR で定義された 0 以外のエラー コードを返します。H。 参照されるデータがREG_MULTI_SZ型でない場合は、ERROR_INVALID_DATAが返されます。

### <a name="remarks"></a>解説

このメソッドは、データ`RegQueryValueEx`の正しい型が返されることを使用し、確認します。 詳細については、[次を](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)参照してください。

> [!IMPORTANT]
> このメソッドを使用すると、呼び出し元は、信頼できないデータを読み取る可能性のあるレジストリの場所を指定できます。 また、このメソッドで使用される[RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)関数は、NULL で終了した文字列を明示的に処理しません。 両方の条件は、呼び出し元のコードによってチェックする必要があります。

## <a name="cregkeyqueryqwordvalue"></a><a name="queryqwordvalue"></a>キー::クエリQワードバリュー

指定した値名の QWORD データを取得します。

```
LONG QueryQWORDValue(
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
照会する値の名前を含む null で終わる文字列へのポインター。

*値*<br/>
QWORD を受け取るバッファーへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功すると、ERROR_SUCCESSが返されます。 メソッドが値の読み取りに失敗した場合、WINERROR で定義された 0 以外のエラー コードを返します。H。 参照されるデータがREG_QWORD型でない場合は、ERROR_INVALID_DATAが返されます。

### <a name="remarks"></a>解説

このメソッドは、データ`RegQueryValueEx`の正しい型が返されることを使用し、確認します。 詳細については、[次を](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)参照してください。

> [!IMPORTANT]
> このメソッドを使用すると、呼び出し元は、信頼できないデータを読み取る可能性のあるレジストリの場所を指定できます。 また、このメソッドで使用される[RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)関数は、NULL で終了した文字列を明示的に処理しません。 両方の条件は、呼び出し元のコードによってチェックする必要があります。

## <a name="cregkeyquerystringvalue"></a><a name="querystringvalue"></a>次の文字列を指定します。

指定した値名の文字列データを取得します。

```
LONG QueryStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
照会する値の名前を含む null で終わる文字列へのポインター。

*値*<br/>
文字列データを受け取るバッファーへのポインター。

*pnChars*<br/>
*pszValue*が指すバッファのサイズ (TCHARs 単位) です。 メソッドが返されるときに *、pnChars*には、末尾の null 文字を含む、取得した文字列の TCHAR でのサイズが含まれています。

### <a name="return-value"></a>戻り値

メソッドが成功すると、ERROR_SUCCESSが返されます。 メソッドが値の読み取りに失敗した場合、WINERROR で定義された 0 以外のエラー コードを返します。H。 参照されるデータがREG_SZ型でない場合は、ERROR_INVALID_DATAが返されます。 メソッドがERROR_MORE_DATAを返す場合 *、pnChars は*0 に等しく、必要なバッファ サイズ (バイト単位) ではありません。

### <a name="remarks"></a>解説

このメソッドは、データ`RegQueryValueEx`の正しい型が返されることを使用し、確認します。 詳細については、[次を](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)参照してください。

> [!IMPORTANT]
> このメソッドを使用すると、呼び出し元は、信頼できないデータを読み取る可能性のあるレジストリの場所を指定できます。 また、このメソッドで使用される[RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw)関数は、NULL で終了した文字列を明示的に処理しません。 両方の条件は、呼び出し元のコードによってチェックする必要があります。

## <a name="cregkeyqueryvalue"></a><a name="queryvalue"></a>クエリキー::クエリ値

m_hKeyの指定された値フィールドのデータを[取得します。](#m_hkey) このメソッドの以前のバージョンはサポートされなくなり、ATL_DEPRECATEDとしてマークされています。

```
LONG QueryValue(
    LPCTSTR pszValueName,
    DWORD* pdwType,
    void* pData,
    ULONG* pnBytes) throw();

ATL_DEPRECATED LONG QueryValue(
    DWORD& dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG QueryValue(
    LPTSTR szValue,
    LPCTSTR lpszValueName,
    DWORD* pdwCount);
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
照会する値の名前を含む null で終わる文字列へのポインター。 *pszValueName*が NULL または空の文字列である場合、"" は、キーの名前のない値または既定値の型とデータを取得します (存在する場合)。

*pdw タイプ*<br/>
指定した値に格納されているデータの種類を示すコードを受け取る変数へのポインター。 型コードが必要ない場合 *、pdwType*パラメーターは NULL にすることができます。

*Pdata*<br/>
値のデータを受け取るバッファーへのポインター。 データが不要な場合、このパラメーターは NULL になります。

*pn バイト*<br/>
*pData*パラメーターが指すバッファーのサイズをバイト単位で指定する変数へのポインター。 メソッドが戻るとき、この変数には pData にコピーされるデータのサイズが含*まれます。*

*値*<br/>
値フィールドの数値データ。

*名前を変更します。*<br/>
照会する値フィールドを指定します。

*sz値*<br/>
値フィールドの文字列データ。

*をクリックします。*<br/>
文字列データのサイズ。 この値は、最初は*szValue*バッファーのサイズに設定されます。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESSを返します。それ以外の場合は、WINERROR で定義された 0 以外のエラー コードです。H。

### <a name="remarks"></a>解説

の 2 つの`QueryValue`元のバージョンはサポートされなくなり、ATL_DEPRECATEDとしてマークされています。 これらのフォームが使用されている場合、コンパイラは警告を発行します。

残りのメソッドは、値を呼び出します。

> [!IMPORTANT]
> このメソッドを使用すると、呼び出し元は、信頼できないデータを読み取る可能性のあるレジストリの場所を指定できます。 また、このメソッドで使用される RegQueryValueEx 関数は、NULL で終了した文字列を明示的に処理しません。 両方の条件は、呼び出し元のコードによってチェックする必要があります。

## <a name="cregkeyrecursedeletekey"></a><a name="recursedeletekey"></a>キー::再呪い削除キー

指定したキーをレジストリから削除し、サブキーを明示的に削除します。

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>パラメーター

*キーを指定します。*<br/>
削除するキーの名前を指定します。 この名前は、 のサブキー [m_hKey](#m_hkey)する必要があります。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESSを返します。それ以外の場合は、WINERROR で定義された 0 以外のエラー値。H。

### <a name="remarks"></a>解説

キーにサブキーがある場合は、このメソッドを呼び出してキーを削除する必要があります。

## <a name="cregkeysetbinaryvalue"></a><a name="setbinaryvalue"></a>を設定します。

レジストリ キーのバイナリ値を設定します。

```
LONG SetBinaryValue(
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。

*pValue*<br/>
指定された値名で格納されるデータを格納するバッファーへのポインター。

*Nbytes*<br/>
*pValue*パラメーターによって指される情報のサイズをバイト単位で指定します。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

このメソッドは、レジストリに値を書き込むために[RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw)を使用します。

## <a name="cregkeysetdwordvalue"></a><a name="setdwordvalue"></a>キー::セットドワードバリュー

レジストリ キーの DWORD 値を設定します。

```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。

*値*<br/>
指定された値名で格納される DWORD データ。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

このメソッドは、レジストリに値を書き込むために[RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw)を使用します。

## <a name="cregkeysetguidvalue"></a><a name="setguidvalue"></a>キー::セットGUID 値

レジストリ キーの GUID 値を設定します。

```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。

*guid値*<br/>
指定した値名で格納される GUID への参照。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

このメソッドは、GUID`CRegKey::SetStringValue`を[使用して文字列](/windows/win32/api/combaseapi/nf-combaseapi-stringfromguid2)に変換します。

## <a name="cregkeysetkeyvalue"></a><a name="setkeyvalue"></a>キー::セットキー値

指定したキーの指定した値フィールドにデータを格納します。

```
LONG SetKeyValue(
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
作成または開くキーの名前を指定します。 この名前は、 のサブキー [m_hKey](#m_hkey)する必要があります。

*値*<br/>
格納するデータを指定します。 このパラメーターは NULL 以外でなければなりません。

*名前を変更します。*<br/>
設定する値フィールドを指定します。 この名前の値フィールドがキーに存在しない場合は、その値フィールドが追加されます。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESSを返します。それ以外の場合は、WINERROR で定義された 0 以外のエラー コードです。H。

### <a name="remarks"></a>解説

このメソッドを呼び出して *、lpszKeyName*キーを作成または開き *、lpszValue*値フィールドに*lpszValue*データを格納します。

## <a name="cregkeysetkeysecurity"></a><a name="setkeysecurity"></a>キー::セットキーセキュリティ

レジストリ キーのセキュリティを設定します。

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>パラメーター

*Si*<br/>
設定するセキュリティ記述子のコンポーネントを指定します。 値は、次の値の組み合わせにすることができます。

|値|意味|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|キーの随意アクセス制御リスト (DACL) を設定します。 キーにはWRITE_DACアクセス権が必要か、呼び出しプロセスがオブジェクトの所有者である必要があります。|
|GROUP_SECURITY_INFORMATION|キーのプライマリ グループ セキュリティ識別子 (SID) を設定します。 キーにアクセスWRITE_OWNERが必要か、呼び出しプロセスがオブジェクトの所有者である必要があります。|
|OWNER_SECURITY_INFORMATION|キーの所有者 SID を設定します。 キーにアクセスWRITE_OWNER必要がある場合、または呼び出し側プロセスがオブジェクトの所有者であるか、SE_TAKE_OWNERSHIP_NAME特権が有効になっている必要があります。|
|SACL_SECURITY_INFORMATION|キーのシステム アクセス制御リスト (SACL) を設定します。 キーにはアクセスACCESS_SYSTEM_SECURITY必要があります。 このアクセスを取得する適切な方法は、呼び出し元の現在のアクセス トークンでSE_SECURITY_NAME[特権](/windows/win32/secauthz/privileges)を有効にし、ACCESS_SYSTEM_SECURITYアクセス用のハンドルを開き、その特権を無効にすることです。|

*Psd*<br/>
指定したキーに設定するセキュリティ属性を指定する[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

キーのセキュリティ属性を設定します。 詳細については[、「レジストリ キー セキュリティ](/windows/win32/api/winreg/nf-winreg-regsetkeysecurity)」を参照してください。

## <a name="cregkeysetmultistringvalue"></a><a name="setmultistringvalue"></a>を設定します。

レジストリ キーの複数文字列値を設定します。

```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。

*値*<br/>
指定された値名で格納されるマルチストリング データへのポインター。 複数文字列は、NULL で終わる文字列の配列で、2 つの NULL 文字で終わるものです。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

このメソッドは、レジストリに値を書き込むために[RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw)を使用します。

## <a name="cregkeysetqwordvalue"></a><a name="setqwordvalue"></a>キー::セットクワードバリュー

レジストリ キーの QWORD 値を設定します。

```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。

*値*<br/>
指定された値名で保管される QWORD データ。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

このメソッドは、レジストリに値を書き込むために[RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw)を使用します。

## <a name="cregkeysetstringvalue"></a><a name="setstringvalue"></a>キー::セット文字列値

レジストリ キーの文字列値を設定します。

```
LONG SetStringValue(
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。

*値*<br/>
指定された値名で格納される文字列データへのポインター。

*dwタイプ*<br/>
レジストリに書き込む文字列の型。REG_SZ (既定値) または REG_EXPAND_SZ (複数文字列の場合)。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。

### <a name="remarks"></a>解説

このメソッドは、レジストリに値を書き込むために[RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw)を使用します。

## <a name="cregkeysetvalue"></a><a name="setvalue"></a>キー::セットバリュー

m_hKeyの指定した値フィールドにデータを[格納します。](#m_hkey) このメソッドの以前のバージョンはサポートされなくなり、ATL_DEPRECATEDとしてマークされています。

```
LONG SetValue(
    LPCTSTR pszValueName,
    DWORD dwType,
    const void* pValue,
    ULONG nBytes) throw();

static LONG WINAPI SetValue(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL);

ATL_DEPRECATED LONG SetValue(
    DWORD dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG SetValue(
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL,
    bool bMulti = false,
    int nValueLen = -1);
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
設定する値の名前を格納する文字列へのポインター。 この名前の値がキーにまだ存在しない場合、メソッドはそれをキーに追加します。 *pszValueName*が NULL または空の文字列である場合は""" を指定すると、このメソッドはキーの名前のない値または既定値の型とデータを設定します。

*dwタイプ*<br/>
*pValue*パラメーターが指すデータの種類を示すコードを指定します。

*pValue*<br/>
指定された値名で格納されるデータを格納するバッファーへのポインター。

*Nbytes*<br/>
*pValue*パラメーターによって指される情報のサイズをバイト単位で指定します。 データがタイプREG_SZ、REG_EXPAND_SZ、またはREG_MULTI_SZの場合 *、nBytes*には終端の NULL 文字のサイズを含める必要があります。

*キーペアレント*<br/>
開いているキーのハンドル。

*名前を変更します。*<br/>
作成または開くキーの名前を指定します。 この名前は *、hKeyParent*のサブキーである必要があります。

*値*<br/>
格納するデータを指定します。 このパラメーターは NULL 以外でなければなりません。

*名前を変更します。*<br/>
設定する値フィールドを指定します。 この名前の値フィールドがキーに存在しない場合は、その値フィールドが追加されます。

*値*<br/>
格納するデータを指定します。

*bマルチ*<br/>
false の場合、文字列の型がREG_SZを示します。 true の場合、文字列がREG_MULTI_SZ型のマルチストリングであることを示します。

*nバリューレン*<br/>
*bMulti*が true の場合 *、nValueLen*は、文字内の*lpszValue*文字列の長さです。 *bMulti*が false の場合、値 -1 は、メソッドが自動的に長さを計算することを示します。

### <a name="return-value"></a>戻り値

成功した場合は、ERROR_SUCCESSを返します。それ以外の場合は、WINERROR で定義された 0 以外のエラー コードです。H。

### <a name="remarks"></a>解説

の 2 つの`SetValue`元のバージョンはATL_DEPRECATEDとしてマークされ、使用は終了する必要があります。 これらのフォームが使用されている場合、コンパイラは警告を発行します。

3 番目のメソッドは[、値を](/windows/win32/api/winreg/nf-winreg-regsetvalueexw)呼び出します。

## <a name="see-also"></a>関連項目

[DCOM サンプル](../../overview/visual-cpp-samples.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
