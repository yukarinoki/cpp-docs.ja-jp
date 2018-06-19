---
title: COM インターフェイス エントリ マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c3ba41a05813c4112c1e5dd51bfe447d2c8debf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366589"
---
# <a name="cominterfaceentry-macros"></a>COM_INTERFACE_ENTRY マクロ  
 アクセスできるように、これらのマクロがその COM マップにオブジェクトのインターフェイスを入力`QueryInterface`です。 COM マップ エントリの順序は、対応する注文インターフェイスがチェックされます**IID**中に`QueryInterface`です。  

 |||
 |-|-|
 |[COM_INTERFACE_ENTRY](#com_interface_entry)|インターフェイスを COM インターフェイス マップに入力します。|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|継承の 2 つの分岐のあいまいさを解消するのにには、このマクロを使用します。|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|インターフェイスを COM マップに入力し、インターフェイスの IID を指定するには、このマクロを使用します。|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|同じ[COM_INTERFACE_ENTRY2](#com_interface_entry2)異なる IID を指定する点を除いて、します。|  
|[定義](#com_interface_entry_aggregate)|インターフェイスがによって識別される`iid`、クエリが実行`COM_INTERFACE_ENTRY_AGGREGATE`転送`punk`です。|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|同じ[で定義](#com_interface_entry_aggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除いて、`punk`です。|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|同じ[で定義](#com_interface_entry_aggregate)、場合を除く`punk`は**NULL**で説明されている集計を自動的に作成、`clsid`です。|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|同じ[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除いて、 `punk`、場合`punk`は**NULL**、自動的に作成しますにより記述された集計、`clsid`です。|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|呼び出さないと、 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297)について、指定したインターフェイスが照会されたときにします。|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|すべてのインスタンスのインターフェイスに固有のデータを保存します。|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|ティアオフ インターフェイスを公開します。|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|処理が、COM マップ内のこのエントリに達すると、基底クラスの COM マップを処理します。|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL にフックするための一般的な機構`QueryInterface`ロジック。|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|同じ[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)への呼び出しで結果の任意の IID のクエリを実行することを除いて、`func`です。|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|返します**E_NOINTERFACE**と COM マップ処理について、指定したインターフェイスが照会されたときに終了します。|  

## <a name="requirements"></a>要件
**ヘッダー:** atlcom.h

## <a name="com_interface_entry"></a> COM_INTERFACE_ENTRY
インターフェイスを COM インターフェイス マップに入力します。

### <a name="syntax"></a>構文

```
COM_INTERFACE_ENTRY( x )
```
### <a name="parameters"></a>パラメーター

[in] インターフェイスの名前の x、クラスのオブジェクトから派生直接します。

### <a name="remarks"></a>コメント
通常、これは、最も頻繁に使用するエントリの種類です。

### <a name="example"></a>例
```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```
### <a name="requirements"></a>要件
**ヘッダー:** atlcom.h
  
##  <a name="com_interface_entry2"></a>  COM_INTERFACE_ENTRY2  
 継承の 2 つの分岐のあいまいさを解消するのにには、このマクロを使用します。  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]オブジェクトから公開するインターフェイスの名前。  
  
 `x2`  
 [in]元の継承の分岐の名前*x*公開されます。  
  
### <a name="remarks"></a>コメント  
 たとえば、次の 2 つのデュアル インターフェイスからクラス オブジェクトを派生する場合を公開する`IDispatch`を使用して`COM_INTERFACE_ENTRY2`ため`IDispatch`インターフェイスのいずれかから取得できます。  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="com_interface_entry_iid"></a>  COM_INTERFACE_ENTRY_IID  
 インターフェイスを COM マップに入力し、インターフェイスの IID を指定するには、このマクロを使用します。  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]公開されるインターフェイスの GUID です。  
  
 *x*  
 [in]Vtable で識別されるインターフェイスとして公開されるクラスの名前`iid`です。  
  
 
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="com_interface_entry2_iid"></a>  COM_INTERFACE_ENTRY2_IID  
 同じ[COM_INTERFACE_ENTRY2](#com_interface_entry2)異なる IID を指定する点を除いて、します。  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]インターフェイスを指定する GUID です。  
  
 *x*  
 [in]クラスのオブジェクトが直接から派生したインターフェイスの名前。  
  
 `x2`  
 [in]クラスのオブジェクトが直接から派生する 2 番目のインターフェイスの名前。  
  
##  <a name="com_interface_entry_aggregate"></a>  定義  
 インターフェイスがによって識別される`iid`、クエリが実行`COM_INTERFACE_ENTRY_AGGREGATE`転送`punk`です。  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]に対してクエリを実行するインターフェイスの GUID です。  
  
 `punk`  
 [in]名前、 **IUnknown**ポインター。  
  
