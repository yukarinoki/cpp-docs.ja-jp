---
title: コネクション マップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 475314edba2a11535349991db644a4915e352ae7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372839"
---
# <a name="connection-maps"></a>コネクション マップ
OLE コントロールは、他のアプリケーションへのインターフェイスを公開できます。 これらのインターフェイスは、そのコントロールにのみ、コンテナーからのアクセスを許可します。 OLE コントロールは、他の OLE オブジェクトの外部インターフェイスにアクセスする場合、接続ポイントを確立する必要があります。 この接続ポイントは、コントロールからイベント マップや通知関数などの外部のディスパッチ マップへのアクセスを許可します。  
  
 Microsoft Foundation Class ライブラリには、接続ポイントをサポートするプログラミング モデルが用意されています。 このモデルでは「コネクション マップ」インターフェイスまたは OLE コントロールの接続ポイントを指定するために使用します。 コネクション マップには、接続ポイントごとに 1 つのマクロが含まれています。 コネクション マップの詳細については、次を参照してください。、[関数](../../mfc/reference/cconnectionpoint-class.md)クラスです。  
  
 通常、コントロールが 2 つの接続ポイントをサポートします。 イベントおよびプロパティの通知のいずれかのいずれか。 によって実装されて、`COleControl`基底クラスと、ライターによって、コントロールの追加の作業は必要ありません。 クラスに実装する任意の追加の接続ポイントを手動で追加する必要があります。 コネクション マップおよびポイントをサポートするためには、MFC には、次のマクロが用意されています。  
  
