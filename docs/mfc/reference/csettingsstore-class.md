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
ms.openlocfilehash: b1acf959c371aa23ac55ace7fea9466f0e20813f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318466"
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
|[ストア::C設定ストア](#csettingsstore)|`CSettingsStore` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[保存場所::閉じる](#close)|開いているレジストリ キーを閉じます。|
|[ストア::キーの作成](#createkey)|指定したキーを開くか、存在しない場合は作成します。|
|[セッティングストア::Dエレテキー](#deletekey)|指定したキーとそのすべての子を削除します。|
|[:Dセレテの価値](#deletevalue)|開いているキーの指定した値を削除します。|
|[ストアを開く](#open)|指定したキーを開きます。|
|[ストア::読み取り](#read)|指定したキー値のデータを取得します。|
|[書き込み](#write)|開いているキーの下のレジストリに値を書き込みます。|

## <a name="remarks"></a>解説

メンバー関数`CreateKey`と`Open`非常に似ています。 レジストリ キーが既に存在`CreateKey`する`Open`場合、同じように機能します。 ただし、レジストリ キーが存在しない場合は`CreateKey`、そのレジストリ`Open`キーを作成しますが、エラー値が返されます。

## <a name="example"></a>例

クラスの Open メソッドと Read メソッドを使用する方法`CSettingsStore`を次の例に示します。 このコード スニペットは、[ツール ヒント デモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CSettingsStore`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxsettingsstore.h

## <a name="csettingsstoreclose"></a><a name="close"></a>保存場所::閉じる

開いているレジストリ キーを閉じます。

```
virtual void Close();
```

### <a name="remarks"></a>解説

既定では、このメソッドは[CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)のデストラクターから呼び出されます。

## <a name="csettingsstorecreatekey"></a><a name="createkey"></a>ストア::キーの作成

レジストリ キーを開くか、存在しない場合は作成します。

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
[in]作成または開くキーの名前を指定します。

### <a name="return-value"></a>戻り値

成功した場合は 0。それ以外の場合は 0 以外の値。

### <a name="remarks"></a>解説

`CreateKey`は`m_hKey`レジストリ照会のルートとして使用されます。 のサブキーとして*pszPath*を検索`m_hKey`します。 キーが存在しない場合は、`CreateKey`作成します。 それ以外の場合は、キーを開きます。 `CreateKey`作成された`m_hKey`キーまたは開いたキーに設定します。

## <a name="csettingsstorecsettingsstore"></a><a name="csettingsstore"></a>ストア::C設定ストア

`CSettngsStore` オブジェクトを作成します。

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>パラメーター

*b管理者*<br/>
[in]オブジェクトが管理者モードで動作`CSettingsStore`するかどうかを指定するブール値パラメーター。

*読み取り専用*<br/>
[in]`CSettingsStore`オブジェクトを読み取り専用モードで作成するかどうかを指定するブール値パラメーター。

### <a name="remarks"></a>解説

*bAdmin*が TRUE に設定`m_hKey`されている場合、メンバー変数は**HKEY_LOCAL_MACHINE**に設定されます。 *bAdmin*を FALSE に`m_hKey`設定した場合は、**が HKEY_CURRENT_USER**に設定されます。

セキュリティ アクセスは *、bReadOnly*パラメーターによって異なります。 *bReadonly*が FALSE の場合、セキュリティ アクセスは**KEY_ALL_ACCESS**に設定されます。 *bReadyOnly*が TRUE の場合、セキュリティ アクセスは **、KEY_QUERY_VALUE、KEY_NOTIFY、****およびKEY_ENUMERATE_SUB_KEYS**の組み合わせに設定されます。 レジストリと共にセキュリティ アクセスの詳細については、「[レジストリ キーのセキュリティとアクセス権](/windows/win32/SysInfo/registry-key-security-and-access-rights)」を参照してください。

リリースのデストラクター`CSettingsStore`は`m_hKey`自動的に行われます。

## <a name="csettingsstoredeletekey"></a><a name="deletekey"></a>セッティングストア::Dエレテキー

キーとそのすべての子をレジストリから削除します。

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
[in]削除するキーの名前。

*b管理者*<br/>
[in]削除するキーの場所を指定するスイッチ。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`CSettingsStore`オブジェクトが読み取り専用モードの場合、このメソッドは失敗します。

パラメータ*bAdmin*が 0`DeleteKey`の場合は **、HKEY_CURRENT_USER**で削除するキーを検索します。 *bAdmin*が 0`DeleteKey`以外の場合は **、HKEY_LOCAL_MACHINE**で削除するキーを検索します。

## <a name="csettingsstoredeletevalue"></a><a name="deletevalue"></a>:Dセレテの価値

から`m_hKey`値を削除します。

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>パラメーター

*値*<br/>
[in]削除する値フィールドを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="csettingsstoreopen"></a><a name="open"></a>ストアを開く

レジストリ キーを開きます。

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
[in]レジストリ キーの名前。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメソッドは、指定されたキーを正常に開いた`m_hKey`後、このキーのハンドルに設定します。

## <a name="csettingsstoreread"></a><a name="read"></a>ストア::読み取り

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

*キー*<br/>
[in]レジストリから読み取る値の名前を含む null で終わる文字列へのポインター。

*iVal*<br/>
[アウト]レジストリ キーから読み取られた値を受け取る整数変数への参照。

*ドヴァル*<br/>
[アウト]レジストリ キーから読み取られた値を受け取る 32 ビットのダブル ワード変数への参照。

*sVal*<br/>
[アウト]レジストリ キーから読み取った値を受け取る文字列変数への参照。

*一覧*<br/>
[アウト]レジストリ キーから読み取られた値を受け取る文字列リスト変数への参照。

*scアレイ*<br/>
[アウト]レジストリ キーから読み取られた値を受け取る文字列配列変数への参照。

*ドフアレイ*<br/>
[アウト]レジストリ キーから読み取られた値を受け取る 32 ビットのダブル ワード配列変数への参照。

*を実行する*<br/>
[アウト]レジストリ キーから読み取られた値を受け取る 16 ビットワード配列変数への参照。

*bcアレイ*<br/>
[アウト]レジストリ キーから読み取られた値を受け取るバイト配列変数への参照。

*lpPoint*<br/>
[アウト]レジストリ キーから読み`POINT`取られた値を受け取る構造体へのポインターへの参照。

*Rect*<br/>
[アウト]レジストリ キーから読み取られた値を受け取る[CRect](../../atl-mfc-shared/reference/crect-class.md)変数への参照。

*Ppdata*<br/>
[アウト]レジストリ キーから読み取られた値を受け取るデータへのポインターへのポインター。

*バイト数*<br/>
[アウト]符号なし整数変数へのポインター。 この変数は *、ppData*が指すバッファのサイズを受け取ります。

*list*<br/>
[アウト]レジストリ キーから読み取った値を受け取る[CObList](../../mfc/reference/coblist-class.md)変数への参照。

*obj*<br/>
[アウト]レジストリ キーから読み取られた値を受け取る[CObject](../../mfc/reference/cobject-class.md)変数への参照。

*を使用します。*<br/>
[アウト]レジストリ キーから読み`CObject`取られた値を受け取る変数へのポインターへの参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`Read`のサブ*キーとして pszKey*を`m_hKey`チェックします。

## <a name="csettingsstorewrite"></a><a name="write"></a>書き込み

開いているキーの下のレジストリに値を書き込みます。

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

*キー*<br/>
[in]設定する値の名前を含む文字列へのポインター。

*iVal*<br/>
[in]格納するデータを格納する整数変数への参照。

*ドヴァル*<br/>
[in]格納するデータを格納する 32 ビットのダブル ワード変数への参照。

*pszVal*<br/>
[in]格納するデータを格納する null で終わる文字列変数へのポインター。

*一覧*<br/>
[in]格納するデータを格納する[CStringList](../../mfc/reference/cstringlist-class.md)変数への参照。

*bcアレイ*<br/>
[in]格納するデータを格納するバイト配列変数への参照。

*scアレイ*<br/>
[in]格納するデータを格納する文字列配列変数への参照。

*ドフアレイ*<br/>
[in]格納するデータを格納する 32 ビットのダブル ワード配列変数への参照。

*を実行する*<br/>
[in]格納するデータを格納する 16 ビットワード配列変数への参照。

*Rect*<br/>
[in]格納するデータを格納する[CRect](../../atl-mfc-shared/reference/crect-class.md)変数への参照。

*lpPoint*<br/>
[in]格納するデータを`POINT`格納する変数へのポインターへの参照。

*Pdata*<br/>
[in]格納するデータを格納するバッファーへのポインター。

*Nbytes*<br/>
[in]*pData*パラメーターが指すデータのサイズをバイト単位で指定します。

*list*<br/>
[in]格納するデータを格納する[CObList](../../mfc/reference/coblist-class.md)変数への参照。

*obj*<br/>
[in]格納するデータを格納する[CObject](../../mfc/reference/cobject-class.md)変数への参照。

*を使用します。*<br/>
[in]格納するデータを`CObject`格納する変数へのポインターへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

レジストリに書き込むには[、CSettingsStore](../../mfc/reference/csettingsstore-class.md)オブジェクトを作成するときに、0 以外の値に*bReadOnly*を設定する必要があります。 詳細については[、「CSettings ストア::CSettings ストア](#csettingsstore)」を参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
