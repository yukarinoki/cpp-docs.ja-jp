---
description: '詳細については、次を参照してください: __writegsbyte、__writegsdword、__writegsqword、__writegsword'
title: __writegsbyte、__writegsdword、__writegsqword、__writegsword
ms.date: 09/02/2019
f1_keywords:
- __writegsbyte
- __writegsqword
- __writegsdword
- __writegsword
helpviewer_keywords:
- __writegsqword intrinsic
- __writegsbyte intrinsic
- __writegsword intrinsic
- __writegsdword intrinsic
ms.assetid: 7746cf6d-2259-4139-9aab-c07dd75c8037
ms.openlocfilehash: e3dd3284d38f4c1518fbf5f7184d15fc0c9d67d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331833"
---
# <a name="__writegsbyte-__writegsdword-__writegsqword-__writegsword"></a>__writegsbyte、__writegsdword、__writegsqword、__writegsword

**Microsoft 固有の仕様**

GS セグメントの先頭を基準としたオフセットによって指定された位置にメモリを書き込みます。

## <a name="syntax"></a>構文

```C
void __writegsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __writegsword(
   unsigned long Offset,
   unsigned short Data
);
void __writegsdword(
   unsigned long Offset,
   unsigned long Data
);
void __writegsqword(
   unsigned long Offset,
   unsigned __int64 Data
);
```

### <a name="parameters"></a>パラメーター

*影*\
から書き込み先の GS の先頭からのオフセット。

*データ*\
から書き込む値。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__writegsbyte`|X64|
|`__writegsdword`|X64|
|`__writegsqword`|X64|
|`__writegsword`|X64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

これらのルーチンは、組み込み関数としてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__readgsbyte、 \_ _readgsdword、 \_ _readgsqword、 \_ _readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
