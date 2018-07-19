---
title: COM インターフェイス エントリ マクロ |Microsoft Docs
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
ms.openlocfilehash: 9fa450436bee52aa9cd13803e3bf51c6a500fa0e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883376"
---
# <a name="cominterfaceentry-macros"></a>COM_INTERFACE_ENTRY マクロ  
 アクセスできるように、これらのマクロでその COM マップにオブジェクトのインターフェイスが入力`QueryInterface`します。 COM マップ内のエントリの順序は、注文インターフェイスのチェック中に一致する IID 対象となる`QueryInterface`します。  

 |||
 |-|-|
 |[COM_INTERFACE_ENTRY](#com_interface_entry)|COM インターフェイス マップ インターフェイスに入力します。|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|継承の 2 つの分岐を解消するために、このマクロを使用します。|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|このマクロを使用して、インターフェイスを COM マップに入力し、インターフェイスの IID を指定します。|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|同じ[COM_INTERFACE_ENTRY2](#com_interface_entry2)。 ただし、別の IID を指定することができます。|  
|[定義](#com_interface_entry_aggregate)|インターフェイスがで識別される*iid*照会、`COM_INTERFACE_ENTRY_AGGREGATE`転送`punk`します。|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|同じ[で定義](#com_interface_entry_aggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除いて、 *punk*します。|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|同じ[で定義](#com_interface_entry_aggregate)、場合を除く*punk*が null の場合で説明されている集計を自動的に作成、 *clsid*します。|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|同じ[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除いて、 *punk*、場合*punk*が null の場合、自動的に作成します。説明されている集計、 *clsid*します。|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|プログラムを呼び出すと、 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297)について、指定したインターフェイスを照会する場合。|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|インスタンスごとにインターフェイスに固有のデータを保存します。|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|ティアオフ インターフェイスを公開します。|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|COM マップ内のこのエントリに達したら、処理は、基底クラスの COM マップを処理します。|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL にフックする汎用的なメカニズム`QueryInterface`ロジック。|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|同じ[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)への呼び出しの結果の任意の IID のクエリを実行することを除いて、 *func*します。|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|E_NOINTERFACE を返すし、COM マップ処理の指定したインターフェイスが照会されたときに終了します。|  

## <a name="requirements"></a>必要条件
**ヘッダー:** atlcom.h

## <a name="com_interface_entry"></a> COM_INTERFACE_ENTRY
COM インターフェイス マップ インターフェイスに入力します。

### <a name="syntax"></a>構文

```
COM_INTERFACE_ENTRY( x )
```
### <a name="parameters"></a>パラメーター

[in] インターフェイスの名前の x クラスのオブジェクトから派生直接します。

### <a name="remarks"></a>Remarks
通常、これは最も頻繁に使用するエントリの種類です。

### <a name="example"></a>例
```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```
### <a name="requirements"></a>必要条件
**ヘッダー:** atlcom.h
  
##  <a name="com_interface_entry2"></a>  COM_INTERFACE_ENTRY2  
 継承の 2 つの分岐を解消するために、このマクロを使用します。  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]オブジェクトから公開するインターフェイスの名前。  
  
 *x2*  
 [in]継承元のブランチの名前*x*公開されます。  
  
### <a name="remarks"></a>Remarks  
 たとえば、2 つのデュアル インターフェイス オブジェクトのクラスを派生する場合を公開する`IDispatch`COM_INTERFACE_ENTRY2 以降を使用して`IDispatch`インターフェイスのいずれかから取得できます。  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="com_interface_entry_iid"></a>  COM_INTERFACE_ENTRY_IID  
 このマクロを使用して、インターフェイスを COM マップに入力し、インターフェイスの IID を指定します。  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>パラメーター  
 *iid*  
 [in]公開されるインターフェイスの GUID です。  
  
 *x*  
 [in]Vtable で識別されるインターフェイスとして公開されるクラスの名前*iid*します。  
  
 
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="com_interface_entry2_iid"></a>  COM_INTERFACE_ENTRY2_IID  
 同じ[COM_INTERFACE_ENTRY2](#com_interface_entry2)。 ただし、別の IID を指定することができます。  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>パラメーター  
 *iid*  
 [in]インターフェイスを指定する GUID です。  
  
 *x*  
 [in]クラスのオブジェクトが直接から派生したインターフェイスの名前。  
  
 *x2*  
 [in]クラスのオブジェクトが直接から派生する 2 番目のインターフェイスの名前。  
  
##  <a name="com_interface_entry_aggregate"></a>  定義  
 インターフェイスがで識別される*iid*で定義を転送するは、クエリが実行*punk*します。  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>パラメーター  
 *iid*  
 [in]クエリを実行するインターフェイスの GUID です。  
  
 *punk*  
 [in]名前、`IUnknown`ポインター。  
  
### <a name="remarks"></a>Remarks  
 *Punk*パラメーターが指す集計の内部不明または null の場合、この場合、エントリは無視されますと見なされます。 通常の場合`CoCreate`で集計`FinalConstruct`します。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="com_interface_entry_aggregate_blind"></a>  COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 同じ[で定義](#com_interface_entry_aggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除いて、 *punk*します。  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>パラメーター  
 *punk*  
 [in]名前、`IUnknown`ポインター。  
  
### <a name="remarks"></a>Remarks  
 インターフェイスのクエリが失敗したかどうかは、COM マップの処理は継続します。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  

##  <a name="com_interface_entry_autoaggregate"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 同じ[で定義](#com_interface_entry_aggregate)、場合を除く*punk*が null の場合で説明されている集計を自動的に作成、 *clsid*します。  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>パラメーター  
 *iid*  
 [in]クエリを実行するインターフェイスの GUID です。  
  
 *punk*  
 [in]名前、`IUnknown`ポインター。 COM マップを含むクラスのメンバーである必要があります。  
  
 *clsid*  
 [in]場合に作成される集計の識別子*punk*は NULL です。  
  
### <a name="remarks"></a>Remarks  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="com_interface_entry_autoaggregate_blind"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 同じ[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除いて、 *punk*、場合*punk*が null の場合、自動的に作成します。説明されている集計、 *clsid*します。  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>パラメーター  
 *punk*  
 [in]名前、`IUnknown`ポインター。 COM マップを含むクラスのメンバーである必要があります。  
  
 *clsid*  
 [in]場合に作成される集計の識別子*punk*は NULL です。  
  
### <a name="remarks"></a>Remarks  
 インターフェイスのクエリが失敗したかどうかは、COM マップの処理は継続します。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="com_interface_entry_break"></a>  COM_INTERFACE_ENTRY_BREAK  
 プログラムを呼び出すと、 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297)について、指定したインターフェイスを照会する場合。  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]インターフェイスの識別子を作成するために使用するテキスト。  
  
### <a name="remarks"></a>Remarks  
 インターフェイスの IID を追加することによって構築されます*x*に`IID_`します。 たとえば場合、 *x*は`IPersistStorage`、IID がなります`IID_IPersistStorage`。  
  
  
  
##  <a name="com_interface_entry_cached_tear_off"></a>  COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 インスタンスごとにインターフェイスに固有のデータを保存します。  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>パラメーター  
 *iid*  
 [in]ティアオフ インターフェイスの GUID です。  
  
 *x*  
 [in]インターフェイスを実装するクラスの名前。  
  
 *punk*  
 [in]名前、`IUnknown`ポインター。 COM マップを含むクラスのメンバーである必要があります。 クラス オブジェクトのコンス トラクターに NULL に初期化する必要があります。  
  
### <a name="remarks"></a>Remarks  
 このインターフェイスを使用しない場合、オブジェクトのインスタンス全体のサイズが低くなります。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="com_interface_entry_tear_off"></a>  COM_INTERFACE_ENTRY_TEAR_OFF  
 ティアオフ インターフェイスを公開します。  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>パラメーター  
 *iid*  
 [in]ティアオフ インターフェイスの GUID です。  
  
 *x*  
 [in]インターフェイスを実装するクラスの名前。  
  
### <a name="remarks"></a>Remarks  
 ティアオフ インターフェイスは、たびに、インターフェイスを表しますがインスタンス化する個別のオブジェクトのクエリを実行するように実装されます。 通常、vtable のポインター、主要なオブジェクトのすべてのインスタンスに保存されますので、インターフェイスを使用ことはほとんどありませんが場合に、ティアオフとして、インターフェイスを構築します。 参照カウントが 0 になるときに、ティアオフは削除されます。 ティアオフを実装するクラスから派生する必要があります`CComTearOffObjectBase`独自の COM マップがあるとします。  
  
  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="com_interface_entry_chain"></a>  COM_INTERFACE_ENTRY_CHAIN  
 COM マップ内のこのエントリに達したら、処理は、基底クラスの COM マップを処理します。  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>パラメーター  
 *classname*  
 [in]現在のオブジェクトの基本クラス。  
  
### <a name="remarks"></a>Remarks  
 たとえば、次のコードで  
  
 [!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 COM マップの最初のエントリは、COM マップを格納しているオブジェクトのインターフェイスである必要がありますに注意してください。 したがって、COM_INTERFACE_ENTRY_CHAIN、これにより、ポイントで検索する別のオブジェクトの COM マップで、COM マップ エントリを開始することはできません、 **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** オブジェクトの COM マップに表示されます。 別のオブジェクトの COM マップを最初に検索する場合は、インターフェイスのエントリを追加`IUnknown`COM マップに、その他のオブジェクトの COM マップし、チェーンします。 例えば:  
  
 [!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
  
  
##  <a name="com_interface_entry_func"></a>  COM_INTERFACE_ENTRY_FUNC  
 ATL にフックする汎用的なメカニズム`QueryInterface`ロジック。  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>パラメーター  
 *iid*  
 [in]公開されるインターフェイスの GUID です。  
  
 *dw*  
 [in]パラメーターに渡す、 *func*します。  
  
 *func*  
 [in]関数ポインターを返す*iid*します。  
  
### <a name="remarks"></a>Remarks  
 場合*iid*で指定された関数、クエリを実行するインターフェイスの IID と一致する*func*が呼び出されます。 関数の宣言は次のようになります。  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 関数が呼び出されると、`pv`クラス オブジェクトを指します。 *Riid*パラメーターは、クエリ対象のインターフェイスを指します`ppv`関数が、インターフェイスへのポインターを格納する必要がありますの場所へのポインターと*dw*パラメーターをエントリで指定します。 関数を設定する必要があります\*`ppv`を NULL と戻り値の E_NOINTERFACE または自由にインターフェイスを返す場合は S_FALSE。 E_NOINTERFACE では、COM マップの処理が終了します。 S_false、COM マップの処理が引き続き発生する場合でも、インターフェイス ポインターが返されませんでした。 インターフェイス ポインターを関数から返された場合 S_OK が返されます。  
  
  
  
##  <a name="com_interface_entry_func_blind"></a>  COM_INTERFACE_ENTRY_FUNC_BLIND  
 同じ[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)への呼び出しの結果の任意の IID のクエリを実行することを除いて、 *func*します。  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>パラメーター  
 *dw*  
 [in]パラメーターに渡す、 *func*します。  
  
 *func*  
 [in]COM マップ内のこのエントリが処理されるときに呼び出される関数。  
  
### <a name="remarks"></a>Remarks  
 失敗すると、COM マップの処理は継続します。 インターフェイス ポインターを関数から返された場合 S_OK が返されます。  
  
  
##  <a name="com_interface_entry_nointerface"></a>  COM_INTERFACE_ENTRY_NOINTERFACE  
 E_NOINTERFACE を返すし、COM マップ処理の指定したインターフェイスが照会されたときに終了します。  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]インターフェイスの識別子を作成するために使用するテキスト。  
  
### <a name="remarks"></a>Remarks  
 インターフェイスが特定のケースで使用されていることを防ぐために、このマクロを使用することができます。 たとえば、インターフェイスのクエリが集計の内部の"不明"に転送されることを防ぐために COM_INTERFACE_ENTRY_AGGREGATE_BLIND 直前、COM マップに、このマクロを挿入できます。  
  
 インターフェイスの IID を追加することによって構築されます*x*に`IID_`します。 たとえば場合、 *x*は`IPersistStorage`、IID がなります`IID_IPersistStorage`。  
  
  