### <a name="remarks"></a>コメント  
 `punk`パラメーターは、内部の不明な集計の をポイントすると見なされます**NULL**、その場合、エントリは無視されます。 通常、 **CoCreate**にまとめて`FinalConstruct`です。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="com_interface_entry_aggregate_blind"></a>  COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 同じ[で定義](#com_interface_entry_aggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除いて、`punk`です。  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>パラメーター  
 `punk`  
 [in]名前、 **IUnknown**ポインター。  
  
### <a name="remarks"></a>コメント  
 インターフェイスのクエリは失敗し、COM マップの処理は継続します。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  

##  <a name="com_interface_entry_autoaggregate"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 同じ[で定義](#com_interface_entry_aggregate)、場合を除く`punk`は**NULL**で説明されている集計を自動的に作成、`clsid`です。  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]に対してクエリを実行するインターフェイスの GUID です。  
  
 `punk`  
 [in]名前、 **IUnknown**ポインター。 COM マップを含むクラスのメンバーである必要があります。  
  
 `clsid`  
 [in]場合に作成される集計の識別子`punk`は**NULL**です。  
  
### <a name="remarks"></a>コメント  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="com_interface_entry_autoaggregate_blind"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 同じ[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除いて、 `punk`、場合`punk`は**NULL**、自動的に作成しますにより記述された集計、`clsid`です。  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>パラメーター  
 `punk`  
 [in]名前、 **IUnknown**ポインター。 COM マップを含むクラスのメンバーである必要があります。  
  
 `clsid`  
 [in]場合に作成される集計の識別子`punk`は**NULL**です。  
  
### <a name="remarks"></a>コメント  
 インターフェイスのクエリは失敗し、COM マップの処理は継続します。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="com_interface_entry_break"></a>  COM_INTERFACE_ENTRY_BREAK  
 呼び出さないと、 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297)について、指定したインターフェイスが照会されたときにします。  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]インターフェイス識別子を構築するために使用するテキスト。  
  
### <a name="remarks"></a>コメント  
 IID が追加することによって作成されるインターフェイス*x*に`IID_`です。 たとえば場合、 *x*は`IPersistStorage`、IID がなります`IID_IPersistStorage`です。  
  
  
  
##  <a name="com_interface_entry_cached_tear_off"></a>  COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 すべてのインスタンスのインターフェイスに固有のデータを保存します。  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]ティアオフ インターフェイスの GUID です。  
  
 *x*  
 [in]インターフェイスを実装するクラスの名前。  
  
 `punk`  
 [in]名前、 **IUnknown**ポインター。 COM マップを含むクラスのメンバーである必要があります。 初期化する必要があります**NULL**クラス オブジェクトのコンス トラクターでします。  
  
### <a name="remarks"></a>コメント  
 インターフェイスは使用しない場合、このオブジェクトのインスタンス全体のサイズが削減されます。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="com_interface_entry_tear_off"></a>  COM_INTERFACE_ENTRY_TEAR_OFF  
 ティアオフ インターフェイスを公開します。  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]ティアオフ インターフェイスの GUID です。  
  
 *x*  
 [in]インターフェイスを実装するクラスの名前。  
  
