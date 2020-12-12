---
description: '詳細については、次を参照してください: __lidt'
title: __lidt
ms.date: 09/02/2019
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 9b9f4bc51bab07a578671932c16548a0a49d155b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167774"
---
# <a name="__lidt"></a>__lidt

**Microsoft 固有の仕様**

指定されたメモリ位置の値を使用して、割り込み記述子テーブルレジスタ (IDTR) を読み込みます。

## <a name="syntax"></a>構文

```C
void __lidt(void * Source);
```

### <a name="parameters"></a>パラメーター

*電源*\
からIDTR にコピーされる値へのポインター。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__lidt`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

関数はコンピューター命令と同じであり、 `__lidt` `LIDT` カーネルモードでのみ使用できます。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) サイトのドキュメント「Intel Architecture Software Developer's Manual, Volume 2: 命令セットリファレンス」を検索してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__sidt](../intrinsics/sidt.md)
