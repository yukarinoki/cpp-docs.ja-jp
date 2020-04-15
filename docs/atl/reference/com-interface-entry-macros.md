---
title: COM インターフェイス エントリ マクロ
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
ms.openlocfilehash: bb7498f639f463290a4a6593ef7c0fbac09b539b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326674"
---
# <a name="com_interface_entry-macros"></a>COM_INTERFACE_ENTRYマクロ

これらのマクロは、オブジェクトのインターフェイスを COM マップに入力し、`QueryInterface`でアクセスできるようにします。 COM マップのエントリの順序は、インターフェイスが一致する IID の間に`QueryInterface`チェックされる順序です。

|||
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|インターフェイスを COM インターフェイス マップに入力します。|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|このマクロを使用して、2 つの継承の分岐を明確にします。|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|このマクロを使用して、インターフェイスを COM マップに入力し、その IID を指定します。|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|[COM_INTERFACE_ENTRY2](#com_interface_entry2)と同じですが、別の IID を指定できます。|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|*iid*で識別されるインターフェイスが照会されると、`COM_INTERFACE_ENTRY_AGGREGATE`に転送されます`punk`。|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)と同じですが、IID のクエリを実行するとクエリが*パンク*に転送される点が異なります。|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)と同じですが、*パンク*が NULL の場合を除いて *、clsid*によって記述された集計が自動的に作成されます。|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)と同じですが、IID のクエリを実行するとクエリが*punk*に転送され、*パンク*が NULL の場合は*clsid*で記述された集計が自動的に作成されます。|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|指定したインターフェイスが照会されたときに、プログラムが[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)を呼び出します。|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|すべてのインスタンスのインターフェイス固有のデータを保存します。|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|ティアオフ インターフェイスを公開します。|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|処理が COM マップ内のこのエントリに到達したときに、基本クラスの COM マップを処理します。|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL のロジックにフックするための一般的な`QueryInterface`メカニズム。|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)と同じですが、IID のクエリを実行すると*func*が呼び出される点が異なります。|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|指定されたインターフェイスに対してクエリが実行されたときに、E_NOINTERFACEを返し、COM マップ処理を終了します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="com_interface_entry"></a><a name="com_interface_entry"></a>COM_INTERFACE_ENTRY

インターフェイスを COM インターフェイス マップに入力します。

### <a name="syntax"></a>構文

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]クラス オブジェクトが直接派生するインターフェイスの名前。

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

**ヘッダー:** atlcom.h

## <a name="com_interface_entry2"></a><a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2

このマクロを使用して、2 つの継承の分岐を明確にします。

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]オブジェクトから公開するインターフェイスの名前。

*x2*<br/>
[in]*x*が公開される継承ブランチの名前。

### <a name="remarks"></a>解説

たとえば、クラス オブジェクトを 2 つのデュアル インターフェイスから派生させる`IDispatch`場合、いずれかの`IDispatch`インターフェイスから取得できるため、COM_INTERFACE_ENTRY2を使用して公開します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

## <a name="com_interface_entry_iid"></a><a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID

このマクロを使用して、インターフェイスを COM マップに入力し、その IID を指定します。

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]公開されるインターフェイスの GUID。

*X*<br/>
[in]vtable が*iid*で識別されるインターフェイスとして公開されるクラスの名前。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

## <a name="com_interface_entry2_iid"></a><a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID

[COM_INTERFACE_ENTRY2](#com_interface_entry2)と同じですが、別の IID を指定できます。

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]インターフェイスに指定する GUID。

*X*<br/>
[in]クラス オブジェクトが直接派生するインターフェイスの名前。

*x2*<br/>
[in]クラス オブジェクトが直接派生する 2 番目のインターフェイスの名前。

## <a name="com_interface_entry_aggregate"></a><a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE

*iid*で識別されるインタフェースが問い合わせられると、COM_INTERFACE_ENTRY_AGGREGATEは*punk*に転送されます。

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]照会対象のインターフェイスの GUID。

*パンク*<br/>
[in]`IUnknown`ポインターの名前。

### <a name="remarks"></a>解説

*punk*パラメーターは、集約の内部不明または NULL を指していると想定され、その場合、エントリーは無視されます。 通常は、`CoCreate`の集計を`FinalConstruct`使用します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

## <a name="com_interface_entry_aggregate_blind"></a><a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND

[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)と同じですが、IID のクエリを実行するとクエリが*パンク*に転送される点が異なります。

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
[in]`IUnknown`ポインターの名前。

### <a name="remarks"></a>解説

インターフェイス クエリが失敗した場合、COM マップの処理は続行されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

## <a name="com_interface_entry_autoaggregate"></a><a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE

[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)と同じですが、*パンク*が NULL の場合を除いて *、clsid*によって記述された集計が自動的に作成されます。

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]照会対象のインターフェイスの GUID。

*パンク*<br/>
[in]`IUnknown`ポインターの名前。 COM マップを含むクラスのメンバーである必要があります。

*Clsid*<br/>
[in]*パンク*が NULL の場合に作成される集計の識別子。

### <a name="remarks"></a>解説

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

## <a name="com_interface_entry_autoaggregate_blind"></a><a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)と同じですが、IID のクエリを実行するとクエリが*punk*に転送され、*パンク*が NULL の場合は*clsid*で記述された集計が自動的に作成されます。

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
[in]`IUnknown`ポインターの名前。 COM マップを含むクラスのメンバーである必要があります。

