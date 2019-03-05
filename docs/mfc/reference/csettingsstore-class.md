---
title: CSettingsStore Class
ms.date: 11/04/2016
f1_keywords:
- CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::Close
- AFXSETTINGSSTORE/CSettingsStore::CreateKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteValue
- AFXSETTINGSSTORE/CSettingsStore::Open
- AFXSETTINGSSTORE/CSettingsStore::Read
- AFXSETTINGSSTORE/CSettingsStore::Write
helpviewer_keywords:
- CSettingsStore [MFC], CSettingsStore
- CSettingsStore [MFC], Close
- CSettingsStore [MFC], CreateKey
- CSettingsStore [MFC], DeleteKey
- CSettingsStore [MFC], DeleteValue
- CSettingsStore [MFC], Open
- CSettingsStore [MFC], Read
- CSettingsStore [MFC], Write
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
ms.openlocfilehash: 1de26ceedfd29f276693be512bd41f169fb44b94
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274545"
---
# <a name="csettingsstore-class"></a>CSettingsStore Class

Windows API 関数をラップし、レジストリへのアクセスに使用するオブジェクト指向インターフェイスを提供します。

## <a name="syntax"></a>構文

```
class CSettingsStore : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSettingsStore::CSettingsStore](#csettingsstore)|`CSettingsStore` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSettingsStore::Close](#close)|開いているレジストリ キーを閉じます。|
|[CSettingsStore::CreateKey](#createkey)|指定のキーを開くか、存在しない場合は作成します。|
|[CSettingsStore::DeleteKey](#deletekey)|指定したキーとそのすべての子を削除します。|
|[CSettingsStore::DeleteValue](#deletevalue)|開いているキーの指定された値を削除します。|
|[CSettingsStore::Open](#open)|指定したキーを開きます。|
|[CSettingsStore::Read](#read)|指定したキー値のデータを取得します。|
|[CSettingsStore::Write](#write)|開いているキーの下のレジストリ値を書き込みます。|

## <a name="remarks"></a>Remarks

メンバー関数は、`CreateKey`と`Open`とよく似ています。 レジストリ キーが既に存在する場合`CreateKey`と`Open`と同じように機能します。 ただし、レジストリ キーが存在しない場合、`CreateKey`が作成されます`Open`はエラー値を返します。

## <a name="example"></a>例

次の例では、開く、読み取りのメソッドを使用する方法、`CSettingsStore`クラス。 このコード スニペットの一部、[ツール ヒントのデモ サンプル](../../visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CSettingsStore`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxsettingsstore.h

##  <a name="close"></a>  CSettingsStore::Close

開いているレジストリ キーを閉じます。

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

既定では、このメソッドの呼び出しのデストラクターは、元の[CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)します。

##  <a name="createkey"></a>  CSettingsStore::CreateKey

レジストリ キーを開くかが存在しない場合は作成します。

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>パラメーター

*pszPath*<br/>
[in]作成または開かれたキーの名前を指定します。

### <a name="return-value"></a>戻り値

成功した場合は 0それ以外の場合、0 以外の値。

### <a name="remarks"></a>Remarks

`CreateKey` 使用して`m_hKey`レジストリの照会のルートとして。 検索*pszPath*のサブキーとして`m_hKey`します。 キーが存在しない場合`CreateKey`によって作成されます。 それ以外の場合、キーを開きます。 `CreateKey` 設定し`m_hKey`作成または開かれたキーにします。

##  <a name="csettingsstore"></a>  CSettingsStore::CSettingsStore

`CSettngsStore` オブジェクトを作成します。

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>パラメーター

*bAdmin*<br/>
[in]ブール型パラメーターを指定するかどうか、`CSettingsStore`管理者モードで動作しているオブジェクト。

*bReadOnly*<br/>
[in]ブール型パラメーターを指定するかどうか、`CSettingsStore`読み取り専用モードでオブジェクトを作成します。

### <a name="remarks"></a>Remarks

場合*bAdmin*を TRUE に設定されている、`m_hKey`にメンバー変数が設定されている**HKEY_LOCAL_MACHINE**します。 設定した場合*bAdmin*を FALSE に`m_hKey`に設定されている**HKEY_CURRENT_USER**します。

セキュリティのアクセス権は異なります、 *bReadOnly*パラメーター。 場合*bReadonly* false で、セキュリティのアクセスに設定する**KEY_ALL_ACCESS**します。 場合*bReadyOnly*が true の場合、アクセスのセキュリティの組み合わせに設定されます**KEY_QUERY_VALUE、KEY_NOTIFY**と**KEY_ENUMERATE_SUB_KEYS**します。 レジストリとセキュリティのアクセスの詳細については、次を参照してください。[レジストリ キーのセキュリティとアクセス権](/windows/desktop/SysInfo/registry-key-security-and-access-rights)します。

デストラクター`CSettingsStore`解放`m_hKey`自動的にします。

##  <a name="deletekey"></a>  CSettingsStore::DeleteKey

レジストリからキーとそのすべての子を削除します。

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>パラメーター

*pszPath*<br/>
[in]削除するキーの名前。

*bAdmin*<br/>
[in]削除するキーの場所を指定するスイッチです。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドが失敗、`CSettingsStore`オブジェクトは読み取り専用モードにします。

場合、パラメーター *bAdmin*ゼロ、`DeleteKey`下で削除するキーの検索**HKEY_CURRENT_USER**します。 場合*bAdmin* 0 以外の場合、`DeleteKey`下で削除するキーの検索**HKEY_LOCAL_MACHINE**します。

