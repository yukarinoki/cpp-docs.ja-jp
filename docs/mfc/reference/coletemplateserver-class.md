---
title: COleTemplateServer クラス
ms.date: 11/04/2016
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
helpviewer_keywords:
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
ms.openlocfilehash: 3abdf1dc2da5ef9a111371b501d5cd8ce208825d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781212"
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
|[COleTemplateServer::Unregister](#unregister)|関連付けられたドキュメント テンプレートを登録解除します。|
|[COleTemplateServer::UpdateRegistry](#updateregistry)|OLE システム レジストリをドキュメントの種類を登録します。|

## <a name="remarks"></a>Remarks

このクラスは、クラスから派生[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)。 通常は、使用することができます`COleTemplateServer`、独自のクラスを派生するのではなく、直接します。 `COleTemplateServer` 使用して、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) server ドキュメントを管理するオブジェクト。 使用`COleTemplateServer`フル サーバー、つまり、スタンドアロン アプリケーションとして実行できるサーバーを実装する場合。 フル サーバーがマルチ ドキュメント インターフェイス (MDI) アプリケーションでは通常シングル ドキュメント インターフェイス (SDI) アプリケーションがサポートされています。 1 つ`COleTemplateServer`アプリケーションがサポートするサーバーのドキュメントの種類ごとにオブジェクトは必要です。 これは、サーバー アプリケーションでは、ワークシートとグラフの両方をサポートする場合が必要 2 つ`COleTemplateServer`オブジェクト。

`COleTemplateServer` 上書き、`OnCreateInstance`によって定義されたメンバー関数`COleObjectFactory`します。 このメンバー関数は、適切な型の C++ オブジェクトを作成するためにフレームワークによって呼び出されます。

サーバーの詳細については、記事を参照してください。[サーバー。サーバーを実装する](../../mfc/servers-implementing-a-server.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

##  <a name="coletemplateserver"></a>  COleTemplateServer::COleTemplateServer

`COleTemplateServer` オブジェクトを構築します。

```
COleTemplateServer();
```

### <a name="remarks"></a>Remarks

使用した簡単な説明については、`COleTemplateServer`クラスを参照してください、 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)クラスの概要。

##  <a name="connecttemplate"></a>  COleTemplateServer::ConnectTemplate

接続によって示されるドキュメント テンプレート*pDocTemplate* 、基になる[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)オブジェクト。

```
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
テンプレートを要求する OLE クラス ID への参照。

*pDocTemplate*<br/>
ドキュメント テンプレートへのポインター。

*bMultiInstance*<br/>
アプリケーションの 1 つのインスタンスが複数のインスタンスをサポートできるかどうかを示します。 TRUE の場合は、オブジェクトを作成するには、各要求に対して、アプリケーションの複数のインスタンスが起動されます。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [CLSID キー](/windows/desktop/com/clsid-key-hklm) Windows SDK に含まれています。

##  <a name="unregister"></a>  COleTemplateServer::Unregister

関連付けられたドキュメント テンプレートを登録解除します。

```
BOOL Unregister();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

EnterRemarks

##  <a name="updateregistry"></a>  COleTemplateServer::UpdateRegistry

ドキュメント テンプレート文字列からのファイルの種類の情報の読み込みを OLE システム レジストリに格納します。

```
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>パラメーター

*nAppType*<br/>
OLE_APPTYPE の列挙体は、列挙子の値。H. 次の値のいずれかのことができます。

- OAT_INPLACE_SERVER Server では、サーバー全体のユーザー インターフェイスがあります。

- OAT_SERVER サーバーは、埋め込みのみをサポートします。

- OAT_CONTAINER コンテナーは、埋め込みオブジェクトへのリンクをサポートします。

- OAT_DISPATCH_OBJECT オブジェクトが`IDispatch`に対応します。

- OAT_DOC_OBJECT_SERVER サーバーは両方ともサポートを埋め込むと、ドキュメント オブジェクトのコンポーネント モデル。

*rglpszRegister*<br/>
エントリが存在しない場合にのみ、レジストリに書き込まれるエントリのリスト。

*rglpszOverwrite*<br/>
既にエントリが存在するかどうかに関係なく、レジストリに書き込まれるエントリのリスト。

*bRegister*<br/>
クラスを登録するかどうかを判断します。 場合*bRegister*が true の場合、クラスのシステム レジストリに登録します。 それ以外の場合、クラスが登録解除します。

### <a name="remarks"></a>Remarks

呼び出しを使用して、登録情報が読み込まれる[CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)します。 取得する部分文字列は、インデックスによって識別される`regFileTypeId`、 `regFileTypeName`、および`fileNewName`」の説明に従って、`GetDocString`ページを参照します。

場合、`regFileTypeId`部分文字列が空または呼び出し`GetDocString`何らかの他の理由でこの関数が失敗したが失敗し、レジストリ、ファイルの情報が入力されていません。

引数の情報は、 *rglpszRegister*と*rglpszOverwrite*を呼び出すことによって、レジストリに書き込まれる[AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass)します。 2 つの引数が NULL の場合、登録は、既定の情報は、ほとんどのアプリケーションに適しています。 これらの引数の情報の構造については、`AfxOleRegisterServerClass`を参照してください。

詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[COleObjectFactory クラス](../../mfc/reference/coleobjectfactory-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)
