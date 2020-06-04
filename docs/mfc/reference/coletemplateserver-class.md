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
ms.openlocfilehash: 561da5060aae3c938dc3e55d0310718a881c1a3b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753724"
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
|[サーバーを使用します。](#coletemplateserver)|`COleTemplateServer` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を使用します。](#connecttemplate)|基になる`COleObjectFactory`オブジェクトにドキュメント テンプレートを接続します。|
|[を使用します。](#unregister)|関連付けられたドキュメント テンプレートの登録を解除します。|
|[を使用します。](#updateregistry)|OLE システム レジストリにドキュメントの種類を登録します。|

## <a name="remarks"></a>解説

このクラスは、クラス[から](../../mfc/reference/coleobjectfactory-class.md)派生します。通常は、独自の`COleTemplateServer`クラスを派生させるのではなく、直接使用できます。 `COleTemplateServer`は、サーバードキュメントを管理するために[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクトを使用します。 完全`COleTemplateServer`なサーバー、つまりスタンドアロン アプリケーションとして実行できるサーバーを実装する場合に使用します。 通常、フル サーバーはマルチ ドキュメント インターフェイス (MDI) アプリケーションですが、単一のドキュメント インターフェイス (SDI) アプリケーションがサポートされています。 アプリケーション`COleTemplateServer`がサポートするサーバー ドキュメントの種類ごとに 1 つのオブジェクトが必要です。つまり、サーバー アプリケーションがワークシートとグラフの両方をサポートしている場合は、2`COleTemplateServer`つのオブジェクトが必要です。

`COleTemplateServer`によって定義された`OnCreateInstance`メンバー関数がオーバーライド`COleObjectFactory`されます。 このメンバー関数は、適切な型の C++ オブジェクトを作成するために、フレームワークによって呼び出されます。

サーバーの詳細については、「[サーバー : サーバーの実装](../../mfc/servers-implementing-a-server.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="coletemplateservercoletemplateserver"></a><a name="coletemplateserver"></a>サーバーを使用します。

`COleTemplateServer` オブジェクトを構築します。

```
COleTemplateServer();
```

### <a name="remarks"></a>解説

クラスの使用方法の簡単な説明については、クラスの概要を参照してください。 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) `COleTemplateServer`

## <a name="coletemplateserverconnecttemplate"></a><a name="connecttemplate"></a>を使用します。

*参照*先のドキュメント テンプレートを基になる[オブジェクト](../../mfc/reference/coleobjectfactory-class.md)に接続します。

```cpp
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
テンプレートが要求する OLE クラス ID への参照。

*テンプレート*<br/>
ドキュメント テンプレートへのポインター。

*を使用します。*<br/>
アプリケーションの単一のインスタンスが複数のインスタンス化をサポートできるかどうかを示します。 TRUE の場合、オブジェクトを作成する要求ごとに、アプリケーションの複数のインスタンスが起動されます。

### <a name="remarks"></a>解説

詳細については、Windows SDK[の CLSID キー](/windows/win32/com/clsid-key-hklm)を参照してください。

## <a name="coletemplateserverunregister"></a><a name="unregister"></a>を使用します。

関連付けられたドキュメント テンプレートの登録を解除します。

```
BOOL Unregister();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

注釈を入力します。

## <a name="coletemplateserverupdateregistry"></a><a name="updateregistry"></a>を使用します。

ドキュメント テンプレート文字列からファイルの種類の情報を読み込み、その情報を OLE システム レジストリに格納します。

```cpp
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>パラメーター

*アプリの種類*<br/>
AFXDISP で定義されているOLE_APPTYPE列挙体の値。H。 次のいずれかの値を指定できます。

- OAT_INPLACE_SERVER サーバーには、サーバーのユーザー インターフェイスが完全に含まれています。

- OAT_SERVER サーバーは埋め込みのみをサポートしています。

- OAT_CONTAINERコンテナは埋め込みオブジェクトへのリンクをサポートします。

- OAT_DISPATCH_OBJECT オブジェクト`IDispatch`は -対応です。

- OAT_DOC_OBJECT_SERVER サーバーは、埋め込みとドキュメント オブジェクト コンポーネント モデルの両方をサポートします。

*ルグルプスレジスタ*<br/>
エントリが存在しない場合にのみレジストリに書き込まれるエントリの一覧。

*上書き*<br/>
先行するエントリが存在するかどうかに関係なく、レジストリに書き込まれるエントリの一覧。

*b登録*<br/>
クラスを登録するかどうかを決定します。 *bRegister*が TRUE の場合、クラスはシステム レジストリに登録されます。 それ以外の場合は、クラスの登録を解除します。

### <a name="remarks"></a>解説

登録情報は、[呼](../../mfc/reference/cdoctemplate-class.md#getdocstring)び出しによって読み込まれます。 取得される部分文字列は、参照ページで`regFileTypeId`説明されているように、 `regFileTypeName`、 `fileNewName`、 、 によって`GetDocString`識別される部分文字列です。

部分文字列`regFileTypeId`が空の場合、または呼び出`GetDocString`しが失敗した場合、この関数は失敗し、ファイル情報はレジストリに入力されません。

引数*rglpszRegister および rglpszOverwrite*の情報は[、AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass)への呼び出しを通じてレジストリに書き込まれます。 *rglpszOverwrite* 2 つの引数が NULL の場合に登録されるデフォルト情報は、ほとんどのアプリケーションに適しています。 これらの引数の情報の構造については、を参照してください`AfxOleRegisterServerClass`。

詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[COleObjectFactory クラス](../../mfc/reference/coleobjectfactory-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)
