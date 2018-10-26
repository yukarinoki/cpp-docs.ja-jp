---
title: CComObjectRootEx クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 413485bc7675fbc68f2c224ceefdd0f552538eb9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076985"
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx クラス

このクラスは、非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理するメソッドを提供します。

## <a name="syntax"></a>構文

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>パラメーター

*表*<br/>
目的のスレッド処理モデルのメソッドとして実装するクラスです。 スレッド処理モデルを設定して明示的に選択できます*表*に[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)、 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)、または[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)します。 設定して、サーバーの既定のスレッド モデルをそのまま使用できる*表*に[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)または[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)します。

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CComObjectRootEx](#ccomobjectrootex)|コンストラクターです。|
|[InternalAddRef](#internaladdref)|非集計オブジェクトの参照カウントをインクリメントします。|
|[InternalRelease](#internalrelease)|非集計オブジェクトの参照カウントをデクリメントします。|
|[ロック](#lock)|スレッド モデルがマルチ スレッドの場合は、クリティカル セクション オブジェクトの所有権を取得します。|
|[ロックを解除します。](#unlock)|スレッド モデルがマルチ スレッドの場合は、クリティカル セクション オブジェクトの所有権を解放します。|

### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase メソッド

|||
|-|-|
|[Finalconstruct 関数](#finalconstruct)|オブジェクトに必要な初期化を実行するクラスでオーバーライドします。|
|[FinalRelease](#finalrelease)|オブジェクトに必要なクリーンアップを実行するクラスでオーバーライドします。|
|[OuterAddRef](#outeraddref)|集約オブジェクトの参照カウントをインクリメントします。|
|[OuterQueryInterface](#outerqueryinterface)|デリゲートを外部`IUnknown`の集約オブジェクト。|
|[OuterRelease](#outerrelease)|集約オブジェクトの参照カウントをデクリメントします。|

### <a name="static-functions"></a>静的関数

|||
|-|-|
|[InternalQueryInterface](#internalqueryinterface)|デリゲート、`IUnknown`の非集約オブジェクト。|
|[ObjectMain](#objectmain)|モジュールの初期化とオブジェクトのマップに記載されている派生クラスの終了時に呼び出されます。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_dwRef](#m_dwref)|`m_pOuterUnknown`共用体の一部であります。 オブジェクトがの参照カウントを保持するために集計されないときに使用`AddRef`と`Release`します。|
|[アグリゲート](#m_pouterunknown)|`m_dwRef`共用体の一部であります。 オブジェクトは外側の"不明"にポインターを保持するために集計するときに使用します。|

## <a name="remarks"></a>Remarks

`CComObjectRootEx` 非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理します。 オブジェクトが集計されていませんし、オブジェクトが集約されている場合、不明な外部へのポインターを保持する場合は、オブジェクトの参照カウントを保持します。 集計のオブジェクトの`CComObjectRootEx`を構築する内部オブジェクトのエラーを処理するメソッドを使用でき、内部のインターフェイスがリリースされたときに削除されないように、外側のオブジェクトまたは内部のオブジェクトを保護するために削除されます。

COM サーバーを実装するクラスを継承する必要があります`CComObjectRootEx`または[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)します。

クラスの定義が指定されている場合、 [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)マクロ、ATL のインスタンスを作成します。`CComPolyObject<CYourClass>`とき`IClassFactory::CreateInstance`が呼び出されます。 作成時に、不明な外部の値がチェックされます。 NULL の場合`IUnknown`の非集計オブジェクトに実装されます。 不明な外部が NULL でない場合`IUnknown`集約オブジェクトに実装されます。

ATL がのインスタンスを作成する場合は、クラスが DECLARE_POLY_AGGREGATABLE マクロを指定しない`CAggComObject<CYourClass>`集約オブジェクトまたはのインスタンスの`CComObject<CYourClass>`の非集約オブジェクト。

使用する利点`CComPolyObject`は両方を持つように`CComAggObject`と`CComObject`集計データおよび非集計のケースを処理するモジュールでします。 1 つ`CComPolyObject`オブジェクトは両方のケースを処理します。 そのため、vtable の 1 つだけのコピーと関数の 1 つのコピーは、モジュール内に存在します。 Vtable が大きい場合、モジュールのサイズが大幅に減りこのことができます。 ただし、vtable が小さい場合を使用して`CComPolyObject`には、集計または非集約オブジェクトは、最適化されていないために、モジュールのサイズを少し大きめにつながるは`CComAggObject`と`CComObject`します。

オブジェクトを集約すると場合、 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)によって実装される`CComAggObject`または`CComPolyObject`します。 これらのクラスに委任`QueryInterface`、 `AddRef`、および`Release`呼び出し`CComObjectRootEx`の`OuterQueryInterface`、 `OuterAddRef`、および`OuterRelease`不明な外部に転送します。 通常、オーバーライドする`CComObjectRootEx::FinalConstruct`な集約オブジェクトを作成し、オーバーライドするクラスで`CComObjectRootEx::FinalRelease`メモリを解放するオブジェクトを集計します。

場合は、オブジェクトは集計されず`IUnknown`によって実装される`CComObject`または`CComPolyObject`します。 この場合、呼び出し`QueryInterface`、 `AddRef`、および`Release`に委任されます`CComObjectRootEx`の`InternalQueryInterface`、 `InternalAddRef`、および`InternalRelease`実際の操作を実行します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="ccomobjectrootex"></a>  CComObjectRootEx::CComObjectRootEx

コンス トラクターでは、参照カウントを 0 に初期化します。

```
CComObjectRootEx();
```

##  <a name="finalconstruct"></a>  CComObjectRootEx::FinalConstruct

このメソッドは、オブジェクトの必要な初期化を実行する派生クラスでオーバーライドできます。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

HRESULT 値、成功時または標準エラーのいずれかに S_OK を返します。

### <a name="remarks"></a>Remarks

既定では、`CComObjectRootEx::FinalConstruct`単に S_OK を返します。

初期化を実行するための利点がある`FinalConstruct`クラスのコンス トラクターではなく。

- 状態コードは、コンス トラクターから返すことはできませんの HRESULT を返すことができます、`FinalConstruct`の値を返します。 ATL によって提供される標準のクラス ファクトリを使用して、クラスのオブジェクトの作成中と、は、詳細なエラー情報を提供することができます、COM クライアントにこの戻り値が反映されます。

- クラスのコンス トラクターから仮想関数のメカニズムを通じて仮想関数を呼び出すことはできません。 継承階層内の時点で定義されている、静的に解決される、関数呼び出しで結果をクラスのコンス トラクターから仮想関数を呼び出します。 純粋仮想関数への呼び出しは、リンカー エラーが発生します。

   継承階層で最派生クラスではなく、その機能の一部を提供する ATL によって提供される派生クラスに依存します。 初期化は、(これは確かに、クラスのオブジェクトが他のオブジェクトを集計する必要がある場合) そのクラスによって提供される機能を使用する必要がある可能性があるが、クラスにコンス トラクターには、これらの機能にアクセスする方法はありません。 クラスの構築用のコードは、最派生クラスが完全に構築される前に実行されます。

   ただし、`FinalConstruct`仮想関数を呼び出すし、ATL で提供される、参照カウントの実装を使用することができますクラスが完全に生成される、最も多く派生後すぐには呼び出されます

### <a name="example"></a>例

通常から派生したクラスでは、このメソッドをオーバーライド`CComObjectRootEx`オブジェクトの集計を作成します。 例えば:

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

構築に失敗した場合は、エラーを取得できます。 マクロを使用することもできます。[アグリゲート](aggregation-and-class-factory-macros.md#declare_protect_final_construct)されない、外側のオブジェクトを保護する場合、作成時に、内部オブジェクト カウントをインクリメント、デクリメントして参照カウントを 0 には削除します。

集計を作成する一般的な方法を次に示します。

- 追加、`IUnknown`クラスへのポインター オブジェクトをコンス トラクターで NULL に初期化します。

- オーバーライド`FinalConstruct`集計を作成します。

- 使用して、`IUnknown`ポインターをパラメーターとして定義されている、[で定義](com-interface-entry-macros.md#com_interface_entry_aggregate)マクロ。

- オーバーライド`FinalRelease`を解放する、`IUnknown`ポインター。

##  <a name="finalrelease"></a>  CComObjectRootEx::FinalRelease

このメソッドは、オブジェクトの必要なクリーンアップを実行する派生クラスでオーバーライドできます。

```
void FinalRelease();
```

### <a name="remarks"></a>Remarks

既定では、`CComObjectRootEx::FinalRelease`何も行われません。

クリーンアップを実行する`FinalRelease`は、オブジェクトの位置を表すポイントで引き続き完全構築のため、クラスのデストラクターにコードを追加することをお勧め`FinalRelease`が呼び出されます。 これにより、最派生クラスによって提供されるメソッドを安全にアクセスできます。 これは、削除する前にすべての集計オブジェクトの解放にとって特に重要です。

##  <a name="internaladdref"></a>  CComObjectRootEx::InternalAddRef

非集計オブジェクトの参照カウントを 1 だけインクリメントします。

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>戻り値

診断に役立ちますし、テスト可能性のある値。

### <a name="remarks"></a>Remarks

スレッド モデルがマルチ スレッドの場合は`InterlockedIncrement`を 1 つ以上のスレッドが同時に、参照カウントを変更することを防ぐために使用します。

##  <a name="internalqueryinterface"></a>  CComObjectRootEx::InternalQueryInterface

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
[in]COM に公開されるインターフェイスのマップを格納しているオブジェクトへのポインター`QueryInterface`します。

*pEntries*<br/>
[in]ポインター、`_ATL_INTMAP_ENTRY`使用可能なインターフェイスのマップにアクセスする構造体。

*iid*<br/>
[in]要求されているインターフェイスの GUID です。

*ppvObject*<br/>
[out]指定されたインターフェイス ポインターへのポインター *iid*インターフェイスが見つからない場合は null です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>Remarks

`InternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。 オブジェクトを集約すると場合、`InternalQueryInterface`不明な外部への委任しません。 インターフェイスは、マクロ、COM マップ テーブルを入力できます[COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)またはそのバリエーションの 1 つ。

##  <a name="internalrelease"></a>  CComObjectRootEx::InternalRelease

非集計オブジェクトの参照カウントを 1 だけデクリメントします。

```
ULONG InternalRelease();
```

### <a name="return-value"></a>戻り値

どちらも非デバッグし、デバッグ ビルド、テストや診断に使用できる値を返します。 参照カウントになるで使用して、オペレーティング システムなどのさまざまな要因に依存する場合や、ことはできません、正確な値が返されます。

### <a name="remarks"></a>Remarks

スレッド モデルがマルチ スレッドの場合は`InterlockedDecrement`を 1 つ以上のスレッドが同時に、参照カウントを変更することを防ぐために使用します。

##  <a name="lock"></a>  CComObjectRootEx::Lock

このメソッドが、Win32 API 関数を呼び出すスレッド モデルがマルチ スレッドの場合は、 [EnterCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-entercriticalsection)、どの待機スレッドがクリティカル セクション オブジェクトの所有権を取得できるまでは、プライベート データ メンバーを通じて取得します。

```
void Lock();
```

### <a name="remarks"></a>Remarks

保護されたコードでは、実行が完了すると、スレッドを呼び出す必要があります`Unlock`クリティカル セクションの所有権を解放します。

スレッド モデルがシングル スレッドの場合、このメソッドは何もしません。

##  <a name="m_dwref"></a>  CComObjectRootEx::m_dwRef

4 バイトのメモリにアクセスする共用体の一部です。

```
long m_dwRef;
```

### <a name="remarks"></a>Remarks

`m_pOuterUnknown`共用体の一部であります。

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

オブジェクトは集計されず、参照カウントがによってアクセス`AddRef`と`Release`は`m_dwRef`します。 不明な外部へのポインターが格納されている場合は、オブジェクトを集計すると、[アグリゲート](#m_pouterunknown)します。

##  <a name="m_pouterunknown"></a>  CComObjectRootEx::m_pOuterUnknown

4 バイトのメモリにアクセスする共用体の一部です。

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>Remarks

`m_dwRef`共用体の一部であります。

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

不明な外部へのポインターが格納されている場合は、オブジェクトを集計すると、`m_pOuterUnknown`します。 オブジェクトは集計されず、参照カウントがによってアクセス`AddRef`と`Release`は[m_dwRef](#m_dwref)します。

##  <a name="objectmain"></a>  CComObjectRootEx::ObjectMain

モジュールが初期化される場合、1 回、オブジェクトのマップに表示されている各クラスのこの関数が呼び出され、もう一度が終了したとき。

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>パラメーター

*bStarting*<br/>
[out]値が TRUE の場合は、クラス初期化しています。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

値、 *bStarting*パラメーターは、モジュールがされているかどうかを示します初期化または終了します。 既定の実装`ObjectMain`、何も行われませんが、初期化またはクラスに割り当てるリソースをクリーンアップするには、クラスでこの関数をオーバーライドすることができます。 なお`ObjectMain`クラスのすべてのインスタンスが要求される前に呼び出されます。

`ObjectMain` エントリ ポイント関数が実行できる操作の種類が制限されているために、DLL のエントリ ポイントから呼び出されます。 これらの制限の詳細については、次を参照してください。 [Dll と Visual c ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)と[DllMain](/windows/desktop/Dlls/dllmain)します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]

##  <a name="outeraddref"></a>  CComObjectRootEx::OuterAddRef

集計の不明な外部の参照カウントをインクリメントします。

```
ULONG OuterAddRef();
```

### <a name="return-value"></a>戻り値

診断に役立ちますし、テスト可能性のある値。

##  <a name="outerqueryinterface"></a>  CComObjectRootEx::OuterQueryInterface

要求されたインターフェイスへの間接ポインターを取得します。

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
[in]要求されているインターフェイスの GUID です。

*ppvObject*<br/>
[out]指定されたインターフェイス ポインターへのポインター *iid*集計は、インターフェイスをサポートしていない場合は null です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

##  <a name="outerrelease"></a>  CComObjectRootEx::OuterRelease

集計の不明な外部の参照カウントをデクリメントします。

```
ULONG OuterRelease();
```

### <a name="return-value"></a>戻り値

非デバッグ ビルドで常に 0 を返します。 デバッグ ビルドでは、テストや診断に使用する値を返します。

##  <a name="unlock"></a>  CComObjectRootEx::Unlock

このメソッドが、Win32 API 関数を呼び出すスレッド モデルがマルチ スレッドの場合は、[により](/windows/desktop/api/synchapi/nf-synchapi-leavecriticalsection)、クリティカル セクション オブジェクトの所有権を解放するが、プライベート データ メンバーを介して取得します。

```
void Unlock();
```

### <a name="remarks"></a>Remarks

所有権を取得するスレッドを呼び出す必要があります`Lock`します。 呼び出しごとに`Lock`に対応する呼び出しを必要と`Unlock`クリティカル セクションの所有権を解放します。

スレッド モデルがシングル スレッドの場合、このメソッドは何もしません。

## <a name="see-also"></a>関連項目

[CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject クラス](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
