---
title: __readgsbyte、__readgsdword、__readgsqword、__readgsword
ms.date: 11/04/2016
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
ms.openlocfilehash: 1bc6a3b2ef2d78e5b30ea36149ea691468c9b0ec
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327513"
---
# <a name="readgsbyte-readgsdword-readgsqword-readgsword"></a>__readgsbyte、__readgsdword、__readgsqword、__readgsword

**Microsoft 固有の仕様**

GS セグメントの先頭の相対オフセットで指定された場所からは、メモリを読み取ります。

## <a name="syntax"></a>構文

```
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

#### <a name="parameters"></a>パラメーター

*オフセット*<br/>
[in]先頭からのオフセット`GS`から読み取る。

## <a name="return-value"></a>戻り値

メモリの内容をバイト、ワード、ダブルワード、quadword (として呼び出される関数の名前で示されます) の場所に`GS:[Offset]`します。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__readgsbyte`|X64|
|`__readgsdword`|X64|
|`__readgsqword`|X64|
|`__readgsword`|X64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

これらの組み込みはカーネル モードで使用可能なのみとルーチンは組み込みとしてのみです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_ _writegsbyte、 \__writegsdword、 \__writegsqword、 \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)