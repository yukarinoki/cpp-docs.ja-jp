---
title: SchedulerPolicy クラス
ms.date: 11/04/2016
f1_keywords:
- SchedulerPolicy
- concrt/concurrency::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::GetPolicyValue
- concrt/concurrency::SchedulerPolicy::SetConcurrencyLimits
- concrt/concurrency::SchedulerPolicy::SetPolicyValue
helpviewer_keywords:
- SchedulerPolicy class
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
ms.openlocfilehash: 2eff40b11e4e9a5981ad85c37c8345abefb13fed
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265536"
---
# <a name="schedulerpolicy-class"></a>SchedulerPolicy クラス

`SchedulerPolicy` クラスには、ポリシー要素ごとに 1 つずつ、スケジューラ インスタンスの動作を制御するキーと値のペアのセットが含まれています。

## <a name="syntax"></a>構文

```
class SchedulerPolicy;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[SchedulerPolicy](#ctor)|オーバーロードされます。 新しいスケジューラ ポリシーを構築し、値を設定します[ポリシー キー](concurrency-namespace-enums.md)同時実行ランタイム スケジューラおよびリソース マネージャーでサポートされています。|
|[~ SchedulerPolicy デストラクター](#dtor)|スケジューラ ポリシーを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[GetPolicyValue](#getpolicyvalue)|
  `key` パラメーターとして指定されるポリシー キーの値を取得します。|
|[SetConcurrencyLimits](#setconcurrencylimits)|
  `MinConcurrency` オブジェクトに対して、`MaxConcurrency` ポリシーおよび `SchedulerPolicy` ポリシーを同時に設定します。|
|[SetPolicyValue](#setpolicyvalue)|
  `key` パラメーターとして指定されるポリシー キーの値を設定し、古い値を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator=](#operator_eq)|別のスケジューラ ポリシーからスケジューラ ポリシーを割り当てます。|

## <a name="remarks"></a>Remarks

使用して制御できるポリシーの詳細については、`SchedulerPolicy`クラスを参照してください[PolicyElementKey](concurrency-namespace-enums.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`SchedulerPolicy`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h, concrtrm.h

**名前空間:** concurrency

##  <a name="getpolicyvalue"></a> GetPolicyValue


  `key` パラメーターとして指定されるポリシー キーの値を取得します。

```
unsigned int GetPolicyValue(PolicyElementKey key) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
ポリシー キーの値を取得します。

### <a name="return-value"></a>戻り値

キーが指定されている場合、`key`パラメーターがサポートされている、キーのポリシー値をキャスト、`unsigned int`します。

### <a name="remarks"></a>Remarks

メソッドがスローされます[invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md)の無効なポリシー キー。

##  <a name="operator_eq"></a> 演算子 =

別のスケジューラ ポリシーからスケジューラ ポリシーを割り当てます。

```
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```

### <a name="parameters"></a>パラメーター

*_RhsPolicy*<br/>
このポリシーに割り当てるポリシーです。

### <a name="return-value"></a>戻り値

スケジューラ ポリシーへの参照。

### <a name="remarks"></a>Remarks

通常、新しいスケジューラ ポリシーを定義する最も簡単な方法は、既存のポリシーをコピーし、それを `SetPolicyValue` メソッドまたは `SetConcurrencyLimits` メソッドを使用して変更することです。

##  <a name="ctor"></a> SchedulerPolicy

新しいスケジューラ ポリシーを構築し、値を設定します[ポリシー キー](concurrency-namespace-enums.md)同時実行ランタイム スケジューラおよびリソース マネージャーでサポートされています。

```
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```

### <a name="parameters"></a>パラメーター

*_PolicyKeyCount*<br/>

  `_PolicyKeyCount` パラメーターの後に続くキーと値のペアの数。

*_SrcPolicy*<br/>
コピー元のポリシー。

### <a name="remarks"></a>Remarks

最初のコンストラクターでは、すべてのポリシーが既定値に初期化される新しいスケジューラ ポリシーを作成します。

2 番目のコンストラクターでは、名前付きパラメーター スタイルの初期化を使用する新しいスケジューラ ポリシーを作成します。 
  `_PolicyKeyCount` パラメーターの後の値は、キーと値のペアとして渡されます。 このコンストラクターで指定されていないポリシー キーには既定値が設定されます。 このコンス トラクターが例外をスローする[invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md)、 [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)または[invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).

3 番目のコンストラクターはコピー コンストラクターです。 通常、新しいスケジューラ ポリシーを定義する最も簡単な方法は、既存のポリシーをコピーし、それを `SetPolicyValue` メソッドまたは `SetConcurrencyLimits` メソッドを使用して変更することです。

##  <a name="dtor"></a> ~ SchedulerPolicy

スケジューラ ポリシーを破棄します。

```
~SchedulerPolicy();
```

##  <a name="setconcurrencylimits"></a> SetConcurrencyLimits


  `MinConcurrency` オブジェクトに対して、`MaxConcurrency` ポリシーおよび `SchedulerPolicy` ポリシーを同時に設定します。

```
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```

### <a name="parameters"></a>パラメーター

*_MinConcurrency*<br/>
値、`MinConcurrency`ポリシー キー。

*_MaxConcurrency*<br/>
値、`MaxConcurrency`ポリシー キー。

### <a name="remarks"></a>Remarks

メソッドがスローされます[invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md)の値が指定されている場合、`MinConcurrency`ポリシーが指定されているより大きい、`MaxConcurrency`ポリシー。

メソッドもスロー [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)に他の無効な値。

##  <a name="setpolicyvalue"></a> SetPolicyValue


  `key` パラメーターとして指定されるポリシー キーの値を設定し、古い値を返します。

```
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
値を設定するポリシーのキー。

*value*<br/>
ポリシー キーに設定する値。

### <a name="return-value"></a>戻り値

キーが指定されている場合、`key`パラメーターがサポートされている、キーの古いポリシー値をキャスト、`unsigned int`します。

### <a name="remarks"></a>Remarks

メソッドがスローされます[invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) 、無効なポリシー キーまたは任意のポリシー キーで値を設定することはできません、`SetPolicyValue`メソッド。

メソッドがスローされます[invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)で指定されたキーのサポートされていない値に対して、`key`パラメーター。

このメソッドは、設定することはできません注、`MinConcurrency`または`MaxConcurrency`ポリシー。 これらの値を設定するには、使用、 [SetConcurrencyLimits](#setconcurrencylimits)メソッド。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[CurrentScheduler クラス](currentscheduler-class.md)<br/>
[Scheduler クラス](scheduler-class.md)<br/>
[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
