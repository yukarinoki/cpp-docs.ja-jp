---
title: scoped_d3d_access_lock クラス
ms.date: 11/04/2016
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
ms.openlocfilehash: e36c3c2cfa9d1b617e377a7e340f98875457bdf1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272465"
---
# <a name="scopedd3daccesslock-class"></a>scoped_d3d_access_lock クラス

accelerator_view オブジェクトに対する D3D アクセス ロックの RAII ラッパーです。

### <a name="syntax"></a>構文

```
class scoped_d3d_access_lock;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[scoped_d3d_access_lock コンス トラクター](#ctor)|オーバーロードされます。 `scoped_d3d_access_lock` オブジェクトを構築します。 このオブジェクトがスコープから外れると、ロックは解放されます。|
|[~ scoped_d3d_access_lock デストラクター](#dtor)|関連付けられた `accelerator_view` オブジェクトに対する D3D アクセスのロックを解除します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator=](#operator_eq)|別の `scoped_d3d_access_lock` からロックの所有権を取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`scoped_d3d_access_lock`

## <a name="requirements"></a>必要条件

**ヘッダー:** amprt.h

**Namespace:** concurrency::direct3d

##  <a name="ctor"></a> scoped_d3d_access_lock

`scoped_d3d_access_lock` オブジェクトを構築します。 このオブジェクトがスコープから外れると、ロックは解放されます。

```
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

## <a name="construction"></a>構築

[1] コンス トラクターの D3D アクセスのロックを取得する、指定された[accelerator_view](accelerator-view-class.md)オブジェクト。 ロックが取得されるまでの構築ブロック。

[2] のコンス トラクターから D3D アクセスのロックを採用する、指定された[accelerator_view](accelerator-view-class.md)オブジェクト。

[3] 移動コンス トラクターは、別の既存の D3D アクセス ロック`scoped_d3d_access_lock`オブジェクト。 構造体はブロックを行いません。

##  <a name="dtor"></a> ~scoped_d3d_access_lock

関連付けられた `accelerator_view` オブジェクトに対する D3D アクセスのロックを解除します。

```
~scoped_d3d_access_lock();
```

## <a name="operator_eq"></a> 演算子 =

以前のロックを解放して、別の `scoped_d3d_access_lock` オブジェクトから D3D アクセスのロックの所有権を取得します。

```
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
D3D アクセスのロックの移動元である accelerator_view。

### <a name="return-value"></a>戻り値

この `scoped_accelerator_view_lock` への参照。

## <a name="see-also"></a>関連項目

[Concurrency::direct3d 名前空間](concurrency-direct3d-namespace.md)
