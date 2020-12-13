---
description: '詳細については、次を参照してください: __halt'
title: __halt
ms.date: 09/02/2019
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: e38478b14b59c910e6d6ac12f9cb69fa369e3459
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336985"
---
# <a name="__halt"></a>__halt

**Microsoft 固有の仕様**

有効な割り込み、nonmaskable interrupt (NMI)、またはリセットが発生するまで、マイクロプロセッサを停止します。

## <a name="syntax"></a>構文

```C
void __halt( void );
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__halt`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

関数はコンピューター命令と同じであり、 `__halt` `HLT` カーネルモードでのみ使用できます。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) サイトのドキュメント「Intel Architecture Software Developer's Manual, Volume 2: 命令セットリファレンス」を検索してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
