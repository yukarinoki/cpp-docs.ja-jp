---
description: 詳細については、「__incfsbyte、__incfsword、__incfsdword」を参照してください。
title: __incfsbyte、__incfsword、__incfsdword
ms.date: 09/02/2019
f1_keywords:
- __incfsword
- __incfsbyte_cpp
- __incfsbyte
- __incfsdword
- __incfsword_cpp
- __incfsdword_cpp
helpviewer_keywords:
- __incfsword intrinsic
- __incfsdword intrinsic
- __incfsbyte intrinsic
ms.assetid: 820457fb-e35e-42d3-bcb6-725da3281c64
ms.openlocfilehash: 29d86de51ad282789cb19b72ca953f65af2dc19d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336960"
---
# <a name="__incfsbyte-__incfsword-__incfsdword"></a>__incfsbyte、__incfsword、__incfsdword

**Microsoft 固有の仕様**

セグメントの先頭を基準としたオフセットによって指定されたメモリ位置の値に1つを追加し `FS` ます。

## <a name="syntax"></a>構文

```C
void __incfsbyte(
   unsigned long Offset
);
void __incfsword(
   unsigned long Offset
);
void __incfsdword(
   unsigned long Offset
);
```

### <a name="parameters"></a>パラメーター

*影*\
からの先頭からのオフセット `FS` 。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__incfsbyte`|x86|
|`__incfsword`|x86|
|`__incfsdword`|x86|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

これらの組み込みはカーネルモードでのみ使用でき、ルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[\__addfsbyte、 \_ _addfsword、 \_ _addfsdword](../intrinsics/addfsbyte-addfsword-addfsdword.md)\
[\__readfsbyte、 \_ _readfsdword、 \_ _readfsqword、 \_ _readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)\
[\__writefsbyte、 \_ _writefsdword、 \_ _writefsqword、 \_ _writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
