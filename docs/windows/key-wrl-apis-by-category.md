---
title: キーのカテゴリ別な WRL Api |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d79888a58e5fc6d6911c4cc123877c1537f22cf1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441929"
---
# <a name="key-wrl-apis-by-category"></a>カテゴリ別の主要な WRL API
次の表は、主要な Windows ランタイム C++ テンプレート ライブラリのクラス、構造体、関数、およびマクロを示します。 ヘルパーの名前空間とクラスの構成要素は省略されます。 これらのリストは、API のドキュメントは別に並べ替える名前空間を拡張します。
  
### <a name="classes"></a>クラス
  
|Title|説明|
|-----------|-----------------|
|[ActivationFactory クラス](../windows/activationfactory-class.md)|1 つ以上のクラスを Windows ランタイムによってアクティブ化できるようにします。|
|[AsyncBase クラス](../windows/asyncbase-class.md)|Windows ランタイムの非同期ステート マシンを実装します。|
|[ClassFactory クラス](../windows/classfactory-class.md)|`IClassFactory` インターフェイスの基本機能を実装します。|
|[ComPtr クラス](../windows/comptr-class.md)|テンプレート パラメーターで指定されたインターフェイスを表す *スマート ポインター* 型を作成します。 ComPtr は、基になるインターフェイス ポインターの参照カウントを自動的に維持し、参照カウントがゼロになるとそのインターフェイスを解放します。|
|[Event クラス (Windows ランタイム C++ テンプレート ライブラリ)](../windows/event-class-windows-runtime-cpp-template-library.md)|イベントを表します。|
|[EventSource クラス](../windows/eventsource-class.md)|イベントを表します。 `EventSource` メンバー関数は、イベント ハンドラーの追加、削除、および呼び出しを実行します。|
|[FtmBase クラス](../windows/ftmbase-class.md)|フリー スレッド マーシャラー オブジェクトを表します。|
|[HandleT クラス](../windows/handlet-class.md)|オブジェクトへのハンドルを表します。|
|[HString クラス](../windows/hstring-class.md)|HSTRING ハンドルの操作をサポートします。|
|[HStringReference クラス](../windows/hstringreference-class.md)|既存の文字列から作成された HSTRING を表します。|
|[Module クラス](../windows/module-class.md)|関連するオブジェクトから成るコレクションを表します。|
|[Module::GenericReleaseNotifier クラス](../windows/module-genericreleasenotifier-class.md)|現在のモジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。 イベント ハンドラーは、ラムダをファンクター、または関数へのポインターによって指定されます。|
|[Module::MethodReleaseNotifier クラス](../windows/module-methodreleasenotifier-class.md)|現在のモジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。 イベント ハンドラーは、オブジェクトとそのメソッドへのポインター メンバーによって指定されます。|
|[Module::ReleaseNotifier クラス](../windows/module-releasenotifier-class.md)|モジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。|
|[RoInitializeWrapper クラス](../windows/roinitializewrapper-class.md)|Windows ランタイムを初期化します。|
|[RuntimeClass クラス](../windows/runtimeclass-class.md)|指定した数のインターフェイスを継承し、指定した Windows ランタイム、クラシック COM、および弱い参照をサポートする、インスタンス化されたクラスを表します。|
|[SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)|Windows ランタイムまたはクラシック COM の基底クラスを作成するための基本的なメカニズムを提供します。|
|[SimpleClassFactory クラス](../windows/simpleclassfactory-class.md)|基底クラスを作成するための基本的なメカニズムを提供します。|
|[WeakRef クラス](../windows/weakref-class.md)|クラシック COM ではなく、Windows ランタイムでのみ使用できる *弱い参照* を表します。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。|
  
### <a name="structures"></a>構造体
  
|Title|説明|
|-----------|-----------------|
|[ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)|一連のインターフェイス ID に適用できる検証および初期化関数を指定します。|
|[CloakedIid 構造体](../windows/cloakediid-structure.md)|示します、 `RuntimeClass`、`Implements`と`ChainInterfaces`テンプレートの指定したインターフェイスが IID リストにアクセスできないことです。|
|[Implements 構造体](../windows/implements-structure.md)|実装`QueryInterface`と`GetIid`のインターフェイスで指定します。|
|[MixIn 構造体](../windows/mixin-structure.md)|ランタイム クラスが Windows ランタイム インターフェイス (存在する場合) から派生し、次にクラシック COM インターフェイスから派生していることを確認します。|
  
### <a name="functions"></a>関数
  
|Title|説明|
|-----------|-----------------|
|[ActivateInstance 関数](../windows/activateinstance-function.md)|登録し、指定したクラス ID で定義されている指定された型のインスタンスを取得します。|
|[AsWeak 関数](../windows/asweak-function.md)|指定されたインスタンスへの弱い参照を取得します。|
|[コールバック関数](../windows/callback-function-windows-runtime-cpp-template-library.md)|メンバー関数がコールバック メソッドであるオブジェクトを作成します。|
|[CreateActivationFactory 関数](../windows/createactivationfactory-function.md)|Windows ランタイムによるアクティブ化が可能な、指定されたクラスのインスタンスを生成するファクトリを作成します。|
|[CreateClassFactory 関数](../windows/createclassfactory-function.md)|指定されたクラスのインスタンスを生成するファクトリを作成します。|
|[GetActivationFactory 関数](../windows/getactivationfactory-function.md)|テンプレート パラメーターで指定された型のアクティベーション ファクトリを取得します。|
|[Make 関数](../windows/make-function.md)|指定した Windows ランタイム クラスを初期化します。|
  
### <a name="macros"></a>[マクロ]
  
|Title|説明|
|-----------|-----------------|
|[ActivatableClass マクロ](../windows/activatableclass-macros.md)|指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを設定します。|
|[InspectableClass マクロ](../windows/inspectableclass-macro.md)|ランタイム クラス名と信頼レベルを設定します。|
  
## <a name="see-also"></a>関連項目

[Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)