### <a name="connection-map-declaration-and-demarcation"></a>コネクション マップの宣言と定義  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|埋め込み (クラス宣言で使用する必要があります)、追加の接続ポイントを実装するクラスを宣言します。|  
|[END_CONNECTION_PART](#end_connection_part)|接続ポイント (クラス宣言で使用する必要があります) の宣言を終了します。|  
|[CONNECTION_IID](#connection_iid)|コントロールの接続ポイントのインターフェイス ID を指定します。|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|コネクション マップがクラス (クラス宣言で使用する必要があります) で使用されることを宣言します。|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|コネクション マップ (クラスの実装で使用する必要があります) の定義を開始します。|  
|[END_CONNECTION_MAP](#end_connection_map)|コネクション マップ (クラスの実装で使用する必要があります) の定義を終了します。|  
|[CONNECTION_PART](#connection_part)|コントロールの接続のマップ内の接続ポイントを指定します。|  
  
 次の関数を確立して、接続ポイントを使用して、接続の切断をシンクが役立ちます。  
  
### <a name="initializationtermination-of-connection-points"></a>コネクション ポイントの初期化/終了  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|ソースとシンク間の接続を確立します。|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|ソースとシンクの間の接続を切断します。|  
  
##  <a name="begin_connection_part"></a>  BEGIN_CONNECTION_PART  
 使用して、`BEGIN_CONNECTION_PART`マクロのイベントおよびプロパティの通知の接続ポイントを超えた追加の接続ポイントの定義を開始します。  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 コネクション ポイントを持つコントロール クラスの名前を指定します。  
  
 *マクロ*  
 接続ポイントを実装するローカル クラスの名前を指定します。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する宣言 (.h) ファイル、起動接続ポイントが、`BEGIN_CONNECTION_PART`マクロを追加して、`CONNECTION_IID`マクロと実装、および接続ポイントのマップを完了したいその他の任意のメンバー関数`END_CONNECTION_PART`マクロです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="end_connection_part"></a>  END_CONNECTION_PART  
 コネクション ポイントの宣言を終了します。  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>パラメーター  
 *マクロ*  
 接続ポイントを実装するローカル クラスの名前を指定します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="connection_iid"></a>  CONNECTION_IID  
 間で使用して、`BEGIN_CONNECTION_PART`と`END_CONNECTION_PART`OLE コントロールでサポートされる接続ポイントのインターフェイス ID を定義するマクロです。  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 接続ポイントによると呼ばれるインターフェイスのインターフェイス ID です。  
  
### <a name="remarks"></a>コメント  
 `iid`引数は、接続ポイントを接続シンクで呼び出すインターフェイスを識別するインターフェイス ID です。 例えば:  
  
 [!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 呼び出す接続ポイントを指定します、`ISinkInterface`インターフェイスです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="declare_connection_map"></a>  DECLARE_CONNECTION_MAP  
 各`COleControl`-プログラム内の派生クラスには、自分の管理をサポートする追加の接続ポイントを指定する接続のマップが用意されています。  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>コメント  
 使用して、コントロールは、追加の点をサポートする場合、`DECLARE_CONNECTION_MAP`クラスの宣言の最後にマクロです。 クラスのメンバー関数を定義する .cpp ファイルを使用して、`BEGIN_CONNECTION_MAP`マクロ、`CONNECTION_PART`用の各コントロールの接続ポイントでは、マクロ、および`END_CONNECTION_MAP`コネクション マップの最後を宣言するマクロ。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="begin_connection_map"></a>  BEGIN_CONNECTION_MAP  
 各`COleControl`-プログラム内の派生クラスには、コントロールがサポートする接続ポイントを指定する接続のマップが用意されています。  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 コネクション マップを持つコントロール クラスの名前を指定します。  
  
 *基底*  
 基本クラスの名前を指定`theClass`です。  
  
### <a name="remarks"></a>コメント  
 実装 (です。CPP) ファイルをクラスのメンバー関数を定義すると接続のマップの開始、`BEGIN_CONNECTION_MAP`マクロを使用して、接続ポイントの各マクロ エントリを追加、 [CONNECTION_PART](#connection_part)マクロです。 コネクション マップを最後に、完了、 [END_CONNECTION_MAP](#end_connection_map)マクロです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="end_connection_map"></a>  END_CONNECTION_MAP  
 コネクション マップの定義を終了します。  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="connection_part"></a>  CONNECTION_PART  
 OLE コントロールの接続ポイントを特定のインターフェイス ID にマップします。  
  
```   
CONNECTION_PART(theClass, iid, localClass)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 コネクション ポイントを持つコントロール クラスの名前を指定します。  
  
 `iid`  
 接続ポイントによると呼ばれるインターフェイスのインターフェイス ID です。  
  
 *マクロ*  
 接続ポイントを実装するローカル クラスの名前を指定します。  
  
### <a name="remarks"></a>コメント  
 例えば:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 呼び出しである接続ポイントとの接続のマップを実装、`IID_ISinkInterface`インターフェイスです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="afxconnectionadvise"></a>  AfxConnectionAdvise  
 指定される、ソースとの間の接続を確立するには、この関数を呼び出す`pUnkSrc`とで指定された、シンク`pUnkSink`です。  
  
```   
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD FAR* pdwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkSrc`  
 インターフェイスを呼び出し、オブジェクトへのポインター。  
  
 `pUnkSink`  
 インターフェイスを実装するオブジェクトへのポインター。  
  
 `iid`  
 接続のインターフェイス ID です。  
  
 `bRefCount`  
 **TRUE**接続を作成するの参照カウントが発生ことを示します`pUnkSink`インクリメントします。 **FALSE**参照カウントをインクリメントいないことを示します。  
  
 `pdwCookie`  
 ポインター、`DWORD`接続 id が返されます。 としてこの値を渡す必要があります、`dwCookie`パラメーターを`AfxConnectionUnadvise`接続を切断するときにします。  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、接続が確立されました。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h 

##  <a name="afxconnectionunadvise"></a>  AfxConnectionUnadvise  
 指定される、ソースとの間の接続を切断するには、この関数を呼び出す`pUnkSrc`とで指定された、シンク`pUnkSink`です。  
  
```   
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD dwCookie); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkSrc`  
 インターフェイスを呼び出し、オブジェクトへのポインター。  
  
 `pUnkSink`  
 インターフェイスを実装するオブジェクトへのポインター。  
  
 `iid`  
 コネクション ポイント インターフェイスのインターフェイス ID です。  
  
 `bRefCount`  
 **TRUE** 、接続の切断との参照カウントが発生する必要があることを示します`pUnkSink`デクリメントされます。 **FALSE**できないことを示す、参照カウントをデクリメントします。  
  
 `dwCookie`  
 によって返される接続識別子`AfxConnectionAdvise`です。  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、接続が切断されました。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h 

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
