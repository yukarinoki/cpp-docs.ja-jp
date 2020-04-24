---
title: COleObjectFactory クラス
ms.date: 11/04/2016
f1_keywords:
- COleObjectFactory
- AFXDISP/COleObjectFactory
- AFXDISP/COleObjectFactory::COleObjectFactory
- AFXDISP/COleObjectFactory::GetClassID
- AFXDISP/COleObjectFactory::IsLicenseValid
- AFXDISP/COleObjectFactory::IsRegistered
- AFXDISP/COleObjectFactory::Register
- AFXDISP/COleObjectFactory::RegisterAll
- AFXDISP/COleObjectFactory::Revoke
- AFXDISP/COleObjectFactory::RevokeAll
- AFXDISP/COleObjectFactory::UnregisterAll
- AFXDISP/COleObjectFactory::UpdateRegistry
- AFXDISP/COleObjectFactory::UpdateRegistryAll
- AFXDISP/COleObjectFactory::GetLicenseKey
- AFXDISP/COleObjectFactory::OnCreateObject
- AFXDISP/COleObjectFactory::VerifyLicenseKey
- AFXDISP/COleObjectFactory::VerifyUserLicense
helpviewer_keywords:
- COleObjectFactory [MFC], COleObjectFactory
- COleObjectFactory [MFC], GetClassID
- COleObjectFactory [MFC], IsLicenseValid
- COleObjectFactory [MFC], IsRegistered
- COleObjectFactory [MFC], Register
- COleObjectFactory [MFC], RegisterAll
- COleObjectFactory [MFC], Revoke
- COleObjectFactory [MFC], RevokeAll
- COleObjectFactory [MFC], UnregisterAll
- COleObjectFactory [MFC], UpdateRegistry
- COleObjectFactory [MFC], UpdateRegistryAll
- COleObjectFactory [MFC], GetLicenseKey
- COleObjectFactory [MFC], OnCreateObject
- COleObjectFactory [MFC], VerifyLicenseKey
- COleObjectFactory [MFC], VerifyUserLicense
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
ms.openlocfilehash: 165ba7c1918c3ccc5d5d7e0bc067fba86678a3e7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753808"
---
# <a name="coleobjectfactory-class"></a>COleObjectFactory クラス

OLE クラスのファクトリを実装しています。このクラスによって、サーバー、オートメーション オブジェクト、ドキュメントなどの OLE オブジェクトを作成できます。

## <a name="syntax"></a>構文

```
class COleObjectFactory : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[オブジェクトファクトリ::オブジェクトファクトリ](#coleobjectfactory)|`COleObjectFactory` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クラスの数を取得します。](#getclassid)|このファクトリが作成するオブジェクトの OLE クラス ID を返します。|
|[コンポーネントファクトリー::ライセンス有効](#islicensevalid)|コントロールのライセンスが有効かどうかを判断します。|
|[オブジェクトファクトリ::が登録されています。](#isregistered)|オブジェクト ファクトリが OLE システム DLL に登録されているかどうかを示します。|
|[オブジェクトファクトリ::レジスタ](#register)|このオブジェクト ファクトリを OLE システム DLL に登録します。|
|[すべてのオブジェクトの工場を登録します。](#registerall)|アプリケーションのすべてのオブジェクト ファクトリを OLE システム DLL に登録します。|
|[オブジェクトファクトリ::取り消し](#revoke)|OLE システム DLL に対するこのオブジェクト ファクトリの登録を取り消します。|
|[すべての取り消し](#revokeall)|OLE システム DLL に対するアプリケーションのオブジェクト ファクトリの登録を取り消します。|
|[すべての登録を解除します。](#unregisterall)|アプリケーションのオブジェクト ファクトリをすべて登録解除します。|
|[コンポーネントのファクトリ::レジストリの更新](#updateregistry)|このオブジェクト ファクトリを OLE システム レジストリに登録します。|
|[すべてのオブジェクトの工場::更新プログラム](#updateregistryall)|アプリケーションのすべてのオブジェクト ファクトリを OLE システム レジストリに登録します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[コンポーネントのファクトリ::ライセンスキーを取得します。](#getlicensekey)|コントロールの DLL に一意のキーを要求します。|
|[オブジェクトの作成](#oncreateobject)|このファクトリの型の新しいオブジェクトを作成するために、フレームワークによって呼び出されます。|
|[コンポーネントの作成:ライセンスキーの確認](#verifylicensekey)|コントロールに埋め込まれたキーが、コンテナーに埋め込まれているキーと一致することを確認します。|
|[オブジェクトのファクトリ::ユーザーライセンスを確認します。](#verifyuserlicense)|コントロールがデザイン時に使用するためのライセンスを取得していることを確認します。|

## <a name="remarks"></a>解説

この`COleObjectFactory`クラスには、次の機能を実行するためのメンバー関数があります。

- オブジェクトの登録を管理します。

- OLE システム レジスタの更新、およびオブジェクトが実行中でメッセージを受信する準備ができていることを OLE に通知するランタイム登録を更新します。

- デザイン時にライセンスを持つ開発者と実行時にライセンスを持つアプリケーションに対して、コントロールの使用を制限することによってライセンスを強制する。

- OLE システム レジストリにコントロール オブジェクト ファクトリを登録しています。

オブジェクトの作成の詳細については、「[データ オブジェクトとデータ ソース (OLE)」](../../mfc/data-objects-and-data-sources-ole.md)および「[データ オブジェクトとデータ ソース: 作成と破棄](../../mfc/data-objects-and-data-sources-creation-and-destruction.md)」を参照してください。 登録の詳細については、記事「[登録](../../mfc/registration.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleObjectFactory`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="coleobjectfactorycoleobjectfactory"></a><a name="coleobjectfactory"></a>オブジェクトファクトリ::オブジェクトファクトリ

