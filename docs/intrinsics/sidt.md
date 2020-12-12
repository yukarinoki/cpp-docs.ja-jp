---
description: '詳細については、次を参照してください: __sidt'
title: __sidt
ms.date: 09/02/2019
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 075351bc10981dd8453381e9ce9393a046dfd884
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306964"
---
# <a name="__sidt"></a>__sidt

**Microsoft 固有の仕様**

指定されたメモリ位置に割り込み記述子テーブルレジスタ (IDTR) の値を格納します。

## <a name="syntax"></a>構文

```C
void __sidt(void * Destination);
```

### <a name="parameters"></a>パラメーター

*インストール*\
からIDTR が格納されているメモリ位置へのポインター。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__sidt`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`__sidt` 関数は `SIDT` マシン語命令と同じです。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) サイトのドキュメント「Intel Architecture Software Developer's Manual, Volume 2: 命令セットリファレンス」を検索してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__lidt](../intrinsics/lidt.md)
