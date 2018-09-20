---
title: unorm クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
dev_langs:
- C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 131a928c5943ab9bf4dcc327b044d76e5646ede7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377384"
---
# <a name="unorm-class"></a>unorm クラス

Unorm 数を表します。 各要素は、浮動小数点 [0.0 f, 1.0f] の範囲の数。

## <a name="syntax"></a>構文

```
class unorm;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[unorm コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター 0.0f を初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|unorm::operator--||
|unorm::operator float|変換演算子。 Unorm 数値に変換する浮動小数点値。|
|unorm::operator * =||
|unorm::operator/=||
|unorm::operator +||
|unorm::operator+=||
|unorm::operator=||
|unorm::operator-=||

## <a name="inheritance-hierarchy"></a>継承階層

`unorm`

## <a name="requirements"></a>要件

**ヘッダー:** amp_short_vectors.h

**Namespace:** concurrency::graphics

##  <a name="ctor"></a> unorm

既定のコンストラクター 0.0f を初期化します。

```
unorm(
    void) restrict(amp,
    cpu);

explicit unorm(
    float _V) restrict(amp,
    cpu);

explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

explicit unorm(
    int _V) restrict(amp,
    cpu);

explicit unorm(
    double _V) restrict(amp,
    cpu);

unorm(
    const unorm& _Other) restrict(amp,
    cpu);

inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>パラメーター

*(_V).*<br/>
初期化するために使用される値。

*_Other*<br/>
初期化するために使用される norm オブジェクト。

## <a name="see-also"></a>関連項目

[Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