##  <a name="deletevalue"></a>  CSettingsStore::DeleteValue

値を削除します`m_hKey`します。

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>パラメーター

*終端*<br/>
[in]削除する値のフィールドを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="open"></a>  CSettingsStore::Open

レジストリ キーを開きます。

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>パラメーター

*pszPath*<br/>
[in]レジストリ キーの名前。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドは、指定したキーが正常に開いたら、設定`m_hKey`にこのキーのハンドル。

##  <a name="read"></a>  CSettingsStore::Read

レジストリのキーから値を読み取ります。

```
virtual BOOL Read(
    LPCTSTR pszKey,
    int& iVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    DWORD& dwVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CString& sVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Read(
    LPCTSTR pszKey,
    CRect& rect);

virtual BOOL Read(
    LPCTSTR pszKey,
    BYTE** ppData,
    UINT* pBytes);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject*& pObj);
```

### <a name="parameters"></a>パラメーター

*pszKey*<br/>
[in]レジストリから読み取る値の名前を含む null で終わる文字列へのポインター。

*iVal*<br/>
[out]レジストリ キーから読み取る値を受け取る整数変数への参照。

*dwVal*<br/>
[out]レジストリ キーから読み取る値を受け取る 32 ビットのダブルワード変数への参照。

*sVal*<br/>
[out]レジストリ キーから読み取る値を受け取る文字列変数への参照。

*scStringList*<br/>
[out]レジストリ キーから読み取る値を受け取る文字列リストの変数への参照。

*scArray*<br/>
[out]レジストリ キーから読み取る値を受け取る文字列の配列変数への参照。

*dwcArray*<br/>
[out]レジストリ キーから読み取る値を受け取る 32 ビットのダブルワードの配列変数への参照。

*wcArray*<br/>
[out]レジストリ キーから読み取る値を受信する 16 ビット ワードの配列変数への参照。

*bcArray*<br/>
[out]レジストリ キーから読み取る値を受信するバイト配列の変数への参照。

*lpPoint*<br/>
[out]ポインターへの参照を`POINT`レジストリ キーの値を受け取る構造体を読み取る。

*rect*<br/>
[out]参照を[CRect](../../atl-mfc-shared/reference/crect-class.md)レジストリ キーから値を受け取る変数の読み取り。

*ppData*<br/>
[out]値を受け取るデータへのポインターへのポインターは、レジストリ キーから読み取る。

*ペタバイト*<br/>
[out]符号なし整数型の変数へのポインター。 この変数には、バッファーのサイズを*ppData*を指します。

*リスト*<br/>
[out]参照を[CObList](../../mfc/reference/coblist-class.md)レジストリ キーから値を受け取る変数の読み取り。

*obj*<br/>
[out]参照を[CObject](../../mfc/reference/cobject-class.md)レジストリ キーから値を受け取る変数の読み取り。

*pObj*<br/>
[out]ポインターへの参照を`CObject`レジストリ キーから値を受け取る変数の読み取り。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

`Read` チェック*pszKey*のサブキーとして`m_hKey`します。

##  <a name="write"></a>  CSettingsStore::Write

開いているキーの下のレジストリ値を書き込みます。

```
virtual BOOL Write(
    LPCTSTR pszKey,
    int iVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    DWORD dwVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPCTSTR pszVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Write(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    const CRect& rect);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPBYTE pData,
    UINT nBytes);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject* pObj);
```

### <a name="parameters"></a>パラメーター

*pszKey*<br/>
[in]設定する値の名前を含む文字列へのポインター。

*iVal*<br/>
[in]格納するデータを含む整数変数への参照。

*dwVal*<br/>
[in]格納するデータを含む 32 ビットのダブルワード変数への参照。

*pszVal*<br/>
[in]格納するデータを含む null で終わる文字列変数へのポインター。

*scStringList*<br/>
[in]参照を[CStringList](../../mfc/reference/cstringlist-class.md)を格納するデータを含む変数。

*bcArray*<br/>
[in]格納するデータを含むバイト配列の変数への参照。

*scArray*<br/>
[in]格納するデータを含む文字列配列変数への参照。

*dwcArray*<br/>
[in]32 ビットのダブルワードの配列変数を格納するデータを含むへの参照。

*wcArray*<br/>
[in]格納するデータを含む 16 ビット ワード配列変数への参照。

*rect*<br/>
[in]参照を[CRect](../../atl-mfc-shared/reference/crect-class.md)を格納するデータを含む変数。

*lpPoint*<br/>
[in]ポインターへの参照を`POINT`を格納するデータを含む変数。

*pData*<br/>
[in]格納するデータを格納しているバッファーへのポインター。

*nBytes*<br/>
[in]サイズを指定しているデータのバイト単位、 *pData*パラメーター ポイント。

*リスト*<br/>
[in]参照を[CObList](../../mfc/reference/coblist-class.md)を格納するデータを含む変数。

*obj*<br/>
[in]参照を[CObject](../../mfc/reference/cobject-class.md)を格納するデータを含む変数。

*pObj*<br/>
[in]ポインターへのポインターを`CObject`を格納するデータを含む変数。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

設定する必要があります、レジストリに書き込むには、 *bReadOnly* 0 以外の値を作成するときに、 [CSettingsStore](../../mfc/reference/csettingsstore-class.md)オブジェクト。 詳細については、次を参照してください。 [CSettingsStore::CSettingsStore](#csettingsstore)します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
