---
description: '詳細情報: 基準クラス'
title: norm クラス
ms.date: 11/04/2016
f1_keywords:
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
ms.openlocfilehash: 29e376e5e42212c87ae244c7a606a38d6a07ddf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327651"
---
# <a name="norm-class"></a>norm クラス

標準数値を表します。 各要素は、[-1.0 f, 1.0 f] の範囲の浮動小数点数です。

## <a name="syntax"></a>構文

```cpp
class norm;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[標準コンストラクター](#ctor)|オーバーロードされます。 既定のコンストラクターです。 を 0.0 f に初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|基準:: operator-||
|基準:: operator--||
|基準:: operator float|変換演算子。 標準数を浮動小数点値に変換します。|
|基準:: operator * =||
|基準:: operator/=||
|基準:: operator + +||
|基準:: operator + =||
|基準:: operator =||
|基準:: operator-=||

## <a name="inheritance-hierarchy"></a>継承階層

`norm`

## <a name="requirements"></a>要件

**ヘッダー:** amp_short_vectors

**名前空間:** Concurrency:: graphics

## <a name="norm"></a><a name="ctor"></a> 満た

既定のコンストラクターです。 を 0.0 f に初期化します。

```cpp
norm(
    void) restrict(amp,
    cpu);

explicit norm(
    float _V) restrict(amp,
    cpu);

explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

explicit norm(
    int _V) restrict(amp,
    cpu);

explicit norm(
    double _V) restrict(amp,
    cpu);

norm(
    const norm& _Other) restrict(amp,
    cpu);

norm(
    const unorm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>パラメーター

*_V*<br/>
の初期化に使用される値。

*_Other*<br/>
の初期化に使用されるオブジェクト。

## <a name="see-also"></a>関連項目

[Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
