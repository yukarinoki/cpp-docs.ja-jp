---
title: クラス
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
ms.openlocfilehash: e8db86f6214f95cd9bb08d3b5f6c6c1a38ca475c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327603"
---
# <a name="ccomobjectrootex-class"></a>クラス

このクラスには、非集約オブジェクトと集約オブジェクトの両方のオブジェクト参照カウント管理を処理するメソッドが用意されています。

## <a name="syntax"></a>構文

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>パラメーター

*スレッドモデル*<br/>
メソッドが目的のスレッド モデルを実装するクラス。 *スレッドモデル*を[CCom シングルスレッドモデル、CCom マルチスレッドモデル 、または](../../atl/reference/ccomsinglethreadmodel-class.md) [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)に設定することで、スレッドモデルを明示的に選択できます。 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) サーバーの既定のスレッド モデルを受け入れるには、*スレッド モデル*を CCom オブジェクト スレッド モデルまたは[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)に設定します。 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[ココムオブジェクトルート](#ccomobjectrootex)|コンストラクターです。|
|[内部AddRef](#internaladdref)|非集約オブジェクトの参照カウントをインクリメントします。|
|[内部リリース](#internalrelease)|非集約オブジェクトの参照カウントを減算します。|
|[[Lock] (ロック)](#lock)|スレッド モデルがマルチスレッドの場合、クリティカル セクション オブジェクトの所有権を取得します。|
|[ロック 解除](#unlock)|スレッド モデルがマルチスレッドの場合、クリティカル セクション オブジェクトの所有権を解放します。|

### <a name="ccomobjectrootbase-methods"></a>メソッド

|||
|-|-|
|[ファイナルコンストラクト](#finalconstruct)|オブジェクトに必要な初期化を実行するには、クラスでオーバーライドします。|
|[ファイナルリリース](#finalrelease)|オブジェクトに必要なクリーンアップを実行するには、クラスでオーバーライドします。|
|[アウターアドレフ](#outeraddref)|集約されたオブジェクトの参照カウントをインクリメントします。|
|[インターフェイス](#outerqueryinterface)|集約オブジェクトの外側`IUnknown`にデリゲートします。|
|[アウターリリース](#outerrelease)|集約オブジェクトの参照カウントを減算します。|

### <a name="static-functions"></a>静的関数

|||
|-|-|
|[内部クエリ インターフェイス](#internalqueryinterface)|非集約オブジェクト`IUnknown`の にデリゲートします。|
|[オブジェクトメイン](#objectmain)|オブジェクト マップにリストされている派生クラスのモジュールの初期化および終了中に呼び出されます。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_dwRef](#m_dwref)|と`m_pOuterUnknown`、ユニオンの一部。 の参照カウント`AddRef`を保持するためにオブジェクトが集約されていない場合に使用`Release`します。|
|[m_pOuterUnknown](#m_pouterunknown)|と`m_dwRef`、ユニオンの一部。 オブジェクトが集計されるときに、外部不明へのポインターを保持するときに使用されます。|

## <a name="remarks"></a>解説

`CComObjectRootEx`非集約オブジェクトと集約オブジェクトの両方のオブジェクト参照カウント管理を処理します。 オブジェクトが集約されていない場合はオブジェクト参照カウントを保持し、オブジェクトが集約されている場合は外部不明へのポインタを保持します。 集約オブジェクトの場合、`CComObjectRootEx`メソッドを使用して内部オブジェクトの構築の失敗を処理し、内部インターフェイスが解放されたり内部オブジェクトが削除されたりしたときに外部オブジェクトが削除されないように保護できます。

COM サーバーを実装するクラスは、または`CComObjectRootEx`[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)から継承する必要があります。

クラス定義で[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)マクロを指定すると、ATL は`CComPolyObject<CYourClass>`when`IClassFactory::CreateInstance`が呼び出されるインスタンスを作成します。 作成中に、外部不明の値がチェックされます。 NULL の場合`IUnknown`、非集約オブジェクトに対して実装されます。 外側の不明な値が NULL`IUnknown`でない場合は、集約オブジェクトに対して実装されます。

クラスでDECLARE_POLY_AGGREGATABLE マクロを指定しない場合、ATL は集約オブジェクト`CAggComObject<CYourClass>`のインスタンスまたは非集約オブジェクトの`CComObject<CYourClass>`インスタンスを作成します。

使用`CComPolyObject`の利点は、集約されたケースと非`CComAggObject`集約`CComObject`型のケースを処理するために、モジュールの両方を使用しないようにすることです。 1`CComPolyObject`つのオブジェクトが両方のケースを処理します。 したがって、モジュールには、vtable のコピーと関数のコピーが 1 つだけ存在します。 vtable が大きい場合、モジュールのサイズが大幅に減少する可能性があります。 ただし、vtable が小さい場合は`CComPolyObject`、モジュールサイズが少し大きくなる可能性があります`CComAggObject``CComObject`。

オブジェクトが集約されている場合[、IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)は または`CComAggObject``CComPolyObject`によって実装されます。 これらのクラスは`QueryInterface`、 `AddRef`、`Release`を`CComObjectRootEx`デリゲートし`OuterQueryInterface`、's、 、 を`OuterAddRef`呼び出して`OuterRelease`、外側の不明なクラスに転送します。 通常、クラスで`CComObjectRootEx::FinalConstruct`オーバーライドして集約オブジェクトを作成し、すべての集約オブジェクトを`CComObjectRootEx::FinalRelease`解放するようにオーバーライドします。

オブジェクトが集約されていない場合は、`IUnknown`または`CComObject``CComPolyObject`によって実装されます。 この場合、 `QueryInterface`、 `AddRef`、`Release`を呼び出して`CComObjectRootEx`、 `InternalQueryInterface``InternalAddRef`に委任`InternalRelease`し、実際の操作を実行します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomobjectrootexccomobjectrootex"></a><a name="ccomobjectrootex"></a>::CComオブジェクトルート

コンストラクターは、参照カウントを 0 に初期化します。

```
CComObjectRootEx();
```

## <a name="ccomobjectrootexfinalconstruct"></a><a name="finalconstruct"></a>CComオブジェクトルートエクステックス::ファイナルコンストラクト

派生クラスでこのメソッドをオーバーライドして、オブジェクトに必要な初期化を実行できます。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、標準エラー HRESULT 値の 1 つを返します。

### <a name="remarks"></a>解説

デフォルトでは、`CComObjectRootEx::FinalConstruct`単にS_OKを返します。

クラスのコンストラクタではなく、初期化`FinalConstruct`を実行する利点があります。

- コンストラクターから状態コードを返すことはできませんが、戻り値を使用して HRESULT`FinalConstruct`を返すことができます。 ATL が提供する標準クラス ファクトリを使用してクラスのオブジェクトを作成する場合、この戻り値は COM クライアントに反映され、詳細なエラー情報を提供できます。

- クラスのコンストラクターから仮想関数の機構を通じて仮想関数を呼び出すことはできません。 クラスのコンストラクターから仮想関数を呼び出すと、継承階層のその時点で定義されている関数の呼び出しが静的に解決されます。 純粋仮想関数を呼び出すと、リンカー エラーが発生します。

   クラスは継承階層の中で最も派生したクラスではなく、ATL によって提供される派生クラスに依存して、その機能の一部を提供します。 初期化では、そのクラスで提供される機能を使用する必要がある可能性が高いですが (クラスのオブジェクトが他のオブジェクトを集約する必要がある場合は、これは確かに当てはまります)、クラスのコンストラクタはそれらの機能にアクセスする方法がありません。 クラスの構築コードは、最派生クラスが完全に構築される前に実行されます。

   ただし、`FinalConstruct`最も派生したクラスが完全に構築された直後に呼び出され、仮想関数を呼び出して ATL によって提供される参照カウントの実装を使用できます。

### <a name="example"></a>例

通常、派生したクラスでこのメソッド`CComObjectRootEx`をオーバーライドして、集約オブジェクトを作成します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

構築に失敗した場合は、エラーを返すことができます。 また、マクロ[DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct)を使用して、内部集計オブジェクトが参照カウントをインクリメントし、カウントを 0 に減らす場合に、外部オブジェクトが削除されないようにすることもできます。

集計を作成する一般的な方法を次に示します。

- クラス`IUnknown`オブジェクトへのポインターを追加し、コンストラクターで NULL に初期化します。

- 集計`FinalConstruct`を作成するためにオーバーライドします。

- COM_INTERFACE_ENTRY_AGGREGATE`IUnknown`マクロのパラメーターとして定義したポインターを[COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate)使用します。

- ポインター`FinalRelease`を解放する`IUnknown`場合はオーバーライドします。

## <a name="ccomobjectrootexfinalrelease"></a><a name="finalrelease"></a>CComオブジェクトルート::最終リリース

派生クラスでこのメソッドをオーバーライドして、オブジェクトに必要なクリーンアップを実行できます。

```
void FinalRelease();
```

### <a name="remarks"></a>解説

デフォルトでは、`CComObjectRootEx::FinalRelease`何もしません。

クリーンアップを`FinalRelease`実行する場合は、クラスのデストラクターにコードを追加する方が`FinalRelease`望ましいです。 これにより、最も派生したクラスによって提供されるメソッドに安全にアクセスできます。 これは、削除前に集約オブジェクトを解放する場合に特に重要です。

## <a name="ccomobjectrootexinternaladdref"></a><a name="internaladdref"></a>を使用します。

非集約オブジェクトの参照カウントを 1 ずつインクリメントします。

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>戻り値

診断とテストに役立つ値。

### <a name="remarks"></a>解説

スレッド モデルがマルチスレッドの場合は`InterlockedIncrement`、複数のスレッドが同時に参照カウントを変更することを防ぐために使用されます。

## <a name="ccomobjectrootexinternalqueryinterface"></a><a name="internalqueryinterface"></a>次のクラス::内部クエリインターフェイス

要求されたインターフェイスへのポインターを取得します。

```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*pこれ*<br/>
[in]に公開されているインターフェイスの COM マップを格納しているオブジェクトへのポインター `QueryInterface`。

*エントリー*<br/>
[in]使用可能なインターフェイスの`_ATL_INTMAP_ENTRY`マップにアクセスする構造体へのポインター。

*Iid*<br/>
[in]要求されているインターフェイスの GUID。

*オブジェクト*<br/>
[アウト]*iid*で指定されたインターフェイス ポインターへのポインター、 またはインターフェイスが見つからない場合は NULL。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

`InternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。 オブジェクトが集約されている場合、`InternalQueryInterface`外部不明にデリゲートしません。 COM マップ テーブルにインターフェイスを入力するには、マクロ[COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)またはそのバリアントを使用します。

## <a name="ccomobjectrootexinternalrelease"></a><a name="internalrelease"></a>CComオブジェクトルートエクスックス::内部リリース

非集約オブジェクトの参照カウントを 1 で減算します。

```
ULONG InternalRelease();
```

### <a name="return-value"></a>戻り値

デバッグビルドとデバッグ ビルド以外のビルドの両方で、この関数は診断やテストに役立つ値を返します。 返される正確な値は、使用されるオペレーティング システムなどの多くの要因によって異なり、参照カウントである場合としない場合もあります。

### <a name="remarks"></a>解説

スレッド モデルがマルチスレッドの場合は`InterlockedDecrement`、複数のスレッドが同時に参照カウントを変更することを防ぐために使用されます。

## <a name="ccomobjectrootexlock"></a><a name="lock"></a>CComオブジェクトルート::ロック

スレッド モデルがマルチスレッドの場合、このメソッドは Win32 API 関数[EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)を呼び出し、スレッドがプライベート データ メンバーを通じて取得したクリティカル セクション オブジェクトの所有権を取得できるまで待機します。

```
void Lock();
```

### <a name="remarks"></a>解説

保護されたコードの実行が終了したら、クリティカル セクションの`Unlock`所有権を解放するためにスレッドが呼び出す必要があります。

スレッド モデルがシングル スレッドの場合、このメソッドは何も実行しません。

## <a name="ccomobjectrootexm_dwref"></a><a name="m_dwref"></a>ココムオブジェクトルートエクスックス::m_dwRef

4 バイトのメモリにアクセスする共用体の一部。

```
long m_dwRef;
```

### <a name="remarks"></a>解説

では`m_pOuterUnknown`、ユニオンの一部:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

オブジェクトが集約されていない場合、参照カウントは によって`AddRef`アクセスされ、`Release`に`m_dwRef`格納されます。 オブジェクトが集約されている場合、外部不明へのポインターは[m_pOuterUnknown](#m_pouterunknown)に格納されます。

## <a name="ccomobjectrootexm_pouterunknown"></a><a name="m_pouterunknown"></a>ココムオブジェクトルートエクスックス::m_pOuterUnknown

4 バイトのメモリにアクセスする共用体の一部。

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>解説

では`m_dwRef`、ユニオンの一部:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

オブジェクトが集約されている場合、外側の不明なオブジェクトへのポインターは`m_pOuterUnknown`に格納されます。 オブジェクトが集約されていない場合、参照カウントは アクセス`AddRef`され、 `Release` [m_dwRef](#m_dwref)に格納されます。

## <a name="ccomobjectrootexobjectmain"></a><a name="objectmain"></a>オブジェクトメイン

オブジェクト マップにリストされている各クラスに対して、この関数は、モジュールが初期化されるときに 1 回呼び出され、終了したときに再度呼び出されます。

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>パラメーター

*b開始*<br/>
[アウト]クラスが初期化されている場合は、値は TRUE です。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*bStarting*パラメーターの値は、モジュールが初期化されているか終了されるかを示します。 の既定の`ObjectMain`実装では何も実行されませんが、クラスでこの関数をオーバーライドして、クラスに割り当てるリソースを初期化またはクリーンアップできます。 クラスの`ObjectMain`インスタンスが要求される前に呼び出されることに注意してください。

`ObjectMain`は DLL のエントリ ポイントから呼び出されるため、エントリ ポイント関数が実行できる操作の種類は制限されます。 これらの制限の詳細については、「 DLL[と Visual C++ ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)」および「 [DllMain](/windows/win32/Dlls/dllmain)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]

## <a name="ccomobjectrootexouteraddref"></a><a name="outeraddref"></a>オブジェクトルート::アウターアドレフ

集計の外部不明の参照カウントをインクリメントします。

```
ULONG OuterAddRef();
```

### <a name="return-value"></a>戻り値

診断とテストに役立つ値。

## <a name="ccomobjectrootexouterqueryinterface"></a><a name="outerqueryinterface"></a>インターフェイス::インターフェイス

要求されたインターフェイスへの間接ポインターを取得します。

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]要求されているインターフェイスの GUID。

*オブジェクト*<br/>
[アウト]*iid*で指定されたインターフェイス ポインターへのポインターまたは NULL 、または集約がインターフェイスをサポートしていない場合。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomobjectrootexouterrelease"></a><a name="outerrelease"></a>CComオブジェクトルート::アウターリリース

集計の外部不明の参照カウントをデクリメントします。

```
ULONG OuterRelease();
```

### <a name="return-value"></a>戻り値

非デバッグ ビルドでは、常に 0 を返します。 デバッグ ビルドでは、診断やテストに役立つ値を返します。

## <a name="ccomobjectrootexunlock"></a><a name="unlock"></a>CComオブジェクトルートEx::ロック解除

スレッド モデルがマルチスレッドの場合、このメソッドは Win32 API 関数[LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)を呼び出し、プライベート データ メンバーを通じて取得したクリティカル セクション オブジェクトの所有権を解放します。

```
void Unlock();
```

### <a name="remarks"></a>解説

所有権を取得するには、スレッドが`Lock`を呼び出す必要があります。 各呼び`Lock`出しは、クリティカル`Unlock`セクションの所有権を解放するために、対応する呼び出しが必要です。

スレッド モデルがシングル スレッドの場合、このメソッドは何も実行しません。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[クラス](../../atl/reference/ccomobject-class.md)<br/>
[クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
