---
description: '詳細情報: Platform:: SizeT value クラス'
title: Platform::SizeT 値クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: ebcca27a94d23082374daafaa9fd7db180955a30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308017"
---
# <a name="platformsizet-value-class"></a>Platform::SizeT 値クラス

オブジェクトのサイズを表します。 SizeT は符号なしのデータ型です。

## <a name="syntax"></a>構文

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>メンバー

|メンバー|説明|
|------------|-----------------|
|[SizeT::SizeT コンストラクター](#ctor)|指定された値で、クラスの新しいインスタンスを初期化します。|

### <a name="requirements"></a>要件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform. winmd

## <a name="sizetsizet-constructor"></a><a name="ctor"></a> SizeT:: SizeT コンストラクター

指定された値を持つ SizeT の新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>パラメーター

*value1*<br/>
符号なし 32 ビット値。

*value2*<br/>
符号なし 32 ビット値へのポインター。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