### <a name="remarks"></a>コメント  
 ティアオフ インターフェイスは、インターフェイス表しますたびにインスタンス化される個別のオブジェクトが照会されたとして実装されます。 通常、インターフェイスをほとんど使用する場合、vtable ポインターが保存される、主要なオブジェクトのすべてのインスタンスでこのために、ティアオフとして、インターフェイスを構築します。 ティアオフ、参照カウントがゼロになるとは削除されます。 ティアオフを実装するクラスから派生する必要があります`CComTearOffObjectBase`独自の COM マップがあるとします。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="com_interface_entry_chain"></a>  COM_INTERFACE_ENTRY_CHAIN  
 処理が、COM マップ内のこのエントリに達すると、基底クラスの COM マップを処理します。  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>パラメーター  
 *classname*  
 [in]現在のオブジェクトの基本クラス。  
  
### <a name="remarks"></a>コメント  
 たとえば、次のコード。  
  
 [!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 COM マップ内の最初のエントリは、COM マップを格納するオブジェクトのインターフェイスである必要がありますに注意してください。 したがってで、COM マップ エントリを開始することはできません`COM_INTERFACE_ENTRY_CHAIN`、それが原因で、ポイントで検索する別のオブジェクトの COM マップ場所**COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** オブジェクトの COM マップに表示されます。 別のオブジェクトの COM マップを最初に検索する場合は、追加のインターフェイスのエントリを**IUnknown** COM マップにその他のオブジェクトの COM マップし、チェーンします。 例えば:  
  
 [!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
  
  
##  <a name="com_interface_entry_func"></a>  COM_INTERFACE_ENTRY_FUNC  
 ATL にフックするための一般的な機構`QueryInterface`ロジック。  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]公開されるインターフェイスの GUID です。  
  
 `dw`  
 [in]パラメーターに渡す、`func`です。  
  
 `func`  
 [in]返す関数ポインター`iid`です。  
  
### <a name="remarks"></a>コメント  
 場合*iid*で指定された関数について、照会されたインターフェイスの IID と一致する`func`と呼びます。 関数の宣言は次のようになります。  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 関数が呼び出されると、`pv`クラス オブジェクトを指します。 `riid`パラメーターは、クエリ対象のインターフェイスを指します`ppv`関数が、インターフェイスへのポインターを格納する場所へのポインターと`dw`エントリで指定するパラメーターです。 関数を設定する必要があります\*`ppv`に**NULL**返す**E_NOINTERFACE**または**S_FALSE**インターフェイスを返さないことを選択した場合。 **E_NOINTERFACE**、COM マップの処理を終了します。 **S_FALSE**、COM マップの処理が解決しない場合でも、インターフェイス ポインターが返されませんでした。 かどうか、関数からインターフェイス ポインターを返します`S_OK`です。  
  
  
  
##  <a name="com_interface_entry_func_blind"></a>  COM_INTERFACE_ENTRY_FUNC_BLIND  
 同じ[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)への呼び出しで結果の任意の IID のクエリを実行することを除いて、`func`です。  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>パラメーター  
 `dw`  
 [in]パラメーターに渡す、`func`です。  
  
 `func`  
 [in]取得、COM マップ内のこのエントリが処理されるときに呼び出される関数。  
  
### <a name="remarks"></a>コメント  
 失敗すると、COM マップの処理は継続します。 かどうか、関数からインターフェイス ポインターを返します`S_OK`です。  
  
  
##  <a name="com_interface_entry_nointerface"></a>  COM_INTERFACE_ENTRY_NOINTERFACE  
 返します**E_NOINTERFACE**と COM マップ処理について、指定したインターフェイスが照会されたときに終了します。  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]インターフェイス識別子を構築するために使用するテキスト。  
  
### <a name="remarks"></a>コメント  
 インターフェイスが、特定のケースで使用されていることを防ぐには、このマクロを使用できます。 使用している COM にこのマクロを挿入するなど、直前にマップ`COM_INTERFACE_ENTRY_AGGREGATE_BLIND`をインターフェイスのクエリが、集計の内部の"不明"に転送されることを防ぐためにします。  
  
 IID が追加することによって作成されるインターフェイス*x*に`IID_`です。 たとえば場合、 *x*は`IPersistStorage`、IID がなります`IID_IPersistStorage`です。  
  
  