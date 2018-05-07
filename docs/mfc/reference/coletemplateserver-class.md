---
title: COleTemplateServer クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
dev_langs:
- C++
helpviewer_keywords:
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90b24d65dbd6f800dda0b25088288bee6fdcf3c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="coletemplateserver-class"></a>COleTemplateServer クラス
OLE のビジュアル編集サーバー、オートメーション サーバー、およびリンク コンテナー (埋め込みアイテムへのリンクをサポートするアプリケーションのことです) で使います。  
  
## <a name="syntax"></a>構文  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|`COleTemplateServer` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|ドキュメント テンプレートを基になる接続`COleObjectFactory`オブジェクト。|  
|[COleTemplateServer::Unregister](#unregister)|関連付けられたドキュメント テンプレートの登録を解除します。|  
|[COleTemplateServer::UpdateRegistry](#updateregistry)|OLE システム レジストリをドキュメントの種類を登録します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、クラスから派生[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)以外の場合は通常、使用することができます`COleTemplateServer`独自のクラスを派生するのではなく、直接です。 `COleTemplateServer` 使用して、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)サーバー ドキュメントを管理するオブジェクト。 使用して`COleTemplateServer`スタンドアロン アプリケーションとして実行できるサーバーは、サーバー全体を実装する場合。 フル サーバーは、シングル ドキュメント インターフェイス (SDI) アプリケーションはサポートされていますが、マルチ ドキュメント インターフェイス (MDI) アプリケーションでは、通常します。 1 つ`COleTemplateServer`アプリケーションをサポートしているサーバー ドキュメントの種類ごとにオブジェクトが必要です。 つまり、サーバー アプリケーションは、ワークシートとグラフの両方をサポートする場合必要がありますに 2 つ`COleTemplateServer`オブジェクト。  
  
 `COleTemplateServer` 上書き、`OnCreateInstance`によって定義されたメンバー関数`COleObjectFactory`です。 このメンバー関数は、適切な型の C++ オブジェクトを作成するためにフレームワークによって呼び出されます。  
  
 サーバーの詳細については、記事を参照してください。[サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="coletemplateserver"></a>  COleTemplateServer::COleTemplateServer  
 `COleTemplateServer` オブジェクトを構築します。  
  
```  
COleTemplateServer();
```  
  
### <a name="remarks"></a>コメント  
 使用した簡単な説明、`COleTemplateServer`クラスを参照してください、[直接](../../mfc/reference/colelinkingdoc-class.md)クラスの概要です。  
  
##  <a name="connecttemplate"></a>  COleTemplateServer::ConnectTemplate  
 接続によって示されるドキュメント テンプレート`pDocTemplate`基になる[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)オブジェクト。  
  
```  
void ConnectTemplate(
    REFCLSID clsid,  
    CDocTemplate* pDocTemplate,  
    BOOL bMultiInstance);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 テンプレートを要求する OLE クラス ID への参照。  
  
 `pDocTemplate`  
 ドキュメント テンプレートへのポインター。  
  
 `bMultiInstance`  
 アプリケーションの 1 つのインスタンスが複数のインスタンスをサポートできるかどうかを示します。 場合**TRUE**オブジェクトを作成するには、各要求に対して、アプリケーションの複数のインスタンスを起動します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK に含まれています。  
  
##  <a name="unregister"></a>  COleTemplateServer::Unregister  
 関連付けられたドキュメント テンプレートの登録を解除します。  
  
```  
BOOL Unregister();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 EnterRemarks  
  
##  <a name="updateregistry"></a>  COleTemplateServer::UpdateRegistry  
 ドキュメント テンプレート文字列からファイルの種類の情報を読み込んで OLE システム レジストリに格納します。  
  
```  
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL,  
    BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAppType`  
 値、 **OLE_APPTYPE**列挙体、列挙子。H. 次の値のいずれかを取ります。  
  
- `OAT_INPLACE_SERVER` サーバーには、サーバー全体のユーザー インターフェイスがあります。  
  
- `OAT_SERVER` サーバーは、埋め込みだけをサポートします。  
  
- `OAT_CONTAINER` コンテナーは、埋め込みオブジェクトへのリンクをサポートします。  
  
- `OAT_DISPATCH_OBJECT` オブジェクトが`IDispatch`に対応します。  
  
- **OAT_DOC_OBJECT_SERVER**サーバーでは、両方がサポートを埋め込むと、ドキュメント オブジェクト コンポーネント モデル。  
  
 `rglpszRegister`  
 エントリが存在しない場合にのみ、レジストリに書き込まれるエントリの一覧です。  
  
 `rglpszOverwrite`  
 既にエントリが存在するかどうかに関係なく、レジストリに書き込まれるエントリの一覧です。  
  
 `bRegister`  
 クラスを登録するかどうかを判断します。 場合`bRegister`は**TRUE**クラスは、システム レジストリに登録されています。 それ以外の場合、クラスが登録解除します。  
  
### <a name="remarks"></a>コメント  
 呼び出しを使用して、登録情報が読み込まれる[CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)です。 取得した部分文字列がインデックスによって識別される、**取り出さ**、 **regFileTypeName**、および**fileNewName**で説明されている、 `GetDocString`ページを参照します。  
  
 場合、**取り出さ**部分文字列が空またはへの呼び出し`GetDocString`何らかの理由、この関数が失敗し、レジストリで、ファイルの情報が入力されていません。  
  
 引数の情報は、`rglpszRegister`と`rglpszOverwrite`を呼び出すことによって、レジストリに書き込まれる[AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass)です。 既定の情報が登録されているは、次の 2 つの引数が**NULL**、ほとんどのアプリケーションに適しています。 これらの引数内の情報の構造については、次を参照してください。`AfxOleRegisterServerClass`です。  
  
 詳細については、「 [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [COleObjectFactory クラス](../../mfc/reference/coleobjectfactory-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)   
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)
