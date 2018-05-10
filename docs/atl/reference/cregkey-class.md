---
title: CRegKey クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6daec3347aecaed3ba0aba5dec106d049a6a701
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="cregkey-class"></a>CRegKey クラス
このクラスは、システム レジストリのエントリを操作するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CRegKey
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRegKey::CRegKey](#cregkey)|コンストラクターです。|  
|[CRegKey:: ~ CRegKey](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRegKey::Attach](#attach)|HKEY をアタッチするには、このメソッドを呼び出して、`CRegKey`オブジェクトを設定して、 [m_hKey](#m_hkey)メンバーを識別するハンドル`hKey`です。|  
|[CRegKey::Close](#close)|解放するには、このメソッドを呼び出して、 [m_hKey](#m_hkey)メンバーを処理し、NULL に設定します。|  
|[CRegKey::Create](#create)|サブキーとしてが存在しない場合、指定したキーを作成するには、このメソッドを呼び出す`hKeyParent`です。|  
|[CRegKey::DeleteSubKey](#deletesubkey)|このメソッドを呼び出して、指定したキーをレジストリから削除します。|  
|[CRegKey::DeleteValue](#deletevalue)|値フィールドを削除するには、このメソッドを呼び出す[m_hKey](#m_hkey)です。|  
|[CRegKey::Detach](#detach)|デタッチするには、このメソッドを呼び出して、 [m_hKey](#m_hkey)メンバーのハンドルから、`CRegKey`オブジェクトおよび設定`m_hKey`を NULL にします。|  
|[して](#enumkey)|このメソッドを呼び出して、開いているレジストリ キーのサブキーを列挙します。|  
|[CRegKey::Flush](#flush)|このメソッドを呼び出して、レジストリに書き込むためにすべての開いているレジストリ キーの属性です。|  
|[CRegKey::GetKeySecurity](#getkeysecurity)|開いているレジストリ キーを保護するセキュリティ記述子のコピーを取得するには、このメソッドを呼び出します。|  
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|このメソッドでは、属性または開いているレジストリ キーの内容の変更について、呼び出し元に通知します。|  
|[Cregkey::open](#open)|指定したキーを開きを設定するには、このメソッドを呼び出す[m_hKey](#m_hkey)をこのキーのハンドル。|  
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|指定された値の名前のバイナリ データを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryDWORDValue](#querydwordvalue)|指定された値の名前の DWORD データを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryGUIDValue](#queryguidvalue)|指定された値の名前に GUID データを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|指定された値の名前の複数文字列のデータを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|QWORD データを指定した値の名前を取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryStringValue](#querystringvalue)|指定された値名の文字列データを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryValue](#queryvalue)|指定した値フィールドのデータを取得するには、このメソッドを呼び出す[m_hKey](#m_hkey)です。 このメソッドの以前のバージョンはサポートされなくととしてマークされて**されず**です。|  
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|このメソッドを呼び出して、指定したキーをレジストリから削除し、すべてのサブキーを明示的に削除します。|  
|[CRegKey::SetBinaryValue](#setbinaryvalue)|レジストリ キーのバイナリ値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetDWORDValue](#setdwordvalue)|レジストリ キーの DWORD 値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetGUIDValue](#setguidvalue)|レジストリ キーの GUID 値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetKeySecurity](#setkeysecurity)|レジストリ キーのセキュリティを設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetKeyValue](#setkeyvalue)|指定したキーの指定した値フィールドにデータを格納するには、このメソッドを呼び出します。|  
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|レジストリ キーの複数文字列値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetQWORDValue](#setqwordvalue)|レジストリ キーの QWORD 値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetStringValue](#setstringvalue)|レジストリ キーの文字列値を設定します。|  
|[CRegKey::SetValue](#setvalue)|指定した値フィールドにデータを格納するには、このメソッドを呼び出す[m_hKey](#m_hkey)です。 このメソッドの以前のバージョンはサポートされなくととしてマークされて**されず**です。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CRegKey::operator HKEY](#operator_hkey)|変換、 `CRegKey` HKEY するオブジェクト。|  
|[CRegKey::operator =](#operator_eq)|代入演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRegKey::m_hKey](#m_hkey)|関連付けられているレジストリ キーのハンドルを含む、`CRegKey`オブジェクト。|  
|[CRegKey::m_pTM](#m_ptm)|ポインター`CAtlTransactionManager`オブジェクト|  
  
## <a name="remarks"></a>コメント  
 `CRegKey` 作成すると、システム レジストリのキーと値を削除するには、メソッドを提供します。 レジストリには、インストールに固有の一連ソフトウェアのバージョン番号は、インストールされているハードウェア、および COM オブジェクトの論理/物理マッピングなどのシステム コンポーネントの定義にはが含まれています。  
  
 `CRegKey` 特定のコンピューターのシステム レジストリへのプログラミング インターフェイスを提供します。 たとえば、特定のレジストリ キーを開くを呼び出す`CRegKey::Open`です。 取得したり、データ値を変更したりするには、呼び出す`CRegKey::QueryValue`または`CRegKey::SetValue`、それぞれします。 キーを閉じるを呼び出す`CRegKey::Close`です。  
  
 キーを閉じると、そのレジストリ データに書き込まれます (フラッシュされる)、ハード_ディスク。 このプロセスは数秒をかかります。 場合は、アプリケーションは、ハード_ディスクにレジストリ データを明示的に記述する必要がありますを呼び出すことができます、 [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32 関数。 ただし、 **RegFlushKey**多くのシステム リソースを使用して、どうしても必要な場合にのみ呼び出す必要があります。  
  
> [!IMPORTANT]
>  レジストリの場所を指定する呼び出し元を許可するすべてのメソッドには、信頼できないデータを読み取る可能性があります。 ようにするメソッドを使用して[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) NULL 終了文字列の値が、この関数によって明示的に処理しない考慮に入れておく必要があります。 呼び出し元のコードでは、両方の条件をチェックする必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="attach"></a>  CRegKey::Attach  
 HKEY をアタッチするには、このメソッドを呼び出して、`CRegKey`オブジェクトを設定して、 [m_hKey](#m_hkey)メンバーを識別するハンドル`hKey`です。  
  
```
void Attach(HKEY hKey) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hKey`  
 レジストリ キーのハンドルです。  
  
### <a name="remarks"></a>コメント  
 **アタッチ**場合アサート`m_hKey`以外の場合します。  
  
##  <a name="close"></a>  CRegKey::Close  
 解放するには、このメソッドを呼び出して、 [m_hKey](#m_hkey)メンバーを処理し、NULL に設定します。  
  
```
LONG Close() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合、エラー値を返します。  
  
##  <a name="create"></a>  CRegKey::Create  
 サブキーとしてが存在しない場合、指定したキーを作成するには、このメソッドを呼び出す`hKeyParent`です。  
  
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
 `hKeyParent`  
 開いているキーのハンドル。  
  
 `lpszKeyName`  
 作成したり開いたりキーの名前を指定します。 この名前のサブキーである必要があります`hKeyParent`です。  
  
 `lpszClass`  
 作成または開くのためのキーのクラスを指定します。 既定値は、REG_NONE です。  
  
 `dwOptions`  
 キーのオプションです。 既定値は、REG_OPTION_NON_VOLATILE です。 使用可能な値と説明の一覧は、次を参照してください。 [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) Windows SDK に含まれています。  
  
 `samDesired`  
 キーのセキュリティのアクセス。 既定値は KEY_READ &#124; KEY_WRITE です。 使用可能な値と説明の一覧は、次を参照してください。 **RegCreateKeyEx**です。  
  
 *lpSecAttr*  
 ポインター、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造体をキーのハンドルを子プロセスが継承できるかどうかを示すです。 既定では、このパラメーターは NULL (つまり、ハンドルを継承することはできません)  
  
 *lpdwDisposition*  
 [out]場合は NULL 以外の場合は、REG_CREATED_NEW_KEY (キーが存在せず作成した場合) またはポインターのいずれかを取得し、(キーが存在し、開かれた) 場合。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、error_success を返しますを返し、キーを開きます。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 **作成**設定、 [m_hKey](#m_hkey)このキーのハンドルへのメンバーです。  
  
##  <a name="cregkey"></a>  CRegKey::CRegKey  
 コンストラクターです。  
  
```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 `CRegKey` オブジェクトへの参照。  
  
 `hKey`  
 レジストリ キーへのハンドル。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 新しい `CRegKey` オブジェクトを作成します。 既存のオブジェクトを作成することができます`CRegKey`オブジェクト、またはレジストリ キーへのハンドル。  
  
##  <a name="dtor"></a>  CRegKey:: ~ CRegKey  
 デストラクターです。  
  
```
~CRegKey() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターのリリース`m_hKey`です。  
  
##  <a name="deletesubkey"></a>  CRegKey::DeleteSubKey  
 このメソッドを呼び出して、指定したキーをレジストリから削除します。  
  
```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSubKey`  
 削除するキーの名前を指定します。 この名前のサブキーである必要があります[m_hKey](#m_hkey)です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 `DeleteSubKey` サブキーがキーのみ削除できません。 キーにサブキーがある場合は、呼び出す[ある](#recursedeletekey)代わりにします。  
  
##  <a name="deletevalue"></a>  CRegKey::DeleteValue  
 値フィールドを削除するには、このメソッドを呼び出す[m_hKey](#m_hkey)です。  
  
```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszValue`  
 削除対象の値フィールドを指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
##  <a name="detach"></a>  CRegKey::Detach  
 デタッチするには、このメソッドを呼び出して、 [m_hKey](#m_hkey)メンバーのハンドルから、`CRegKey`オブジェクトおよび設定`m_hKey`を NULL にします。  
  
```
HKEY Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられている、HKEY、`CRegKey`オブジェクト。  
  
##  <a name="enumkey"></a>  して  
 このメソッドを呼び出して、開いているレジストリ キーのサブキーを列挙します。  
  
```
LONG EnumKey(  
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iIndex`  
 サブキーのインデックス。 このパラメーターは、最初の呼び出しで 0 にする必要があり、後続の呼び出しに増加し、  
  
 `pszName`  
 終端の null 文字を含む、サブキーの名前を受け取るバッファーへのポインター。 サブキーの名前のみが、完全なキーの階層ではない、バッファーにコピーされます。  
  
 *戻る*  
 指定したバッファーの Tchar で、サイズを指定する変数へのポインター、`pszName`パラメーター。 このサイズは、終端の null 文字を含める必要があります。 メソッドが返す場合、変数が指す*戻る*バッファーに格納されている文字の数が含まれています。 返されるカウントでは、終端の null 文字は含まれません。  
  
 *pftLastWriteTime*  
 時間を受信する変数を指すポインター、列挙するサブキーに最後に書き込んだです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 サブキーを列挙するには、呼び出す`CRegKey::EnumKey`でゼロから始まるインデックス。 インデックス値をインクリメントし、メソッドが戻る ERROR_NO_MORE_ITEMS までを繰り返します。 詳細については、次を参照してください。 [RegEnumKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724862) Windows SDK に含まれています。  
  
##  <a name="flush"></a>  CRegKey::Flush  
 このメソッドを呼び出して、レジストリに書き込むためにすべての開いているレジストリ キーの属性です。  
  
```
LONG Flush() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [RegEnumFlush](http://msdn.microsoft.com/library/windows/desktop/ms724867) Windows SDK に含まれています。  
  
##  <a name="getkeysecurity"></a>  CRegKey::GetKeySecurity  
 開いているレジストリ キーを保護するセキュリティ記述子のコピーを取得するには、このメソッドを呼び出します。  
  
```
LONG GetKeySecurity(  
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `si`  
 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573)を必要なセキュリティ情報を示す値。  
  
 `psd`  
 要求されたセキュリティ記述子のコピーを受け取るバッファーへのポインター。  
  
 `pnBytes`  
 指すバッファーのバイト単位のサイズ`psd`です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 メソッドが失敗した場合、戻り値は 0 以外のエラー コードが WINERROR で定義されているです。H.  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [RegGetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379313)です。  
  
##  <a name="m_hkey"></a>  CRegKey::m_hKey  
 関連付けられているレジストリ キーのハンドルを含む、`CRegKey`オブジェクト。  
  
```
HKEY m_hKey;
```  
  
##  <a name="m_ptm"></a>  CRegKey::m_pTM  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="notifychangekeyvalue"></a>  CRegKey::NotifyChangeKeyValue  
 このメソッドでは、属性または開いているレジストリ キーの内容の変更について、呼び出し元に通知します。  
  
```
LONG NotifyChangeKeyValue(  
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *bWatchSubtree*  
 指定したキーとそのすべてのサブキーまたは指定したキーでのみ変更を報告するかどうかを示すフラグを指定します。 このパラメーターが TRUE の場合、メソッドは、キーとサブキーの変更を報告します。 パラメーターが FALSE の場合、メソッドは、キーの変更のみを報告します。  
  
 *dwNotifyFilter*  
 変更を制御するフラグのセットを報告するかを指定します。 このパラメーターは、次の値の組み合わせを指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|REG_NOTIFY_CHANGE_NAME|サブキーが追加または削除された場合、呼び出し元に通知します。|  
|REG_NOTIFY_CHANGE_ATTRIBUTES|セキュリティ記述子の情報など、キーの属性の変更の呼び出し元に通知します。|  
|REG_NOTIFY_CHANGE_LAST_SET|キーの値に対する変更の呼び出し元に通知します。 これには、追加や、値を削除する既存の値の変更を含めることができます。|  
|REG_NOTIFY_CHANGE_SECURITY|キーのセキュリティ記述子への変更の呼び出し元に通知します。|  
  
 `hEvent`  
 イベントに対するハンドル。 場合、 *bAsync*パラメーターが TRUE の場合、メソッドからすぐに、このイベントを通知することによって変更が報告されます。 場合`bAsync`false で、`hEvent`は無視されます。  
  
 `bAsync`  
 メソッドが変更を報告する方法を示すフラグを指定します。 このパラメーターが TRUE の場合、このメソッドは直ちに返され、レポートは、指定されたイベントを通知することによって変更。 このパラメーターが FALSE の場合、変更が発生するまで、メソッドは返しません。 場合`hEvent`有効なイベントで指定されていない、`bAsync`パラメーターが TRUE にすることはできません。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  指定したキーが削除された場合、このメソッドでは、呼び出し元が通知されません。  
  
 詳細およびサンプル プログラムでは、次を参照してください。 [RegNotifyChangeKeyValue](http://msdn.microsoft.com/library/windows/desktop/ms724892)です。  
  
##  <a name="open"></a>  Cregkey::open  
 指定したキーを開きを設定するには、このメソッドを呼び出す[m_hKey](#m_hkey)をこのキーのハンドル。  
  
```
LONG Open(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hKeyParent`  
 開いているキーのハンドル。  
  
 `lpszKeyName`  
 作成したり開いたりキーの名前を指定します。 この名前のサブキーである必要があります`hKeyParent`です。  
  
 `samDesired`  
 キーのセキュリティのアクセス。 既定値は、KEY_ALL_ACCESS です。 使用可能な値と説明の一覧は、次を参照してください。 [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合、0 以外のエラー値は、WINERROR で定義されています。H.  
  
### <a name="remarks"></a>コメント  
 場合、`lpszKeyName`パラメーターが NULL またはポイント空の文字列に**開く**で識別されるキーの新しいハンドルを開く`hKeyParent`がいずれかの前に開かれたハンドルは閉じません。  
  
 異なり[CRegKey::Create](#create)、**開く**が存在しない場合、指定したキーは作成されません。  
  
##  <a name="operator_hkey"></a>  CRegKey::operator HKEY  
 変換、 `CRegKey` HKEY するオブジェクト。  
  
```  
operator HKEY() const throw();
```  
  
##  <a name="operator_eq"></a>  CRegKey::operator =  
 代入演算子。  
  
```
CRegKey& operator= (CRegKey& key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 コピーするキー。  
  
### <a name="return-value"></a>戻り値  
 新しいキーへの参照を返します。  
  
### <a name="remarks"></a>コメント  
 この演算子をデタッチ`key`その現在のオブジェクトからに割り当てます、`CRegKey`オブジェクトの代わりにします。  
  
##  <a name="querybinaryvalue"></a>  CRegKey::QueryBinaryValue  
 指定された値の名前のバイナリ データを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryBinaryValue(  
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリに値の名前を表す null で終わる文字列へのポインター。  
  
 `pValue`  
 値のデータを受け取るバッファーへのポインター。  
  
 `pnBytes`  
 バッファーのバイト単位のサイズを指定する変数へのポインターが指す、`pValue`パラメーター。 このメソッドが戻るときに、この変数には、バッファーにコピーするデータのサイズが含まれています。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 メソッドは、値の読み取りに失敗した場合、WINERROR で定義されている 0 以外のエラー コードを返します。H. 参照されるデータは、種類は REG_BINARY されませんが、定義が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細についてはします。  
  
> [!IMPORTANT]
>  このメソッドは、可能性のある信頼できないデータを読み取り、レジストリの場所を指定する呼び出し元を使用します。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドによって使用される関数が NULL 終了文字列を明示的に処理しません。 呼び出し元のコードでは、両方の条件をチェックする必要があります。  
  
##  <a name="querydwordvalue"></a>  CRegKey::QueryDWORDValue  
 指定された値の名前の DWORD データを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryDWORDValue(  
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリに値の名前を表す null で終わる文字列へのポインター。  
  
 `dwValue`  
 DWORD を受け取るバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 メソッドは、値の読み取りに失敗した場合、WINERROR で定義されている 0 以外のエラー コードを返します。H. 参照されるデータはない場合の種類が REG_DWORD の定義が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細についてはします。  
  
> [!IMPORTANT]
>  このメソッドは、可能性のある信頼できないデータを読み取り、レジストリの場所を指定する呼び出し元を使用します。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドによって使用される関数が NULL 終了文字列を明示的に処理しません。 呼び出し元のコードでは、両方の条件をチェックする必要があります。  
  
##  <a name="queryguidvalue"></a>  CRegKey::QueryGUIDValue  
 指定された値の名前に GUID データを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryGUIDValue(  
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリに値の名前を表す null で終わる文字列へのポインター。  
  
 `guidValue`  
 GUID を受け取る変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 メソッドは、値の読み取りに失敗した場合、WINERROR で定義されている 0 以外のエラー コードを返します。H. 参照されるデータは、有効な GUID ではない、定義が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用`CRegKey::QueryStringValue`GUID を使用して、文字列に変換および[CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589)です。  
  
> [!IMPORTANT]
>  このメソッドは、可能性のある信頼できないデータを読み取り、レジストリの場所を指定する呼び出し元を使用します。  
  
##  <a name="querymultistringvalue"></a>  CRegKey::QueryMultiStringValue  
 指定された値の名前の複数文字列のデータを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryMultiStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリに値の名前を表す null で終わる文字列へのポインター。  
  
 `pszValue`  
 複数文字列のデータを受信するバッファーへのポインター。 複数文字列は、2 つの null 文字で終わる、null で終わる文字列の配列です。  
  
 `pnChars`  
 サイズが指すバッファーの Tchar`pszValue`です。 このメソッドが戻るときに`pnChars`終端の null 文字も含めて取得、multistring の Tchar 単位のサイズが含まれています。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 メソッドは、値の読み取りに失敗した場合、WINERROR で定義されている 0 以外のエラー コードを返します。H. REG_MULTI_SZ 型の参照されるデータがない場合は、定義が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細についてはします。  
  
> [!IMPORTANT]
>  このメソッドは、可能性のある信頼できないデータを読み取り、レジストリの場所を指定する呼び出し元を使用します。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドによって使用される関数が NULL 終了文字列を明示的に処理しません。 呼び出し元のコードでは、両方の条件をチェックする必要があります。  
  
##  <a name="queryqwordvalue"></a>  CRegKey::QueryQWORDValue  
 QWORD データを指定した値の名前を取得するには、このメソッドを呼び出します。  
  
```
LONG QueryQWORDValue(  
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリに値の名前を表す null で終わる文字列へのポインター。  
  
 `qwValue`  
 QWORD を受け取るバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 メソッドは、値の読み取りに失敗した場合、WINERROR で定義されている 0 以外のエラー コードを返します。H. 参照されるデータの種類で定義ではありません、定義が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細についてはします。  
  
> [!IMPORTANT]
>  このメソッドは、可能性のある信頼できないデータを読み取り、レジストリの場所を指定する呼び出し元を使用します。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドによって使用される関数が NULL 終了文字列を明示的に処理しません。 呼び出し元のコードでは、両方の条件をチェックする必要があります。  
  
##  <a name="querystringvalue"></a>  CRegKey::QueryStringValue  
 指定された値名の文字列データを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリに値の名前を表す null で終わる文字列へのポインター。  
  
 `pszValue`  
 文字列データを受信するバッファーへのポインター。  
  
 `pnChars`  
 サイズが指すバッファーの Tchar`pszValue`です。 このメソッドが戻るときに`pnChars`終端の null 文字も含めて取得するには、文字列の Tchar 単位のサイズが含まれています。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 メソッドは、値の読み取りに失敗した場合、WINERROR で定義されている 0 以外のエラー コードを返します。H. 参照されるデータは、種類 REG_SZ のされませんが、定義が返されます。 メソッドに返しますを返す場合`pnChars`が 0 でない必要なバッファー サイズ (バイト単位)。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細についてはします。  
  
> [!IMPORTANT]
>  このメソッドは、可能性のある信頼できないデータを読み取り、レジストリの場所を指定する呼び出し元を使用します。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドによって使用される関数が NULL 終了文字列を明示的に処理しません。 呼び出し元のコードでは、両方の条件をチェックする必要があります。  
  
##  <a name="queryvalue"></a>  CRegKey::QueryValue  
 指定した値フィールドのデータを取得するには、このメソッドを呼び出す[m_hKey](#m_hkey)です。 このメソッドの以前のバージョンはサポートされなくととしてマークされて**されず**です。  
  
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
 `pszValueName`  
 クエリに値の名前を表す null で終わる文字列へのポインター。 場合`pszValueName`が NULL または空の文字列""、メソッド型を取得、およびデータ キーの名前のないまたは存在する場合、既定値です。  
  
 `pdwType`  
 指定した値に格納されたデータの種類を示すコードを受け取る変数へのポインター。 `pdwType`型コードが必要ない場合、パラメーターは NULL を指定できます。  
  
 `pData`  
 値のデータを受け取るバッファーへのポインター。 このパラメーターは、データが必要ない場合、NULL にすることができます。  
  
 `pnBytes`  
 バッファーのバイト単位のサイズを指定する変数へのポインターが指す、`pData`パラメーター。 この変数にコピーするデータのサイズが含まれています、メソッドが戻るとき*pData です。*  
  
 `dwValue`  
 値フィールドの数値データ。  
  
 `lpszValueName`  
 クエリを実行する、値フィールドを指定します。  
  
 `szValue`  
 値フィールドの文字列データです。  
  
 `pdwCount`  
 文字列データのサイズ。 その値は、初期のサイズに設定は、`szValue`バッファー。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合は 0 以外のエラー コードは、WINERROR で定義されます。H.  
  
### <a name="remarks"></a>コメント  
 2 つの元のバージョンの`QueryValue`はサポートされなくなりとマークされて**されず**です。 これらの形式が使用されている場合、コンパイラは警告を発行します。  
  
 残りのメソッドは、RegQueryValueEx を呼び出します。  
  
> [!IMPORTANT]
>  このメソッドは、可能性のある信頼できないデータを読み取り、レジストリの場所を指定する呼び出し元を使用します。 また、このメソッドによって使用される regqueryvalueex により関数は明示的に文字列は処理しませんは`NULL`終了します。 呼び出し元のコードでは、両方の条件をチェックする必要があります。  
  
##  <a name="recursedeletekey"></a>  CRegKey::RecurseDeleteKey  
 このメソッドを呼び出して、指定したキーをレジストリから削除し、すべてのサブキーを明示的に削除します。  
  
```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszKey*  
 削除するキーの名前を指定します。 この名前のサブキーである必要があります[m_hKey](#m_hkey)です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合、0 以外のエラー値は、WINERROR で定義されています。H.  
  
### <a name="remarks"></a>コメント  
 キーにサブキーがある場合は、キーを削除するには、このメソッドを呼び出す必要があります。  
  
##  <a name="setbinaryvalue"></a>  CRegKey::SetBinaryValue  
 レジストリ キーのバイナリ値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetBinaryValue(  
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `pValue`  
 指定された値の名前で格納されるデータを格納するバッファーへのポインター。  
  
 `nBytes`  
 (バイト単位) によって示される情報のサイズを指定、`pValue`パラメーター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)に値をレジストリに書き込めません。  
  
##  <a name="setdwordvalue"></a>  CRegKey::SetDWORDValue  
 レジストリ キーの DWORD 値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `dwValue`  
 指定された値の名前で保存する DWORD データ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)に値をレジストリに書き込めません。  
  
##  <a name="setguidvalue"></a>  CRegKey::SetGUIDValue  
 レジストリ キーの GUID 値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `guidValue`  
 指定された値の名前で格納される GUID への参照。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用`CRegKey::SetStringValue`GUID を使用して文字列に変換および[StringFromGUID2](http://msdn.microsoft.com/library/windows/desktop/ms683893)です。  
  
##  <a name="setkeyvalue"></a>  CRegKey::SetKeyValue  
 指定したキーの指定した値フィールドにデータを格納するには、このメソッドを呼び出します。  
  
```
LONG SetKeyValue(  
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszKeyName`  
 作成または開くのためのキーの名前を指定します。 この名前のサブキーである必要があります[m_hKey](#m_hkey)です。  
  
 `lpszValue`  
 データを格納するを指定します。 このパラメーターは、NULL を指定する必要があります。  
  
 `lpszValueName`  
 設定する値 フィールドを指定します。 キーにもこの名前の値フィールドが既に存在しない場合が追加されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合は 0 以外のエラー コードは、WINERROR で定義されます。H.  
  
### <a name="remarks"></a>コメント  
 作成または開くには、このメソッドを呼び出して、`lpszKeyName`キーし、保存、`lpszValue`内のデータ、`lpszValueName`値フィールド。  
  
##  <a name="setkeysecurity"></a>  CRegKey::SetKeySecurity  
 レジストリ キーのセキュリティを設定するには、このメソッドを呼び出します。  
  
```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `si`  
 設定するセキュリティ記述子のコンポーネントを指定します。 値は、次の値の組み合わせにすることができます。  
  
|[値]|説明|  
|-----------|-------------|  
|DACL_SECURITY_INFORMATION|キーの随意アクセス制御リスト (DACL) を設定します。 呼び出し元のプロセスは、オブジェクトの所有者である必要がありますか、キーは WRITE_DAC アクセスにあります。|  
|GROUP_SECURITY_INFORMATION|キーのプライマリ グループ セキュリティ識別子 (SID) を設定します。 呼び出し元のプロセスは、オブジェクトの所有者である必要がありますか、キーは WRITE_OWNER アクセスにあります。|  
|OWNER_SECURITY_INFORMATION|キーの所有者の SID を設定します。 呼び出し元のプロセスのオブジェクトの所有者であるか有効になっている SE_TAKE_OWNERSHIP_NAME 権限を持っている必要がありますか、キーは WRITE_OWNER アクセスにあります。|  
|SACL_SECURITY_INFORMATION|キーのシステム アクセス制御リスト (SACL) を設定します。 ACCESS_SYSTEM_SECURITY アクセス キーが必要です。 このアクセスするために適切な方法は、SE_SECURITY_NAME を有効にする[特権](http://msdn.microsoft.com/library/windows/desktop/aa379306)呼び出し元の現在のアクセス トークンで ACCESS_SYSTEM_SECURITY アクセスのためのハンドルを開くし、特権を無効にします。|  
  
 `psd`  
 ポインター、 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)を指定したキーに設定するセキュリティ属性を指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 キーのセキュリティ属性を設定します。 参照してください[RegSetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379314)詳細についてはします。  
  
##  <a name="setmultistringvalue"></a>  CRegKey::SetMultiStringValue  
 レジストリ キーの複数文字列値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `pszValue`  
 指定された値の名前で保存する複数文字列のデータへのポインター。 複数文字列は、2 つの null 文字で終わる、null で終わる文字列の配列です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)に値をレジストリに書き込めません。  
  
##  <a name="setqwordvalue"></a>  CRegKey::SetQWORDValue  
 レジストリ キーの QWORD 値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `qwValue`  
 指定された値の名前で保存する QWORD データ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)に値をレジストリに書き込めません。  
  
##  <a name="setstringvalue"></a>  CRegKey::SetStringValue  
 レジストリ キーの文字列値を設定します。  
  
```
LONG SetStringValue(  
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `pszValue`  
 指定された値名で格納される文字列データへのポインター。  
  
 `dwType`  
 レジストリに書き込む文字列の型。REG_SZ (既定値) または REG_EXPAND_SZ (複数文字列の場合)。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている 0 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923\(v=vs.85\).aspx)に値をレジストリに書き込めません。  
  
##  <a name="setvalue"></a>  CRegKey::SetValue  
 指定した値フィールドにデータを格納するには、このメソッドを呼び出す[m_hKey](#m_hkey)です。 このメソッドの以前のバージョンはサポートされなくととしてマークされて**されず**です。  
  
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
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値が存在しないキーで、メソッドによりキーに追加します。 場合`pszValueName`が NULL または空の文字列""、種類を設定、およびデータ キーの名前のないまたは既定値です。  
  
 `dwType`  
 によって示されるデータの種類を示すコードを指定します、`pValue`パラメーター。  
  
 `pValue`  
 指定された値の名前で格納されるデータを格納するバッファーへのポインター。  
  
 `nBytes`  
 (バイト単位) によって示される情報のサイズを指定、`pValue`パラメーター。 データは、種類 REG_SZ、REG_EXPAND_SZ、または、REG_MULTI_SZ 場合`nBytes`終端の null 文字のサイズを含める必要があります。  
  
 `hKeyParent`  
 開いているキーのハンドル。  
  
 `lpszKeyName`  
 作成したり開いたりキーの名前を指定します。 この名前のサブキーである必要があります`hKeyParent`です。  
  
 `lpszValue`  
 データを格納するを指定します。 このパラメーターは、NULL を指定する必要があります。  
  
 `lpszValueName`  
 設定する値 フィールドを指定します。 キーにもこの名前の値フィールドが既に存在しない場合が追加されます。  
  
 `dwValue`  
 データを格納するを指定します。  
  
 `bMulti`  
 False の場合、種類 REG_SZ は、文字列を示します。 True の場合は、文字列は REG_MULTI_SZ 型の複数文字列を示します。  
  
 `nValueLen`  
 場合`bMulti`が true の場合、`nValueLen`の長さ、 *lpszValue*文字列の文字です。 場合`bMulti`が false の場合、メソッドの計算で長さが自動的に処理が-1 の値を示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合は 0 以外のエラー コードは、WINERROR で定義されます。H.  
  
### <a name="remarks"></a>コメント  
 2 つの元のバージョンの`SetValue`としてマークされて**されず**と使用する必要があります。 これらの形式が使用されている場合、コンパイラは警告を発行します。  
  
 3 番目のメソッド呼び出し[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)です。  
  
## <a name="see-also"></a>関連項目  
 [DCOM のサンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
