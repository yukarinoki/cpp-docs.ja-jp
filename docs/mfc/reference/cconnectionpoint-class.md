---
description: '詳細情報: CConnectionPoint クラス'
title: CConnectionPoint クラス
ms.date: 11/04/2016
f1_keywords:
- CConnectionPoint
- AFXDISP/CConnectionPoint
- AFXDISP/CConnectionPoint::CConnectionPoint
- AFXDISP/CConnectionPoint::GetConnections
- AFXDISP/CConnectionPoint::GetContainer
- AFXDISP/CConnectionPoint::GetIID
- AFXDISP/CConnectionPoint::GetMaxConnections
- AFXDISP/CConnectionPoint::GetNextConnection
- AFXDISP/CConnectionPoint::GetStartPosition
- AFXDISP/CConnectionPoint::OnAdvise
- AFXDISP/CConnectionPoint::QuerySinkInterface
helpviewer_keywords:
- CConnectionPoint [MFC], CConnectionPoint
- CConnectionPoint [MFC], GetConnections
- CConnectionPoint [MFC], GetContainer
- CConnectionPoint [MFC], GetIID
- CConnectionPoint [MFC], GetMaxConnections
- CConnectionPoint [MFC], GetNextConnection
- CConnectionPoint [MFC], GetStartPosition
- CConnectionPoint [MFC], OnAdvise
- CConnectionPoint [MFC], QuerySinkInterface
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
ms.openlocfilehash: 62525428d8f9bf5303f379140837d75e53cbb387
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227846"
---
# <a name="cconnectionpoint-class"></a>CConnectionPoint クラス

他の OLE オブジェクトと通信するために使われる "コネクション ポイント" と呼ばれる特別な型のインターフェイスを定義します。

## <a name="syntax"></a>構文

