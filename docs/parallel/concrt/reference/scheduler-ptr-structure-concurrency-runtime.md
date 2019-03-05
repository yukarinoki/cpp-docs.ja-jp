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
ms.openlocfilehash: 2373fe3bc8cac501d1b6b32ca66996eff47ba6f3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295046"
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

スケジューラには、生のポインターを返します。

```
scheduler_interface* get() const;
```

### <a name="return-value"></a>戻り値

##  <a name="operator_bool"></a>  scheduler_ptr::operator bool

スケジューラ ポインターが null 以外であるかどうかをテストします。

```
operator bool() const;
```

##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;

ポインターのように動作します。

```
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>戻り値

##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr コンス トラクター

Shared_ptr からスケジューラにスケジューラ ポインターを作成します。

```
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>パラメーター

*scheduler*<br/>
変換するスケジューラー。

*pScheduler*<br/>
変換するスケジューラ ポインター。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
