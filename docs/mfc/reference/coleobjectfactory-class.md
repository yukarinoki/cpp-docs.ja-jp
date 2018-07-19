---
title: COleObjectFactory クラス |Microsoft Docs
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
ms.openlocfilehash: 4d2ac698466709931259f1df28d6c75aa38b30f2
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850707"
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
|[COleObjectFactory::GetClassID](#getclassid)|返します、OLE クラスのこのファクトリを作成するオブジェクトの ID。|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|コントロールのライセンスが有効であるかを決定します。|  
|[COleObjectFactory::IsRegistered](#isregistered)|OLE システム Dll オブジェクト ファクトリを登録するかどうかを示します。|  
|[COleObjectFactory::Register](#register)|OLE システム Dll をこのオブジェクトのファクトリを登録します。|  
|[COleObjectFactory::RegisterAll](#registerall)|OLE システム Dll には、すべてのアプリケーションのオブジェクト ファクトリを登録します。|  
|[COleObjectFactory::Revoke](#revoke)|OLE システム Dll のオブジェクト ファクトリの登録を取り消します。|  
|[COleObjectFactory::RevokeAll](#revokeall)|OLE システム Dll を持つアプリケーションのオブジェクト ファクトリの登録を取り消します。|  
|[COleObjectFactory::UnregisterAll](#unregisterall)|すべてのアプリケーションのオブジェクト ファクトリを登録解除します。|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|このオブジェクトのファクトリを OLE システム レジストリに登録します。|  
|[されます](#updateregistryall)|OLE システム レジストリには、すべてのアプリケーションのオブジェクト ファクトリを登録します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|コントロールの DLL からの一意のキーを要求します。|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|このファクトリの型の新しいオブジェクトを作成するためにフレームワークによって呼び出されます。|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|コントロールに埋め込まれたキーが、コンテナーに埋め込まれたキーと一致することを確認します。|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|コントロールがデザイン時の使用ライセンスされていることを確認します。|  
  
## <a name="remarks"></a>Remarks  
 `COleObjectFactory`クラスには、次の関数を実行するためのメンバー関数。  
  
-   オブジェクトの登録を管理します。  
  
-   OLE システム レジスタとランタイムの登録オブジェクトが実行しているし、メッセージを受信する準備を更新しています。  
  
-   ライセンスを付与された開発者は設計時および実行時にライセンスされたアプリケーションにコントロールの使用を制限することでライセンス処理を実行します。  
  
-   OLE システム レジストリには、コントロールのオブジェクト ファクトリを登録しています。  
  
 オブジェクトの作成の詳細については、記事をご覧ください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)と[データ オブジェクトとデータ ソース: 作成と破棄](../../mfc/data-objects-and-data-sources-creation-and-destruction.md)します。 登録の詳細については「[登録](../../mfc/registration.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory  
 構築、`COleObjectFactory`オブジェクトとして登録されていないオブジェクト ファクトリを初期化およびファクトリの一覧に追加します。  
  
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
 *clsid*  
 OLE クラス ID オブジェクト ファクトリをこのへの参照を表します。  
  
 *pRuntimeClass*  
 C のランタイム クラスへのポインター オブジェクトをこのファクトリを作成できます。  
  
 *bMultiInstance*  
 アプリケーションの 1 つのインスタンスが複数のインスタンスをサポートできるかどうかを示します。 TRUE の場合は、オブジェクトを作成するには、各要求に対して、アプリケーションの複数のインスタンスが起動されます。  
  
 *nFlags*  
 次のフラグの 1 つ以上含まれています。  
  
- `afxRegDefault` 指定する ThreadingModel スレッド処理モデル アパートメントを = です。  
  
- `afxRegInsertable` により、コントロールを表示する、**オブジェクトの挿入**OLE オブジェクトのダイアログ ボックス。  
  
- `afxRegApartmentThreading` ThreadingModel レジストリ内のスレッド処理モデルの設定アパートメントを = です。  
  
- `afxRegFreeThreading` スレッド処理モデルを ThreadingModel をレジストリに設定する Free を =。  
  
     2 つのフラグを結合する`afxRegApartmentThreading`と`afxRegFreeThreading`ThreadingModel を設定する = Both。 参照してください[InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390)スレッド モデルの登録の詳細については、Windows SDK に含まれています。  
  
 *lpszProgID*  
 "Excel"などの口頭でのプログラム識別子を含む文字列へのポインター  
  
### <a name="remarks"></a>Remarks  
 オブジェクトを使用して、ただし、する必要がありますに登録します。  
  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK に含まれています。  
  
##  <a name="getclassid"></a>  COleObjectFactory::GetClassID  
 このファクトリを表す OLE クラス ID への参照を返します。  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE クラス ID このファクトリへの参照を表します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK に含まれています。  
  
##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey  
 コントロールの DLL から固有のライセンス キーを要求し、指す BSTR に格納*pbstrKey*します。  
  
```  
virtual BOOL GetLicenseKey(
    DWORD dwReserved,  
    BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwReserved*  
 将来使用するために予約されています。  
  
 *pbstrKey*  
 ライセンス キーを保存する BSTR へのポインター。  
  
### <a name="return-value"></a>戻り値  
 ライセンス キーの文字列が NULL 以外ではない場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装は、0 を返し、BSTR に何も格納します。 MFC ActiveX ControlWizard をプロジェクトの作成に使用する場合、ControlWizard はコントロールのライセンス キーを取得する上書きを提供します。  
  
##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid  
 コントロールのライセンスが有効であるかを決定します。  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合は正常それ以外の場合は false。  
  
##  <a name="isregistered"></a>  COleObjectFactory::IsRegistered  
 OLE システム Dll、ファクトリが登録されている場合は、0 以外の値を返します。  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファクトリが登録されている場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject  
 新しいオブジェクトを作成するためにフレームワークによって呼び出されます。  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>戻り値  
 作成されたオブジェクトへのポインター。 失敗した場合、メモリ不足例外をスローされることです。  
  
### <a name="remarks"></a>Remarks  
 以外のものから、オブジェクトを作成するには、この関数をオーバーライド、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)コンス トラクターに渡されます。  
  
##  <a name="register"></a>  COleObjectFactory::Register  
 OLE システム Dll をこのオブジェクトのファクトリを登録します。  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ファクトリが正常に登録します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は通常、によって呼び出されます。 [:initinstance](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーションが起動したときにします。  
  
##  <a name="registerall"></a>  COleObjectFactory::RegisterAll  
 OLE システム Dll には、すべてのアプリケーションのオブジェクト ファクトリを登録します。  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ファクトリが正常に登録されています。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は通常、によって呼び出されます。 [:initinstance](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーションが起動したときにします。  
  
##  <a name="revoke"></a>  COleObjectFactory::Revoke  
 OLE システム Dll のオブジェクト ファクトリの登録を取り消します。  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、アプリケーションが終了する前に、この関数を自動的に呼び出します。 必要に応じてからのオーバーライドを呼び出す[し](../../mfc/reference/cwinapp-class.md#exitinstance)します。  
  
##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll  
 すべての OLE システム Dll を持つアプリケーションのオブジェクト ファクトリの登録を取り消します。  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、アプリケーションが終了する前に、この関数を自動的に呼び出します。 必要に応じてからのオーバーライドを呼び出す[し](../../mfc/reference/cwinapp-class.md#exitinstance)します。  
  
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
 *lpszProgID*  
 "Excel.Document.5"など、人間が判読できるプログラム識別子を含む文字列へのポインター  
  
 *bRegister*  
 コントロール クラスのオブジェクト ファクトリを登録するかどうかを判断します。  
  
### <a name="remarks"></a>Remarks  
 この関数の 2 つの形式の簡単な説明に従います。  
  
- **Updateregistry に (** `lpszProgID` **)** OLE システム レジストリでこのオブジェクトのファクトリを登録します。 この関数は通常、によって呼び出されます。 [:initinstance](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーションが起動したときにします。  
  
- **Updateregistry に (** `bRegister` **)** 関数のこの形式はオーバーライド可能な。 場合*bRegister*は TRUE、コントロール クラスのシステム レジストリでこの関数のレジスタです。 それ以外の場合、クラスが登録解除します。  
  
     MFC ActiveX ControlWizard をプロジェクトの作成に使用する場合、ControlWizard には、この純粋仮想関数をオーバーライドが用意されています。  
  
##  <a name="updateregistryall"></a>  されます  
 OLE システム レジストリには、すべてのアプリケーションのオブジェクト ファクトリを登録します。  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bRegister*  
 コントロール クラスのオブジェクト ファクトリを登録するかどうかを判断します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ファクトリが正常に更新されました。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は通常、によって呼び出されます。 [:initinstance](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーションが起動したときにします。  
  
##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey  
 OLE コントロールを使用して、コンテナーがライセンスされていることを確認します。  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrKey*  
 ライセンス文字列のコンテナーのバージョンを格納する BSTR。  
  
### <a name="return-value"></a>戻り値  
 実行時のライセンスが有効な場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 既定のバージョン[GetLicenseKey](#getlicensekey)コントロールのコピーを取得するのライセンスの文字列と内の文字列比較*bstrKey*します。 0 以外の値を返します 2 つの文字列が一致する場合それ以外の場合 0 を返します。  
  
 ライセンスの確認方法をカスタマイズするには、この関数をオーバーライドすることができます。  
  
 関数は、 [VerifyUserLicense](#verifyuserlicense)デザイン時ライセンスを確認します。  
  
##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense  
 OLE コントロールのデザイン時ライセンスを確認します。  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>戻り値  
 デザイン時ライセンスが有効な場合は 0 以外それ以外の場合 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)
