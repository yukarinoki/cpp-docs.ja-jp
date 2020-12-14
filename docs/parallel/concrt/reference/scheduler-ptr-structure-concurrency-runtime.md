---
description: '詳細情報: scheduler_ptr 構造'
title: scheduler_ptr 構造体
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 314f587c0fd55772a8b1b7b5b8fdf3ddeb53a7a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188782"
---
# <a name="scheduler_ptr-structure"></a>scheduler_ptr 構造体

スケジューラへのポインターを表します。 このクラスは、shared_ptr を使用して共有の有効期間を指定できるようにするか、生のポインターを使用して単純な参照のみを許可するために存在します。

## <a name="syntax"></a>構文

```cpp
struct scheduler_ptr;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[scheduler_ptr:: scheduler_ptr](#ctor)|オーバーロードされます。 shared_ptr からスケジューラを指すスケジューラ ポインターを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[scheduler_ptr:: get](#get)|スケジューラへの生のポインターを返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[scheduler_ptr:: operator bool](#operator_bool)|スケジューラ ポインターが null 以外であるかどうかをテストします。|
|[scheduler_ptr:: operator-&gt;](#operator_ptr)|ポインターのように動作します。|

## <a name="inheritance-hierarchy"></a>継承階層

`scheduler_ptr`

## <a name="requirements"></a>要件

**ヘッダー:** pplinterface.h

**名前空間:** concurrency

## <a name="scheduler_ptrget-method"></a><a name="get"></a> scheduler_ptr:: get メソッド

スケジューラへの生のポインターを返します。

```cpp
scheduler_interface* get() const;
```

### <a name="return-value"></a>戻り値

## <a name="scheduler_ptroperator-bool"></a><a name="operator_bool"></a> scheduler_ptr:: operator bool

スケジューラポインターが null でないかどうかをテストします。

```cpp
operator bool() const;
```

## <a name="scheduler_ptroperator-gt"></a><a name="operator_ptr"></a> scheduler_ptr:: operator-&gt;

ポインターのように動作します。

```cpp
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>戻り値

## <a name="scheduler_ptrscheduler_ptr-constructor"></a><a name="ctor"></a> scheduler_ptr:: scheduler_ptr コンストラクター

Shared_ptr から scheduler へのスケジューラポインターを作成します。

```cpp
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>パラメーター

*組む*<br/>
変換するスケジューラ。

*pScheduler*<br/>
変換するスケジューラポインター。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
