---
title: CSettingsStore クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7711e0105085f0b7af1344ce230839e90f2b6851
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079489"
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
|[CSettingsStore::CreateKey](#createkey)|指定したキーを開くか、存在しない場合は作成します。|  
|[CSettingsStore::DeleteKey](#deletekey)|指定したキーとそのすべての子を削除します。|  
|[CSettingsStore::DeleteValue](#deletevalue)|開いているキーの指定した値を削除します。|  
|[CSettingsStore::Open](#open)|指定したキーを開きます。|  
|[CSettingsStore::Read](#read)|指定したキー値のデータを取得します。|  
|[CSettingsStore::Write](#write)|開いているキーの下のレジストリ値を書き込みます。|  
  
## <a name="remarks"></a>Remarks  
 メンバー関数は、`CreateKey`と`Open`非常に似ています。 レジストリ キーが既に存在する場合`CreateKey`と`Open`同じように機能します。 ただし、レジストリ キーが存在しない場合、`CreateKey`一方が作成されます`Open`はエラー値を返します。  
  
## <a name="example"></a>例  
 次の例でのオープンと読み取りメソッドを使用する方法、`CSettingsStore`クラスです。 このコード スニペットの一部である、[ツール ヒントのデモ サンプル](../../visual-cpp-samples.md)です。  
  
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
 デストラクターは、既定では、このメソッドが呼び出されます、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)です。  
  
##  <a name="createkey"></a>  CSettingsStore::CreateKey  
 レジストリ キーを開くか、存在しない場合は作成します。  
  
```  
virtual BOOL CreateKey(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pszPath*  
 作成したり開いたりキーの名前を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0それ以外の場合は 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 `CreateKey` 使用して`m_hKey`レジストリの照会のルートとして。 検索*pszPath*のサブキーとして`m_hKey`です。 キーが存在しない場合`CreateKey`によって作成されます。 それ以外の場合、キーを開きます。 `CreateKey` 設定し、`m_hKey`作成または開かれたキーにします。  
  
##  <a name="csettingsstore"></a>  CSettingsStore::CSettingsStore  
 
          `CSettngsStore` オブジェクトを作成します。  
  
```  
CSettingsStore(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bAdmin*  
 指定するブール型のパラメーターかどうか、`CSettingsStore`管理者モードで動作しているオブジェクト。  
  
 [in]*bReadOnly*  
 指定するブール型のパラメーターかどうか、`CSettingsStore`オブジェクトが読み取り専用モードで作成します。  
  
### <a name="remarks"></a>Remarks  
 場合*bAdmin*に設定されている`true`、`m_hKey`にメンバー変数が設定されている`HKEY_LOCAL_MACHINE`です。 設定した場合*bAdmin*に`false`、`m_hKey`に設定されている`HKEY_CURRENT_USER`です。  
  
 アクセスのセキュリティによって異なります、 *bReadOnly*パラメーター。 場合*bReadonly*は`false`、セキュリティのアクセスに設定されます`KEY_ALL_ACCESS`です。 場合*bReadyOnly*は`true`、アクセスのセキュリティの組み合わせに設定されます`KEY_QUERY_VALUE, KEY_NOTIFY`と`KEY_ENUMERATE_SUB_KEYS`です。 レジストリとセキュリティのアクセスの詳細については、次を参照してください。[レジストリ キーのセキュリティとアクセス権](http://msdn.microsoft.com/library/windows/desktop/ms724878)です。  
  
 デストラクター`CSettingsStore`解放`m_hKey`自動的にします。  
  
##  <a name="deletekey"></a>  CSettingsStore::DeleteKey  
 レジストリからキーとそのすべての子を削除します。  
  
```  
virtual BOOL DeleteKey(
    LPCTSTR pszPath,  
    BOOL bAdmin = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pszPath*  
 削除するキーの名前。  
  
 [in]*bAdmin*  
 削除するキーの場所を指定するスイッチです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドが失敗、`CSettingsStore`オブジェクトは読み取り専用モードにします。  
  
 場合、パラメーター *bAdmin*ゼロ、`DeleteKey`下で削除するキーの検索`HKEY_CURRENT_USER`です。 場合*bAdmin*がゼロ以外、`DeleteKey`下で削除するキーの検索`HKEY_LOCAL_MACHINE`です。  
  
##  <a name="deletevalue"></a>  CSettingsStore::DeleteValue  
 値を削除`m_hKey`です。  
  
```  
virtual BOOL DeleteValue(LPCTSTR pszValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*終端*  
 削除対象の値フィールドを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="open"></a>  CSettingsStore::Open  
 レジストリ キーを開きます。  
  
```  
virtual BOOL Open(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pszPath*  
 レジストリ キーの名前。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、指定したキーを正常に開いたら、設定`m_hKey`をこのキーのハンドル。  
  
##  <a name="read"></a>  CSettingsStore::Read  
 レジストリ内のキーから値を読み取ります。  
  
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
 [in]*pszKey*  
 レジストリから読み取る値の名前を表す null で終わる文字列へのポインター。  
  
 [out]*iVal*  
 レジストリ キーからの読み取り値を受け取る整数変数への参照。  
  
 [out]*dwVal*  
 レジストリ キーから読み取られた値を受け取る 32 ビットのダブルワード変数への参照。  
  
 [out]*sVal*  
 レジストリ キーから読み取られた値を受け取る文字列変数への参照。  
  
 [out]*scStringList*  
 レジストリ キーから読み取った値を受け取る文字列リストの変数への参照。  
  
 [out]*scArray*  
 レジストリ キーから読み取られた値を受け取る文字列の配列変数への参照。  
  
 [out]*dwcArray*  
 レジストリ キーからの読み取り値を受け取る 32 ビットのダブルワードの配列変数への参照。  
  
 [out]*wcArray*  
 レジストリ キーから読み取られた値を受信する 16 ビット ワードの配列変数への参照。  
  
 [out]*bcArray*  
 レジストリ キーから読み取られた値を受信するバイト配列の変数への参照。  
  
 [out]*lpPoint*  
 ポインターへの参照、`POINT`レジストリ キーから値を受け取る構造の読み取り。  
  
 [out]*rect*  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)レジストリ キーから値を受け取る変数の読み取り。  
  
 [out]*ppData*  
 レジストリ キーから読み取る値を受け取るデータへのポインターへのポインター。  
  
 [out]*ペタバイト*  
 符号なし整数の変数へのポインター。 この変数には、バッファーのサイズを*ppData*を指します。  
  
 [out]*一覧*  
 参照、 [CObList](../../mfc/reference/coblist-class.md)レジストリ キーから値を受け取る変数の読み取り。  
  
 [out]*obj*  
 参照、 [CObject](../../mfc/reference/cobject-class.md)レジストリ キーから値を受け取る変数の読み取り。  
  
 [out]*pObj*  
 ポインターへの参照、`CObject`レジストリ キーから値を受け取る変数の読み取り。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `Read` チェック*pszKey*のサブキーとして`m_hKey`です。  
  
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
 [in]*pszKey*  
 設定する値の名前を含む文字列へのポインター。  
  
 [in]*iVal*  
 格納するデータを含む整数型の変数への参照。  
  
 [in]*dwVal*  
 格納するデータを含む 32 ビットのダブルワード変数への参照。  
  
 [in]*pszVal*  
 格納するデータを含む null で終わる文字列変数へのポインター。  
  
 [in]*scStringList*  
 参照、 [CStringList](../../mfc/reference/cstringlist-class.md)を格納するデータを含む変数。  
  
 [in]*bcArray*  
 格納するデータを含むバイト配列の変数への参照。  
  
 [in]*scArray*  
 格納するデータを含む文字列配列変数への参照。  
  
 [in]*dwcArray*  
 32 ビットのダブルワードの配列変数を格納するデータを含むへの参照。  
  
 [in]*wcArray*  
 16 ビット ワードの配列変数を格納するデータを含むへの参照。  
  
 [in]*rect*  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)を格納するデータを含む変数。  
  
 [in]*lpPoint*  
 ポインターへの参照、`POINT`を格納するデータを含む変数。  
  
 [in]*pData*  
 格納するデータを格納するバッファーへのポインター。  
  
 [in]*nBytes*  
 (バイト単位) をデータのサイズを指定、 *pData*パラメーター ポイント。  
  
 [in]*一覧*  
 参照、 [CObList](../../mfc/reference/coblist-class.md)を格納するデータを含む変数。  
  
 [in]*obj*  
 参照、 [CObject](../../mfc/reference/cobject-class.md)を格納するデータを含む変数。  
  
 [in]*pObj*  
 ポインターへのポインター、`CObject`を格納するデータを含む変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>Remarks  
 レジストリへの書き込みをするために設定する必要があります*bReadOnly* 0 以外の値を作成するときに、 [CSettingsStore](../../mfc/reference/csettingsstore-class.md)オブジェクト。 詳細については、次を参照してください。 [CSettingsStore::CSettingsStore](#csettingsstore)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
