---
title: ATL クラスと構造体 |Microsoft Docs
ms.date: 05/03/2018
helpviewer_keywords:
- classes [C++], ATL
- ATL, classes
ms.assetid: 7da42e2d-ac84-4506-92bd-502a86d68bdc
ms.openlocfilehash: 561d6cb41ca066f5a2435b4eb1e8710ccaa99ea1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248941"
---
# <a name="atl-classes-and-structs"></a>ATL クラスと構造体

Active Template Library (ATL) では、次のクラスと構造体が含まれています。 カテゴリ別、特定のクラスを探すを参照してください。、 [ATL クラスの概要](../../atl/atl-class-overview.md)します。

|クラス/構造体|説明|ヘッダー ファイル|
|-----------|-----------------|-----------------|
|[ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)|プリンター、メタファイル、または ActiveX コントロールなどのさまざまなターゲットへのレンダリングに使用される情報が含まれています。|atlctl.h|
|[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)|ATL でウィンドウ作成コードのクラス インスタンスのデータが含まれています|atlbase.h|
|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)|ATL を使用するすべてのプロジェクトで使用されます。|atlbase.h|
|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)|ATL で COM に関連するコードで使用されます。| atlbase.h|
|[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)|ディスパッチ インターフェイスでメソッドまたはプロパティを記述するために使用する型情報が含まれています。|atlcom.h|
|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)|すべての ATL モジュールによって使用されるデータが含まれています。|atlbase.h|
|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|ATL でウィンドウ作成コードで使用されます。|atlbase.h|
|[CA2AEX](../../atl/reference/ca2aex-class.md)|このクラスは、文字列変換マクロ CA2TEX と CT2AEX、typedef CA2A によって使用されます。|atlconv.h|
|[CA2CAEX](../../atl/reference/ca2caex-class.md)|このクラスは、文字列変換マクロ CA2CTEX と CT2CAEX、typedef CA2CA によって使用されます。|atlconv.h|
|[CA2WEX](../../atl/reference/ca2wex-class.md)|このクラスは、文字列変換マクロ CA2TEX、CA2CTEX、CT2WEX、および CT2CWEX、および typedef CA2W によって使用されます。|atlconv.h|
|[CAccessToken](../../atl/reference/caccesstoken-class.md)|このクラスは、アクセス トークンのラッパーです。|atlsecurity.h|
|[CAcl](../../atl/reference/cacl-class.md)|このクラスは、ACL (アクセス制御リスト) の構造体のラッパーです。|atlsecurity.h|
|[CAdapt](../../atl/reference/cadapt-class.md)|このテンプレートは、オブジェクトのアドレス以外の値を返すために、アドレス演算子を再定義するクラスをラップするときに使用されます。|atlcomcli.h|
|[CAtlArray](../../atl/reference/catlarray-class.md)|このクラスは、配列オブジェクトを実装します。|atlcoll.h|
|[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)|このクラスは、スレッド プール、アパートメント モデルの COM サーバーを実装します。|atlbase.h|
|[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)|このクラスは、スレッド プール、アパートメント モデルの COM サーバーを実装するためのメソッドを提供します。|atlbase.h|
|[CAtlBaseModule](../../atl/reference/catlbasemodule-class.md)|このクラスは、すべての ATL プロジェクトでインスタンス化されます。|atlcore.h|
|[CAtlComModule](../../atl/reference/catlcommodule-class.md)|このクラスは、COM サーバー モジュールを実装します。|atlbase.h|
|[CAtlDebugInterfacesModule](../../atl/reference/catldebuginterfacesmodule-class.md)|このクラスは、デバッグのインターフェイスのサポートを提供します。|atlbase.h|
|[CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)|このクラスは、DLL のモジュールを表します。|atlbase.h|
|[CAtlException](../../atl/reference/catlexception-class.md)|このクラスは、ATL の例外を定義します。|atlexcept.h|
|[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)|このクラスは、アプリケーションのモジュールを表します。|atlbase.h|
|[CAtlFile](../../atl/reference/catlfile-class.md)|このクラスは、ファイル処理 API、Windows の thin ラッパーを提供します。|atlfile.h|
|[CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)|このクラスのメソッドへのキャスト演算子の追加メモリ マップト ファイルを表します[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)します。|atlfile.h|
|[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)|このクラスは、メモリ マップト ファイルを表します。|atlfile.h|
|[CAtlList](../../atl/reference/catllist-class.md)|このクラスは、作成およびリスト オブジェクトを管理するためのメソッドを提供します。|atlcoll.h|
|[CAtlMap](../../atl/reference/catlmap-class.md)|このクラスは、作成して、map オブジェクトを管理するためのメソッドを提供します。|atlcoll.h|
|[CAtlModule](../../atl/reference/catlmodule-class.md)|このクラスは、いくつかの ATL モジュール クラスによって使用されるメソッドを提供します。|atlbase.h|
|[CAtlModuleT](../../atl/reference/catlmodulet-class.md)|このクラスは、ATL モジュールを実装します。|atlbase.h|
|[CAtlPreviewCtrlImpl](../../atl/reference/catlpreviewctrlimpl-class.md)|このクラスは、リッチ プレビュー用に、シェルによって提供されるホスト ウィンドウに配置されているウィンドウの ATL 実装です。|atlpreviewctrlimpl.h|
|[CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md)|このクラスは、サービスを実装します。|atlbase.h|
|[CAtlTemporaryFile](../../atl/reference/catltemporaryfile-class.md)|このクラスは、一時ファイルを使用して作成メソッドを提供します。|atlfile.h|
|[CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)|このクラスは、カーネル トランザクション マネージャー (KTM) 関数のラッパーを提供します。|atltransactionmanager.h|
|[CAtlWinModule](../../atl/reference/catlwinmodule-class.md)|このクラスは、ATL windowing コンポーネントのサポートを提供します。|atlbase.h|
|[CAutoPtr](../../atl/reference/cautoptr-class.md)|このクラスは、スマート ポインター オブジェクトを表します。|atlbase.h|
|[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)|このクラスは、スマート ポインターの配列を構築するときに役立つメソッドを提供します。|atlbase.h|
|[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)|このクラスは、スマート ポインターのコレクションを作成するときに、メソッド、静的関数、および便利な typedef を提供します。|atlcoll.h|
|[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)|このクラスは、スマート ポインターのリストを構築するときに役立つメソッドを提供します。|atlcoll.h|
|[CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)|このクラスは、新しいベクトルを使用してスマート ポインター オブジェクトを表し、オペレーターを削除します。|atlbase.h|
|[CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md)|メソッド、静的関数、および typedef と delete 演算子を新しいベクトルを使用してスマート ポインターのコレクションを作成するときに便利です。 このクラスを提供します。|atlcoll.h|
|[CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)|このクラスは、ActiveX コントロールをホストするダイアログ ボックス (モーダルまたはモードレス) を実装します。|atlwin.h|
|[CAxWindow](../../atl/reference/caxwindow-class.md)|このクラスは、ActiveX コントロールをホスト ウィンドウを操作するためのメソッドを提供します。|atlwin.h|
|[CAxWindow2T](../../atl/reference/caxwindow2t-class.md)|このクラスは、ActiveX コントロールをホストし、ライセンスされた ActiveX コントロールをホストするためのサポートがあります。 ウィンドウを操作するためのメソッドを提供します。|atlwin.h|
|[CBindStatusCallback](../../atl/reference/cbindstatuscallback-class.md)|このクラスは、 `IBindStatusCallback` インターフェイスを実装します。|atlctl.h|
|[CComAggObject](../../atl/reference/ccomaggobject-class.md)|このクラスは実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)集約オブジェクト。|atlcom.h|
|[CComAllocator](../../atl/reference/ccomallocator-class.md)|このクラスは、COM メモリのルーチンを使用してメモリを管理するためのメソッドを提供します。|atlbase.h|
|[CComApartment](../../atl/reference/ccomapartment-class.md)|このクラスは、スレッド プールの EXE モジュールでアパートメントを管理するためのサポートを提供します。|atlbase.h|
|[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)|このクラスは、取得およびクリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。|atlcore.h|
|[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)|ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール](../../atl/atl-module-classes.md)の詳細。|atlbase.h|
|[CComBSTR](../../atl/reference/ccombstr-class.md)|このクラスは、Bstr のラッパーです。|atlbase.h|
|[CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)|このクラスは実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)ティアオフ インターフェイス。|atlcom.h|
|[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)|このクラスは、実装、 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイス。|atlcom.h|
|[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)|このクラスは、実装、 [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2)インターフェイス。|atlcom.h|
|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)|このクラスは、実装、 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスでき、複数のアパートメント内に作成するオブジェクト。|atlcom.h|
|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)|このクラスから派生[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 1 つのオブジェクトを構築します。|atlcom.h|
|[CComCoClass](../../atl/reference/ccomcoclass-class.md)|このクラスは、クラスのインスタンスを作成し、そのプロパティを取得するためのメソッドを提供します。|atlcom.h|
|[CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)|このクラスは、複合コントロールを実装するために必要なメソッドを提供します。|atlctl.h|
|[CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)|このクラスは実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)所有者オブジェクトの委任することによって`IUnknown`します。|atlcom.h|
|[CComControl](../../atl/reference/ccomcontrol-class.md)|このクラスは、作成および ATL のコントロールを管理するためのメソッドを提供します。|atlctl.h|
|[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)|このクラスは、作成および ATL のコントロールを管理するためのメソッドを提供します。|atlctl.h|
|[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)|このクラスは、取得およびクリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。|atlcore.h|
|[CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)|このクラスは、ロックとクリティカル セクション オブジェクトをロック解除のためのメソッドを提供します。|atlbase.h|
|[CComCurrency](../../atl/reference/ccomcurrency-class.md)|このクラスは、作成および、CURRENCY オブジェクトを管理するためのメソッドと演算子には。|atlcur.h|
|[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)|このクラスの配列を格納する`IUnknown`ポインター。|atlcom.h|
|[CComEnum](../../atl/reference/ccomenum-class.md)|このクラスは、配列ベースの COM の列挙子オブジェクトを定義します。|atlcom.h|
|[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)|このクラスは、配列に列挙されている項目を格納する、COM の列挙子インターフェイスの実装を提供します。|atlcom.h|
|[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)|このクラスは、C++ 標準ライブラリ コレクションに基づいて COM 列挙子オブジェクトを定義します。|atlcom.h|
|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)|このクラスと同じメソッドを提供する[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)クリティカル セクションは提供されません。|atlcore.h|
|[CComGITPtr](../../atl/reference/ccomgitptr-class.md)|このクラスは、インターフェイス ポインターを処理するためのメソッドおよびグローバル インターフェイス テーブル (GIT) を提供します。|atlbase.h|
|[CComHeap](../../atl/reference/ccomheap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) COM メモリの割り当て関数を使用します。|ATLComMem.h|
|[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)|ヒープのポインターを管理するためのスマート ポインター クラス。|atlbase.h|
|[CComModule](../../atl/reference/ccommodule-class.md)|ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール](../../atl/atl-module-classes.md)の詳細。|atlbase.h|
|[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)|このクラスは、変数の値、インクリメントおよびデクリメントするためのスレッド セーフなメソッドを提供します。|atlbase.h|
|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)|このクラスは、クリティカル セクションをロックまたはロック解除機能せず、インクリメントおよびデクリメント、変数の値をスレッド セーフなメソッドを提供します。|atlbase.h|
|[CComObject](../../atl/reference/ccomobject-class.md)|このクラスは実装`IUnknown`非集約オブジェクト。|atlcom.h|
|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)|このクラスの参照カウントを含むモジュールの管理、`Base`オブジェクト。|atlcom.h|
|[CComObjectNoLock](../../atl/reference/ccomobjectnolock-class.md)|このクラスは実装`IUnknown`の集約オブジェクトは、モジュールのロック数をコンス トラクターでインクリメントされません。|atlcom.h|
|[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)|この typedef の[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)スレッド モデルがサーバーの既定のテンプレート化されます。|atlcom.h|
|[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)|このクラスは、非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理するメソッドを提供します。|atlcom.h|
|[CComObjectStack](../../atl/reference/ccomobjectstack-class.md)|このクラスは、一時的な COM オブジェクトを作成し、スケルトンの実装が提供されます`IUnknown`します。|atlcom.h|
|[CComPolyObject](../../atl/reference/ccompolyobject-class.md)|このクラスは実装`IUnknown`集計または非集約オブジェクト。|atlcom.h|
|[CComPtr](../../atl/reference/ccomptr-class.md)|COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。|atlcomcli.h|
|[CComPtrBase](../../atl/reference/ccomptrbase-class.md)|このクラスは、メモリの COM ベースのルーチンを使用するスマート ポインター クラスの基盤を提供します。|atlcomcli.h|
|[CComQIPtr](../../atl/reference/ccomqiptr-class.md)|COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。|atlcomcli.h|
|[CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)|このクラスは、COM インターフェイス ポインターのコレクションを作成するときに、メソッド、静的関数、および便利な typedef を提供します。|atlcoll.h|
|[CComSafeArray](../../atl/reference/ccomsafearray-class.md)|このクラスは、のラッパー、`SAFEARRAY Data Type`構造体。|atlsafe.h|
|[CComSafeArrayBound](../../atl/reference/ccomsafearraybound-class.md)|このクラスは、のラッパーを`SAFEARRAYBOUND`構造体。|atlsafe.h|
|[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)|このクラスは、クラスのスレッドの選択を管理[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。|atlbase.h|
|[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)|このクラスは、変数の値、インクリメントおよびデクリメントするためのメソッドを提供します。|atlbase.h|
|[CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)|このクラスは、ティアオフ インターフェイスを実装します。|atlcom.h|
|[CComUnkArray](../../atl/reference/ccomunkarray-class.md)|このクラスは格納`IUnknown`ポインターへのパラメーターとして使用するものでは、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラス。|atlcom.h|
|[CComVariant](../../atl/reference/ccomvariant-class.md)|このクラスは、格納されているデータの種類を示すメンバーを提供する、バリアント型をラップします。|atlcomcli.h|
|[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)|このクラスは、別のオブジェクト内に含まれるウィンドウを実装します。|atlwin.h|
|[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)|このクラスは、CRT メモリ ルーチンを使用してメモリを管理するためのメソッドを提供します。|atlcore.h|
|[CCRTHeap](../../atl/reference/ccrtheap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) CRT ヒープ関数を使用します。|atlmem.h|
|[CDacl](../../atl/reference/cdacl-class.md)|このクラスは、DACL (随意アクセス制御リスト) 構造体のラッパーです。|atlsecurity.h|
|[CDebugReportHook クラス](../../atl/reference/cdebugreporthook-class.md)|このクラスを使用すると、名前付きパイプにデバッグ レポートを送信します。|atlutil.h|
|[CDefaultCharTraits](../../atl/reference/cdefaultchartraits-class.md)|このクラスは、大文字と小文字を変換するための 2 つの静的関数を提供します。|atlcoll.h|
|[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)|このクラスは、既定の要素の比較関数を提供します。|atlcoll.h|
|[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)|このクラスは、コレクション クラスの既定のメソッドおよび関数を提供します。|atlcoll.h|
|[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)|このクラスは、ハッシュ値を計算するための静的関数を提供します。|atlcoll.h|
|[CDialogImpl](../../atl/reference/cdialogimpl-class.md)|このクラスは、モーダルまたはモードレス ダイアログ ボックスを作成するためのメソッドを提供します。|atlwin.h|
|[CDynamicChain](../../atl/reference/cdynamicchain-class.md)|このクラスは、メッセージ マップの動的な組み合わせをサポートするメソッドを提供します。|atlwin.h|
|[CElementTraits](../../atl/reference/celementtraits-class.md)|このクラスは、移動、コピー、比較、およびハッシュ演算のメソッドや関数を提供するコレクション クラスによって使用されます。|atlcoll.h|
|[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)|このクラスは、既定のコピーを提供し、コレクション クラスのメソッドを移動します。|atlcoll.h|
|[CFirePropNotifyEvent](../../atl/reference/cfirepropnotifyevent-class.md)|このクラスは、コントロール プロパティの変更について、コンテナーのシンクに通知するためのメソッドを提供します。|atlctl.h|
|[CGlobalHeap](../../atl/reference/cglobalheap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)グローバル ヒープの Win32 関数を使用します。|atlmem.h|
|[CHandle](../../atl/reference/chandle-class.md)|このクラスは、作成してオブジェクトのハンドルを使用するためのメソッドを提供します。|atlbase.h|
|[CHeapPtr](../../atl/reference/cheapptr-class.md)|ヒープのポインターを管理するためのスマート ポインター クラス。|atlcore.h|
|[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)|このクラスは、いくつかのヒープのスマート ポインター クラスの基礎を形成します。|atlcore.h|
|[CHeapPtrElementTraits クラス](../../atl/reference/cheapptrelementtraits-class.md)|このクラスは、ヒープのポインターのコレクションを作成するときに、メソッド、静的関数、および便利な typedef を提供します。|atlcoll.h|
|[CHeapPtrList](../../atl/reference/cheapptrlist-class.md)|このクラスは、ヒープのポインターのリストを構築するときに役立つメソッドを提供します。|atlcoll.h|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|読み込み、JPEG、GIF、BMP、およびポータブル ネットワーク グラフィックス (PNG) 形式で画像を保存する機能など、ビットマップの拡張サポートを提供します。|atlimage.h|
|[CInterfaceArray](../../atl/reference/cinterfacearray-class.md)|このクラスは、COM インターフェイス ポインターの配列を構築するときに役立つメソッドを提供します。|atlcoll.h|
|[CInterfaceList](../../atl/reference/cinterfacelist-class.md)|このクラスは、COM インターフェイス ポインターのリストを構築するときに役立つメソッドを提供します。|atlcoll.h|
|[CLocalHeap](../../atl/reference/clocalheap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)ローカル ヒープの Win32 関数を使用します。|atlmem.h|
|[CMessageMap](../../atl/reference/cmessagemap-class.md)|このクラスは、オブジェクトのメッセージが別のオブジェクトがアクセスするマップを使用できます。|atlwin.h|
|[CNonStatelessWorker クラス](../../atl/reference/cnonstatelessworker-class.md)|スレッド プールからの要求を受信し、要求ごとに作成および破棄される worker オブジェクトに渡されます。|atlutil.h|
|[CNoWorkerThread クラス](../../atl/reference/cnoworkerthread-class.md)|引数としてこのクラスを使用して、`MonitorClass`テンプレート パラメーターのキャッシュ クラスの動的キャッシュのメンテナンスを無効にしたい場合。|atlutil.h|
|[CPathT クラス](../../atl/reference/cpatht-class.md)|このクラスは、パスを表します。|atlpath.h|
|[CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)|このクラスは既定のメソッドとプリミティブ データ型のコレクション クラスの関数で構成されます。|atlcoll.h|
|[CPrivateObjectSecurityDesc](../../atl/reference/cprivateobjectsecuritydesc-class.md)|このクラスは、プライベート オブジェクトのセキュリティ記述子オブジェクトを表します。|atlsecurity.h|
|[CRBMap](../../atl/reference/crbmap-class.md)|このクラスは、バイナリ レッド ブラック ツリーを使用して、マップ構造体を表します。|atlcoll.h|
|[CRBMultiMap](../../atl/reference/crbmultimap-class.md)|このクラスは、各キーに関連付けるバイナリ レッド ブラック ツリーを使用して、1 つ以上の値を許可するマップの構造体を表します。|atlcoll.h|
|[CRBTree](../../atl/reference/crbtree-class.md)|このクラスは、作成およびレッド ブラック ツリーを利用するためのメソッドを提供します。|atlcoll.h|
|[CRegKey](../../atl/reference/cregkey-class.md)|このクラスは、システム レジストリのエントリを操作するためのメソッドを提供します。|atlbase.h|
|[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)|このクラスは、CRT のスレッドの作成機能を提供します。 スレッドの CRT 関数が使用する場合は、このクラスを使用します。|atlbase.h|
|[CSacl](../../atl/reference/csacl-class.md)|このクラスは、SACL (システムへのアクセス制御リスト) 構造体のラッパーです。|atlsecurity.h|
|[CSecurityAttributes](../../atl/reference/csecurityattributes-class.md)|このクラスは、シン ラッパーを`SECURITY_ATTRIBUTES`構造体。|atlsecurity.h|
|[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)|このクラスは、のラッパー、`SECURITY_DESCRIPTOR`構造体。|atlsecurity.h|
|[CSid](../../atl/reference/csid-class.md)|このクラスは、のラッパーを`SID`(セキュリティ識別子) 構造体。|atlsecurity.h|
|[CSimpleArray](../../atl/reference/csimplearray-class.md)|このクラスは、単純な配列を管理するためのメソッドを提供します。|atlsimpcoll.h|
|[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)|このクラスのヘルパーは、 [CSimpleArray](../../atl/reference/csimplearray-class.md)クラス。|atlsimpcoll.h|
|[CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)|このクラスのヘルパーは、 [CSimpleArray](../../atl/reference/csimplearray-class.md)クラス。|atlsimpcoll.h|
|[CSimpleDialog](../../atl/reference/csimpledialog-class.md)|このクラスは、基本的なモーダル ダイアログ ボックスを実装します。|atlwin.h|
|[CSimpleMap](../../atl/reference/csimplemap-class.md)|このクラスは、単純なマッピングの配列のサポートを提供します。|atlsimpcoll.h|
|[CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)|このクラスのヘルパーは、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラス。|atlsimpcoll.h|
|[CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)|このクラスのヘルパーは、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラス。|atlsimpcoll.h|
|[CSnapInItemImpl](../../atl/reference/csnapinitemimpl-class.md)|このクラスは、スナップインからノード オブジェクトを実装するためのメソッドを提供します。|atlsnap.h|
|[CSnapInPropertyPageImpl](../../atl/reference/csnapinpropertypageimpl-class.md)|このクラスは、スナップインのプロパティ ページ オブジェクトを実装するためのメソッドを提供します。|atlsnap.h|
|[CStockPropImpl](../../atl/reference/cstockpropimpl-class.md)|このクラスは、ストック プロパティの値をサポートするためのメソッドを提供します。|atlctl.h|
|[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)|このクラスを格納するコレクション クラスで使用される静的関数を提供する`CString`オブジェクト。|cstringt.h|
|[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)|このクラスは、コレクション クラスのオブジェクトに格納された文字列に関連する静的関数を提供します。 似ています[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)が小文字の比較を実行します。|atlcoll.h|
|[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)|このクラスは、コレクション クラスのオブジェクトに格納された文字列に関連する静的関数を提供します。 文字列オブジェクトの参照として処理します。|atlcoll.h|
|[CThreadPool クラス](../../atl/reference/cthreadpool-class.md)|このクラスは、作業項目のキューを処理するワーカー スレッドのプールを提供します。|atlutil.h|
|[CTokenGroups](../../atl/reference/ctokengroups-class.md)|このクラスは、のラッパー、`TOKEN_GROUPS`構造体。|atlsecurity.h|
|[CTokenPrivileges](../../atl/reference/ctokenprivileges-class.md)|このクラスは、のラッパー、`TOKEN_PRIVILEGES`構造体。|atlsecurity.h|
|[CUrl クラス](../../atl/reference/curl-class.md)|このクラスは、URL を表します。 既存の URL を解析するかどうか、他のユーザーとは無関係に、URL の各要素を操作できる文字列またはゼロからの文字列を作成します。|atlutil.h|
|[CW2AEX](../../atl/reference/cw2aex-class.md)|このクラスは、文字列変換マクロ CT2AEX、CW2TEX、CW2CTEX、および CT2CAEX、および typedef CW2A によって使用されます。|atlconv.h|
|[CW2CWEX](../../atl/reference/cw2cwex-class.md)|このクラスは、文字列変換マクロ CW2CTEX と CT2CWEX、typedef CW2CW によって使用されます。|atlconv.h|
|[CW2WEX](../../atl/reference/cw2wex-class.md)|このクラスは、文字列変換マクロ CW2TEX と CT2WEX、typedef CW2W によって使用されます。|atlconv.h|
|[CWin32Heap](../../atl/reference/cwin32heap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 ヒープ割り当て関数を使用します。|atlmem.h|
|[CWindow](../../atl/reference/cwindow-class.md)|このクラスは、ウィンドウを操作するためのメソッドを提供します。|atlwin.h|
|[CWindowImpl](../../atl/reference/cwindowimpl-class.md)|このクラスは、作成またはウィンドウをサブクラス化するためのメソッドを提供します。|atlwin.h|
|[CWinTraits](../../atl/reference/cwintraits-class.md)|このクラスは、ウィンドウ オブジェクトを作成するときに使用するスタイルを標準化するためのメソッドを提供します。|atlwin.h|
|[CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)|このクラスは、ウィンドウ オブジェクトを作成するときに使用するスタイルを標準化するためのメソッドを提供します。|atlwin.h|
|[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)|このクラスは、ウィンドウ クラスの情報を登録するためのメソッドを提供します。|atlwin.h|
|[CWorkerThread クラス](../../atl/reference/cworkerthread-class.md)|このクラスは、ワーカー スレッドを作成します。 または、既存のものを使用して化し、1 つ以上のカーネル オブジェクトのハンドルを待機ハンドルがシグナル通知されたときに、指定したクライアント関数を実行します。|atlutil.h|
|[IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)|このクラスへのインターフェイスを表す、`CreateInstance`メソッド。|atlbase.h|
|[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)|このクラスは、メモリ マネージャーへのインターフェイスを表します。|atlmem.h|
|[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)|このインターフェイスは、ホストされるコントロールまたはコンテナーの特性を指定するためのメソッドを提供します。|atlbase.h、ATLIFace.h|
|[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)|このインターフェイスは、ホストされるコントロールの補足のアンビエント プロパティを実装します。|atlbase.h、ATLIFace.h|
|[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)|このインターフェイスは、コントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。|atlbase.h、ATLIFace.h|
|[IAxWinHostWindowLic](../../atl/reference/iaxwinhostwindowlic-interface.md)|このインターフェイスは、ライセンスされたコントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。|atlbase.h、ATLIFace.h|
|[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)|このクラスは、コレクション クラスで使用されるメソッドを提供します。|atlcom.h|
|[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)|このクラスのコレクションを管理する接続ポイント コンテナー [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)オブジェクト。|atlcom.h|
|[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)|このクラスは、接続ポイントを実装します。|atlcom.h|
|[IDataObjectImpl](../../atl/reference/idataobjectimpl-class.md)|このクラスは、汎用データ転送をサポートしていると、接続を管理するためのメソッドを提供します。|atlctl.h|
|[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)|このクラスの既定の実装を提供する、`IDispatch`デュアル インターフェイスの部分。|atlcom.h|
|[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)|このクラスの実装を提供する、`IDispatch`メソッド。|atlcom.h|
|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)|このクラスの実装を提供する、`IDispatch`メソッドは、タイプ ライブラリから型情報を取得せずします。|atlcom.h|
|[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)|Microsoft の HTML 解析およびレンダリング エンジンへのインターフェイス。|atlbase.h、ATLIFace.h|
|[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)|このクラスは、C++ 標準ライブラリ コレクションに基づいて列挙子インターフェイスを定義します。|atlcom.h|
|[IObjectSafetyImpl](../../atl/reference/iobjectsafetyimpl-class.md)|このクラスの既定の実装を提供する、`IObjectSafety`クライアントを取得し、オブジェクトの安全性レベルを設定できるようにするインターフェイス。|atlctl.h|
|[IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)|このクラスは、オブジェクトのサイトと通信を可能にするメソッドを提供します。|atlcom.h|
|[IOleControlImpl](../../atl/reference/iolecontrolimpl-class.md)|このクラスの既定の実装を提供する、`IOleControl`インターフェイスと実装`IUnknown`します。|atlctl.h|
|[IOleInPlaceActiveObjectImpl](../../atl/reference/ioleinplaceactiveobjectimpl-class.md)|このクラスは、インプレース コントロールとコンテナー間の通信を支援するメソッドを提供します。|atlctl.h|
|[IOleInPlaceObjectWindowlessImpl](../../atl/reference/ioleinplaceobjectwindowlessimpl-class.md)|このクラスは実装`IUnknown`ウィンドウ メッセージを受信して、ドラッグ アンド ドロップ操作に参加するウィンドウなしのコントロールを有効にするメソッドを提供します。|atlctl.h|
|[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)|このクラスは実装`IUnknown`とは、コンテナーがコントロールでの通信に使用するプリンシパルのインターフェイスです。|atlctl.h|
|[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)|このクラスは実装`IUnknown`し、クライアントは、オブジェクトのプロパティ ページの情報にアクセスできます。|atlctl.h|
|[IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)|このクラスは実装`IUnknown`でき、そのプロパティをクライアントが指定したプロパティ バッグに保存するオブジェクト。|atlcom.h|
|[IPersistStorageImpl](../../atl/reference/ipersiststorageimpl-class.md)|このクラスは、実装、 [IPersistStorage](/windows/desktop/api/objidl/nn-objidl-ipersiststorage)インターフェイス。|atlcom.h|
|[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)|このクラスは実装`IUnknown`の既定の実装を提供し、 [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit)インターフェイス。|atlcom.h|
|[IPointerInactiveImpl](../../atl/reference/ipointerinactiveimpl-class.md)|このクラスは実装`IUnknown`と[IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive)インターフェイスのメソッド。|atlctl.h|
|[IPropertyNotifySinkCP](../../atl/reference/ipropertynotifysinkcp-class.md)|このクラスは、公開、 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)接続可能なオブジェクトに対するアウトゴーイング インターフェイスとしてインターフェイス。|atlctl.h|
|[IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)|このクラスは実装`IUnknown`の既定の実装の継承と[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)します。|atlctl.h|
|[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)|このクラスは実装`IUnknown`の既定の実装を提供し、 [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage)インターフェイス。|atlctl.h|
|[IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md)|このクラスの既定の実装を提供する、 [IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo)と[IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2)メソッド。|atlcom.h|
|[IQuickActivateImpl](../../atl/reference/iquickactivateimpl-class.md)|このクラスは、1 つの呼び出しにコンテナーのコントロールの初期化を結合します。|atlctl.h|
|[IRunnableObjectImpl](../../atl/reference/irunnableobjectimpl-class.md)|このクラスは実装`IUnknown`の既定の実装を提供し、 [IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject)インターフェイス。|atlctl.h|
|[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)|このクラスの既定の実装を提供する、`IServiceProvider`インターフェイス。|atlcom.h|
|[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)|このクラスは実装`IUnknown`の既定の実装を提供し、 [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages)インターフェイス。|atlcom.h|
|[ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md)|このクラスの既定の実装を提供する、`ISupportErrorInfo Interface`インターフェイスを 1 つのインターフェイスのみがオブジェクトのエラーを生成するときに使用できます。|atlcom.h|
|[IThreadPoolConfig インターフェイス](../../atl/reference/ithreadpoolconfig-interface.md)|このインターフェイスは、スレッド プールを構成するためのメソッドを提供します。|atlutil.h|
|[IViewObjectExImpl](../../atl/reference/iviewobjecteximpl-class.md)|このクラスは実装`IUnknown`の既定の実装を提供し、 [IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject)、 [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2)、および[IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex)インターフェイス。|atlctl.h|
|[IWorkerThreadClient インターフェイス](../../atl/reference/iworkerthreadclient-interface.md)|`IWorkerThreadClient` クライアントによって実装されるインターフェイスは、 [CWorkerThread](../../atl/reference/cworkerthread-class.md)クラス。|atlutil.h|
|[_U_MENUorID](../../atl/reference/u-menuorid-class.md)|このクラスのラッパーを提供する`CreateWindow`と`CreateWindowEx`します。|atlwin.h|
|[_U_RECT](../../atl/reference/u-rect-class.md)|この引数アダプター クラスを使用するか`RECT`ポインターまたは参照ポインターの観点から実装されている関数に渡されます。|atlwin.h|
|[_U_STRINGorID](../../atl/reference/u-stringorid-class.md)|この引数のアダプター クラスは、リソース名 (LPCTSTRs) またはリソース Id、ID を持つときはマクロを使用して文字列に変換する、呼び出し元を必要とせず、関数に渡される (ついて) のいずれかを使用できます。|atlwin.h|
|[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)|このクラスは、Windows のスレッドの作成機能を提供します。 スレッドの CRT 関数を使用しない場合は、このクラスを使用します。|atlbase.h|

## <a name="see-also"></a>関連項目

[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)<br/>
[関数](../../atl/reference/atl-functions.md)<br/>
[グローバル変数](../../atl/reference/atl-global-variables.md)<br/>
[Typedefs](../../atl/reference/atl-typedefs.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
