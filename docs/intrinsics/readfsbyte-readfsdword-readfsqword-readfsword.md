---
description: '詳細については、次を参照してください: __readfsbyte、__readfsdword、__readfsqword、__readfsword'
title: __readfsbyte、__readfsdword、__readfsqword、__readfsword
ms.date: 09/02/2019
f1_keywords:
- __readfsword
- __readfsdword
- __readfsbyte
- __readfsqword
helpviewer_keywords:
- __readfsword intrinsic
- readfsword intrinsic
- __readfsdword intrinsic
- readfsbyte intrinsic
- __readfsbyte intrinsic
- readfsdword intrinsic
- readfsqword intrinsic
- __readfsqword intrinsic
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
ms.openlocfilehash: 2b733ced12045253c78e823379c10a5e70f65143
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340984"
---
# <a name="__readfsbyte-__readfsdword-__readfsqword-__readfsword"></a>__readfsbyte、__readfsdword、__readfsqword、__readfsword

**Microsoft 固有の仕様**

オフセットによって指定された場所から、FS セグメントの先頭を基準とするメモリを読み取ります。

## <a name="syntax"></a>構文

```C
unsigned char __readfsbyte(
   unsigned long Offset
);
unsigned short __readfsword(
   unsigned long Offset
);
unsigned long __readfsdword(
   unsigned long Offset
);
unsigned __int64 __readfsqword(
   unsigned long Offset
);
```

### <a name="parameters"></a>パラメーター

*影*\
からの先頭から `FS` 読み取るオフセット。

## <a name="return-value"></a>戻り値

バイト、ワード、ダブルワード、または quadword のメモリの内容 (呼び出された関数の名前によって示され `FS:[Offset]` ます)。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__readfsbyte`|x86|
|`__readfsdword`|x86|
|`__readfsqword`|x86|
|`__readfsword`|x86|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

これらのルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__writefsbyte、 \_ _writefsdword、 \_ _writefsqword、 \_ _writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
