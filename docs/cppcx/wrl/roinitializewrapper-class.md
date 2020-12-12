---
description: '詳細情報: RoInitializeWrapper クラス'
title: RoInitializeWrapper クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
ms.openlocfilehash: b7f2c49bd461f08ad732680f1a02968ee7717116
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319301"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper クラス

Windows ランタイムを初期化します。

## <a name="syntax"></a>構文

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>解説

`RoInitializeWrapper` は、Windows ランタイムを初期化し、操作が成功したかどうかを示す HRESULT を返す便宜的な方法です。 クラスデストラクターはを呼び出すため `::Windows::Foundation::Uninitialize` 、のインスタンス `RoInitializeWrapper` はグローバルまたは最上位のスコープで宣言する必要があります。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                    | 説明
----------------------------------------------------------------------- | -----------------------------------------------------------------
[RoInitializeWrapper:: RoInitializeWrapper](#roinitializewrapper)        | `RoInitializeWrapper` クラスの新しいインスタンスを初期化します。
[RoInitializeWrapper:: ~ RoInitializeWrapper](#tilde-roinitializewrapper) | クラスの現在のインスタンスを破棄 `RoInitializeWrapper` します。

### <a name="public-operators"></a>パブリック演算子

名前                                       | 説明
------------------------------------------ | ------------------------------------------------------------------------
[RoInitializeWrapper:: HRESULT ()](#hresult) | コンストラクターによって生成された HRESULT を取得し `RoInitializeWrapper` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`RoInitializeWrapper`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="roinitializewrapperhresult"></a><a name="hresult"></a> RoInitializeWrapper:: HRESULT ()

最後のコンストラクターによって生成された HRESULT 値を取得し `RoInitializeWrapper` ます。

```cpp
operator HRESULT()
```

## <a name="roinitializewrapperroinitializewrapper"></a><a name="roinitializewrapper"></a> RoInitializeWrapper:: RoInitializeWrapper

`RoInitializeWrapper` クラスの新しいインスタンスを初期化します。

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>パラメーター

*flags*<br/>
Windows ランタイムによって提供されるサポートを指定する RO_INIT_TYPE 列挙型の1つ。

### <a name="remarks"></a>解説

クラスはを `RoInitializeWrapper` 呼び出し `Windows::Foundation::Initialize(flags)` ます。

## <a name="roinitializewrapperroinitializewrapper"></a><a name="tilde-roinitializewrapper"></a> RoInitializeWrapper:: ~ RoInitializeWrapper

Windows ランタイムを初期化前します。

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>解説

クラスはを `RoInitializeWrapper` 呼び出し `Windows::Foundation::Uninitialize()` ます。