オブジェクトを`COleObjectFactory`構築し、未登録のオブジェクト ファクトリとして初期化し、ファクトリのリストに追加します。

```
COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    LPCTSTR lpszProgID);

COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    int nFlags,
    LPCTSTR lpszProgID);
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
このオブジェクト ファクトリが表す OLE クラス ID への参照。

*クラス*<br/>
このファクトリが作成できる C++ オブジェクトのランタイム クラスへのポインター。

*を使用します。*<br/>
アプリケーションの単一のインスタンスが複数のインスタンス化をサポートできるかどうかを示します。 TRUE の場合、オブジェクトを作成する要求ごとに、アプリケーションの複数のインスタンスが起動されます。

*Nflags*<br/>
次のフラグの 1 つ以上を含みます。

- `afxRegDefault`スレッド モデルをスレッドモデル=アパートメントに設定します。

- `afxRegInsertable`OLE オブジェクトの **[オブジェクトの挿入**] ダイアログ ボックスにコントロールを表示できるようにします。

- `afxRegApartmentThreading`レジストリのスレッド モデルをスレッドモデル=アパートメントに設定します。

- `afxRegFreeThreading`レジストリのスレッド モデルをスレッド処理モデル=Free に設定します。

   2 つのフラグ`afxRegApartmentThreading`を組み`afxRegFreeThreading`合わせて、ThreadingModel=Both を設定できます。 スレッド モデルの登録の詳細については、Windows SDK の[InprocServer32](/windows/win32/com/inprocserver32)を参照してください。

*をクリックします。*<br/>
"Excel" などの口頭でのプログラム識別子を含む文字列へのポインター。

### <a name="remarks"></a>解説

ただし、オブジェクトを使用するには、オブジェクトを登録する必要があります。

詳細については、Windows SDK[の CLSID キー](/windows/win32/com/clsid-key-hklm)を参照してください。

## <a name="coleobjectfactorygetclassid"></a><a name="getclassid"></a>クラスの数を取得します。

このファクトリが表す OLE クラス ID への参照を返します。

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>戻り値

このファクトリが表す OLE クラス ID への参照。

### <a name="remarks"></a>解説

詳細については、Windows SDK[の CLSID キー](/windows/win32/com/clsid-key-hklm)を参照してください。

## <a name="coleobjectfactorygetlicensekey"></a><a name="getlicensekey"></a>コンポーネントのファクトリ::ライセンスキーを取得します。

コントロールの DLL から一意のライセンス キーを要求し、 *pbstrKey*が指す BSTR に格納します。

```
virtual BOOL GetLicenseKey(
    DWORD dwReserved,
    BSTR* pbstrKey);
