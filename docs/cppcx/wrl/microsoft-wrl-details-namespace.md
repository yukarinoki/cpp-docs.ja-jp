---
title: Microsoft::WRL::Details 名前空間
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
ms.openlocfilehash: 50208242d77d7b54951bcb44608f1a20b5147efc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223474"
---
# <a name="microsoftwrldetails-namespace"></a>Microsoft::WRL::Details 名前空間

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
namespace Microsoft::WRL::Details;
```

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|名前|[説明]|
|----------|-----------------|
|[ComPtrRef クラス](comptrref-class.md)|ComPtr 型のオブジェクトへの参照を表し \<T> ます。|
|[ComPtrRefBase クラス](comptrrefbase-class.md)|[Comptrref](comptrref-class.md)クラスの基本クラスを表します。|
|[DontUseNewUseMake クラス](dontusenewusemake-class.md)|で演算子を使用できないよう `new` に `RuntimeClass` します。 そのため、代わりに[Make 関数](make-function.md)を使用する必要があります。|
|[EventTargetArray クラス](eventtargetarray-class.md)|イベントハンドラーの配列を表します。|
|[MakeAllocator クラス](makeallocator-class.md)|弱い参照をサポートするか、または使用せずに、アクティブ化可能なクラスにメモリを割り当てます。|
|[ModuleBase クラス](modulebase-class.md)|[モジュール](module-class.md)クラスの基本クラスを表します。|
|[RemoveIUnknown クラス](removeiunknown-class.md)|は、ベースの型に相当する型を作成し `IUnknown` ますが、非仮想 `QueryInterface` 、 `AddRef` 、および `Release` メソッドを持ちます。|
|[WeakReference クラス](weakreference-class.md)|Windows ランタイムまたは従来の COM と共に使用できる*弱い参照*を表します。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。|

### <a name="structures"></a>構造体

|名前|[説明]|
|----------|-----------------|
|[ArgTraits 構造体](argtraits-structure.md)|指定されたデリゲートインターフェイスと、指定された数のパラメーターを持つ匿名メンバー関数を宣言します。|
|[ArgTraitsHelper 構造体](argtraitshelper-structure.md)|デリゲート引数の共通の特性を定義するのに役立ちます。|
|[BoolStruct 構造体](boolstruct-structure.md)|`ComPtr`がインターフェイスのオブジェクトの有効期間を管理しているかどうかを定義します。 `BoolStruct`は、[ブール型 ()](comptr-class.md#operator-microsoft-wrl-details-booltype)演算子によって内部的に使用されます。|
|[CreatorMap 構造体](creatormap-structure.md)|オブジェクトを初期化、登録、および登録解除する方法について説明します。|
|[DerefHelper 構造体](derefhelper-structure.md)|テンプレートパラメーターへの逆参照ポインターを表し `T*` ます。|
|[EnableIf 構造体](enableif-structure.md)|最初のテンプレートパラメーターがに評価される場合、2番目のテンプレートパラメーターによって指定された型のデータメンバーを定義し **`true`** ます。|
|[FactoryCache 構造体](factorycache-structure.md)|クラスファクトリの場所と、登録されている Windows ランタイムまたは COM クラスオブジェクトを識別する値を格納します。|
|[ImplementsBase 構造体](implementsbase-structure.md)|[Implements 構造体](implements-structure.md)でテンプレートパラメーターの型を検証するために使用されます。|
|[ImplementsHelper 構造体](implementshelper-structure.md)|[Implements](implements-structure.md)構造体を実装するのに役立ちます。|
|[InterfaceList 構造体](interfacelist-structure.md)|インターフェイスの再帰的リストを作成するために使用します。|
|[InterfaceListHelper 構造体](interfacelisthelper-structure.md)|`InterfaceList`指定されたテンプレートパラメーター引数を再帰的に適用して、型を構築します。|
|[InterfaceTraits 構造体](interfacetraits-structure.md)|インターフェイスの一般的な特性を実装します。|
|[InvokeHelper 構造体](invokehelper-structure.md)|`Invoke()`指定された引数の数と型に基づいて、メソッドの実装を提供します。|
|[IsBaseOfStrict 構造体](isbaseofstrict-structure.md)|一方の型がもう一方の型の基本クラスであるかどうかをテストします。|
|[IsSame 構造体](issame-structure.md)|指定した1つの型が、指定した別の型と同じかどうかをテストします。|
|[Nil 構造体](nil-structure.md)|省略可能なテンプレートパラメーターを指定するために使用されます。|
|[RemoveReference 構造体](removereference-structure.md)|指定したクラステンプレートパラメーターから参照または右辺値参照の特徴を取り除きます。|
|[RuntimeClassBase 構造体](runtimeclassbase-structure.md)|Make 関数でを検出するために使用され `RuntimeClass` ます。 [Make](make-function.md)|
|[RuntimeClassBaseT 構造体](runtimeclassbaset-structure.md)|操作にヘルパーメソッド `QueryInterface` を提供し、インターフェイス id を取得します。|
|[VerifyInheritanceHelper 構造体](verifyinheritancehelper-structure.md)|あるインターフェイスが別のインターフェイスから派生しているかどうかをテストします。|
|[VerifyInterfaceHelper 構造体](verifyinterfacehelper-structure.md)|テンプレートパラメーターによって指定されたインターフェイスが特定の要件を満たしていることを確認します。|

### <a name="enumerations"></a>列挙型

|名前|[説明]|
|----------|-----------------|
|[AsyncStatusInternal 列挙型](asyncstatusinternal-enumeration.md)|非同期操作の状態と列挙体の内部列挙間のマッピングを指定し `Windows::Foundation::AsyncStatus` ます。|

### <a name="functions"></a>関数

|名前|[説明]|
|----------|-----------------|
|[ActivationFactoryCallback 関数](activationfactorycallback-function.md)|指定されたアクティベーション ID のアクティベーションファクトリを取得します。|
|[Move 関数](move-function.md)|指定された引数をある場所から別の場所に移動します。|
|[RaiseException 関数](raiseexception-function.md)|呼び出し元のスレッドで例外を発生させます。|
|[Swap 関数 (WRL)](swap-function-wrl.md)|指定した2つの引数の値を交換します。|
|[TerminateMap 関数](terminatemap-function.md)|指定されたモジュール内のクラスファクトリをシャットダウンします。|

## <a name="requirements"></a>必要条件

**Header:** async、client、corewrappers .h、event .h、ftm、およびを実装します。 .h,、内部 .h,、.h,、.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)<br/>
[Microsoft:: WRL:: Wrapper 名前空間](microsoft-wrl-wrappers-namespace.md)
