---
title: CComObjectRootEx クラス
ms.date: 11/04/2016
f1_keywords:
- CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::InternalAddRef
- ATLCOM/ATL::InternalRelease
- ATLCOM/ATL::Lock
- ATLCOM/ATL::Unlock
- ATLCOM/ATL::FinalConstruct
- ATLCOM/ATL::FinalRelease
- ATLCOM/ATL::OuterAddRef
- ATLCOM/ATL::OuterQueryInterface
- ATLCOM/ATL::OuterRelease
- ATLCOM/ATL::InternalQueryInterface
- ATLCOM/ATL::ObjectMain
- ATLCOM/ATL::m_dwRef
- ATLCOM/ATL::m_pOuterUnknown
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
ms.openlocfilehash: b4dbc42cb0c6fe2c9c6692e0db37267ce3fff361
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833648"
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx クラス

このクラスは、非集計と集計されたオブジェクトの両方のオブジェクト参照カウント管理を処理するメソッドを提供します。

## <a name="syntax"></a>構文

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>パラメーター

*ThreadModel*<br/>
目的のスレッド処理モデルを実装するメソッドを持つクラス。 *Threadmodel*を[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)、 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)、または[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)に設定することによって、スレッドモデルを明示的に選択できます。 *Threadmodel*を[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)または[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)に設定することにより、サーバーの既定のスレッドモデルを受け入れることができます。

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|関数|説明|
|-|-|
|[CComObjectRootEx](#ccomobjectrootex)|コンストラクターです。|
|[InternalAddRef](#internaladdref)|非集計オブジェクトの参照カウントをインクリメントします。|
|[InternalRelease](#internalrelease)|非集計オブジェクトの参照カウントをデクリメントします。|
|[[Lock] (ロック)](#lock)|スレッドモデルがマルチスレッドの場合、はクリティカルセクションオブジェクトの所有権を取得します。|
|[ロック](#unlock)|スレッドモデルがマルチスレッドの場合、はクリティカルセクションオブジェクトの所有権を解放します。|

### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase メソッド

|関数|説明|
|-|-|
|[FinalConstruct](#finalconstruct)|クラスでをオーバーライドして、オブジェクトに必要な初期化を実行します。|
|[FinalRelease](#finalrelease)|クラスでをオーバーライドして、オブジェクトに必要なクリーンアップを実行します。|
|[OuterAddRef](#outeraddref)|集計されたオブジェクトの参照カウントをインクリメントします。|
|[OuterQueryInterface](#outerqueryinterface)|集計されたオブジェクトの外側にデリゲートし `IUnknown` ます。|
|[OuterRelease](#outerrelease)|集計されたオブジェクトの参照カウントをデクリメントします。|

### <a name="static-functions"></a>静的関数

|関数|説明|
|-|-|
|[InternalQueryInterface](#internalqueryinterface)|`IUnknown`非集計オブジェクトのにデリゲートします。|
|[ObjectMain](#objectmain)|オブジェクトマップに示されている派生クラスのモジュールの初期化中および終了時に呼び出されます。|

### <a name="data-members"></a>データ メンバー

|データ メンバー|説明|
|-|-|
|[m_dwRef](#m_dwref)|では `m_pOuterUnknown` 、共用体の一部です。 およびの参照カウントを保持するためにオブジェクトが集約されていない場合に使用され `AddRef` `Release` ます。|
|[m_pOuterUnknown](#m_pouterunknown)|では `m_dwRef` 、共用体の一部です。 オブジェクトが集計され、外側の不明へのポインターを保持するときに使用されます。|

## <a name="remarks"></a>解説

`CComObjectRootEx` 非集計と集計されたオブジェクトの両方のオブジェクト参照カウント管理を処理します。 オブジェクトが集計されていない場合、オブジェクト参照カウントを保持し、オブジェクトが集計されている場合は、外側の unknown へのポインターを保持します。 集計オブジェクトの場合、 `CComObjectRootEx` メソッドを使用して、構築する内部オブジェクトのエラーを処理したり、内部インターフェイスが解放されたとき、または内部オブジェクトが削除されたときに外部オブジェクトを削除から保護したりできます。

COM サーバーを実装するクラスは、または CComObjectRoot から継承する必要があり `CComObjectRootEx` ます。 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

クラス定義で [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) マクロが指定されている場合、ATL `CComPolyObject<CYourClass>` はが呼び出されたときにのインスタンスを作成し `IClassFactory::CreateInstance` ます。 作成時に、[外側の不明] の値がチェックされます。 NULL の場合は、 `IUnknown` 非集計オブジェクトに対してが実装されます。 外側の unknown が NULL でない場合、 `IUnknown` は集計オブジェクトに対して実装されます。

クラスで DECLARE_POLY_AGGREGATABLE マクロが指定されていない場合、ATL は集計された `CAggComObject<CYourClass>` オブジェクトまたはのインスタンスを非集計オブジェクト用に作成し `CComObject<CYourClass>` ます。

を使用する利点 `CComPolyObject` は、集計された `CComAggObject` `CComObject` ケースと非集計ケースを処理するためにとの両方のモジュールを使用しないことです。 1つの `CComPolyObject` オブジェクトが両方のケースを処理します。 したがって、モジュールには、vtable のコピーと関数のコピーが1つだけ存在します。 Vtable が大きい場合は、モジュールのサイズを大幅に減らすことができます。 ただし、vtable が小さい場合、を使用する `CComPolyObject` と、とのように集計または非集計オブジェクトに対して最適化されていないため、モジュールサイズが少し大きくなり `CComAggObject` `CComObject` ます。

オブジェクトが集計されている場合、 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) はまたはによって実装され `CComAggObject` `CComPolyObject` ます。 これらのクラスは、、、 `QueryInterface` `AddRef` および `Release` を呼び出して、 `CComObjectRootEx` `OuterQueryInterface` `OuterAddRef` `OuterRelease` 不明な外側のに転送します。 通常、クラスでをオーバーライドして `CComObjectRootEx::FinalConstruct` 集計オブジェクトを作成し、をオーバーライドして `CComObjectRootEx::FinalRelease` 集計されたオブジェクトをすべて解放します。

オブジェクトが集計されていない場合、は `IUnknown` またはによって実装され `CComObject` `CComPolyObject` ます。 この場合、 `QueryInterface` 、、およびへ `AddRef` の呼び出し `Release` は `CComObjectRootEx` `InternalQueryInterface` 、実際の `InternalAddRef` `InternalRelease` 操作を実行するために、、、およびに委任されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

## <a name="ccomobjectrootexccomobjectrootex"></a><a name="ccomobjectrootex"></a> CComObjectRootEx:: CComObjectRootEx

コンストラクターは、参照カウントを0に初期化します。

```
CComObjectRootEx();
```

## <a name="ccomobjectrootexfinalconstruct"></a><a name="finalconstruct"></a> CComObjectRootEx:: FinalConstruct

派生クラスでこのメソッドをオーバーライドすると、オブジェクトに必要な初期化を実行できます。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、標準エラーの HRESULT 値の1つを返します。

### <a name="remarks"></a>解説

既定では、は `CComObjectRootEx::FinalConstruct` 単に S_OK を返します。

クラスのコンストラクターではなく、で初期化を実行すると、次のような利点があり `FinalConstruct` ます。

- コンストラクターから状態コードを返すことはできませんが、の戻り値を使用して HRESULT を返すことができ `FinalConstruct` ます。 クラスのオブジェクトが ATL によって提供される標準のクラスファクトリを使用して作成されている場合、この戻り値は COM クライアントに反映され、詳細なエラー情報を提供することができます。

- 仮想関数をクラスのコンストラクターから呼び出すことはできません。 クラスのコンストラクターから仮想関数を呼び出すと、継承階層のその時点で定義されているように、関数の呼び出しが静的に解決されます。 純粋仮想関数を呼び出すと、リンカーエラーが発生します。

   クラスは、継承階層の最派生クラスではありません。このクラスは、その機能の一部を提供するために、ATL によって提供される派生クラスに依存しています。 初期化では、そのクラスによって提供される機能を使用する必要があります (これは、クラスのオブジェクトが他のオブジェクトを集計する必要がある場合は確かに当てはまりますが、クラスのコンストラクターにはこれらの機能にアクセスする方法がないためです)。 クラスの構築コードは、最派生クラスが完全に構築される前に実行されます。

   ただし、 `FinalConstruct` は、ほとんどの派生クラスが完全に構築された直後に呼び出されます。これにより、仮想関数を呼び出し、ATL によって提供される参照カウントの実装を使用できるようになります。

### <a name="example"></a>例

通常は、から派生したクラスでこのメソッドをオーバーライドして、 `CComObjectRootEx` 集計されたオブジェクトを作成します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

構築に失敗した場合は、エラーを返すことができます。 また、作成時に内部集計オブジェクトが参照カウントをインクリメントし、カウントを0にデクリメントする場合、マクロ [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) を使用して外部オブジェクトを削除から保護することもできます。

次に、集計を作成する一般的な方法を示します。

- `IUnknown`クラスオブジェクトへのポインターを追加し、コンストラクターで NULL に初期化します。

- をオーバーライドし `FinalConstruct` て、集計を作成します。

- `IUnknown` [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate)マクロのパラメーターとして定義したポインターを使用します。

- をオーバーライドし `FinalRelease` て、ポインターを解放し `IUnknown` ます。

## <a name="ccomobjectrootexfinalrelease"></a><a name="finalrelease"></a> CComObjectRootEx:: FinalRelease

派生クラスでこのメソッドをオーバーライドすると、オブジェクトに必要なクリーンアップを実行できます。

```cpp
void FinalRelease();
```

### <a name="remarks"></a>解説

既定で `CComObjectRootEx::FinalRelease` は、は何も行いません。

でクリーンアップを実行 `FinalRelease` することは、が呼び出された時点でオブジェクトが完全に構築されているため、クラスのデストラクターにコードを追加することをお勧めし `FinalRelease` ます。 これにより、最も派生したクラスによって提供されるメソッドに安全にアクセスできます。 これは、削除前に集計されたオブジェクトを解放する場合に特に重要です。

## <a name="ccomobjectrootexinternaladdref"></a><a name="internaladdref"></a> CComObjectRootEx:: InternalAddRef

非集計オブジェクトの参照カウントを1だけインクリメントします。

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>戻り値

診断とテストに役立つ可能性のある値。

### <a name="remarks"></a>解説

スレッドモデルがマルチスレッドの場合、を使用して、複数の `InterlockedIncrement` スレッドが同時に参照カウントを変更できないようにします。

## <a name="ccomobjectrootexinternalqueryinterface"></a><a name="internalqueryinterface"></a> CComObjectRootEx:: InternalQueryInterface

要求されたインターフェイスへのポインターを取得します。

```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*pThis*<br/>
からに公開されているインターフェイスの COM マップを格納しているオブジェクトへのポインター `QueryInterface` 。

*pEntries*<br/>
から `_ATL_INTMAP_ENTRY` 使用可能なインターフェイスのマップにアクセスする構造体へのポインター。

*iid*<br/>
から要求されているインターフェイスの GUID。

*ppvObject*<br/>
入出力 *Iid*で指定されたインターフェイスポインターへのポインター。インターフェイスが見つからない場合は NULL。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

`InternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。 オブジェクトが集計されている場合、 `InternalQueryInterface` は外側の不明なに委任しません。 COM マップテーブルには、マクロ [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) またはそのバリアントの1つを使用して、インターフェイスを入力できます。

## <a name="ccomobjectrootexinternalrelease"></a><a name="internalrelease"></a> CComObjectRootEx:: InternalRelease

非集計オブジェクトの参照カウントを1だけデクリメントします。

```
ULONG InternalRelease();
```

### <a name="return-value"></a>戻り値

非デバッグビルドとデバッグビルドの両方で、この関数は、診断またはテストに役立つ可能性がある値を返します。 返される正確な値は、使用されるオペレーティングシステムなどの多くの要因によって異なります。また、参照カウントである可能性もあります。

### <a name="remarks"></a>解説

スレッドモデルがマルチスレッドの場合、を使用して、複数の `InterlockedDecrement` スレッドが同時に参照カウントを変更できないようにします。

## <a name="ccomobjectrootexlock"></a><a name="lock"></a> CComObjectRootEx:: Lock

スレッドモデルがマルチスレッドの場合、このメソッドは Win32 API 関数 [EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)を呼び出します。この関数は、スレッドがプライベートデータメンバーを通じて取得したクリティカルセクションオブジェクトの所有権を取得するまで待機します。

```cpp
void Lock();
```

### <a name="remarks"></a>解説

保護されたコードの実行が完了したら、スレッドはを呼び出して、 `Unlock` クリティカルセクションの所有権を解放する必要があります。

スレッドモデルがシングルスレッドの場合、このメソッドは何も行いません。

## <a name="ccomobjectrootexm_dwref"></a><a name="m_dwref"></a> CComObjectRootEx:: m_dwRef

4バイトのメモリにアクセスする共用体の一部。

```
long m_dwRef;
```

### <a name="remarks"></a>解説

では `m_pOuterUnknown` 、共用体の一部を使用します。

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

オブジェクトが集計されていない場合、およびによってアクセスされる参照カウント `AddRef` `Release` はに格納され `m_dwRef` ます。 オブジェクトが集計されている場合は、外側の不明へのポインターが [m_pOuterUnknown](#m_pouterunknown)に格納されます。

## <a name="ccomobjectrootexm_pouterunknown"></a><a name="m_pouterunknown"></a> CComObjectRootEx:: m_pOuterUnknown

4バイトのメモリにアクセスする共用体の一部。

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>解説

では `m_dwRef` 、共用体の一部を使用します。

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

オブジェクトが集計されている場合は、外側の不明へのポインターがに格納され `m_pOuterUnknown` ます。 オブジェクトが集計されていない場合、およびによってアクセスされる参照カウント `AddRef` `Release` は [m_dwRef](#m_dwref)に格納されます。

## <a name="ccomobjectrootexobjectmain"></a><a name="objectmain"></a> CComObjectRootEx:: ObjectMain

オブジェクトマップに示されている各クラスに対して、この関数は、モジュールが初期化されたときに1回、または終了したときに呼び出されます。

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>パラメーター

*bStarting*<br/>
入出力クラスが初期化されている場合、値は TRUE になります。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*Bstarting*パラメーターの値は、モジュールが初期化されているか、終了しているかを示します。 の既定の実装で `ObjectMain` は何も実行されませんが、クラスでこの関数をオーバーライドして、クラスに割り当てたいリソースを初期化またはクリーンアップできます。 `ObjectMain`クラスのインスタンスが要求される前に、が呼び出されることに注意してください。

`ObjectMain` は DLL のエントリポイントから呼び出されるため、エントリポイント関数が実行できる操作の種類は制限されます。 これらの制限の詳細については、「 [dll and Visual C++ ランタイムライブラリの動作](../../build/run-time-library-behavior.md) と [DllMain](/windows/win32/Dlls/dllmain)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]

## <a name="ccomobjectrootexouteraddref"></a><a name="outeraddref"></a> CComObjectRootEx:: OuterAddRef

集計の外側の不明の参照カウントをインクリメントします。

```
ULONG OuterAddRef();
```

### <a name="return-value"></a>戻り値

診断とテストに役立つ可能性のある値。

## <a name="ccomobjectrootexouterqueryinterface"></a><a name="outerqueryinterface"></a> CComObjectRootEx:: OuterQueryInterface

要求されたインターフェイスへの間接ポインターを取得します。

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
から要求されているインターフェイスの GUID。

*ppvObject*<br/>
入出力 *Iid*で指定されたインターフェイスポインターへのポインター。または、集計でインターフェイスがサポートされていない場合は NULL。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

## <a name="ccomobjectrootexouterrelease"></a><a name="outerrelease"></a> CComObjectRootEx:: OuterRelease

集計の外側の不明部分の参照カウントをデクリメントします。

```
ULONG OuterRelease();
```

### <a name="return-value"></a>戻り値

非デバッグビルドでは、は常に0を返します。 デバッグビルドでは、診断またはテストに役立つ値が返されます。

## <a name="ccomobjectrootexunlock"></a><a name="unlock"></a> CComObjectRootEx:: Unlock

スレッドモデルがマルチスレッドの場合、このメソッドは Win32 API 関数 [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)を呼び出します。これにより、プライベートデータメンバーを通じて取得されたクリティカルセクションオブジェクトの所有権が解放されます。

```cpp
void Unlock();
```

### <a name="remarks"></a>解説

所有権を取得するには、スレッドがを呼び出す必要があり `Lock` ます。 への各呼び出しでは、 `Lock` `Unlock` クリティカルセクションの所有権を解放するために、対応する呼び出しが必要です。

スレッドモデルがシングルスレッドの場合、このメソッドは何も行いません。

## <a name="see-also"></a>関連項目

[CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject クラス](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