```

### <a name="parameters"></a>パラメーター

*dw予約済み*<br/>
将来利用するために予約されています。

*pbstrキー*<br/>
ライセンス キーを格納する BSTR へのポインター。

### <a name="return-value"></a>戻り値

ライセンス キー文字列が NULL でない場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数の既定の実装では 0 が返され、BSTR には何も格納されません。 MFC ActiveX コントロール ウィザードを使用してプロジェクトを作成する場合、コントロールのライセンス キーを取得するオーバーライドが提供されます。

## <a name="coleobjectfactoryislicensevalid"></a><a name="islicensevalid"></a>コンポーネントファクトリー::ライセンス有効

コントロールのライセンスが有効かどうかを判断します。

```
BOOL IsLicenseValid();
```

### <a name="return-value"></a>戻り値

成功の場合は TRUE。それ以外の場合は false です。

## <a name="coleobjectfactoryisregistered"></a><a name="isregistered"></a>オブジェクトファクトリ::が登録されています。

ファクトリが OLE システム DLL に登録されている場合は、0 以外の値を返します。

```
virtual BOOL IsRegistered() const;
```

### <a name="return-value"></a>戻り値

ファクトリが登録されている場合は 0 以外。それ以外の場合は 0。

## <a name="coleobjectfactoryoncreateobject"></a><a name="oncreateobject"></a>オブジェクトの作成

新しいオブジェクトを作成するために、フレームワークによって呼び出されます。

```
virtual CCmdTarget* OnCreateObject();
```

### <a name="return-value"></a>戻り値

作成されたオブジェクトへのポインター。 失敗した場合は、メモリ例外をスローできます。

### <a name="remarks"></a>解説

コンストラクターに渡された[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)以外のオブジェクトを作成するには、この関数をオーバーライドします。

## <a name="coleobjectfactoryregister"></a><a name="register"></a>オブジェクトファクトリ::レジスタ

このオブジェクト ファクトリを OLE システム DLL に登録します。

```
virtual BOOL Register();
```

### <a name="return-value"></a>戻り値

ファクトリが正常に登録された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、通常、アプリケーションが起動されたときに[CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)によって呼び出されます。

## <a name="coleobjectfactoryregisterall"></a><a name="registerall"></a>すべてのオブジェクトの工場を登録します。

アプリケーションのすべてのオブジェクト ファクトリを OLE システム DLL に登録します。

```
static BOOL PASCAL RegisterAll();
```

### <a name="return-value"></a>戻り値

ファクトリが正常に登録された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、通常、アプリケーションが起動されたときに[CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)によって呼び出されます。

## <a name="coleobjectfactoryrevoke"></a><a name="revoke"></a>オブジェクトファクトリ::取り消し

OLE システム DLL に対するこのオブジェクト ファクトリの登録を取り消します。

```cpp
void Revoke();
```

### <a name="remarks"></a>解説

フレームワークは、アプリケーションが終了する前に、この関数を自動的に呼び出します。 必要に応じて[、CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)のオーバーライドから呼び出します。

## <a name="coleobjectfactoryrevokeall"></a><a name="revokeall"></a>すべての取り消し

OLE システム DLL に対するアプリケーションのオブジェクト ファクトリの登録をすべて取り消します。

```
static void PASCAL RevokeAll();
```

### <a name="remarks"></a>解説

フレームワークは、アプリケーションが終了する前に、この関数を自動的に呼び出します。 必要に応じて[、CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)のオーバーライドから呼び出します。

## <a name="coleobjectfactoryunregisterall"></a><a name="unregisterall"></a>すべての登録を解除します。

アプリケーションのオブジェクト ファクトリをすべて登録解除します。

```
static BOOL PASCAL UnregisterAll();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

## <a name="coleobjectfactoryupdateregistry"></a><a name="updateregistry"></a>コンポーネントのファクトリ::レジストリの更新

アプリケーションのすべてのオブジェクト ファクトリを OLE システム レジストリに登録します。

```cpp
void UpdateRegistry(LPCTSTR lpszProgID = NULL);
virtual BOOL UpdateRegistry(BOOL bRegister);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
"Excel.Document.5" など、人間が判読できるプログラム識別子を含む文字列へのポインター。

*b登録*<br/>
コントロール クラスのオブジェクト ファクトリを登録するかどうかを決定します。

### <a name="remarks"></a>解説

この関数の 2 つの形式の簡単な説明は次のとおりです。

- **アップデートレジストリ(** `lpszProgID` **)** このオブジェクト ファクトリを OLE システム レジストリに登録します。 この関数は、通常、アプリケーションが起動されたときに[CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)によって呼び出されます。

- **アップデートレジストリ(** `bRegister` **)** この形式の関数はオーバーライド可能です。 *bRegister*が TRUE の場合、この関数はコントロール クラスをシステム レジストリに登録します。 それ以外の場合は、クラスの登録を解除します。

   MFC ActiveX コントロール ウィザードを使用してプロジェクトを作成する場合、この純粋仮想関数にオーバーライドが提供されます。

## <a name="coleobjectfactoryupdateregistryall"></a><a name="updateregistryall"></a>すべてのオブジェクトの工場::更新プログラム

アプリケーションのすべてのオブジェクト ファクトリを OLE システム レジストリに登録します。

```
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```

### <a name="parameters"></a>パラメーター

*b登録*<br/>
コントロール クラスのオブジェクト ファクトリを登録するかどうかを決定します。

### <a name="return-value"></a>戻り値

ファクトリが正常に更新された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、通常、アプリケーションが起動されたときに[CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)によって呼び出されます。

## <a name="coleobjectfactoryverifylicensekey"></a><a name="verifylicensekey"></a>コンポーネントの作成:ライセンスキーの確認

コンテナーが OLE コントロールを使用するためのライセンスを持っていることを確認します。

```
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
コンテナーのライセンス文字列のバージョンを格納する BSTR。

### <a name="return-value"></a>戻り値

ランタイム ライセンスが有効な場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

既定のバージョンでは[、GetLicenseKey](#getlicensekey)を呼び出してコントロールのライセンス文字列のコピーを取得し、それを*bstrKey*の文字列と比較します。 2 つの文字列が一致する場合、この関数は 0 以外の値を返します。それ以外の場合は 0 を返します。

この機能をオーバーライドして、ライセンスの検証をカスタマイズできます。

関数[は、](#verifyuserlicense)デザイン時ライセンスを検証します。

## <a name="coleobjectfactoryverifyuserlicense"></a><a name="verifyuserlicense"></a>オブジェクトのファクトリ::ユーザーライセンスを確認します。

OLE コントロールのデザイン時ライセンスを検証します。

```
virtual BOOL VerifyUserLicense();
```

### <a name="return-value"></a>戻り値

デザイン時ライセンスが有効な場合は 0 以外。それ以外の場合は 0。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)
