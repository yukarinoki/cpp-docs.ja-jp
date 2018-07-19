---
title: task_handle クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
dev_langs:
- C++
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3fa72ed19a691015214fe263033e07f8d6a74c34
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688207"
---
# <a name="taskhandle-class"></a>task_handle クラス
`task_handle` クラスは個々の並列作業項目を表します。 このクラスは、1 つの処理を実行するために必要な命令およびデータをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
template<
    typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Function`  
 によって表される作業の実行に呼び出される関数オブジェクトの種類、`task_handle`オブジェクト。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[task_handle](#ctor)|新しい `task_handle` オブジェクトを構築します。 タスクの作業は、コンス トラクターにパラメーターとして指定された関数を呼び出すことによって実行されます。|  
|[~ task_handle デストラクター](#dtor)|`task_handle` オブジェクトを破棄します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator()](#task_handle__operator_call)|タスク ハンドルの作業を実行するために、ランタイムが呼び出す関数呼び出し演算子です。|  
  
## <a name="remarks"></a>コメント  
 `task_handle` オブジェクトを組み合わせて使用することができます、`structured_task_group`またはより一般的な`task_group`作業を並列タスクを分解するためのオブジェクト。 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)です。  
  
 なおの作成者は、`task_handle`オブジェクトが作成されたの有効期間の管理を担当`task_handle`同時実行ランタイムが必要なくなるまでのオブジェクトします。 通常、これは、`task_handle`オブジェクト必要がありますいないされるまで、消滅させるため、`wait`または`run_and_wait`のメソッド、`task_group`または`structured_task_group`これがキューに入れるが呼び出されました。  
  
 `task_handle` オブジェクトは通常、C++ ラムダと組み合わせて使用されます。 、ラムダ式の実際の型がわからないため、 [make_task](concurrency-namespace-functions.md#make_task)関数が通常作成に使用する`task_handle`オブジェクト。  
  
 ランタイムに渡す処理関数のコピーを作成する、`task_handle`オブジェクト。 したがって、関数で発生した状態の変更はオブジェクトを渡すこと、`task_handle`オブジェクトは、その関数のオブジェクトのコピーには表示されません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `task_handle`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="task_handle__operator_call"></a> operator() 

 タスク ハンドルの作業を実行するために、ランタイムが呼び出す関数呼び出し演算子です。  
  
```  
void operator()() const;

 
```  
  
##  <a name="task_handle__ctor"></a> task_handle 

 新しい `task_handle` オブジェクトを構築します。 タスクの作業は、コンス トラクターにパラメーターとして指定された関数を呼び出すことによって実行されます。  
  
```  
task_handle(const _Function& _Func);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Func`  
 によって表される作業の実行に呼び出される関数、`task_handle`オブジェクト。 シグネチャを持つ関数呼び出し演算子のバージョンをサポートするオブジェクトか、関数へのポインター、ラムダ ファンクタあります`void operator()()`です。  
  
### <a name="remarks"></a>コメント  
 ランタイムでは、コンス トラクターに渡す処理関数のコピーを作成します。 したがって、関数で発生した状態の変更はオブジェクトを渡すこと、`task_handle`オブジェクトは、その関数のオブジェクトのコピーには表示されません。  
  
##  <a name="dtor"></a> ~task_handle 

 `task_handle` オブジェクトを破棄します。  
  
```  
~task_handle();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [task_group クラス](task-group-class.md)   
 [structured_task_group クラス](structured-task-group-class.md)
