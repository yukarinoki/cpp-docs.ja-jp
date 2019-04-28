---
title: __addfsbyte、__addfsword、__addfsdword
ms.date: 11/04/2016
f1_keywords:
- __addfsbyte_cpp
- __addfsdword
- __addfsword_cpp
- __addfsbyte
- __addfsword
- __addfsdword_cpp
helpviewer_keywords:
- __addfsdword intrinsic
- __addfsword intrinsic
- __addfsbyte intrinsic
ms.assetid: 706c70df-6b52-4401-9268-2977ed8ad715
ms.openlocfilehash: 61053d9f8c56d8352b12ed535dfa870c0856f558
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62264479"
---
# <a name="addfsbyte-addfsword-addfsdword"></a>__addfsbyte、__addfsword、__addfsdword

**Microsoft 固有の仕様**

先頭の相対オフセットで指定されたメモリ位置に値を追加、`FS`セグメント。

## <a name="syntax"></a>構文

```
void __addfsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __addfsword(
   unsigned long Offset,
   unsigned short Data
);
void __addfsdword(
   unsigned long Offset,
   unsigned long Data
);
```

#### <a name="parameters"></a>パラメーター

*オフセット*<br/>
[in]先頭からのオフセット`FS`します。

*データ*<br/>
[in]メモリ位置に追加する値。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__addfsbyte`|x86|
|`__addfsword`|x86|
|`__addfsdword`|x86|

## <a name="remarks"></a>Remarks

これらのルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_ _incfsbyte、 \__incfsword、 \__incfsdword](../intrinsics/incfsbyte-incfsword-incfsdword.md)<br/>
[__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)<br/>
[__writefsbyte, \__writefsdword, \__writefsqword, \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)