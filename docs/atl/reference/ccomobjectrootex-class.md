---
title: CComObjectRootEx クラス |Microsoft ドキュメント
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
ms.openlocfilehash: b147f0ad3f1a54c2ae640b6bf2426bcddf060b35
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365982"
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx クラス
このクラスは、非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理するメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `ThreadModel`  
 目的のスレッド処理モデルのメソッドとして実装するクラスです。 明示的に設定して、スレッディング モデルを選択できます`ThreadModel`に[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)、 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)、または[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)です。 設定して、サーバーの既定のスレッド モデルを受け入れることができます`ThreadModel`に[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)または[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)です。  

  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|コンストラクターです。|  
|[InternalAddRef](#internaladdref)|非集約オブジェクトの参照カウントをインクリメントします。|  
|[InternalRelease](#internalrelease)|非集約オブジェクトの参照カウントをデクリメントします。|  
|[ロック](#lock)|スレッド モデルがマルチ スレッドの場合は、クリティカル セクション オブジェクトの所有権を取得します。|  
|[ロックを解除します。](#unlock)|スレッド モデルがマルチ スレッドの場合は、クリティカル セクション オブジェクトの所有権を解放します。|  
  
### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase メソッド  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|オブジェクトに必要な初期化を実行するクラスでオーバーライドします。|  
|[FinalRelease](#finalrelease)|オブジェクトに必要なクリーンアップを実行するクラスでオーバーライドします。|  
|[OuterAddRef](#outeraddref)|集約オブジェクトの参照カウントをインクリメントします。|  
|[OuterQueryInterface](#outerqueryinterface)|デリゲートを外部**IUnknown**集約オブジェクトの。|  
|[OuterRelease](#outerrelease)|集約オブジェクトの参照カウントをデクリメントします。|  
  
### <a name="static-functions"></a>静的関数  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|デリゲート、 **IUnknown**の非集約オブジェクト。|  
|[ObjectMain](#objectmain)|モジュールの初期化と派生クラスのオブジェクト マップの一覧の終了時に呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|`m_pOuterUnknown`共用体の一部です。 オブジェクトがの参照カウントを保持するために集計されないときに使用`AddRef`と**リリース**です。|  
|[アグリゲート](#m_pouterunknown)|`m_dwRef`共用体の一部です。 外部の"不明"にポインターを保持するために集約オブジェクトの場合に使用されます。|  
  
## <a name="remarks"></a>コメント  
 `CComObjectRootEx` 非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理します。 オブジェクトの参照カウントを保持している場合は、オブジェクトがない集計されているし、オブジェクトが集計されている場合、外側の不明なへのポインターを保持します。 集約オブジェクトは、の`CComObjectRootEx`を作成する内部オブジェクトのエラーを処理するメソッドを使用でき、内部のインターフェイスがリリースされたときに削除されないように、外部オブジェクトまたは内部オブジェクトを保護するのには削除します。  
  
 COM サーバーを実装するクラスを継承する必要があります`CComObjectRootEx`または[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)です。  
  
 クラスの定義を指定する場合、 [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)マクロのインスタンスを作成する ATL **CComPolyObject\<CYourClass >** とき**IClassFactory:。CreateInstance**と呼びます。 作成中に、外側の不明な値がチェックされます。 場合は**NULL**、 **IUnknown**非集約オブジェクトには実装されています。 外側の unknown がない場合**NULL**、 **IUnknown**集約オブジェクトには実装されています。  
  
 クラスが指定されていない場合、`DECLARE_POLY_AGGREGATABLE`マクロのインスタンスを作成する ATL **CAggComObject\<CYourClass >** 集約オブジェクトまたはのインスタンスの**CComObject\<CYourClass>** の非集約オブジェクト。  
  
 使用する利点`CComPolyObject`両方を避けることが`CComAggObject`と`CComObject`モジュールに、集計と非集計のケースに対処します。 1 つ`CComPolyObject`オブジェクトは両方のケースを処理します。 そのため、vtable の 1 つだけのコピーと関数の 1 つのコピーは、モジュール内に存在します。 Vtable が大きい場合は、モジュールのサイズを大幅に縮小このできます。 ただし、vtable が小さい場合を使用して`CComPolyObject`には、集計または非集約オブジェクトは、最適化されていないために、わずかに大きくモジュールのサイズになりますが`CComAggObject`と`CComObject`です。  
  
 オブジェクトを集約すると場合、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)によって実装される`CComAggObject`または`CComPolyObject`です。 これらのクラスに委任`QueryInterface`、 `AddRef`、および**リリース**への呼び出し`CComObjectRootEx`の`OuterQueryInterface`、 `OuterAddRef`、および`OuterRelease`を外部の"不明"に転送します。 通常、オーバーライドする`CComObjectRootEx::FinalConstruct`集計された、あらゆるオブジェクトを作成し、オーバーライドするクラスで`CComObjectRootEx::FinalRelease`を解放するには、オブジェクトを集計します。  
  
 場合は、オブジェクトは集計されません**IUnknown**によって実装される`CComObject`または`CComPolyObject`です。 この場合、呼び出し`QueryInterface`、 `AddRef`、および**リリース**に委任されます`CComObjectRootEx`の`InternalQueryInterface`、 `InternalAddRef`、および`InternalRelease`実際の操作を実行します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="ccomobjectrootex"></a>  CComObjectRootEx::CComObjectRootEx  
 コンス トラクターでは、参照カウントを 0 に初期化します。  
  
```
CComObjectRootEx();
```  
  
##  <a name="finalconstruct"></a>  CComObjectRootEx::FinalConstruct  
 作成したオブジェクトに必要な初期化を実行する派生クラスでは、このメソッドをオーバーライドすることができます。  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>戻り値  
 返す`S_OK`成功時または標準エラーのいずれかに`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 既定では、`CComObjectRootEx::FinalConstruct`を単純に返します`S_OK`です。  
  
 初期化を実行する利点があります`FinalConstruct`クラスのコンス トラクターではなく。  
  
-   コンス トラクターからステータス コードを返すことはできませんが、返すことができます、`HRESULT`により`FinalConstruct`の値を返します。 ATL によって提供される標準のクラス ファクトリを使用して、クラスのオブジェクトの作成中、この戻り値は、詳細なエラー情報を提供することができます、COM クライアントに反映されます。  
  
-   クラスのコンス トラクターから仮想関数のメカニズムを通じて仮想関数を呼び出すことはできません。 継承階層内の時点で定義されている、静的に解決される関数の呼び出し、結果、クラスのコンス トラクターから仮想関数を呼び出します。 純粋仮想関数への呼び出しは、リンカー エラーが発生します。  
  
     クラスは継承階層の最派生クラスではありません: 機能の一部を提供する ATL で指定された派生クラスに依存します。 初期化されます (これは特に、クラスのオブジェクトが他のオブジェクトを集計する必要がある場合) そのクラスによって提供される機能を使用する必要がある可能性が高く、クラスのコンス トラクターにはこれらの機能にアクセスする方法がありません。 クラスの構築用のコードは、最派生クラスが完全に構築される前に実行されます。  
  
     ただし、`FinalConstruct`は後が最も派生クラスが完全に構築された仮想関数を呼び出すし、ATL で提供される参照カウントの実装を使用することができますの直前に呼び出されます  
  
### <a name="example"></a>例  
 通常から派生したクラスでは、このメソッドをオーバーライド`CComObjectRootEx`を作成するには、オブジェクトを集計します。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 構築に失敗した場合は、エラーを返すことができます。 マクロを使用することもできます。[アグリゲート](aggregation-and-class-factory-macros.md#declare_protect_final_construct)されてから、外部のオブジェクトを保護する場合、作成中に、内部の集計オブジェクト カウントをインクリメント デクリメントして参照カウントを 0 には削除します。  
  
 集計を作成する一般的な方法を次に示します。  
  
-   追加、 **IUnknown**クラスへのポインターをそのオブジェクトを初期化**NULL**コンス トラクターでします。  
  
-   オーバーライド`FinalConstruct`集計を作成します。  
  
-   使用して、 **IUnknown**ポインターへのパラメーターとして定義されている、[で定義](com-interface-entry-macros.md#com_interface_entry_aggregate)マクロです。  
  
-   オーバーライド`FinalRelease`を解放する、 **IUnknown**ポインター。  
  
##  <a name="finalrelease"></a>  CComObjectRootEx::FinalRelease  
 作成したオブジェクトに必要なクリーンアップを実行する派生クラスでは、このメソッドをオーバーライドすることができます。  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>コメント  
 既定では、`CComObjectRootEx::FinalRelease`何も行われません。  
  
 クリーンアップを実行する`FinalRelease`位置にあるオブジェクトの構築も引き続き完全にために、クラスのデストラクターにコードを追加することをお勧めは`FinalRelease`と呼びます。 これにより、最派生クラスによって提供されるメソッドを安全にアクセスできます。 これは、削除する前に集計されたオブジェクトを解放するため特に重要です。  
  
##  <a name="internaladdref"></a>  CComObjectRootEx::InternalAddRef  
 1 つの非集約オブジェクトの参照カウントをインクリメントします。  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>戻り値  
 診断やテストに使用する値。  
  
### <a name="remarks"></a>コメント  
 場合は、スレッド モデルがマルチ スレッド、 **InterlockedIncrement**を複数のスレッドが同時に、参照カウントを変更することを防ぐために使用します。  
  
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
 `pThis`  
 [in]公開されるインターフェイスの COM マップを含んでいるオブジェクトへのポインター`QueryInterface`です。  
  
 `pEntries`  
 [in]ポインター、 **_ATL_INTMAP_ENTRY**構造体の使用可能なインターフェイス マップにアクセスします。  
  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppvObject`  
 [out]指定されたインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 `InternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。 オブジェクトを集約すると場合、`InternalQueryInterface`外部への委任しません。 インターフェイスを入力するには、COM マップ テーブルにマクロを持つ[COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)またはそのバリエーションの 1 つです。  
  
##  <a name="internalrelease"></a>  CComObjectRootEx::InternalRelease  
 1 つずつ、非集約オブジェクトの参照カウントをデクリメントします。  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>戻り値  
 どちらも非デバッグと、デバッグ ビルド、テストや診断に使用できる値を返します。 参照カウントになるで使用すると、オペレーティング システムなどのさまざまな要因場合や、ことはできません。 正確な値が返されます。  
  
### <a name="remarks"></a>コメント  
 場合は、スレッド モデルがマルチ スレッド、 **InterlockedDecrement**を複数のスレッドが同時に、参照カウントを変更することを防ぐために使用します。  
  
##  <a name="lock"></a>  CComObjectRootEx::Lock  
 このメソッドが、Win32 API 関数を呼び出すスレッド モデルがマルチ スレッドの場合は、 [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608)スレッドは、クリティカル セクション オブジェクトの所有権を取得できるまで待機したどのがプライベート データ メンバーを取得します。  
  
```
void Lock();
```  
  
### <a name="remarks"></a>コメント  
 スレッドを呼び出す必要があります、保護されたコードでは、実行が完了したら、`Unlock`クリティカル セクションの所有権を解放します。  
  
 スレッド モデルがシングル スレッドの場合、このメソッドは何も行いません。  
  
##  <a name="m_dwref"></a>  CComObjectRootEx::m_dwRef  
 4 バイトのメモリにアクセスする共用体の一部です。  
  
```
long m_dwRef;
```  
  
### <a name="remarks"></a>コメント  
 `m_pOuterUnknown`共用体の一部では。  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 オブジェクトは集計されませんが、参照カウントしてもアクセス`AddRef`と**リリース**に格納されて`m_dwRef`です。 外側の不明なへのポインターが格納されている場合は、オブジェクトを集計すると、[アグリゲート](#m_pouterunknown)です。  
  
##  <a name="m_pouterunknown"></a>  CComObjectRootEx::m_pOuterUnknown  
 4 バイトのメモリにアクセスする共用体の一部です。  
  
```
IUnknown*
    m_pOuterUnknown;
```     
  
### <a name="remarks"></a>コメント  
 `m_dwRef`共用体の一部では。  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 外側の不明なへのポインターが格納されている場合は、オブジェクトを集計すると、`m_pOuterUnknown`です。 オブジェクトは集計されませんが、参照カウントしてもアクセス`AddRef`と**リリース**に格納されて[m_dwRef](#m_dwref)です。  
  
##  <a name="objectmain"></a>  CComObjectRootEx::ObjectMain  
 表示される各クラスの[オブジェクト マップ](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f)モジュールが初期化される場合、1 回、この関数は呼び出され、もう一度が終了したとき。  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>パラメーター  
 `bStarting`  
 [out]値が**true**クラスは、それ以外の初期化されている場合**false**です。  
  
### <a name="remarks"></a>コメント  
 値、`bStarting`パラメーターは、モジュールがされているかどうかを示します初期化するか、または終了します。 既定の実装`ObjectMain`、何も行われませんが、初期化またはクラスに割り当てるリソースをクリーンアップするのには、クラスでこの関数をオーバーライドすることができます。 なお`ObjectMain`クラスのすべてのインスタンスが要求される前と呼びます。  
  
 `ObjectMain` エントリ ポイント関数が実行できる操作の種類が制限されているために、DLL のエントリ ポイントから呼び出されます。 これらの制限の詳細については、次を参照してください。 [Dll および Visual c ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)と[DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="outeraddref"></a>  CComObjectRootEx::OuterAddRef  
 集計の外側の不明な参照カウントをインクリメントします。  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>戻り値  
 診断やテストに使用する値。  
  
##  <a name="outerqueryinterface"></a>  CComObjectRootEx::OuterQueryInterface  
 要求されたインターフェイスへの間接ポインターを取得します。  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppvObject`  
 [out]指定されたインターフェイス ポインターへのポインター `iid`、または**NULL**集計は、インターフェイスをサポートしていない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
##  <a name="outerrelease"></a>  CComObjectRootEx::OuterRelease  
 集計の外側の不明な参照カウントをデクリメントします。  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>戻り値  
 非デバッグ ビルドでは、常に 0 を返します。 デバッグ ビルドで、診断に役に立たず、テスト可能な値を返します。  
  
##  <a name="unlock"></a>  CComObjectRootEx::Unlock  
 このメソッドが、Win32 API 関数を呼び出すスレッド モデルがマルチ スレッドの場合は、 [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169)、クリティカル セクション オブジェクトの場合は、どのリリース所有権がプライベート データ メンバーを取得します。  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>コメント  
 所有権を取得する、スレッドを呼び出す必要があります`Lock`です。 各呼び出し`Lock`に対応する呼び出しが必要です`Unlock`クリティカル セクションの所有権を解放します。  
  
 スレッド モデルがシングル スレッドの場合、このメソッドは何も行いません。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComObject クラス](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
