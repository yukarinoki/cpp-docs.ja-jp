---
description: '詳細については、次を参照してください: __inbyte'
title: __inbyte
ms.date: 09/02/2019
f1_keywords:
- __inbyte
- __inbyte_cpp
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
ms.openlocfilehash: 77cc1cfb792ffa2f6aef9879820e644372895193
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337024"
---
# <a name="__inbyte"></a>__inbyte

**Microsoft 固有の仕様**

命令を生成し `in` 、によって指定されたポートから読み取った1バイトを返し `Port` ます。

## <a name="syntax"></a>構文

```C
unsigned char __inbyte(
   unsigned short Port
);
```

### <a name="parameters"></a>パラメーター

*ポート*\
から読み取り元のポート。

## <a name="return-value"></a>戻り値

指定したポートから読み取ったバイト。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__inbyte`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="remarks"></a>解説

このルーチンは、組み込みとしてのみ使用できます。

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
