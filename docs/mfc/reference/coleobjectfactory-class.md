---
title: COleObjectFactory クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd68493c9be5eb0bff63504cf49b38b9a2f216d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375938"
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
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|`COleObjectFactory` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleObjectFactory::GetClassID](#getclassid)|返します OLE クラスのこのファクトリを作成するオブジェクトの ID。|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|コントロールのライセンスが有効なかどうかを判断します。|  
|[COleObjectFactory::IsRegistered](#isregistered)|OLE システム Dll オブジェクト ファクトリを登録するかどうかを示します。|  
|[COleObjectFactory::Register](#register)|OLE システム Dll をこのオブジェクト ファクトリを登録します。|  
|[COleObjectFactory::RegisterAll](#registerall)|OLE システム Dll には、すべてのアプリケーションのオブジェクト ファクトリを登録します。|  
|[COleObjectFactory::Revoke](#revoke)|OLE システム Dll でのオブジェクト ファクトリの登録を取り消します。|  
|[COleObjectFactory::RevokeAll](#revokeall)|OLE システム Dll を含む、アプリケーションのオブジェクト ファクトリの登録を取り消します。|  
|[COleObjectFactory::UnregisterAll](#unregisterall)|すべてのアプリケーションのオブジェクト ファクトリを登録解除します。|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|OLE システム レジストリをこのオブジェクト ファクトリを登録します。|  
|[されます](#updateregistryall)|OLE システム レジストリには、すべてのアプリケーションのオブジェクト ファクトリを登録します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|コントロールの DLL からの一意のキーを要求します。|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|このファクトリの型の新しいオブジェクトを作成するためにフレームワークによって呼び出されます。|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|コンテナーに埋め込まれたキーがコントロールに埋め込まれたキーに一致することを確認します。|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|コントロールがデザイン時の使用ライセンスされていることを確認します。|  
  
## <a name="remarks"></a>コメント  
 `COleObjectFactory`クラスには、次の関数を実行するためのメンバー関数。  
  
-   オブジェクトの登録を管理します。  
  
-   OLE システム レジスタとランタイムの登録オブジェクトを実行しているし、メッセージを受信する準備ができたことを更新しています。  
  
-   デザイン時ライセンスを受けた開発者および実行時にライセンスされたアプリケーションにコントロールの使用を制限することでライセンス処理を実行します。  
  
-   OLE システム レジストリにコントロールのオブジェクト ファクトリを登録しています。  
  
 オブジェクトの作成の詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)と[データ オブジェクトとデータ ソース: 作成と破棄](../../mfc/data-objects-and-data-sources-creation-and-destruction.md)です。 登録の詳細については「[登録](../../mfc/registration.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory  
 構築、`COleObjectFactory`オブジェクトとして登録されていないオブジェクト ファクトリを初期化し、ファクトリのリストに追加します。  
  
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
 `clsid`  
 OLE クラス ID このオブジェクトのファクトリへの参照を表します。  
  
 `pRuntimeClass`  
 このファクトリが作成できる C++ オブジェクトのランタイム クラスへのポインター。  
  
 `bMultiInstance`  
 アプリケーションの 1 つのインスタンスが複数のインスタンスをサポートできるかどうかを示します。 場合**TRUE**オブジェクトを作成するには、各要求に対して、アプリケーションの複数のインスタンスを起動します。  
  
 `nFlags`  
 次のフラグの 1 つ以上含まれています。  
  
- **afxRegDefault** ThreadingModel をスレッディング モデルを設定アパートメントを = です。  
  
- **afxRegInsertable**により、コントロールに表示される、**オブジェクトの挿入**OLE オブジェクトのダイアログ ボックス。  
  
- `afxRegApartmentThreading` スレッド処理モデルを ThreadingModel をレジストリに設定アパートメントを = です。  
  
- **afxRegFreeThreading** ThreadingModel をレジストリで、スレッディング モデルを設定空きを = です。  
  
     2 つのフラグを組み合わせることができます`afxRegApartmentThreading`と`afxRegFreeThreading`ThreadingModel を設定する = Both です。 参照してください[InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390)スレッド処理モデルの登録の詳細について Windows SDK に含まれています。  
  
 `lpszProgID`  
 "Excel"などの口頭でのプログラム識別子を含む文字列へのポインター  
  
### <a name="remarks"></a>コメント  
 オブジェクトを使用して、ただし、必要がありますに登録します。  
  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK に含まれています。  
  
##  <a name="getclassid"></a>  COleObjectFactory::GetClassID  
 このファクトリが表す OLE クラス ID への参照を返します。  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE クラス ID このファクトリへの参照を表します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK に含まれています。  
  
##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey  
 コントロールの DLL から一意のライセンス キーを要求しに格納、`BSTR`によって示される`pbstrKey`です。  
  
```  
virtual BOOL GetLicenseKey(
    DWORD dwReserved,  
    BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwReserved`  
 将来使用するために予約されています。  
  
 `pbstrKey`  
 ポインター、`BSTR`ライセンス キーを格納します。  
  
### <a name="return-value"></a>戻り値  
 ライセンス キー文字列がない場合は 0 以外。 **NULL**。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は 0 を返しでは nothing を格納、`BSTR`です。 MFC ActiveX ControlWizard を使用して、プロジェクトを作成する場合、ControlWizard はコントロールのライセンス キーを取得するオーバーライドを提供します。  
  
##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid  
 コントロールのライセンスが有効なかどうかを判断します。  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合正常です。それ以外の場合は false。  
  
##  <a name="isregistered"></a>  COleObjectFactory::IsRegistered  
 OLE システム Dll にファクトリが登録されている場合は、0 以外の値を返します。  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファクトリが登録されている場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject  
 新しいオブジェクトを作成するためにフレームワークによって呼び出されます。  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>戻り値  
 作成されたオブジェクトへのポインター。 失敗した場合は、メモリ例外をスロー、ことができます。  
  
### <a name="remarks"></a>コメント  
 以外のものからオブジェクトを作成するには、この関数をオーバーライドして、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)コンス トラクターに渡されます。  
  
##  <a name="register"></a>  COleObjectFactory::Register  
 OLE システム Dll をこのオブジェクト ファクトリを登録します。  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>戻り値  
 ファクトリが登録できた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常、この関数は呼び出されます。[場合は](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーションが起動した場合。  
  
##  <a name="registerall"></a>  COleObjectFactory::RegisterAll  
 OLE システム Dll には、すべてのアプリケーションのオブジェクト ファクトリを登録します。  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>戻り値  
 ファクトリが登録できた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常、この関数は呼び出されます。[場合は](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーションが起動した場合。  
  
##  <a name="revoke"></a>  COleObjectFactory::Revoke  
 OLE システム Dll でのオブジェクト ファクトリの登録を取り消します。  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、アプリケーションが終了する前に自動的にこの関数を呼び出します。 必要に応じてのオーバーライドから呼び出す[し](../../mfc/reference/cwinapp-class.md#exitinstance)です。  
  
##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll  
 すべての OLE システム Dll を含む、アプリケーションのオブジェクト ファクトリの登録を取り消します。  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、アプリケーションが終了する前に自動的にこの関数を呼び出します。 必要に応じてのオーバーライドから呼び出す[し](../../mfc/reference/cwinapp-class.md#exitinstance)です。  
  
##  <a name="unregisterall"></a>  COleObjectFactory::UnregisterAll  
 すべてのアプリケーションのオブジェクト ファクトリを登録解除します。  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE、それ以外の場合は FALSE。  
  
##  <a name="updateregistry"></a>  COleObjectFactory::UpdateRegistry  
 OLE システム レジストリには、すべてのアプリケーションのオブジェクト ファクトリを登録します。  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProgID`  
 "Excel.Document.5"など、人間が判読できるプログラム識別子を表す文字列へのポインター  
  
 `bRegister`  
 コントロール クラスのオブジェクト ファクトリを登録するかどうかを判断します。  
  
### <a name="remarks"></a>コメント  
 この関数の 2 つの形式の簡単な説明に従ってください。  
  
- **Updateregistry に (** `lpszProgID` **)** OLE システム レジストリにこのオブジェクト ファクトリを登録します。 通常、この関数は呼び出されます。[場合は](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーションが起動した場合。  
  
- **Updateregistry に (** `bRegister` **)** 関数のこの形式はオーバーライド可能です。 場合`bRegister`は**TRUE**、この関数は、システム レジストリで、コントロール クラスを登録します。 それ以外の場合、クラスが登録解除します。  
  
     MFC ActiveX ControlWizard を使用して、プロジェクトを作成する場合、ControlWizard はこの純粋仮想関数をオーバーライドを提供します。  
  
##  <a name="updateregistryall"></a>  されます  
 OLE システム レジストリには、すべてのアプリケーションのオブジェクト ファクトリを登録します。  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegister`  
 コントロール クラスのオブジェクト ファクトリを登録するかどうかを判断します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ファクトリは正常に更新されました。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常、この関数は呼び出されます。[場合は](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーションが起動した場合。  
  
##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey  
 OLE コントロールを使用して、コンテナーがライセンスされていることを確認します。  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrKey`  
 A`BSTR`ライセンス文字列のコンテナーのバージョンを格納します。  
  
### <a name="return-value"></a>戻り値  
 実行時ライセンスが無効である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定のバージョン[GetLicenseKey](#getlicensekey)コントロールのコピーを取得するのライセンス文字列と比較した文字列内で`bstrKey`です。 0 以外の値を返します 2 つの文字列が一致する場合それ以外の場合 0 を返します。  
  
 ライセンスの確認方法をカスタマイズするには、この関数をオーバーライドすることができます。  
  
 関数は、 [VerifyUserLicense](#verifyuserlicense)デザイン時ライセンスを確認します。  
  
##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense  
 OLE コントロールのデザイン時ライセンスを確認します。  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>戻り値  
 デザイン時ライセンスが無効である場合は 0 以外。それ以外の場合 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)
