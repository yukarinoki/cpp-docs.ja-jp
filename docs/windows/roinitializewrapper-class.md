---
title: RoInitializeWrapper クラス |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3dd1b5df8749f22873a52782b6f528760c3823a1
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788762"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper クラス

Windows ランタイムを初期化します。

## <a name="syntax"></a>構文

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>Remarks

`RoInitializeWrapper` Windows ランタイムを初期化し、操作が成功したかどうかを示す HRESULT を返す便利です。 クラスのデストラクターを呼び出すため、 `::Windows::Foundation::Uninitialize`、インスタンスの`RoInitializeWrapper`グローバルまたは最上位のスコープで宣言する必要があります。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                    | 説明
----------------------------------------------------------------------- | -----------------------------------------------------------------
[Roinitializewrapper::roinitializewrapper](#roinitializewrapper)        | `RoInitializeWrapper` クラスの新しいインスタンスを初期化します。
[RoInitializeWrapper:: ~ RoInitializeWrapper](#tilde-roinitializewrapper) | 現在のインスタンスを破棄、`RoInitializeWrapper`クラス。

### <a name="public-operators"></a>パブリック演算子

名前                                       | 説明
------------------------------------------ | ------------------------------------------------------------------------
[Roinitializewrapper::hresult()](#hresult) | によって生成された HRESULT を取得、`RoInitializeWrapper`コンス トラクター。

## <a name="inheritance-hierarchy"></a>継承階層

`RoInitializeWrapper`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="hresult"></a>Roinitializewrapper::hresult()

最後のによって生成された HRESULT 値を取得します`RoInitializeWrapper`コンス トラクター。

```cpp
operator HRESULT()  
```

## <a name="roinitializewrapper"></a>Roinitializewrapper::roinitializewrapper

`RoInitializeWrapper` クラスの新しいインスタンスを初期化します。

```cpp
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```

### <a name="parameters"></a>パラメーター

*flags*<br/>
RO_INIT_TYPE の列挙体は、Windows ランタイムによって提供されるサポートの 1 つ。

### <a name="remarks"></a>Remarks

`RoInitializeWrapper`クラスを呼び出す`Windows::Foundation::Initialize(flags)`します。

## <a name="tilde-roinitializewrapper"></a>RoInitializeWrapper:: ~ RoInitializeWrapper

Windows ランタイムの初期化を解除します。

```cpp
~RoInitializeWrapper()  
```

### <a name="remarks"></a>Remarks

`RoInitializeWrapper`クラスを呼び出す`Windows::Foundation::Uninitialize()`します。
