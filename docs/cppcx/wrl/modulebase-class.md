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
ms.openlocfilehash: 13a8ceef3133e9946524e1fcd02e96535eccd7fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371271"
---
# <a name="modulebase-class"></a>ModuleBase クラス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
class ModuleBase;
```

## <a name="remarks"></a>解説

[Module](module-class.md)クラスの基本クラスを表します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                         | 説明
-------------------------------------------- | ---------------------------------------------------------
[モジュールベース::モジュールベース](#modulebase)        | `Module` クラスのインスタンスを初期化します。
[モジュールベース:~モジュールベース](#tilde-modulebase) | クラスの現在のインスタンスを初期化解除`Module`します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                      | 説明
--------------------------------------------------------- | -------------------------------------------------------------------------
[:Dオブジェクト数](#decrementobjectcount) | 実装されると、モジュールによって追跡されるオブジェクトの数が減ります。
[オブジェクト数を増やす](#incrementobjectcount) | 実装されると、モジュールによって追跡されるオブジェクトの数が増加します。

## <a name="inheritance-hierarchy"></a>継承階層

`ModuleBase`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="modulebasemodulebase"></a><a name="tilde-modulebase"></a>モジュールベース:~モジュールベース

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>解説

クラスの現在のインスタンスを初期化解除`ModuleBase`します。

## <a name="modulebasedecrementobjectcount"></a><a name="decrementobjectcount"></a>:Dオブジェクト数

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>戻り値

減分演算の前のカウント。

### <a name="remarks"></a>解説

実装されると、モジュールによって追跡されるオブジェクトの数が減ります。

## <a name="modulebaseincrementobjectcount"></a><a name="incrementobjectcount"></a>オブジェクト数を増やす

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>戻り値

インクリメント操作の前のカウント。

### <a name="remarks"></a>解説

実装されると、モジュールによって追跡されるオブジェクトの数が増加します。

## <a name="modulebasemodulebase"></a><a name="modulebase"></a>モジュールベース::モジュールベース

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
ModuleBase();
```

### <a name="remarks"></a>解説

`Module` クラスのインスタンスを初期化します。
