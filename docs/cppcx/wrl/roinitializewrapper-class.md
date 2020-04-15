---
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
ms.openlocfilehash: eba9162f17b98d13a9caf956b4f110b89dd81c37
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371229"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper クラス

Windows ランタイムを初期化します。

## <a name="syntax"></a>構文

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>解説

`RoInitializeWrapper`は、Windows ランタイムを初期化し、操作が成功したかどうかを示す HRESULT を返す便利な方法です。 クラスデストラクターは を`::Windows::Foundation::Uninitialize`呼び出す`RoInitializeWrapper`ため、 のインスタンスは、グローバルスコープまたは最上位のスコープで宣言する必要があります。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                    | 説明
----------------------------------------------------------------------- | -----------------------------------------------------------------
[ロ初期化ラッパー::ロ初期化ラッパー](#roinitializewrapper)        | `RoInitializeWrapper` クラスの新しいインスタンスを初期化します。
[ロ初期化ラッパー::~ロ初期化ラッパー](#tilde-roinitializewrapper) | クラスの現在のインスタンスを破棄`RoInitializeWrapper`します。

### <a name="public-operators"></a>パブリック演算子

名前                                       | 説明
------------------------------------------ | ------------------------------------------------------------------------
[ラ初期化ラッパー::HRESULT()](#hresult) | コンストラクターによって生成された HRESULT`RoInitializeWrapper`を取得します。

## <a name="inheritance-hierarchy"></a>継承階層

`RoInitializeWrapper`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー

## <a name="roinitializewrapperhresult"></a><a name="hresult"></a>ラ初期化ラッパー::HRESULT()

最後`RoInitializeWrapper`のコンストラクターによって生成された HRESULT 値を取得します。

```cpp
operator HRESULT()
```

## <a name="roinitializewrapperroinitializewrapper"></a><a name="roinitializewrapper"></a>ロ初期化ラッパー::ロ初期化ラッパー

`RoInitializeWrapper` クラスの新しいインスタンスを初期化します。

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
Windows ランタイムによって提供されるサポートを指定する、RO_INIT_TYPE列挙の 1 つ。

### <a name="remarks"></a>解説

クラス`RoInitializeWrapper`が を`Windows::Foundation::Initialize(flags)`呼び出します。

## <a name="roinitializewrapperroinitializewrapper"></a><a name="tilde-roinitializewrapper"></a>ロ初期化ラッパー::~ロ初期化ラッパー

Windows ランタイムの初期化を解除します。

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>解説

クラス`RoInitializeWrapper`が を`Windows::Foundation::Uninitialize()`呼び出します。
