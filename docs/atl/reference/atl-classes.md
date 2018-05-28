---
title: ATL クラスと構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/03/2018
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], ATL
- ATL, classes
ms.assetid: 7da42e2d-ac84-4506-92bd-502a86d68bdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e887f0adb7812664047fd30c3d9bb48368b9b564
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="atl-classes-and-structs"></a>ATL クラスと構造体
アクティブ テンプレート ライブラリ (ATL) には、次のクラスと構造体が含まれています。 特定のクラスをカテゴリ別を参照してください、 [ATL クラスの概要](../../atl/atl-class-overview.md)です。  
  
|クラス/構造体|説明|ヘッダー ファイル|  
|-----------|-----------------|-----------------|  
|[ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)|プリンター、メタファイル、ActiveX コントロールなど、さまざまな対象に表示するために使用する情報が含まれています。|atlctl.h|
|[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)|ATL の windowing コードのクラス インスタンス データが含まれています|atlbase.h|
|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)|ATL を使用する他のプロジェクトで使用されます。|atlbase.h|  
|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)|ATL で COM に関連するコードで使用されます。| atlbase.h|  
|[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)|ディスパッチ インターフェイスでメソッドまたはプロパティを記述するために使用する型情報が含まれています。|atlcom.h|  
|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)|すべての ATL モジュールによって使用されるデータが含まれています。|atlbase.h|  
|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|ATL の windowing コードによって使用されます。|atlbase.h|  
|[CA2AEX](../../atl/reference/ca2aex-class.md)|このクラスは、文字列変換マクロによって使用`CA2TEX`と`CT2AEX`、および typedef **CA2A**です。|atlconv.h|  
|[CA2CAEX](../../atl/reference/ca2caex-class.md)|このクラスは、文字列変換マクロは使用`CA2CTEX`と`CT2CAEX`、および typedef **CA2CA**です。|atlconv.h|  
|[CA2WEX](../../atl/reference/ca2wex-class.md)|このクラスは、文字列変換マクロによって使用`CA2TEX`、 `CA2CTEX`、 `CT2WEX`、および`CT2CWEX`、および typedef **CA2W**です。|atlconv.h|  
|[CAccessToken](../../atl/reference/caccesstoken-class.md)|このクラスは、アクセス トークンのラッパーです。|atlsecurity.h|  
|[CAcl](../../atl/reference/cacl-class.md)|このクラスは、用のラッパー、 **ACL** (アクセス制御リスト) 構造体。|atlsecurity.h|  
|[CAdapt](../../atl/reference/cadapt-class.md)|このテンプレートは、オブジェクトのアドレス以外の値を返すために、アドレス演算子を再定義するクラスをラップするときに使用されます。|atlcomcli.h|  
|[CAtlArray](../../atl/reference/catlarray-class.md)|このクラスは、配列オブジェクトを実装します。|atlcoll.h|  
|[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)|このクラスは、スレッド プール、アパートメント モデルの COM サーバーを実装します。|atlbase.h|  
|[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)|このクラスは、スレッド プール、アパートメント モデルの COM サーバーを実装するためのメソッドを提供します。|atlbase.h|  
|[CAtlBaseModule](../../atl/reference/catlbasemodule-class.md)|このクラスは、すべての ATL プロジェクトでインスタンス化します。|atlcore.h|  
|[CAtlComModule](../../atl/reference/catlcommodule-class.md)|このクラスは、COM サーバー モジュールを実装します。|atlbase.h|  
|[CAtlDebugInterfacesModule](../../atl/reference/catldebuginterfacesmodule-class.md)|このクラスは、デバッグのインターフェイスのサポートを提供します。|atlbase.h|  
|[CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)|このクラスは、DLL のモジュールを表します。|atlbase.h|  
|[CAtlException](../../atl/reference/catlexception-class.md)|このクラスは、ATL の例外を定義します。|atlexcept.h|  
|[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)|このクラスは、アプリケーションのモジュールを表します。|atlbase.h|  
|[CAtlFile](../../atl/reference/catlfile-class.md)|このクラスは、ファイル処理 API、Windows の周囲に thin ラッパーを提供します。|atlfile.h|  
|[CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)|このクラスのメソッドへのキャスト演算子の追加メモリ マップト ファイルを表します[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)です。|atlfile.h|  
|[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)|このクラスは、メモリ マップト ファイルを表します。|atlfile.h|  
|[CAtlList](../../atl/reference/catllist-class.md)|このクラスは、作成して、リスト オブジェクトを管理するためのメソッドを提供します。|atlcoll.h|  
|[CAtlMap](../../atl/reference/catlmap-class.md)|このクラスは、作成と管理、map オブジェクトのメソッドを提供します。|atlcoll.h|  
|[CAtlModule](../../atl/reference/catlmodule-class.md)|このクラスは、いくつかの ATL モジュール クラスによって使用されるメソッドを提供します。|atlbase.h|  
|[CAtlModuleT](../../atl/reference/catlmodulet-class.md)|このクラスは、ATL モジュールを実装します。|atlbase.h|  
|[CAtlPreviewCtrlImpl](../../atl/reference/catlpreviewctrlimpl-class.md)|このクラスは、ATL リッチ プレビュー用にシェルによって提供されるホスト ウィンドウに配置されているウィンドウの実装です。|atlpreviewctrlimpl.h|  
|[CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md)|このクラスは、サービスを実装します。|atlbase.h|  
|[CAtlTemporaryFile](../../atl/reference/catltemporaryfile-class.md)|このクラスは、作成および一時ファイルを使用するメソッドを提供します。|atlfile.h|  
|[CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)|このクラスは、カーネル トランザクション マネージャー (KTM) 関数のラッパーを提供します。|atltransactionmanager.h|  
|[CAtlWinModule](../../atl/reference/catlwinmodule-class.md)|このクラスは、ATL の windowing コンポーネントのサポートを提供します。|atlbase.h|  
|[CAutoPtr](../../atl/reference/cautoptr-class.md)|このクラスは、スマート ポインター オブジェクトを表します。|atlbase.h|  
|[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)|このクラスは、スマート ポインターの配列を構築するときに役立つメソッドを提供します。|atlbase.h|  
|[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)|このクラスは、スマート ポインターのコレクションを作成するときに、メソッド、静的関数、および typedef 便利を提供します。|atlcoll.h|  
|[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)|このクラスは、スマート ポインターのリストを構築するときに役立つメソッドを提供します。|atlcoll.h|  
|[CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)|このクラスは、新しいベクトルを使用して、スマート ポインター オブジェクトを表し、オペレーターを削除します。|atlbase.h|  
|[CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md)|このクラスは、メソッド、静的関数、および typedef と delete 演算子を新しいベクトルを使用して、スマート ポインターのコレクションを作成するときに便利です。 を提供します。|atlcoll.h|  
|[CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)|このクラスは、ActiveX コントロールをホストするダイアログ ボックス (モーダルまたはモードレス) を実装します。|atlwin.h|  
|[CAxWindow](../../atl/reference/caxwindow-class.md)|このクラスは、ActiveX コントロールをホストしているウィンドウを操作するためのメソッドを提供します。|atlwin.h|  
|[CAxWindow2T](../../atl/reference/caxwindow2t-class.md)|このクラスは、ActiveX コントロールをホストし、ライセンスされた ActiveX コントロールをホストするためのサポートがウィンドウを操作するためのメソッドを提供します。|atlwin.h|  
|[CBindStatusCallback](../../atl/reference/cbindstatuscallback-class.md)|このクラスは、`IBindStatusCallback` インターフェイスを実装します。|atlctl.h|  
|[CComAggObject](../../atl/reference/ccomaggobject-class.md)|このクラスは実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)集約オブジェクト。|atlcom.h|  
|[CComAllocator](../../atl/reference/ccomallocator-class.md)|このクラスは、COM メモリ ルーチンを使用しているメモリを管理するためのメソッドを提供します。|atlbase.h|  
|[CComApartment](../../atl/reference/ccomapartment-class.md)|このクラスは、アパートメント スレッド プールの EXE モジュールでの管理のサポートを提供します。|atlbase.h|  
|[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)|このクラスは、取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。|atlcore.h|  
|[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)|ATL 7.0 の時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール](../../atl/atl-module-classes.md)詳細についてはします。|atlbase.h|  
|[CComBSTR](../../atl/reference/ccombstr-class.md)|このクラスは、用のラッパー `BSTR`s。|atlbase.h|  
|[CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)|このクラスは実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)ティアオフ インターフェイスです。|atlcom.h|  
|[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)|このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスです。|atlcom.h|  
|[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)|このクラスは、実装、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)インターフェイスです。|atlcom.h|  
|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)|このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスし、オブジェクトが複数のアパートメント内で作成することができます。|atlcom.h|  
|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)|このクラスから派生[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を 1 つのオブジェクトを構築します。|atlcom.h|  
|[CComCoClass](../../atl/reference/ccomcoclass-class.md)|このクラスは、クラスのインスタンスを作成し、そのプロパティを取得するためのメソッドを提供します。|atlcom.h|  
|[CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)|このクラスは、複合コントロールを実装するために必要なメソッドを提供します。|atlctl.h|  
|[CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)|このクラスは実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)所有者オブジェクトの委任することによって**IUnknown**です。|atlcom.h|  
|[CComControl](../../atl/reference/ccomcontrol-class.md)|このクラスは、作成して、ATL コントロールを管理するためのメソッドを提供します。|atlctl.h|  
|[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)|このクラスは、作成して、ATL コントロールを管理するためのメソッドを提供します。|atlctl.h|  
|[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)|このクラスは、取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。|atlcore.h|  
|[CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)|このクラスは、ロックおよびロック解除、クリティカル セクション オブジェクトのメソッドを提供します。|atlbase.h|  
|[CComCurrency](../../atl/reference/ccomcurrency-class.md)|このクラスを作成および管理するためのメソッドと演算子には、`CURRENCY`オブジェクト。|atlcur.h|  
|[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)|このクラスの配列に格納**IUnknown**ポインター。|atlcom.h|  
|[CComEnum](../../atl/reference/ccomenum-class.md)|このクラスは、配列に基づいた COM 列挙子オブジェクトを定義します。|atlcom.h|  
|[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)|このクラスは、配列内に列挙されている項目が格納 COM 列挙子インターフェイスの実装を提供します。|atlcom.h|  
|[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)|このクラスは、C++ 標準ライブラリ コレクションに基づく COM 列挙子オブジェクトを定義します。|atlcom.h|  
|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)|このクラスと同じメソッドを提供する[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)は、クリティカル セクションは提供しません。|atlcore.h|  
|[CComGITPtr](../../atl/reference/ccomgitptr-class.md)|このクラスは、インターフェイス ポインターを処理するためのメソッドと、グローバル インターフェイス テーブル (GIT) を提供します。|atlbase.h|  
|[CComHeap](../../atl/reference/ccomheap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) COM メモリの割り当て関数を使用します。|ATLComMem.h|  
|[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)|ヒープのポインターを管理するためのスマート ポインター クラスです。|atlbase.h|  
|[CComModule](../../atl/reference/ccommodule-class.md)|ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール](../../atl/atl-module-classes.md)詳細についてはします。|atlbase.h|  
|[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)|このクラスは、変数の値、インクリメントおよびデクリメントのスレッド セーフであるメソッドを提供します。|atlbase.h|  
|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)|このクラスは、クリティカル セクションをロックまたはロック解除機能せず、インクリメントおよびデクリメントする変数の値のスレッド セーフであるメソッドを提供します。|atlbase.h|  
|[CComObject](../../atl/reference/ccomobject-class.md)|このクラスは実装**IUnknown**非集約オブジェクト。|atlcom.h|  
|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)|このクラスを含むモジュールの参照カウントを管理する、`Base`オブジェクト。|atlcom.h|  
|[CComObjectNoLock](../../atl/reference/ccomobjectnolock-class.md)|このクラスは実装**IUnknown**の非集約オブジェクトは、コンス トラクターでのモジュールのロック カウント インクリメントされません。|atlcom.h|  
|[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)|この typedef の[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)は既定のサーバーのモデルのスレッドでテンプレート化されます。|atlcom.h|  
|[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)|このクラスは、非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理するメソッドを提供します。|atlcom.h|  
|[CComObjectStack](../../atl/reference/ccomobjectstack-class.md)|このクラスは、一時的な COM オブジェクトを作成しのスケルトンの実装を提供**IUnknown**です。|atlcom.h|  
|[CComPolyObject](../../atl/reference/ccompolyobject-class.md)|このクラスは実装**IUnknown**集計または非集約オブジェクト。|atlcom.h|  
|[CComPtr](../../atl/reference/ccomptr-class.md)|COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。|atlcomcli.h|  
|[CComPtrBase](../../atl/reference/ccomptrbase-class.md)|このクラスは、メモリの COM ベースのルーチンを使用するスマート ポインター クラスの基礎を提供します。|atlcomcli.h|  
|[CComQIPtr](../../atl/reference/ccomqiptr-class.md)|COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。|atlcomcli.h|  
|[CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)|このクラスは、COM インターフェイス ポインターのコレクションを作成するときに、メソッド、静的関数、および typedef 便利を提供します。|atlcoll.h|  
|[CComSafeArray](../../atl/reference/ccomsafearray-class.md)|このクラスは、用のラッパー、`SAFEARRAY Data Type`構造体。|atlsafe.h|  
|[CComSafeArrayBound](../../atl/reference/ccomsafearraybound-class.md)|このクラスは、用のラッパー、`SAFEARRAYBOUND`構造体。|atlsafe.h|  
|[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)|このクラスは、クラスのスレッドの選択を管理[は](../../atl/reference/ccomautothreadmodule-class.md)します。|atlbase.h|  
|[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)|このクラスは、変数の値、インクリメントおよびデクリメントするためのメソッドを提供します。|atlbase.h|  
|[CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)|このクラスは、ティアオフ インターフェイスを実装します。|atlcom.h|  
|[CComUnkArray](../../atl/reference/ccomunkarray-class.md)|このクラスは、格納**IUnknown**ポインターへのパラメーターとして使用するものでは、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラス。|atlcom.h|  
|[CComVariant](../../atl/reference/ccomvariant-class.md)|このクラスは、格納されているデータの種類を表すメンバーを提供する、VARIANT 型をラップします。|atlcomcli.h|  
|[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)|このクラスは、別のオブジェクト内に含まれるウィンドウを実装します。|atlwin.h|  
|[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)|このクラスは、CRT メモリ ルーチンを使用しているメモリを管理するためのメソッドを提供します。|atlcore.h|  
|[CCRTHeap](../../atl/reference/ccrtheap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) CRT ヒープ関数を使用します。|atlmem.h|  
|[CDacl](../../atl/reference/cdacl-class.md)|このクラスは、DACL (随意アクセス制御リスト) 構造体のラッパーです。|atlsecurity.h|  
|[CDebugReportHook クラス](../../atl/reference/cdebugreporthook-class.md)|このクラスを使用すると、名前付きパイプにデバッグ レポートを送信します。|atlutil.h|  
|[CDefaultCharTraits](../../atl/reference/cdefaultchartraits-class.md)|このクラスは、大文字と小文字を変換するための 2 つの静的関数を提供します。|atlcoll.h|  
|[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)|このクラスは、既定の要素の比較関数を提供します。|atlcoll.h|  
|[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)|このクラスは、コレクション クラスの既定のメソッドおよび関数を提供します。|atlcoll.h|  
|[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)|このクラスは、ハッシュ値を計算するための静的関数を提供します。|atlcoll.h|  
|[CDialogImpl](../../atl/reference/cdialogimpl-class.md)|このクラスは、モーダルまたはモードレス ダイアログ ボックスを作成するためのメソッドを提供します。|atlwin.h|  
|[CDynamicChain](../../atl/reference/cdynamicchain-class.md)|このクラスは、メッセージ マップの動的な組み合わせをサポートするメソッドを提供します。|atlwin.h|  
|[CElementTraits](../../atl/reference/celementtraits-class.md)|このクラスは、移動、コピーとを比較する、ハッシュ演算メソッドおよび関数を提供するコレクション クラスによって使用されます。|atlcoll.h|  
|[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)|このクラスは、既定のコピーを提供し、コレクション クラスのメソッドを移動します。|atlcoll.h|  
|[CFirePropNotifyEvent](../../atl/reference/cfirepropnotifyevent-class.md)|このクラスは、コントロール プロパティの変更について、コンテナーのシンクに通知するためのメソッドを提供します。|atlctl.h|  
|[CGlobalHeap](../../atl/reference/cglobalheap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)グローバル ヒープの Win32 関数を使用します。|atlmem.h|  
|[CHandle](../../atl/reference/chandle-class.md)|このクラスは、作成およびオブジェクトのハンドルを使用するためのメソッドを提供します。|atlbase.h|  
|[CHeapPtr](../../atl/reference/cheapptr-class.md)|ヒープのポインターを管理するためのスマート ポインター クラスです。|atlcore.h|  
|[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)|このクラスは、いくつかのヒープのスマート ポインター クラスの基礎を形成します。|atlcore.h|  
|[CHeapPtrElementTraits クラス](../../atl/reference/cheapptrelementtraits-class.md)|このクラスは、ヒープのポインターのコレクションを作成するときに、メソッド、静的関数、および typedef に役立ちますを提供します。|atlcoll.h|  
|[CHeapPtrList](../../atl/reference/cheapptrlist-class.md)|このクラスは、ヒープのポインターのリストを構築するときに役立つメソッドを提供します。|atlcoll.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|読み込み、JPEG、GIF、BMP、およびポータブル ネットワーク グラフィックス (PNG) 形式で画像を保存する機能を含む、ビットマップの拡張サポートを提供します。|atlimage.h|  
|[CInterfaceArray](../../atl/reference/cinterfacearray-class.md)|このクラスは、COM インターフェイス ポインターの配列を構築するときに役立つメソッドを提供します。|atlcoll.h|  
|[CInterfaceList](../../atl/reference/cinterfacelist-class.md)|このクラスは、COM インターフェイス ポインターのリストを構築するときに役立つメソッドを提供します。|atlcoll.h|  
|[CLocalHeap](../../atl/reference/clocalheap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)ローカル ヒープの Win32 関数を使用します。|atlmem.h|  
|[CMessageMap](../../atl/reference/cmessagemap-class.md)|このクラスは、オブジェクトのメッセージが別のオブジェクトがアクセスするマップを使用します。|atlwin.h|  
|[CNonStatelessWorker クラス](../../atl/reference/cnonstatelessworker-class.md)|スレッド プールからの要求を受信し、各要求の作成し、破棄がワーカー オブジェクトに渡されます。|atlutil.h|  
|[CNoWorkerThread クラス](../../atl/reference/cnoworkerthread-class.md)|引数としてこのクラスを使用して、`MonitorClass`テンプレート パラメーター キャッシュ クラスの動的キャッシュのメンテナンスを無効にする場合。|atlutil.h|  
|[CPathT クラス](../../atl/reference/cpatht-class.md)|このクラスは、パスを表します。|atlpath.h|  
|[CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)|このクラスは、既定のメソッドを提供し、プリミティブ データ型のコレクション クラスの関数で構成されます。|atlcoll.h|  
|[CPrivateObjectSecurityDesc](../../atl/reference/cprivateobjectsecuritydesc-class.md)|このクラスは、プライベート オブジェクト セキュリティ記述子オブジェクトを表します。|atlsecurity.h|  
|[CRBMap](../../atl/reference/crbmap-class.md)|このクラスは、赤、黒のバイナリ ツリーを使用して、マッピング構造体を表します。|atlcoll.h|  
|[CRBMultiMap](../../atl/reference/crbmultimap-class.md)|このクラスは、赤、黒のバイナリ ツリーを使用して、1 つ以上の値に関連付けるには、各キーをできるマップの構造体を表します。|atlcoll.h|  
|[CRBTree](../../atl/reference/crbtree-class.md)|このクラスは、作成および赤、黒のツリーを利用するためのメソッドを提供します。|atlcoll.h|  
|[CRegKey](../../atl/reference/cregkey-class.md)|このクラスは、システム レジストリのエントリを操作するためのメソッドを提供します。|atlbase.h|  
|[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)|このクラスは、CRT のスレッドの作成機能を提供します。 スレッドが CRT 関数を使用する場合は、このクラスを使用します。|atlbase.h|  
|[CSacl](../../atl/reference/csacl-class.md)|このクラスは、SACL (システム アクセス制御リスト) 構造体のラッパーです。|atlsecurity.h|  
|[CSecurityAttributes](../../atl/reference/csecurityattributes-class.md)|このクラスは、のシン ラッパー、 **SECURITY_ATTRIBUTES**構造体。|atlsecurity.h|  
|[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)|このクラスは、用のラッパー、 **SECURITY_DESCRIPTOR**構造体。|atlsecurity.h|  
|[CSid](../../atl/reference/csid-class.md)|このクラスは、用のラッパー、 `SID` (セキュリティ識別子) 構造体。|atlsecurity.h|  
|[CSimpleArray](../../atl/reference/csimplearray-class.md)|このクラスは、単純な配列を管理するためのメソッドを提供します。|atlsimpcoll.h|  
|[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)|このクラスは、のヘルパー、 [CSimpleArray](../../atl/reference/csimplearray-class.md)クラスです。|atlsimpcoll.h|  
|[CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)|このクラスは、のヘルパー、 [CSimpleArray](../../atl/reference/csimplearray-class.md)クラスです。|atlsimpcoll.h|  
|[CSimpleDialog](../../atl/reference/csimpledialog-class.md)|このクラスは、基本のモーダル ダイアログ ボックスを実装します。|atlwin.h|  
|[CSimpleMap](../../atl/reference/csimplemap-class.md)|このクラスは、単純なマッピングの配列のサポートを提供します。|atlsimpcoll.h|  
|[CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)|このクラスは、のヘルパー、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラスです。|atlsimpcoll.h|  
|[CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)|このクラスは、のヘルパー、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラスです。|atlsimpcoll.h|  
|[CSnapInItemImpl](../../atl/reference/csnapinitemimpl-class.md)|このクラスは、スナップイン ノード オブジェクトを実装するためのメソッドを提供します。|atlsnap.h|  
|[CSnapInPropertyPageImpl](../../atl/reference/csnapinpropertypageimpl-class.md)|このクラスは、スナップインからプロパティ ページ オブジェクトを実装するためのメソッドを提供します。|atlsnap.h|  
|[CStockPropImpl](../../atl/reference/cstockpropimpl-class.md)|このクラスは、ストック プロパティの値をサポートするためのメソッドを提供します。|atlctl.h|  
|[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)|このクラスに格納するコレクション クラスで使用する静的関数が用意されています`CString`オブジェクト。|cstringt.h|  
|[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)|このクラスは、コレクション クラスのオブジェクトに格納された文字列に関連する静的関数を提供します。 似ています[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)が小文字の比較を実行します。|atlcoll.h|  
|[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)|このクラスは、コレクション クラスのオブジェクトに格納された文字列に関連する静的関数を提供します。 文字列オブジェクトが参照として処理します。|atlcoll.h|  
|[CThreadPool クラス](../../atl/reference/cthreadpool-class.md)|このクラスは、作業項目のキューを処理するワーカー スレッドのプールを提供します。|atlutil.h|  
|[CTokenGroups](../../atl/reference/ctokengroups-class.md)|このクラスは、用のラッパー、 **TOKEN_GROUPS**構造体。|atlsecurity.h|  
|[CTokenPrivileges](../../atl/reference/ctokenprivileges-class.md)|このクラスは、用のラッパー、 **TOKEN_PRIVILEGES**構造体。|atlsecurity.h|  
|[CUrl クラス](../../atl/reference/curl-class.md)|このクラスは、URL を表します。 既存の URL を解析するかどうか、他のユーザーとは無関係に、URL の各要素を操作することができます文字列または文字列を最初から作成します。|atlutil.h|  
|[CW2AEX](../../atl/reference/cw2aex-class.md)|このクラスは、文字列変換マクロによって使用`CT2AEX`、 `CW2TEX`、 `CW2CTEX`、および`CT2CAEX`、および typedef **CW2A**です。|atlconv.h|  
|[CW2CWEX](../../atl/reference/cw2cwex-class.md)|このクラスは、文字列変換マクロによって使用`CW2CTEX`と`CT2CWEX`、および typedef **CW2CW**です。|atlconv.h|  
|[CW2WEX](../../atl/reference/cw2wex-class.md)|このクラスは、文字列変換マクロによって使用`CW2TEX`と`CT2WEX`、および typedef`CW2W`です。|atlconv.h|  
|[CWin32Heap](../../atl/reference/cwin32heap-class.md)|このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 ヒープ割り当て関数を使用します。|atlmem.h|  
|[CWindow](../../atl/reference/cwindow-class.md)|このクラスは、ウィンドウを操作するためのメソッドを提供します。|atlwin.h|  
|[CWindowImpl](../../atl/reference/cwindowimpl-class.md)|このクラスは、作成またはウィンドウをサブクラス化のためのメソッドを提供します。|atlwin.h|  
|[CWinTraits](../../atl/reference/cwintraits-class.md)|このクラスは、window オブジェクトを作成するときに使用するスタイルを標準化するためのメソッドを提供します。|atlwin.h|  
|[CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)|このクラスは、window オブジェクトを作成するときに使用するスタイルを標準化するためのメソッドを提供します。|atlwin.h|  
|[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)|このクラスは、ウィンドウ クラスの情報を登録するためのメソッドを提供します。|atlwin.h|  
|[CWorkerThread クラス](../../atl/reference/cworkerthread-class.md)|このクラスは、ワーカー スレッドを作成または既存のものを使用して化し、1 つまたは複数のカーネル オブジェクトのハンドルを待機がシグナルを受け取るハンドルのいずれかに指定されたクライアント関数を実行します。|atlutil.h|  
|[IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)|このクラスへのインターフェイスを表す、`CreateInstance`メソッドです。|atlbase.h|  
|[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)|このクラスは、メモリ マネージャーへのインターフェイスを表します。|atlmem.h|  
|[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)|このインターフェイスは、ホストされるコントロールまたはコンテナーの特性を指定するためのメソッドを提供します。|atlbase.h、ATLIFace.h|  
|[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)|このインターフェイスは、ホストされるコントロールの補足のアンビエント プロパティを実装します。|atlbase.h、ATLIFace.h|  
|[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)|このインターフェイスは、コントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。|atlbase.h、ATLIFace.h|  
|[IAxWinHostWindowLic](../../atl/reference/iaxwinhostwindowlic-interface.md)|このインターフェイスは、ライセンスされたコントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。|atlbase.h、ATLIFace.h|  
|[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)|このクラスは、コレクション クラスによって使用されるメソッドを提供します。|atlcom.h|  
|[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)|このクラスは実装のコレクションを管理するための接続ポイント コンテナー [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)オブジェクト。|atlcom.h|  
|[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)|このクラスは、接続ポイントを実装します。|atlcom.h|  
|[IDataObjectImpl](../../atl/reference/idataobjectimpl-class.md)|このクラスは、汎用データ転送をサポートして、接続を管理するためのメソッドを提供します。|atlctl.h|  
|[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)|このクラスの既定の実装を提供する、`IDispatch`デュアル インターフェイスの一部です。|atlcom.h|  
|[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)|このクラスの実装を提供する、`IDispatch`メソッドです。|atlcom.h|  
|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)|このクラスの実装を提供する、`IDispatch`メソッド、せず、タイプ ライブラリから型情報を取得します。|atlcom.h|  
|[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)|Microsoft の HTML の解析およびレンダリング エンジンへのインターフェイス。|atlbase.h、ATLIFace.h|  
|[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)|このクラスは、C++ 標準ライブラリ コレクションに基づく列挙子インターフェイスを定義します。|atlcom.h|  
|[IObjectSafetyImpl](../../atl/reference/iobjectsafetyimpl-class.md)|このクラスの既定の実装を提供する、`IObjectSafety`インターフェイスを取得し、オブジェクトの安全性レベルを設定するクライアントを許可します。|atlctl.h|  
|[IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)|このクラスは、サイトと通信するためにオブジェクトを許可するメソッドを提供します。|atlcom.h|  
|[IOleControlImpl](../../atl/reference/iolecontrolimpl-class.md)|このクラスの既定の実装を提供する、 **IOleControl**インターフェイスと実装**IUnknown**です。|atlctl.h|  
|[IOleInPlaceActiveObjectImpl](../../atl/reference/ioleinplaceactiveobjectimpl-class.md)|このクラスは、インプレース コントロールとコンテナー間の通信を支援するメソッドを提供します。|atlctl.h|  
|[IOleInPlaceObjectWindowlessImpl](../../atl/reference/ioleinplaceobjectwindowlessimpl-class.md)|このクラスは実装**IUnknown**ウィンドウなしのコントロールを使用しているウィンドウ メッセージを受信して、ドラッグ アンド ドロップ操作に参加できるようにするためのメソッドを提供します。|atlctl.h|  
|[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)|このクラスは実装**IUnknown**コンテナーがコントロールとの通信に使用するプリンシパルのインターフェイスです。|atlctl.h|  
|[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)|このクラスは実装**IUnknown**クライアント オブジェクトのプロパティ ページの情報にアクセスすることができします。|atlctl.h|  
|[IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)|このクラスは実装**IUnknown**でき、そのプロパティをクライアントが提供するプロパティ バッグに保存するオブジェクト。|atlcom.h|  
|[IPersistStorageImpl](../../atl/reference/ipersiststorageimpl-class.md)|このクラスは、実装、[すること](http://msdn.microsoft.com/library/windows/desktop/ms679731)インターフェイスです。|atlcom.h|  
|[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)|このクラスは実装**IUnknown**の既定の実装を提供し、 [ipersiststreaminit など](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスです。|atlcom.h|  
|[IPointerInactiveImpl](../../atl/reference/ipointerinactiveimpl-class.md)|このクラスは実装**IUnknown**と[IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712)インターフェイスのメソッドです。|atlctl.h|  
|[IPropertyNotifySinkCP](../../atl/reference/ipropertynotifysinkcp-class.md)|このクラスは、公開、 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)接続可能なオブジェクトに対する発信インターフェイスとしてインターフェイスです。|atlctl.h|  
|[IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)|このクラスは実装**IUnknown**の既定の実装の継承と[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)です。|atlctl.h|  
|[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)|このクラスは実装**IUnknown**の既定の実装を提供し、 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246)インターフェイスです。|atlctl.h|  
|[IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md)|このクラスの既定の実装を提供する、 [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303)と[IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764)メソッドです。|atlcom.h|  
|[IQuickActivateImpl](../../atl/reference/iquickactivateimpl-class.md)|このクラスは、1 回の呼び出しにコンテナーのコントロールの初期化を結合します。|atlctl.h|  
|[IRunnableObjectImpl](../../atl/reference/irunnableobjectimpl-class.md)|このクラスは実装**IUnknown**の既定の実装を提供し、 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783)インターフェイスです。|atlctl.h|  
|[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)|このクラスの既定の実装を提供する、`IServiceProvider`インターフェイスです。|atlcom.h|  
|[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)|このクラスは実装**IUnknown**の既定の実装を提供し、 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217)インターフェイスです。|atlcom.h|  
|[ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md)|このクラスの既定の実装を提供する、`ISupportErrorInfo Interface`インターフェイスし、1 つのインターフェイスのみがオブジェクトでのエラーを生成するときに使用できます。|atlcom.h|  
|[IThreadPoolConfig インターフェイス](../../atl/reference/ithreadpoolconfig-interface.md)|このインターフェイスは、スレッド プールを構成するためのメソッドを提供します。|atlutil.h|  
|[IViewObjectExImpl](../../atl/reference/iviewobjecteximpl-class.md)|このクラスは実装**IUnknown**の既定の実装を提供し、 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)、および[IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)インターフェイスです。|atlctl.h|  
|[IWorkerThreadClient インターフェイス](../../atl/reference/iworkerthreadclient-interface.md)|`IWorkerThreadClient` クライアントによって実装されるインターフェイスは、[使用](../../atl/reference/cworkerthread-class.md)クラスです。|atlutil.h|  
|[_U_MENUorID](../../atl/reference/u-menuorid-class.md)|このクラスのラッパーを提供する**CreateWindow**と**について**です。|atlwin.h|  
|[_U_RECT](../../atl/reference/u-rect-class.md)|この引数のアダプター クラスは、いずれかの`RECT`ポインターまたは参照ポインターの観点から実装されている関数に渡されます。|atlwin.h|  
|[_U_STRINGorID](../../atl/reference/u-stringorid-class.md)|この引数のアダプター クラスは、いずれかのリソース名を使用できます (`LPCTSTR`s) またはリソース Id (**UINT**s)、呼び出し元の ID を使用して文字列を変換を必要とせず、関数に渡される、 **されるときは**マクロです。|atlwin.h|  
|[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)|このクラスは、Windows のスレッドの作成機能を提供します。 スレッド CRT 関数を使用しない場合は、このクラスを使用します。|atlbase.h|  
  
## <a name="see-also"></a>関連項目  
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)   
 [関数](../../atl/reference/atl-functions.md)   
 [グローバル変数](../../atl/reference/atl-global-variables.md)   
 [Typedefs](../../atl/reference/atl-typedefs.md)   
 [クラスの概要](../../atl/atl-class-overview.md)


