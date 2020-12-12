---
description: '詳細については、次を参照してください: __writecr4'
title: __writecr4
ms.date: 09/02/2019
f1_keywords:
- _writecr4
helpviewer_keywords:
- _writecr4 intrinsic
ms.assetid: ab7651d7-b86b-4be7-a0a0-7263099c70fc
ms.openlocfilehash: 711a6dff42f3805886865d09b4638479173bc64e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313087"
---
# <a name="__writecr4"></a>__writecr4

**Microsoft 固有の仕様**

値を `Data` CR4 register に書き込みます。

## <a name="syntax"></a>構文

```C
void writecr4(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>パラメーター

*データ*\
からCR4 register に書き込む値。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__writecr4`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

この組み込みはカーネル モードのみで使用でき、そのルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
