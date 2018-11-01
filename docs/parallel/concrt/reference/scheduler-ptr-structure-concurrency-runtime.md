---
title: scheduler_ptr 構造体
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 7fd81a1ccf6702c74a013c5772d59f01121b61a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479223"
---
# <a name="schedulerptr-structure"></a>scheduler_ptr 構造体

スケジューラへのポインターを表します。 このクラスは、生のポインターを使用して、shared_ptr またはプレーンな参照だけを使用して共有有効期間の指定を許可する存在します。

## <a name="syntax"></a>構文

```
struct scheduler_ptr;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[scheduler_ptr::scheduler_ptr](#ctor)|オーバーロードされます。 shared_ptr からスケジューラを指すスケジューラ ポインターを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[scheduler_ptr::get](#get)|スケジューラへの生のポインターを返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[scheduler_ptr::operator bool](#operator_bool)|スケジューラ ポインターが null 以外であるかどうかをテストします。|
|[scheduler_ptr::operator-&gt;](#operator_ptr)|ポインターのように動作します。|

## <a name="inheritance-hierarchy"></a>継承階層

`scheduler_ptr`

## <a name="requirements"></a>必要条件

**ヘッダー:** pplinterface.h

**名前空間:** concurrency

##  <a name="get"></a>  scheduler_ptr::get メソッド

スケジューラへの生のポインターを返します。

```
scheduler_interface* get() const;
```

### <a name="return-value"></a>戻り値

##  <a name="operator_bool"></a>  scheduler_ptr::operator bool

スケジューラ ポインターが null 以外であるかどうかをテストします。

```operator bool() const;
```

##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;

Behave like a pointer

```
scheduler_interface * 演算子は const; () を -> します。
```

### Return Value

##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor

Creates a scheduler pointer from shared_ptr to scheduler

```
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);

明示的な scheduler_ptr (_In_opt_ scheduler_interface * pScheduler)。
```

### Parameters

*scheduler*<br/>
The scheduler to convert.

*pScheduler*<br/>
The scheduler pointer to convert.

## See Also

[concurrency Namespace](concurrency-namespace.md)
