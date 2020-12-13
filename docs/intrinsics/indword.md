---
description: '詳細については、次を参照してください: __indword'
title: __indword
ms.date: 09/02/2019
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __indword intrinsic
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
ms.openlocfilehash: bd637027ee930b551f08508874554e2b19f22461
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336927"
---
# <a name="__indword"></a>__indword

**Microsoft 固有の仕様**

命令を使用して、指定したポートから1つのデータを読み取り `in` ます。

## <a name="syntax"></a>構文

```C
unsigned long __indword(
   unsigned short Port
);
```

### <a name="parameters"></a>パラメーター

*ポート*\
から読み取り元のポート。

## <a name="return-value"></a>戻り値

ポートから読み取られた単語。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__indword`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
