---
title: COM インターフェイスのエントリマクロ
ms.date: 03/28/2017
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
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
ms.openlocfilehash: 1358a51f6bcb65f9c54c2006a6a467cf96593b5f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834701"
---
# <a name="com_interface_entry-macros"></a>COM_INTERFACE_ENTRY マクロ

これらのマクロは、によってアクセスできるように、オブジェクトのインターフェイスを COM マップに入力し `QueryInterface` ます。 COM マップ内のエントリの順序は、の間に、一致する IID に対して順序のインターフェイスがチェックされることを示し `QueryInterface` ます。

|マクロ|説明|
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|COM インターフェイスマップにインターフェイスを入力します。|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|このマクロは、継承の2つの分岐を明確にするために使用します。|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|このマクロを使用して、COM マップにインターフェイスを入力し、その IID を指定します。|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|[COM_INTERFACE_ENTRY2](#com_interface_entry2)と同じですが、別の IID を指定することができます。|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|*Iid*によって識別されるインターフェイスがに対して照会されると、は `COM_INTERFACE_ENTRY_AGGREGATE` に転送され `punk` ます。|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)と同じですが、任意の IID を照会すると、クエリが*punk*に転送される点が異なります。|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)と同じですが、 *punk*が NULL の場合を除き、 *clsid*によって記述された集計が自動的に作成されます。|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)と同じですが、任意の IID に対してクエリを実行すると、クエリが*punk*に転送されます。また、 *punk*が NULL の場合、 *clsid*によって記述された集計が自動的に作成されます。|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|指定したインターフェイスに対してクエリを行うときに、プログラムによって [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) が呼び出されるようにします。|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|すべてのインスタンスのインターフェイス固有のデータを保存します。|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|は、ティアオフインターフェイスを公開します。|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|処理が COM マップ内のこのエントリに到達したときに、基底クラスの COM マップを処理します。|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL のロジックにフックするための一般的なメカニズム `QueryInterface` 。|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)と同じですが、任意の IID を照会すると*FUNC*が呼び出されます。|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|指定したインターフェイスに対してクエリを実行するときに、E_NOINTERFACE を返し、COM マップの処理を終了します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

## <a name="com_interface_entry"></a><a name="com_interface_entry"></a> COM_INTERFACE_ENTRY

COM インターフェイスマップにインターフェイスを入力します。

### <a name="syntax"></a>構文

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
からクラスオブジェクトが直接派生するインターフェイスの名前。

### <a name="remarks"></a>解説

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

**ヘッダー:** atlcom. h

## <a name="com_interface_entry2"></a><a name="com_interface_entry2"></a> COM_INTERFACE_ENTRY2

このマクロは、継承の2つの分岐を明確にするために使用します。

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>パラメーター

*x*<br/>
からオブジェクトから公開するインターフェイスの名前。

*×*<br/>
から *X* が公開される継承分岐の名前。

### <a name="remarks"></a>解説

たとえば、2つのデュアルインターフェイスからクラスオブジェクトを派生させる場合は、 `IDispatch` `IDispatch` インターフェイスのいずれかから取得できるため、COM_INTERFACE_ENTRY2 を使用して公開します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

## <a name="com_interface_entry_iid"></a><a name="com_interface_entry_iid"></a> COM_INTERFACE_ENTRY_IID

このマクロを使用して、COM マップにインターフェイスを入力し、その IID を指定します。

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
から公開されているインターフェイスの GUID。

*x*<br/>
から *Iid*によって識別されるインターフェイスとして公開される vtable を持つクラスの名前。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

## <a name="com_interface_entry2_iid"></a><a name="com_interface_entry2_iid"></a> COM_INTERFACE_ENTRY2_IID

[COM_INTERFACE_ENTRY2](#com_interface_entry2)と同じですが、別の IID を指定することができます。

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
からインターフェイスに指定する GUID。

*x*<br/>
からクラスオブジェクトが直接派生するインターフェイスの名前。

*×*<br/>
からクラスオブジェクトが直接派生する2番目のインターフェイスの名前。

## <a name="com_interface_entry_aggregate"></a><a name="com_interface_entry_aggregate"></a> COM_INTERFACE_ENTRY_AGGREGATE

*Iid*によって識別されるインターフェイスがに対して照会されると、COM_INTERFACE_ENTRY_AGGREGATE は*punk*に転送されます。

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
からに対して照会されたインターフェイスの GUID。

*パンク*<br/>
からポインターの名前 `IUnknown` 。

### <a name="remarks"></a>解説

*Punk*パラメーターは、集計の内部不明または NULL を指していると想定されます。この場合、エントリは無視されます。 通常は、 `CoCreate` で集計し `FinalConstruct` ます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

## <a name="com_interface_entry_aggregate_blind"></a><a name="com_interface_entry_aggregate_blind"></a> COM_INTERFACE_ENTRY_AGGREGATE_BLIND

[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)と同じですが、任意の IID を照会すると、クエリが*punk*に転送される点が異なります。

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
からポインターの名前 `IUnknown` 。

### <a name="remarks"></a>解説

インターフェイスのクエリが失敗した場合、COM マップの処理は続行されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

## <a name="com_interface_entry_autoaggregate"></a><a name="com_interface_entry_autoaggregate"></a> COM_INTERFACE_ENTRY_AUTOAGGREGATE

[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)と同じですが、 *punk*が NULL の場合を除き、 *clsid*によって記述された集計が自動的に作成されます。

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
からに対して照会されたインターフェイスの GUID。

*パンク*<br/>
からポインターの名前 `IUnknown` 。 は、COM マップを含むクラスのメンバーである必要があります。

*clsid*<br/>
から *Punk* が NULL の場合に作成される集計の識別子。

### <a name="remarks"></a>解説

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

## <a name="com_interface_entry_autoaggregate_blind"></a><a name="com_interface_entry_autoaggregate_blind"></a> COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)と同じですが、任意の IID に対してクエリを実行すると、クエリが*punk*に転送されます。また、 *punk*が NULL の場合、 *clsid*によって記述された集計が自動的に作成されます。

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
からポインターの名前 `IUnknown` 。 は、COM マップを含むクラスのメンバーである必要があります。

*clsid*<br/>
から *Punk* が NULL の場合に作成される集計の識別子。

### <a name="remarks"></a>解説

インターフェイスのクエリが失敗した場合、COM マップの処理は続行されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

## <a name="com_interface_entry_break"></a><a name="com_interface_entry_break"></a> COM_INTERFACE_ENTRY_BREAK

指定したインターフェイスに対してクエリを行うときに、プログラムによって [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) が呼び出されるようにします。

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>パラメーター

*x*<br/>
からインターフェイス識別子を構築するために使用されるテキスト。

### <a name="remarks"></a>解説

インターフェイス IID は、に *x* を追加することによって構築され `IID_` ます。 たとえば、 *x* がの場合、IID はになり `IPersistStorage` `IID_IPersistStorage` ます。

## <a name="com_interface_entry_cached_tear_off"></a><a name="com_interface_entry_cached_tear_off"></a> COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

すべてのインスタンスのインターフェイス固有のデータを保存します。

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
からティアオフインターフェイスの GUID。

*x*<br/>
からインターフェイスを実装しているクラスの名前。

*パンク*<br/>
からポインターの名前 `IUnknown` 。 は、COM マップを含むクラスのメンバーである必要があります。 は、クラスオブジェクトのコンストラクターで NULL に初期化される必要があります。

### <a name="remarks"></a>解説

インターフェイスが使用されていない場合は、これにより、オブジェクトのインスタンス全体のサイズが減少します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

## <a name="com_interface_entry_tear_off"></a><a name="com_interface_entry_tear_off"></a> COM_INTERFACE_ENTRY_TEAR_OFF

は、ティアオフインターフェイスを公開します。

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
からティアオフインターフェイスの GUID。

*x*<br/>
からインターフェイスを実装しているクラスの名前。

### <a name="remarks"></a>解説

ティアオフインターフェイスは、それが表すインターフェイスが照会されるたびにインスタンス化される個別のオブジェクトとして実装されます。 通常、インターフェイスがほとんど使用されない場合は、インターフェイスをティアオフとして構築します。これにより、メインオブジェクトのすべてのインスタンスに vtable ポインターが保存されるためです。 破棄は、その参照カウントが0になると削除されます。 ティアオフを実装するクラスは、から派生し、 `CComTearOffObjectBase` 独自の COM マップを持つ必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="com_interface_entry_chain"></a><a name="com_interface_entry_chain"></a> COM_INTERFACE_ENTRY_CHAIN

処理が COM マップ内のこのエントリに到達したときに、基底クラスの COM マップを処理します。

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>パラメーター

*classname*<br/>
から現在のオブジェクトの基本クラス。

### <a name="remarks"></a>解説

たとえば、次のコードを使用します。

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

COM マップの最初のエントリは、COM マップを含むオブジェクトのインターフェイスである必要があることに注意してください。 したがって、COM_INTERFACE_ENTRY_CHAIN で com マップエントリを開始することはできません。これにより、 **COM_INTERFACE_ENTRY_CHAIN (** `COtherObject` **)** がオブジェクトの com マップに表示される位置で、異なるオブジェクトの com マップが検索されます。 別のオブジェクトの COM マップを最初に検索する場合は、のインターフェイスエントリを `IUnknown` com マップに追加してから、他のオブジェクトの com マップをチェーンします。 次に例を示します。

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

## <a name="com_interface_entry_func"></a><a name="com_interface_entry_func"></a> COM_INTERFACE_ENTRY_FUNC

ATL のロジックにフックするための一般的なメカニズム `QueryInterface` 。

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
から公開されているインターフェイスの GUID。

*dw*<br/>
から *Func*に渡されるパラメーター。

*func*<br/>
から *Iid*を返す関数ポインター。

### <a name="remarks"></a>解説

*Iid*がに対して照会されたインターフェイスの iid と一致する場合、 *func*によって指定された関数が呼び出されます。 関数の宣言は次のようになります。

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

関数が呼び出されると、は `pv` クラスオブジェクトをポイントします。 *Riid*パラメーターは、クエリ対象のインターフェイスを参照します。 `ppv` は、関数がインターフェイスへのポインターを格納する場所へのポインターであり、 *dw*はエントリで指定したパラメーターです。 関数は、 \* `ppv` を NULL に設定し、インターフェイスを返さないことを選択した場合は E_NOINTERFACE または S_FALSE を返します。 E_NOINTERFACE では、COM マップの処理が終了します。 S_FALSE を使用すると、インターフェイスポインターが返されなかった場合でも、COM マップ処理が続行されます。 関数がインターフェイスポインターを返す場合は、S_OK を返す必要があります。

## <a name="com_interface_entry_func_blind"></a><a name="com_interface_entry_func_blind"></a> COM_INTERFACE_ENTRY_FUNC_BLIND

[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)と同じですが、任意の IID を照会すると*FUNC*が呼び出されます。

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>パラメーター

*dw*<br/>
から *Func*に渡されるパラメーター。

*func*<br/>
からCOM マップ内のこのエントリが処理されるときに呼び出される関数。

### <a name="remarks"></a>解説

エラーが発生すると、COM マップで処理が続行されます。 関数がインターフェイスポインターを返す場合は、S_OK を返す必要があります。

## <a name="com_interface_entry_nointerface"></a><a name="com_interface_entry_nointerface"></a> COM_INTERFACE_ENTRY_NOINTERFACE

指定したインターフェイスに対してクエリを実行するときに、E_NOINTERFACE を返し、COM マップの処理を終了します。

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>パラメーター

*x*<br/>
からインターフェイス識別子を構築するために使用されるテキスト。

### <a name="remarks"></a>解説

このマクロを使用すると、特定のケースでインターフェイスが使用されないようにすることができます。 たとえば、このマクロを COM マップに挿入して COM_INTERFACE_ENTRY_AGGREGATE_BLIND 前に、インターフェイスのクエリが集計の内部不明に転送されるのを防ぐことができます。

インターフェイス IID は、に *x* を追加することによって構築され `IID_` ます。 たとえば、 *x* がの場合、IID はになり `IPersistStorage` `IID_IPersistStorage` ます。
