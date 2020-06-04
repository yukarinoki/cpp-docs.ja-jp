---
title: scheduler_ptr構造
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 60d71a26e5dffcadfb900ef15c26a6d9dc6d6f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358770"
---
# <a name="scheduler_ptr-structure"></a>scheduler_ptr構造

スケジューラへのポインターを表します。 このクラスは、shared_ptrまたは生のポインターを使用して単純な参照を使用して共有有効期間を指定できるようにするために存在します。

## <a name="syntax"></a>構文

```cpp
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
|[scheduler_ptr::取得](#get)|スケジューラへの生のポインターを返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[scheduler_ptr::オペレーターブール](#operator_bool)|スケジューラ ポインターが null 以外であるかどうかをテストします。|
|[scheduler_ptr::演算子-&gt;](#operator_ptr)|ポインターのように動作します。|

## <a name="inheritance-hierarchy"></a>継承階層

`scheduler_ptr`

## <a name="requirements"></a>必要条件

**ヘッダー:** pplinterface.h

**名前空間:** 同時実行

## <a name="scheduler_ptrget-method"></a><a name="get"></a>scheduler_ptr::メソッドを取得

スケジューラへの生のポインターを返します。

```cpp
scheduler_interface* get() const;
```

### <a name="return-value"></a>戻り値

## <a name="scheduler_ptroperator-bool"></a><a name="operator_bool"></a>scheduler_ptr::オペレーターブール

スケジューラ ポインターが null 以外であるかどうかをテストします。

```cpp
operator bool() const;
```

## <a name="scheduler_ptroperator-gt"></a><a name="operator_ptr"></a>scheduler_ptr::演算子-&gt;

ポインタのように動作します。

```cpp
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>戻り値

## <a name="scheduler_ptrscheduler_ptr-constructor"></a><a name="ctor"></a>scheduler_ptr::scheduler_ptrコンストラクタ

スケジューラへのshared_ptrからスケジューラへのポインターを作成します。

```cpp
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>パラメーター

*スケジューラ*<br/>
変換するスケジューラ。

*スケジューラー*<br/>
変換するスケジューラ ポインター。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)
