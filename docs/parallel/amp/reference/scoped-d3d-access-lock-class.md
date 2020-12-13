---
description: '詳細情報: scoped_d3d_access_lock クラス'
title: scoped_d3d_access_lock クラス
ms.date: 11/04/2016
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
ms.openlocfilehash: 1106673ba9ca095b33660f6a713a40ae8498d384
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329910"
---
# <a name="scoped_d3d_access_lock-class"></a>scoped_d3d_access_lock クラス

accelerator_view オブジェクトに対する D3D アクセス ロックの RAII ラッパーです。

## <a name="syntax"></a>構文

```cpp
class scoped_d3d_access_lock;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[scoped_d3d_access_lock コンストラクター](#ctor)|オーバーロードされます。 `scoped_d3d_access_lock` オブジェクトを構築します。 このオブジェクトがスコープから外れると、ロックは解放されます。|
|[~ scoped_d3d_access_lock デストラクター](#dtor)|関連付けられた `accelerator_view` オブジェクトに対する D3D アクセスのロックを解除します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator =](#operator_eq)|別の `scoped_d3d_access_lock` からロックの所有権を取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`scoped_d3d_access_lock`

## <a name="requirements"></a>要件

**ヘッダー:** amprt. h

**名前空間:** concurrency::d irect3d

## <a name="scoped_d3d_access_lock"></a><a name="ctor"></a> scoped_d3d_access_lock

`scoped_d3d_access_lock` オブジェクトを構築します。 このオブジェクトがスコープから外れると、ロックは解放されます。

```cpp
explicit scoped_d3d_access_lock(// [1] constructor
    accelerator_view& _Av);

explicit scoped_d3d_access_lock(// [2] constructor
    accelerator_view& _Av,
    adopt_d3d_access_lock_t _T);

scoped_d3d_access_lock(// [3] move constructor
    scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>パラメーター

*_Av*<br/>
導入するロックの `accelerator_view`。

*_T*<br/>
`adopt_d3d_access_lock_t` オブジェクト。

*_Other*<br/>
既存のロックの移動元の `scoped_d3d_access_lock` オブジェクト。

## <a name="construction"></a>建設

[1] コンストラクターは、指定された [accelerator_view](accelerator-view-class.md) オブジェクトに対して D3D アクセスロックを取得します。 ロックが取得されるまでの構築ブロック。

[2] コンストラクターは、指定された [accelerator_view](accelerator-view-class.md) オブジェクトから D3D アクセスロックを採用しています。

[3] 移動コンストラクターは、別のオブジェクトからの既存の D3D アクセスロックを取得 `scoped_d3d_access_lock` します。 構造体はブロックを行いません。

## <a name="scoped_d3d_access_lock"></a><a name="dtor"></a> ~ scoped_d3d_access_lock

関連付けられた `accelerator_view` オブジェクトに対する D3D アクセスのロックを解除します。

```cpp
~scoped_d3d_access_lock();
```

## <a name="operator"></a><a name="operator_eq"></a> operator =

以前のロックを解放して、別の `scoped_d3d_access_lock` オブジェクトから D3D アクセスのロックの所有権を取得します。

```cpp
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
D3D アクセスのロックの移動元である accelerator_view。

### <a name="return-value"></a>戻り値

この `scoped_accelerator_view_lock` への参照。

## <a name="see-also"></a>関連項目

[Concurrency::direct3d 名前空間](concurrency-direct3d-namespace.md)
