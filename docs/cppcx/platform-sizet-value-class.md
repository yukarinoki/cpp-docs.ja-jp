---
title: Platform::SizeT 値クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: 02fe62165ce40d267f156eaeb3ad93f636c9ab73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604218"
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

### <a name="requirements"></a>必要条件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="ctor"></a>  Sizet::sizet コンス トラクター

指定された値を持つ SizeT の新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>パラメーター

*Value1*<br/>
符号なし 32 ビット値。

*Value2*<br/>
符号なし 32 ビット値へのポインター。

## <a name="see-also"></a>関連項目

[Platform 名前空間](../cppcx/platform-namespace-c-cx.md)