```
class CConnectionPoint : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|`CConnectionPoint` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CConnectionPoint:: GetConnections](#getconnections)|接続マップ内のすべてのコネクションポイントを取得します。|
|[CConnectionPoint:: GetContainer](#getcontainer)|接続マップを所有するコントロールのコンテナーを取得します。|
|[CConnectionPoint:: GetIID](#getiid)|コネクションポイントのインターフェイス ID を取得します。|
|[CConnectionPoint:: GetMaxConnections](#getmaxconnections)|コントロールでサポートされているコネクションポイントの最大数を取得します。|
|[CConnectionPoint::GetNextConnection](#getnextconnection)|*Pos* の接続要素へのポインターを取得します。|
|[CConnectionPoint::GetStartPosition](#getstartposition)|呼び出しに渡すことができる位置の値を返すことによって、マップの反復処理を開始し `GetNextConnection` ます。|
|[CConnectionPoint:: OnAdvise](#onadvise)|接続を確立または中断するときに、フレームワークによって呼び出されます。|
|[CConnectionPoint:: QuerySinkInterface](#querysinkinterface)|要求されたシンクインターフェイスへのポインターを取得します。|

## <a name="remarks"></a>解説

OLE コントロールの機能を実装および公開するために使用される通常の OLE インターフェイスとは異なり、コネクションポイントは、イベントの発生や変更通知など、他のオブジェクトに対するアクションを開始できる送信インターフェイスを実装します。

接続は2つの部分で構成されます。これは、"source" と呼ばれるインターフェイスを呼び出すオブジェクトと、"シンク" と呼ばれるインターフェイスを実装するオブジェクトです。 コネクションポイントを公開することにより、ソースはシンクがそれ自体への接続を確立できるようになります。 接続ポイント機構を使用して、ソースオブジェクトは、一連のメンバー関数のシンクの実装へのポインターを取得します。 たとえば、シンクによって実装されたイベントを発生させるには、ソースはシンクの実装の適切なメソッドを呼び出すことができます。

既定では、 `COleControl` 派生クラスは2つのコネクションポイントを実装します。1つはイベント用で、もう1つはプロパティ変更通知用です。 これらの接続は、イベントの発生や、プロパティ値が変更されたときにシンクに通知するためにそれぞれ使用されます (コントロールのコンテナーなど)。 追加のコネクションポイントを実装する OLE コントロールのサポートも提供されています。 コントロールクラスに実装されている追加の接続ポイントごとに、コネクションポイントを実装する "接続部分" を宣言する必要があります。 1つ以上のコネクションポイントを実装する場合は、コントロールクラスで1つの "接続マップ" を宣言する必要もあります。

次の例では、2つのコードフラグメントで構成される、OLE コントロールの単純な接続マップと1つの接続ポイントを示し `Sample` ます。最初の部分は接続マップとポイントを宣言し、2つ目はこのマップとポイントを実装します。 最初のフラグメントは、コントロールクラスの宣言のセクションの下に挿入され **`protected`** ます。

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

BEGIN_CONNECTION_PART および END_CONNECTION_PART マクロは、 `XSampleConnPt` この特定のコネクションポイントを実装する (から派生した) 埋め込みクラスを宣言し `CConnectionPoint` ます。 メンバー関数をオーバーライドする場合 `CConnectionPoint` 、または独自のメンバー関数を追加する場合は、これらの2つのマクロの間で宣言します。 たとえば、CONNECTION_IID マクロは、 `CConnectionPoint::GetIID` この2つのマクロの間に配置されるときにメンバー関数をオーバーライドします。

2番目のコード片が実装ファイル () に挿入されます。CPP) を使用します。 このコードは、接続マップを実装します。これには、追加のコネクションポイントが含まれ `SampleConnPt` ます。

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

これらのコードフラグメントが挿入されると、サンプルの OLE コントロールはインターフェイスの接続ポイントを公開し `ISampleSink` ます。

通常、接続ポイントは "マルチキャスト" をサポートします。これは、同じインターフェイスに接続されている複数のシンクにブロードキャストする機能です。 次のコードフラグメントは、コネクションポイントで各シンクを反復処理してマルチキャストを実行する方法を示しています。

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

この例では、接続ポイントの現在の接続のセットを、の呼び出しによって取得し `SampleConnPt` `CConnectionPoint::GetConnections` ます。 次に、接続を反復処理し、 `ISampleSink::SinkFunc` アクティブなすべての接続に対してを呼び出します。

の使用方法の詳細については `CConnectionPoint` 、「 [接続ポイント](../../mfc/connection-points.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>要件

**ヘッダー :** afxdisp.h

## <a name="cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a> CConnectionPoint::CConnectionPoint

`CConnectionPoint` オブジェクトを構築します。

```
CConnectionPoint();
```

## <a name="cconnectionpointgetconnections"></a><a name="getconnections"></a> CConnectionPoint:: GetConnections

コネクションポイントのすべてのアクティブな接続を取得するには、この関数を呼び出します。

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>戻り値

アクティブな接続 (シンク) の配列へのポインター。 配列内の一部のポインターが NULL になる場合があります。 この配列内の NULL 以外の各ポインターは、キャスト演算子を使用して、シンクインターフェイスへのポインターに安全に変換できます。

## <a name="cconnectionpointgetcontainer"></a><a name="getcontainer"></a> CConnectionPoint:: GetContainer

コネクションポイントのを取得するために、フレームワークによって呼び出され `IConnectionPointContainer` ます。

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>戻り値

成功した場合は、コンテナーへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この関数は、通常、BEGIN_CONNECTION_PART マクロによって実装されます。

## <a name="cconnectionpointgetiid"></a><a name="getiid"></a> CConnectionPoint:: GetIID

コネクションポイントのインターフェイス ID を取得するために、フレームワークによって呼び出されます。

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>戻り値

コネクションポイントのインターフェイス ID への参照。

### <a name="remarks"></a>解説

この接続ポイントのインターフェイス ID を返すには、この関数をオーバーライドします。

## <a name="cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a> CConnectionPoint:: GetMaxConnections

コネクションポイントでサポートされている接続の最大数を取得するために、フレームワークによって呼び出されます。

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>戻り値

コントロールでサポートされている接続の最大数。制限がない場合は-1。

### <a name="remarks"></a>解説

既定の実装では、制限がないことを示す-1 が返されます。

コントロールに接続できるシンクの数を制限する場合は、この関数をオーバーライドします。

## <a name="cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a> CConnectionPoint::GetNextConnection

*Pos* の接続要素へのポインターを取得します。

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
前の `GetNextConnection` 呼び出しまたは [GetStartPosition](#getstartposition) 呼び出しによって返される位置の値への参照を指定します。

### <a name="return-value"></a>戻り値

*Pos* によって指定された接続要素へのポインター、または NULL。

### <a name="remarks"></a>解説

この関数は、接続マップ内のすべての要素を反復処理する場合に最も役立ちます。 繰り返し処理を行う場合は、この関数から返された Null をスキップします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

## <a name="cconnectionpointgetstartposition"></a><a name="getstartposition"></a> CConnectionPoint::GetStartPosition

[GetNextConnection](#getnextconnection)呼び出しに渡すことができる位置の値を返すことによって、マップの反復処理を開始します。

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>戻り値

マップの反復処理の開始位置を示す位置の値です。または、マップが空の場合は NULL になります。

### <a name="remarks"></a>解説

イテレーションシーケンスは予測できません。したがって、"map 内の最初の要素" には特別な意味はありません。

### <a name="example"></a>例

  [CConnectionPoint:: GetNextConnection](#getnextconnection)の例を参照してください。

## <a name="cconnectionpointonadvise"></a><a name="onadvise"></a> CConnectionPoint:: OnAdvise

接続が確立または切断されているときに、フレームワークによって呼び出されます。

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>パラメーター

*bAdvise*<br/>
接続が確立されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

既定の実装では、何も行われません。

シンクが接続ポイントに接続または切断したときに通知する場合は、この関数をオーバーライドします。

## <a name="cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a> CConnectionPoint:: QuerySinkInterface

要求されたシンクインターフェイスへのポインターを取得します。

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>パラメーター

*pUnkSink*<br/>
要求されているシンクインターフェイスの識別子。

*ppInterface*<br/>
*PUnkSink* によって識別されるインターフェイスポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合、 \* *PPINTERFACE* は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
