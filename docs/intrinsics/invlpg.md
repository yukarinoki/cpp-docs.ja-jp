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
ms.openlocfilehash: b4f941baae9f03ed288a99d59e2b06262962e339
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023319"
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

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)