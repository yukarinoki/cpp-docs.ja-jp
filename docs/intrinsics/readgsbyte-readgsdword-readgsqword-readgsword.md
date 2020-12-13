---
description: '詳細については、次を参照してください: __readgsbyte、__readgsdword、__readgsqword、__readgsword'
title: __readgsbyte、__readgsdword、__readgsqword、__readgsword
ms.date: 09/02/2019
f1_keywords:
- __readgsbyte
- __readgsdword
- __readgsqword
- __readgsword
helpviewer_keywords:
- __readgsword intrinsic
- __readgsdword intrinsic
- __readgsqword intrinsic
- __readgsbyte intrinsic
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
ms.openlocfilehash: fb1faf0e785f0d0983d7d3611e68a7515298e61c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340971"
---
# <a name="__readgsbyte-__readgsdword-__readgsqword-__readgsword"></a>__readgsbyte、__readgsdword、__readgsqword、__readgsword

**Microsoft 固有の仕様**

GS セグメントの先頭を基準としたオフセットによって指定された場所からメモリを読み取ります。

## <a name="syntax"></a>構文

```C
unsigned char __readgsbyte(
   unsigned long Offset
);
unsigned short __readgsword(
   unsigned long Offset
);
unsigned long __readgsdword(
   unsigned long Offset
);
unsigned __int64 __readgsqword(
   unsigned long Offset
);
```

### <a name="parameters"></a>パラメーター

*影*\
からの先頭から `GS` 読み取るオフセット。

## <a name="return-value"></a>戻り値

位置にある byte、word、double word、または quadword のメモリの内容 (呼び出される関数の名前で示されます) `GS:[Offset]` 。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__readgsbyte`|X64|
|`__readgsdword`|X64|
|`__readgsqword`|X64|
|`__readgsword`|X64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

これらのルーチンは、組み込み関数としてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__writegsbyte、 \_ _writegsdword、 \_ _writegsqword、 \_ _writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
