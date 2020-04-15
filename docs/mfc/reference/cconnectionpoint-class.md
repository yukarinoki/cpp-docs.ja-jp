---
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
ms.openlocfilehash: ce72c156ab31b742a42d2960923fc56afff656c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369426"
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
|[接続ポイント::接続ポイント](#cconnectionpoint)|`CConnectionPoint` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[接続ポイント::接続を取得します。](#getconnections)|接続マップ内のすべての接続ポイントを取得します。|
|[をクリックします。](#getcontainer)|接続マップを所有するコントロールのコンテナーを取得します。|
|[接続ポイント::取得ID](#getiid)|コネクション ポイントのインターフェイス ID を取得します。|
|[接続ポイント::取得最大接続](#getmaxconnections)|コントロールでサポートされるコネクション ポイントの最大数を取得します。|
|[接続ポイント::次の接続を取得します。](#getnextconnection)|*pos*の接続要素へのポインターを取得します。|
|[ポイント::取得位置](#getstartposition)|呼び出しに渡すことができる POSITION 値を返すことによって、`GetNextConnection`マップの反復処理を開始します。|
|[ココネクションポイント::オンアドバイス](#onadvise)|接続を確立または切断するときに、フレームワークによって呼び出されます。|
|[次のクエリポイント::クエリシンクインターフェイス](#querysinkinterface)|要求されたシンク インターフェイスへのポインターを取得します。|

## <a name="remarks"></a>解説

OLE コントロールの機能を実装および公開するために使用される通常の OLE インターフェイスとは異なり、コネクション ポイントは、イベントの発生や変更通知などの他のオブジェクトに対してアクションを開始できる出力インターフェイスを実装します。

接続は、"source" と呼ばれるインターフェイスを呼び出すオブジェクトと、"シンク" と呼ばれるインターフェイスを実装するオブジェクトの 2 つの部分で構成されます。 接続ポイントを公開することにより、ソースはシンクが自身への接続を確立できるようにします。 コネクション ポイント機構を使用して、ソース オブジェクトは、一連のメンバ関数のシンクの実装へのポインターを取得します。 たとえば、シンクによって実装されたイベントを発生させる場合、ソースはシンクの実装の適切なメソッドを呼び出すことができます。

既定では`COleControl`、-derived クラスは、イベント用とプロパティ変更通知用の 2 つのコネクション ポイントを実装します。 これらの接続は、イベントの発生時に使用され、プロパティ値が変更されたときにシンク (コントロールのコンテナーなど) に通知するために使用されます。 OLE コントロールが追加のコネクション ポイントを実装するためのサポートも提供されています。 コントロール クラスに実装された追加の接続ポイントごとに、コネクション ポイントを実装する "接続部分" を宣言する必要があります。 1 つ以上のコネクション ポイントを実装する場合は、コントロール クラスで単一の "接続マップ" を宣言する必要があります。

次の例では、`Sample`単純な接続マップと OLE コントロールの 1 つの接続ポイントを示しています。2 番目のメソッドは、このマップとポイントを実装します。 最初のフラグメントは、コントロール クラスの宣言に **、保護された**セクションの下に挿入されます。

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

BEGIN_CONNECTION_PARTおよびEND_CONNECTION_PART マクロは、`XSampleConnPt`この特定のコネクション ポイント`CConnectionPoint`を実装する埋め込みクラス ( から派生 ) を宣言します。 メンバー`CConnectionPoint`関数をオーバーライドする場合、または独自のメンバー関数を追加する場合は、これら 2 つのマクロの間で宣言します。 たとえば、CONNECTION_IID マクロは、これら`CConnectionPoint::GetIID`2 つのマクロの間に配置されたメンバー関数をオーバーライドします。

2 番目のコードフラグメントが実装ファイルに挿入されます (.CPP) コントロール クラスの。 このコードは、追加のコネクション ポイントを含む接続マップを`SampleConnPt`実装します。

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

これらのコードフラグメントが挿入されると、サンプル OLE コントロールはインターフェイスのコネクション ポイントを公開します`ISampleSink`。

通常、コネクション ポイントは、同じインターフェイスに接続された複数のシンクにブロードキャストする機能である「マルチキャスト」をサポートします。 次のコードは、コネクション ポイント上の各シンクを反復処理してマルチキャストを実行する方法を示しています。

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

この例では、接続ポイントの現在の接続セット`SampleConnPt`を取得し、 を`CConnectionPoint::GetConnections`呼び出します。 その後、接続を反復処理し、`ISampleSink::SinkFunc`アクティブなすべての接続を呼び出します。

の使用方法`CConnectionPoint`の詳細については、[記事「接続ポイント](../../mfc/connection-points.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a>接続ポイント::接続ポイント

`CConnectionPoint` オブジェクトを構築します。

```
CConnectionPoint();
```

## <a name="cconnectionpointgetconnections"></a><a name="getconnections"></a>接続ポイント::接続を取得します。

接続ポイントのすべてのアクティブな接続を取得します。

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>戻り値

アクティブな接続 (シンク) の配列へのポインター。 配列内のポインタの一部が NULL である場合があります。 この配列内の各 NULL 以外のポインターは、キャスト演算子を使用してシンク インターフェイスへのポインターに安全に変換できます。

## <a name="cconnectionpointgetcontainer"></a><a name="getcontainer"></a>をクリックします。

接続ポイントの を`IConnectionPointContainer`取得するために、フレームワークによって呼び出されます。

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>戻り値

成功した場合は、コンテナーへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この関数は、通常、BEGIN_CONNECTION_PART マクロによって実装されます。

## <a name="cconnectionpointgetiid"></a><a name="getiid"></a>接続ポイント::取得ID

コネクション ポイントのインターフェイス ID を取得するために、フレームワークによって呼び出されます。

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>戻り値

コネクション ポイントのインターフェイス ID への参照。

### <a name="remarks"></a>解説

このコネクション ポイントのインターフェイス ID を返す場合は、この関数をオーバーライドします。

## <a name="cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a>接続ポイント::取得最大接続

接続ポイントでサポートされる接続の最大数を取得するために、フレームワークによって呼び出されます。

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>戻り値

コントロールでサポートされる接続の最大数。または制限がない場合は -1。

### <a name="remarks"></a>解説

デフォルトの実装では、制限がないことを示す -1 が返されます。

コントロールに接続できるシンクの数を制限する場合は、この関数をオーバーライドします。

## <a name="cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a>接続ポイント::次の接続を取得します。

*pos*の接続要素へのポインターを取得します。

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
前`GetNextConnection`の呼び出しまたは[GetStartPosition](#getstartposition)呼び出しによって返される POSITION 値への参照を指定します。

### <a name="return-value"></a>戻り値

*pos*または NULL で指定された接続要素へのポインター。

### <a name="remarks"></a>解説

この関数は、接続マップ内のすべての要素を反復処理する場合に最も便利です。 反復処理を行う場合は、この関数から返されるすべてのヌルをスキップします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

## <a name="cconnectionpointgetstartposition"></a><a name="getstartposition"></a>ポイント::取得位置

[GetNextConnection](#getnextconnection)呼び出しに渡すことができる位置値を返すことによって、マップの反復処理を開始します。

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>戻り値

マップを反復処理するための開始位置を示す POSITION 値。マップが空の場合は NULL。

### <a name="remarks"></a>解説

反復シーケンスは予測できません。したがって、「マップの最初の要素」には特別な意味はありません。

### <a name="example"></a>例

  [次](#getnextconnection)の例を参照してください。

## <a name="cconnectionpointonadvise"></a><a name="onadvise"></a>ココネクションポイント::オンアドバイス

接続が確立または切断されているときに、フレームワークによって呼び出されます。

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>パラメーター

*アドバイス*<br/>
接続が確立されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

既定の実装では、何も行われません。

シンクが接続ポイントに接続または接続を切断したときに通知を行う場合は、この関数をオーバーライドします。

## <a name="cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a>次のクエリポイント::クエリシンクインターフェイス

要求されたシンク インターフェイスへのポインターを取得します。

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>パラメーター

*プンクシンク*<br/>
要求されているシンク インターフェイスの識別子。

*インターフェイス*<br/>
*pUnkSink*によって識別されるインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合\**、ppInterface*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
