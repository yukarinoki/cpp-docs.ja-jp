---
title: Platform::SizeT 値クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: 5add9212dc2655bc37cd357741073f855b009bde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322159"
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

**サポートされる最小クライアント:** ウィンドウズ 8

**サポートされる最小サーバー:** ウィンドウズ サーバー 2012

**名前空間:** Platform

**メタデータ:** プラットフォーム.winmd

## <a name="sizetsizet-constructor"></a><a name="ctor"></a>サイズ::サイズTコンストラクタ

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
