---
title: __readfsbyte、__readfsdword、__readfsqword、__readfsword
ms.date: 11/04/2016
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
ms.openlocfilehash: bbf963d3a7b927d46485465a61fa08328b8efb52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507998"
---
# <a name="readfsbyte-readfsdword-readfsqword-readfsword"></a>__readfsbyte、__readfsdword、__readfsqword、__readfsword

**Microsoft 固有の仕様**

FS セグメントの先頭の相対オフセットで指定された場所からは、メモリを読み取ります。

## <a name="syntax"></a>構文

```
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

#### <a name="parameters"></a>パラメーター

*オフセット*<br/>
[in]先頭からのオフセット`FS`から読み取る。

## <a name="return-value"></a>戻り値

メモリの内容をバイト、ワード、ダブルワードを quadword (として呼び出される関数の名前で示されます) の場所に`FS:[Offset]`します。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__readfsbyte`|x86|
|`__readfsdword`|x86|
|`__readfsqword`|x86|
|`__readfsword`|x86|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

これらのルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_ _writefsbyte、 \__writefsdword、 \__writefsqword、 \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)