---
description: '詳細については、次を参照してください: __readpmc'
title: __readpmc
ms.date: 09/02/2019
f1_keywords:
- __readpmc
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
ms.openlocfilehash: ceff8522d4895f69a47cf429e59d267c671e3a66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294133"
---
# <a name="__readpmc"></a>__readpmc

**Microsoft 固有の仕様**

`rdpmc`*カウンター* によって指定されたパフォーマンス監視カウンターを読み取る命令を生成します。

## <a name="syntax"></a>構文

```C
unsigned __int64 __readpmc(
   unsigned long counter
);
```

### <a name="parameters"></a>パラメーター

*対抗*\
から読み取るパフォーマンスカウンター。

## <a name="return-value"></a>戻り値

指定したパフォーマンスカウンターの値。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__readpmc`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

組み込みはカーネルモードでのみ使用でき、ルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
