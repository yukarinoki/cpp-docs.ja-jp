---
description: '詳細については、次を参照してください: __incgsbyte、__incgsword、__incgsdword、__incgsqword'
title: __incgsbyte、__incgsword、__incgsdword、__incgsqword
ms.date: 09/02/2019
f1_keywords:
- __incgsdword
- __incgsqword_cpp
- __incgsword_cpp
- __incgsword
- __incgsbyte
- __incgsbyte_cpp
- __incgsqword
- __incgsdword_cpp
helpviewer_keywords:
- __incgsbyte intrinsic
- __incgsword intrinsic
- __incgsqword intrinsic
- __incgsdword intrinsic
ms.assetid: 06bfdf4f-7643-4fe0-8455-60ce3068073e
ms.openlocfilehash: a19c266c936875765c5681a47845be1a53f18c83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336934"
---
# <a name="__incgsbyte-__incgsword-__incgsdword-__incgsqword"></a>__incgsbyte、__incgsword、__incgsdword、__incgsqword

**Microsoft 固有の仕様**

セグメントの先頭を基準としたオフセットによって指定されたメモリ位置の値に1つを追加し `GS` ます。

## <a name="syntax"></a>構文

```C
void __incgsbyte(
   unsigned long Offset
);
void __incgsword(
   unsigned long Offset
);
void __incgsdword(
   unsigned long Offset
);
void __incgsqword(
   unsigned long Offset
);
```

### <a name="parameters"></a>パラメーター

*影*\
からの先頭からのオフセット `GS` 。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__incgsbyte`|X64|
|`__incgsword`|X64|
|`__incgsdword`|X64|
|`__incgsqword`|X64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

これらのルーチンは、組み込み関数としてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[\__addgsbyte、 \_ _addgsword、 \_ _addgsdword、 \_ _addgsqword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)\
[\__readgsbyte、 \_ _readgsdword、 \_ _readgsqword、 \_ _readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)\
[\__writegsbyte、 \_ _writegsdword、 \_ _writegsqword、 \_ _writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
