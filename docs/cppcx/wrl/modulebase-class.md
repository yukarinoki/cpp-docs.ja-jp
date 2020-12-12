---
description: '詳細情報: ModuleBase クラス'
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
ms.openlocfilehash: 6540068cee62da5d1a9039a15bcb5bd53ff3aea2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186247"
---
# <a name="modulebase-class"></a>ModuleBase クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
class ModuleBase;
```

## <a name="remarks"></a>解説

[モジュール](module-class.md)クラスの基本クラスを表します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                         | 説明
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase:: ModuleBase](#modulebase)        | `Module` クラスのインスタンスを初期化します。
[ModuleBase:: ~ ModuleBase](#tilde-modulebase) | クラスの現在のインスタンスを初期化解除 `Module` します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                      | 説明
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase::D ecrementObjectCount](#decrementobjectcount) | 実装された場合、モジュールによって追跡されるオブジェクトの数をデクリメントします。
[ModuleBase:: IncrementObjectCount](#incrementobjectcount) | 実装された場合、モジュールによって追跡されるオブジェクトの数を増やします。

## <a name="inheritance-hierarchy"></a>継承階層

`ModuleBase`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="modulebasemodulebase"></a><a name="tilde-modulebase"></a> ModuleBase:: ~ ModuleBase

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>解説

クラスの現在のインスタンスを初期化解除 `ModuleBase` します。

## <a name="modulebasedecrementobjectcount"></a><a name="decrementobjectcount"></a> ModuleBase::D ecrementObjectCount

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>戻り値

デクリメント操作の前のカウント。

### <a name="remarks"></a>解説

実装された場合、モジュールによって追跡されるオブジェクトの数をデクリメントします。

## <a name="modulebaseincrementobjectcount"></a><a name="incrementobjectcount"></a> ModuleBase:: IncrementObjectCount

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>戻り値

インクリメント操作の前のカウント。

### <a name="remarks"></a>解説

実装された場合、モジュールによって追跡されるオブジェクトの数を増やします。

## <a name="modulebasemodulebase"></a><a name="modulebase"></a> ModuleBase:: ModuleBase

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
ModuleBase();
```

### <a name="remarks"></a>解説

`Module` クラスのインスタンスを初期化します。
