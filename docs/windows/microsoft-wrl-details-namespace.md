---
title: Microsoft::WRL::Details Namespace |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a038509912c659cc820b73f16210ce874427112
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881771"
---
# <a name="microsoftwrldetails-namespace"></a>Microsoft::WRL::Details 名前空間
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
namespace Microsoft::WRL::Details;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="classes"></a>クラス  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtrRef クラス](../windows/comptrref-class.md)|ComPtr の型のオブジェクトへの参照を表す\<T > です。|  
|[ComPtrRefBase クラス](../windows/comptrrefbase-class.md)|基本クラスを表す、 [ComPtrRef](../windows/comptrref-class.md)クラスです。|  
|[DontUseNewUseMake クラス](../windows/dontusenewusemake-class.md)|演算子を使用できないように`new`で`RuntimeClass`です。 したがって、使用する必要があります、[関数](../windows/make-function.md)代わりにします。|  
|[EventTargetArray クラス](../windows/eventtargetarray-class.md)|イベント ハンドラーの配列を表します。|  
|[MakeAllocator クラス](../windows/makeallocator-class.md)|弱い参照のサポートの有無のアクティブ化可能なクラスのメモリを割り当てます。|  
|[ModuleBase クラス](../windows/modulebase-class.md)|基本クラスを表す、[モジュール](../windows/module-class.md)クラスです。|  
|[RemoveIUnknown クラス](../windows/removeiunknown-class.md)|等価の型を作成、 `IUnknown`-ベースの型が、非仮想`QueryInterface`、 `AddRef`、および`Release`メソッドです。|  
|[WeakReference クラス](../windows/weakreference-class1.md)|表す、*弱い参照*Windows ランタイムまたはクラシック COM で使用できます。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。|  
  
### <a name="structures"></a>構造体  
  
|名前|説明|  
|----------|-----------------|  
|[ArgTraits 構造体](../windows/argtraits-structure.md)|インターフェイスおよびを指定した数のパラメーターを持つ匿名メンバー関数は、指定したデリゲートを宣言します。|  
|[ArgTraitsHelper 構造体](../windows/argtraitshelper-structure.md)|支援は、デリゲート引数の共通の特性を定義します。|  
|[BoolStruct 構造体](../windows/boolstruct-structure.md)|ComPtr がインターフェイスのオブジェクトの有効期間を管理するかどうかを定義します。 BoolStruct が内部で使用される、 [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)演算子。|  
|[CreatorMap 構造体](../windows/creatormap-structure.md)|初期化、登録、およびオブジェクトの登録を解除する方法についてを説明します。|  
|[DerefHelper 構造体](../windows/derefhelper-structure.md)|指すポインターが逆参照を表す、`T*`テンプレート パラメーター。|  
|[EnableIf 構造体](../windows/enableif-structure.md)|最初のテンプレート パラメーターが評価された場合、2 番目のテンプレート パラメーターで指定された型のデータ メンバーを定義する`true`です。|  
|[FactoryCache 構造体](../windows/factorycache-structure.md)|クラス ファクトリと登録済みの Windows ランタイムまたは COM クラス オブジェクトを識別する値の場所が含まれています。|  
|[ImplementsBase 構造体](../windows/implementsbase-structure.md)|テンプレート パラメーターの型の検証に使用される[Implements 構造体](../windows/implements-structure.md)です。|  
|[ImplementsHelper 構造体](../windows/implementshelper-structure.md)|により、実装、 [Implements](../windows/implements-structure.md)構造体。|  
|[InterfaceList 構造体](../windows/interfacelist-structure.md)|インターフェイスの再帰的なリストを作成するために使用します。|  
|[InterfaceListHelper 構造体](../windows/interfacelisthelper-structure.md)|ビルド、`InterfaceList`再帰的に指定されたテンプレート パラメーターの引数を適用する型。|  
|[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)|インターフェイスの一般的な特徴を実装します。|  
|[InvokeHelper 構造体](../windows/invokehelper-structure.md)|指定した数値と引数の型に基づく Invoke() メソッドの実装を提供します。|  
|[IsBaseOfStrict 構造体](../windows/isbaseofstrict-structure.md)|一方の型がもう一方の型の基本クラスであるかどうかをテストします。|  
|[IsSame 構造体](../windows/issame-structure.md)|1 つには、型を指定するかどうかが同じ別のテストには、種類が指定されました。|  
|[Nil 構造体](../windows/nil-structure.md)|指定されていない、省略可能なテンプレート パラメーターを示すために使用します。|  
|[RemoveReference 構造体](../windows/removereference-structure.md)|指定されたクラス テンプレート パラメーターから参照または右辺値参照の特徴を切り離します。|  
|[RuntimeClassBase 構造体](../windows/runtimeclassbase-structure.md)|検出するために使用される`RuntimeClass`で、[ように](../windows/make-function.md)関数。|  
|[RuntimeClassBaseT 構造体](../windows/runtimeclassbaset-structure.md)|用にヘルパー メソッドを提供`QueryInterface`操作とインターフェイスの Id を取得します。|  
|[VerifyInheritanceHelper 構造体](../windows/verifyinheritancehelper-structure.md)|1 つのインターフェイスは別のインターフェイスから派生するかどうかをテストします。|  
|[VerifyInterfaceHelper 構造体](../windows/verifyinterfacehelper-structure.md)|テンプレート パラメーターによって指定されたインターフェイスが特定の要件を満たしていることを確認します。|  
  
### <a name="enumerations"></a>列挙  
  
|名前|説明|  
|----------|-----------------|  
|[AsyncStatusInternal 列挙型](../windows/asyncstatusinternal-enumeration.md)|非同期操作の状態の内部列挙値の間のマッピングを指定し、 **Windows::Foundation::AsyncStatus**列挙します。|  
  
### <a name="functions"></a>関数  
  
|名前|説明|  
|----------|-----------------|  
|[ActivationFactoryCallback 関数](../windows/activationfactorycallback-function.md)|指定されたアクティブ化 ID のアクティベーション ファクトリを取得します|  
|[Move 関数](../windows/move-function.md)|指定された引数を 1 つの場所から移動します。|  
|[RaiseException 関数](../windows/raiseexception-function.md)|呼び出し元のスレッドで例外が発生します。|  
|[Swap 関数 (Windows ランタイム C++ テンプレート ライブラリ)](../windows/swap-function-windows-runtime-cpp-template-library.md)|指定された 2 つの引数の値を交換します。|  
|[TerminateMap 関数](../windows/terminatemap-function.md)|指定されたモジュールでクラス ファクトリを終了します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h、client.h、corewrappers.h、event.h、ftm.h、implements.h、internal.h、module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)