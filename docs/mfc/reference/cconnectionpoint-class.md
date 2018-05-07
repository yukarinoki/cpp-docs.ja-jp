---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22793706a67a3d301f88700ca6b43fb9c83e4dc3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cconnectionpoint-class"></a>関数クラス
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
|[は](#getconnections)|コネクション マップ内のすべての接続ポイントを取得します。|  
|[CConnectionPoint::GetContainer](#getcontainer)|コネクション マップを所有するコントロールのコンテナーを取得します。|  
|[CConnectionPoint::GetIID](#getiid)|接続ポイントのインターフェイス ID を取得します。|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|コントロールでサポートされる接続ポイントの最大数を取得します。|  
|[CConnectionPoint::GetNextConnection](#getnextconnection)|接続要素へのポインターを取得`pos`です。|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|返すことによって、マップの反復処理を開始、**位置**値を渡すことができる、`GetNextConnection`呼び出します。|  
|[CConnectionPoint::OnAdvise](#onadvise)|確立されるかの接続を解除するときに、フレームワークによって呼び出されます。|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|要求されたシンク インターフェイスへのポインターを取得します。|  
  
## <a name="remarks"></a>コメント  
 標準の OLE インターフェイスを実装し、OLE コントロールの機能を公開に使用されるとは異なりは、接続ポイントは、イベントを発生させるなど、他のオブジェクトのアクションを開始して、変更通知が送信インターフェイスを実装します。  
  
 接続は、2 つの部分で構成されています:"source"と、インターフェイスを実装するオブジェクトと呼ばれるインターフェイスを呼び出すオブジェクト シンクと呼ばれる、"です"。 接続ポイントを公開するでは、ソースは、シンク自体への接続の確立を許可します。 接続ポイントのメカニズムは、ソース オブジェクトは、一連のメンバー関数のシンクの実装へのポインターを取得します。 たとえば、シンクによって実装されているイベントを発生させるには、ソースは、シンクの実装の適切なメソッドを呼び出すことができます。  
  
 既定では、 `COleControl`-派生クラスに実装する 2 つの接続ポイント: 変更通知のイベントをプロパティの 1 つです。 これらの接続を使用する、それぞれ、イベントを発生させるとシンク (たとえば、コントロールのコンテナー) を通知する場合、プロパティ値が変更されます。 サポートは追加の接続ポイントを実装する OLE コントロールも提供されます。 を、コントロール クラスに実装されている各追加の接続ポイントには、接続ポイントを実装する「接続部分」を宣言する必要があります。 1 つまたは複数の接続ポイントを実装する場合は、1 つのコントロール クラスの「コネクション マップ」を宣言する必要があります。  
  
 次の例は、単純な接続のマップと 1 つの接続ポイントを`Sample`OLE コントロール、コードの 2 つのフラグメントから成る: 最初の部分宣言コネクション マップとポイント以外の場合は、2 つ目は、このマップとポイントを実装します。 最初のフラグメントが、コントロール クラスの宣言に挿入された、`protected`セクション。  
  
 [!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 `BEGIN_CONNECTION_PART`と`END_CONNECTION_PART`マクロ、埋め込みのクラスを宣言する`XSampleConnPt`(から派生した`CConnectionPoint`) この特定の接続ポイントを実装します。 オーバーライドする場合は、`CConnectionPoint`メンバー関数、または独自のメンバー関数を追加、これら 2 つのマクロの間、それらを宣言します。 たとえば、`CONNECTION_IID`マクロよりも優先、`CConnectionPoint::GetIID`メンバー関数はこれら 2 つのマクロの間に配置します。  
  
 2 番目のコード片は、実装ファイルに挿入 (です。CPP)、コントロールのクラスです。 このコードは、追加の接続ポイントが含まれており、コネクション マップを実装する`SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 サンプルの OLE コントロールがのコネクション ポイントを公開する以下のコード片が挿入されると、 **ISampleSink**インターフェイスです。  
  
 通常、接続ポイントは、「マルチキャスト」は、同じインターフェイスに接続されている複数のシンクにブロードキャストする機能をサポートします。 次のコード フラグメントでは、マルチキャストを繰り返し処理で各シンク接続ポイントで使用して実行する方法を示します。  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 この例では、接続の現在のセットを取得、`SampleConnPt`接続ポイントへの呼び出しが`CConnectionPoint::GetConnections`です。 接続と呼び出しを反復処理し、`ISampleSink::SinkFunc`すべての接続にアクティブにします。  
  
 使用する方法について`CConnectionPoint`、記事を参照して[コネクション ポイント](../../mfc/connection-points.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="cconnectionpoint"></a>  CConnectionPoint::CConnectionPoint  
 `CConnectionPoint` オブジェクトを構築します。  
  
```  
CConnectionPoint();
```  
  
##  <a name="getconnections"></a>  は  
 すべてのアクティブな接続ポイントの接続を取得するには、この関数を呼び出します。  
  
```  
const CPtrArray* GetConnections();
```  
  
### <a name="return-value"></a>戻り値  
 アクティブな接続 (シンク) の配列へのポインター。 NULL ポインター、配列内のいくつかの可能性があります。 この配列内の各 NULL ポインターは、キャスト演算子を使用して、シンク インターフェイスへのポインターに安全に変換できます。  
  
##  <a name="getcontainer"></a>  CConnectionPoint::GetContainer  
 取得するためにフレームワークによって呼び出される、 **IConnectionPointContainer**接続ポイント。  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、コンテナーへのポインターそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 通常、この関数はによって実装され、`BEGIN_CONNECTION_PART`マクロです。  
  
##  <a name="getiid"></a>  CConnectionPoint::GetIID  
 接続ポイントのインターフェイス ID を取得するためにフレームワークによって呼び出されます。  
  
```  
virtual REFIID GetIID() = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 コネクション ポイントのインターフェイス ID への参照  
  
### <a name="remarks"></a>コメント  
 この接続ポイントのインターフェイス ID を返すには、この関数をオーバーライドします。  
  
##  <a name="getmaxconnections"></a>  CConnectionPoint::GetMaxConnections  
 接続ポイントでサポートされている接続の最大数を取得するためにフレームワークによって呼び出されます。  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>戻り値  
 制限がない場合は、コントロール、または-1 でサポートされている接続の最大数。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、制限がないことを示す-1 を返します。  
  
 コントロールに接続できるシンクの数を制限する場合は、この関数をオーバーライドします。  
  
##  <a name="getnextconnection"></a>  CConnectionPoint::GetNextConnection  
 接続要素へのポインターを取得`pos`です。  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照を指定します、**位置**によって以前返される値`GetNextConnection`または[中](#getstartposition)呼び出します。  
  
### <a name="return-value"></a>戻り値  
 指定した接続要素へのポインター `pos`、または NULL。  
  
### <a name="remarks"></a>コメント  
 この関数は、コネクション マップ内のすべての要素の反復処理に最も役立ちます。 を反復処理するときは、この関数から返されたすべての Null をスキップします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="getstartposition"></a>  CConnectionPoint::GetStartPosition  
 返すことによって、マップの反復処理を開始、**位置**値を渡すことができる、[順次アクセス](#getnextconnection)呼び出します。  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**マップを反復処理するための開始位置を表す値または**NULL**マップが空の場合。  
  
### <a name="remarks"></a>コメント  
 イテレーションのシーケンスが予測可能です。したがって、マップの最初の要素""には、特別な意味はありません。  
  
### <a name="example"></a>例  
  例を参照して[CConnectionPoint::GetNextConnection](#getnextconnection)です。  
  
##  <a name="onadvise"></a>  CConnectionPoint::OnAdvise  
 確立されているか、破損は、接続するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAdvise`  
 **TRUE**それ以外の確立された接続されている場合は、 **FALSE**です。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。  
  
 通知は、シンクに接続するか、接続ポイントから切断時に使用する場合は、この関数をオーバーライドします。  
  
##  <a name="querysinkinterface"></a>  CConnectionPoint::QuerySinkInterface  
 要求されたシンク インターフェイスへのポインターを取得します。  
  
```  
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,  
    void** ppInterface);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkSink`  
 要求されたシンク インターフェイスの識別子。  
  
 `ppInterface`  
 によって識別されるインターフェイス ポインターへのポインター`pUnkSink`です。 オブジェクトは、このインターフェイスをサポートしていない場合\*`ppInterface`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)

