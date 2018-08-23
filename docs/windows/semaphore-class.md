---
title: クラスのセマフォ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore class
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb0b3d5dff91bcb1fb1688c7b1a9314fe7ebf00c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598416"
---
# <a name="semaphore-class"></a>Semaphore クラス

ユーザーの数に制限をサポートできる共有リソースを制御する同期オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`SyncLock`|同期ロックをサポートするクラスのシノニムです。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Semaphore::Semaphore コンストラクター](../windows/semaphore-semaphore-constructor.md)|新しいインスタンスを初期化、**セマフォ**クラス。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[InvokeHelper::Invoke メソッド](../windows/invokehelper-invoke-method.md)|指定した数の引数を含むシグネチャを持つイベント ハンドラーを呼び出します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[Semaphore::Lock メソッド](../windows/semaphore-lock-method.md)|シグナルの状態にある現在のオブジェクトまたは指定したハンドルに関連付けられたオブジェクトまでの待機、または指定されたタイムアウト期間が経過しました。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Semaphore::operator= 演算子](../windows/semaphore-operator-assign-operator.md)|指定したハンドルの移動、**セマフォ**現在オブジェクト**セマフォ**オブジェクト。|

## <a name="inheritance-hierarchy"></a>継承階層

`Semaphore`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)