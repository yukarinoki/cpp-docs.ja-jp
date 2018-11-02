---
title: ModuleBase クラス
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::~ModuleBase
helpviewer_keywords:
- ModuleBase class
- Microsoft::WRL::Details::ModuleBase::DecrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::IncrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::ModuleBase, constructor
- Microsoft::WRL::Details::ModuleBase::~ModuleBase, destructor
ms.assetid: edce7591-6893-46f7-94a7-382827775548
ms.openlocfilehash: 4a65b7335626cc36a4eecbe61465778889a9e7e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502129"
---
# <a name="modulebase-class"></a>ModuleBase クラス

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Remarks

基本クラスを表します、[モジュール](../windows/module-class.md)クラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                         | 説明
-------------------------------------------- | ---------------------------------------------------------
[Modulebase::modulebase](#modulebase)        | `Module` クラスのインスタンスを初期化します。
[ModuleBase:: ~ ModuleBase](#tilde-modulebase) | 現在のインスタンスの初期化を解除、`Module`クラス。

### <a name="public-methods"></a>パブリック メソッド

名前                                                      | 説明
--------------------------------------------------------- | -------------------------------------------------------------------------
[Modulebase::decrementobjectcount](#decrementobjectcount) | 実装された場合、デクリメント オブジェクトの数によって追跡モジュール。
[Modulebase::incrementobjectcount](#incrementobjectcount) | 実装された場合、モジュールによって追跡されるオブジェクトの数をインクリメントします。

## <a name="inheritance-hierarchy"></a>継承階層

`ModuleBase`

## <a name="requirements"></a>必要条件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="tilde-modulebase"></a>ModuleBase:: ~ ModuleBase

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>Remarks

現在のインスタンスの初期化を解除、`ModuleBase`クラス。

## <a name="decrementobjectcount"></a>Modulebase::decrementobjectcount

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>戻り値

デクリメント操作の前にカウントします。

### <a name="remarks"></a>Remarks

実装された場合、デクリメント オブジェクトの数によって追跡モジュール。

## <a name="incrementobjectcount"></a>Modulebase::incrementobjectcount

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>戻り値

インクリメント操作の前にカウントします。

### <a name="remarks"></a>Remarks

実装された場合、モジュールによって追跡されるオブジェクトの数をインクリメントします。

## <a name="modulebase"></a>Modulebase::modulebase

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
ModuleBase();
```

### <a name="remarks"></a>Remarks

`Module` クラスのインスタンスを初期化します。
