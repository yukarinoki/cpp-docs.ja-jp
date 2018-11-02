---
title: __incgsbyte、__incgsword、__incgsdword、__incgsqword
ms.date: 11/04/2016
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
ms.openlocfilehash: a6e8307214f85ba376c539ac791c80ca688c619f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586083"
---
# <a name="incgsbyte-incgsword-incgsdword-incgsqword"></a>__incgsbyte、__incgsword、__incgsdword、__incgsqword

**Microsoft 固有の仕様**

先頭の相対オフセットで指定されたメモリ位置に追加する値を 1 つ、`GS`セグメント。

## <a name="syntax"></a>構文

```
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

#### <a name="parameters"></a>パラメーター

*オフセット*<br/>
[in]先頭からのオフセット`GS`します。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__incgsbyte`|X64|
|`__incgsword`|X64|
|`__incgsdword`|X64|
|`__incgsqword`|X64|

## <a name="remarks"></a>Remarks

これらの組み込みはカーネル モードで使用可能なのみとルーチンは組み込みとしてのみです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_ _addgsbyte、 \__addgsword、 \__addgsdword、 \__addgsqword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)<br/>
[_ _readgsbyte、 \__readgsdword、 \__readgsqword、 \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)<br/>
[_ _writegsbyte、 \__writegsdword、 \__writegsqword、 \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)