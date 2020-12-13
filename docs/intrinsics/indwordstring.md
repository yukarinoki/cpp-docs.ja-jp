---
description: '詳細については、次を参照してください: __indwordstring'
title: __indwordstring
ms.date: 09/02/2019
f1_keywords:
- __indwordstring
- __indwordstring_cpp
helpviewer_keywords:
- __indwordstring intrinsic
- rep insd instruction
ms.assetid: 96a1cf33-f691-4916-99e4-fa849b61e3a9
ms.openlocfilehash: 18d18a8981a2dd58c0f7bcd366faaf46629647c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336914"
---
# <a name="__indwordstring"></a>__indwordstring

**Microsoft 固有の仕様**

命令を使用して、指定されたポートからデータを読み取り `rep insd` ます。

## <a name="syntax"></a>構文

```C
void __indwordstring(
   unsigned short Port,
   unsigned long* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>パラメーター

*ポート*\
から読み取り元のポート。

*格納*\
入出力このポートから読み取られたデータがここに書き込まれます。

*数*\
から読み取るデータのバイト数。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__indwordstring`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
