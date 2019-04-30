---
title: __writefsbyte、__writefsdword、__writefsqword、__writefsword
ms.date: 11/04/2016
f1_keywords:
- __writefsword
- __writefsbyte
- __writefsqword
- __writefsdword
helpviewer_keywords:
- writefsbyte intrinsic
- __writefsword intrinsic
- writefsqword intrinsic
- writefsdword intrinsic
- __writefsdword intrinsic
- __writefsqword intrinsic
- __writefsbyte intrinsic
- writefsword intrinsic
ms.assetid: 23ac6e8e-bc91-4e90-a4c6-da02993637ad
ms.openlocfilehash: 6461ef730760298e3159e4ac70dbbdf7bd827092
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389789"
---
# <a name="writefsbyte-writefsdword-writefsqword-writefsword"></a>__writefsbyte、__writefsdword、__writefsqword、__writefsword

**Microsoft 固有の仕様**

FS セグメントの先頭の相対オフセットで指定された場所には、メモリを書き込みます。

## <a name="syntax"></a>構文

```
void __writefsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __writefsword(
   unsigned long Offset,
   unsigned short Data
);
void __writefsdword(
   unsigned long Offset,
   unsigned long Data
);
void __writefsqword(
   unsigned long Offset,
   unsigned __int64 Data
);
```

#### <a name="parameters"></a>パラメーター

*オフセット*<br/>
[in]FS への書き込みの先頭からのオフセット。

*データ*<br/>
[in]書き込む値。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__writefsbyte`|x86|
|`__writefsword`|x86|
|`__writefsdword`|x86|
|`__writefsqword`|x86|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

これらのルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)