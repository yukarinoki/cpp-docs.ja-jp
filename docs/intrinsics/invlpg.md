---
title: __invlpg
ms.date: 11/04/2016
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: 0ff46aa15fbb8728ce02255209a32f01a168609b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629386"
---
# <a name="invlpg"></a>__invlpg

**Microsoft 固有の仕様**

X86 が生成されます`invlpg`、命令が指すメモリに関連付けられているページの変換ルック アサイド バッファ (TLB) を無効になります`Address`します。

## <a name="syntax"></a>構文

```
void __invlpg(
   void* Address
);
```

#### <a name="parameters"></a>パラメーター

*アドレス*<br/>
[in]64 ビットのアドレス。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__invlpg`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

組み込みの`__invlpg`特権命令を生成し、0 の特権レベル (CPL) でのカーネル モードでのみ使用します。

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)