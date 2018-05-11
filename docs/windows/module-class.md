---
title: モジュール クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
dev_langs:
- C++
helpviewer_keywords:
- Module class
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2af8fa5bbafa76ab13f14d1a10e040a38bc6e2fb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="module-class"></a>Module クラス
関連するオブジェクトから成るコレクションを表します。  
  
## <a name="syntax"></a>構文  
  
```  
  
template<ModuleType moduleType>  
class Module;  
  
template<>  
class Module<InProc> : public Details::ModuleBase;  
  
template<>  
class Module<OutOfProc> : public Module<InProc>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `moduleType`  
 1 つまたは複数の組み合わせ[ModuleType](../windows/moduletype-enumeration.md)列挙値。  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-classes"></a>プロテクト クラス  
  
|名前|説明|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier クラス](../windows/module-genericreleasenotifier-class.md)|現在のモジュールの最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。 イベント ハンドラーは、ラムダ、ファンクタ、または関数へのポインターによって指定されます。|  
|[Module::MethodReleaseNotifier クラス](../windows/module-methodreleasenotifier-class.md)|現在のモジュールの最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。 イベント ハンドラーは、オブジェクトとそのメソッドへのポインターのメンバーによって指定されます。|  
|[Module::ReleaseNotifier クラス](../windows/module-releasenotifier-class.md)|モジュール内の最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Module::~Module デストラクター](../windows/module-tilde-module-destructor.md)|モジュール クラスの現在のインスタンスの初期化を解除します。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Module::Module コンストラクター](../windows/module-module-constructor.md)|モジュール クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Module::Create メソッド](../windows/module-create-method.md)|モジュールのインスタンスを作成します。|  
|[Module::DecrementObjectCount メソッド](../windows/module-decrementobjectcount-method.md)|モジュールによって追跡されるオブジェクトの数をデクリメントします。|  
|[Module::GetActivationFactory メソッド](../windows/module-getactivationfactory-method.md)|モジュールのアクティベーション ファクトリを取得します。|  
|[Module::GetClassObject メソッド](../windows/module-getclassobject-method.md)|クラス ファクトリのキャッシュを取得します。|  
|[Module::GetModule メソッド](../windows/module-getmodule-method.md)|モジュールのインスタンスを作成します。|  
|[Module::GetObjectCount メソッド](../windows/module-getobjectcount-method.md)|このモジュールによって管理されるオブジェクトの数を取得します。|  
|[Module::IncrementObjectCount メソッド](../windows/module-incrementobjectcount-method.md)|モジュールによって追跡されるオブジェクトの数をインクリメントします。|  
|[Module::RegisterCOMObject メソッド](../windows/module-registercomobject-method.md)|他のアプリケーションがそれらに接続できるように、1 つまたは複数の COM オブジェクトを登録します。|  
|[Module::RegisterObjects メソッド](../windows/module-registerobjects-method.md)|他のアプリケーションがそれらに接続できるように、COM または Windows ランタイム オブジェクトを登録します。|  
|[Module::RegisterWinRTObject メソッド](../windows/module-registerwinrtobject-method.md)|他のアプリケーションがそれらに接続できるように、1 つまたは複数の Windows ランタイム オブジェクトを登録します。|  
|[Module::Terminate メソッド](../windows/module-terminate-method.md)|すべてのファクトリが、モジュールをシャット ダウンによってインスタンス化が発生します。|  
|[Module::UnregisterCOMObject メソッド](../windows/module-unregistercomobject-method.md)|他のアプリケーションが接続することが原因で、1 つまたは複数の COM オブジェクトを解除します。|  
|[Module::UnregisterObjects メソッド](../windows/module-unregisterobjects-method.md)|指定したモジュール内のオブジェクトの登録を解除して、他のアプリケーションがそれらに接続できないようにします。|  
|[Module::UnregisterWinRTObject メソッド](../windows/module-unregisterwinrtobject-method.md)|他のアプリケーションがそれらに接続できないように、1 つまたは複数の Windows ランタイム オブジェクトを登録解除します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Module::Create メソッド](../windows/module-create-method.md)|モジュールのインスタンスを作成します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[Module::objectCount_ データ メンバー](../windows/module-objectcount-data-member.md)|多くのクラスが作成されたの追跡、[ように](../windows/make-function.md)関数。|  
|[Module::releaseNotifier_ データ メンバー](../windows/module-releasenotifier-data-member.md)|ReleaseNotifier オブジェクトへのポインターを保持します。|  
  
### <a name="macros"></a>[マクロ]  
  
|||  
|-|-|  
|[ActivatableClass](../windows/activatableclass-macros.md)|指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを追加します。 このマクロは、既定のファクトリおよびグループの ID パラメーターを指定します。|  
|[ActivatableClassWithFactory](../windows/activatableclass-macros.md)|指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを追加します。 このマクロでは、特定の工場出荷時のパラメーターを指定することができます。|  
|[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)|指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを追加します。 このマクロでは、特定のファクトリとグループの ID パラメーターを指定することができます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)