*Clsid*<br/>
[in]*パンク*が NULL の場合に作成される集計の識別子。

### <a name="remarks"></a>解説

インターフェイス クエリが失敗した場合、COM マップの処理は続行されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

## <a name="com_interface_entry_break"></a><a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK

指定したインターフェイスが照会されたときに、プログラムが[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)を呼び出します。

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]インターフェイス識別子の作成に使用されるテキスト。

### <a name="remarks"></a>解説

インターフェイス IID は、 に*x* `IID_`を追加して構築されます。 たとえば、 *x*が`IPersistStorage`の場合、IID`IID_IPersistStorage`は になります。

## <a name="com_interface_entry_cached_tear_off"></a><a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

すべてのインスタンスのインターフェイス固有のデータを保存します。

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]ティアオフ インターフェイスの GUID。

*X*<br/>
[in]インターフェイスを実装するクラスの名前。

*パンク*<br/>
[in]`IUnknown`ポインターの名前。 COM マップを含むクラスのメンバーである必要があります。 クラス オブジェクトのコンストラクターで NULL に初期化する必要があります。

### <a name="remarks"></a>解説

インターフェイスを使用しない場合、オブジェクトの全体的なインスタンス サイズが小さくなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

## <a name="com_interface_entry_tear_off"></a><a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF

ティアオフ インターフェイスを公開します。

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]ティアオフ インターフェイスの GUID。

*X*<br/>
[in]インターフェイスを実装するクラスの名前。

### <a name="remarks"></a>解説

ティアオフ インターフェイスは、それが表すインターフェイスが照会されるたびにインスタンス化される個別のオブジェクトとして実装されます。 通常、インターフェイスが使用されることはめったにない場合は、メイン オブジェクトのすべてのインスタンスに vtable ポインターが保存されるため、インターフェイスをティアオフとして構築します。 ティアオフは、参照カウントが 0 になると削除されます。 ティアオフを実装するクラスは、独自の`CComTearOffObjectBase`COM マップから派生し、独自の COM マップを持つ必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="com_interface_entry_chain"></a><a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN

処理が COM マップ内のこのエントリに到達したときに、基本クラスの COM マップを処理します。

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
[in]現在のオブジェクトの基本クラス。

### <a name="remarks"></a>解説

たとえば、次のコードを使用します。

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

COM マップの最初のエントリは、COM マップを含むオブジェクトのインターフェイスである必要があります。 したがって、COM_INTERFACE_ENTRY_CHAINを使用して COM **COM_INTERFACE_ENTRY_CHAIN**`COtherObject`**)** マップ エントリを開始することはできません。 別のオブジェクトの COM マップを検索する場合は、COM マップに`IUnknown`インターフェイス エントリを追加してから、他のオブジェクトの COM マップを連結します。 次に例を示します。

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

## <a name="com_interface_entry_func"></a><a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC

ATL のロジックにフックするための一般的な`QueryInterface`メカニズム。

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]公開されるインターフェイスの GUID。

*dw*<br/>
[in]*func*に渡されるパラメータ。

*Func*<br/>
[in]*iid*を返す関数ポインタ。

### <a name="remarks"></a>解説

*iid*が照会されるインタフェースの IID と一致する場合 *、func*によって指定された関数が呼び出されます。 関数の宣言は次のようになります。

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

関数が呼び出されると`pv`、クラス オブジェクトを指します。 *riid*パラメータは、照会されるインターフェイスを指し、`ppv`関数がインターフェイスへのポインタを格納する場所へのポインタであり *、dw*はエントリで指定したパラメータです。 関数は、NULL\*`ppv`に設定し、インターフェイスを返さない場合はE_NOINTERFACEまたはS_FALSEを返す必要があります。 E_NOINTERFACEすると、COM マップ処理が終了します。 S_FALSEでは、インターフェイス ポインターが返されなかったにもかかわらず、COM マップ処理が続行されます。 関数がインターフェイス ポインターを返す場合は、S_OK返す必要があります。

## <a name="com_interface_entry_func_blind"></a><a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND

[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)と同じですが、IID のクエリを実行すると*func*が呼び出される点が異なります。

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>パラメーター

*dw*<br/>
[in]*func*に渡されるパラメータ。

*Func*<br/>
[in]COM マップ内のこのエントリが処理されるときに呼び出される関数。

### <a name="remarks"></a>解説

エラーが発生すると、COM マップ上で処理が続行されます。 関数がインターフェイス ポインターを返す場合は、S_OK返す必要があります。

## <a name="com_interface_entry_nointerface"></a><a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE

指定されたインターフェイスに対してクエリが実行されたときに、E_NOINTERFACEを返し、COM マップ処理を終了します。

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]インターフェイス識別子の作成に使用されるテキスト。

### <a name="remarks"></a>解説

このマクロを使用すると、特定のケースでインターフェイスが使用されないようにすることができます。 たとえば、このマクロを COM マップに挿入してからCOM_INTERFACE_ENTRY_AGGREGATE_BLIND、インターフェイスのクエリが集計の内部不明に転送されないようにすることができます。

インターフェイス IID は、 に*x* `IID_`を追加して構築されます。 たとえば、 *x*が`IPersistStorage`の場合、IID`IID_IPersistStorage`は になります。
