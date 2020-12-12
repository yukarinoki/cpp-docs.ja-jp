---
description: '詳細については、次を参照してください: _WriteBarrier'
title: _WriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _WriteBarrier
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
ms.openlocfilehash: 7fe78eaa30e7971853ff9d73d7142b8eeddb679f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313139"
---
# <a name="_writebarrier"></a>_WriteBarrier

**Microsoft 固有の仕様**

呼び出し場所全体にわたってメモリ アクセス操作の順序を変更できるコンパイラの最適化を制限します。

> [!CAUTION]
> コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨とらてているため、使用しないでください。 スレッド間通信には、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)で定義されている[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)や[ \<T> std:: atomic](../standard-library/atomic.md)などの機構を使用します。 ハードウェアアクセスの場合は、 [volatile](../cpp/volatile-cpp.md)キーワードと共に[/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラオプションを使用します。

## <a name="syntax"></a>構文

```C
void _WriteBarrier(void);
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_WriteBarrier`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`_WriteBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセス操作を削除または順序変更できるコンパイラの最適化を制限します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_ReadBarrier](../intrinsics/readbarrier.md)\
[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[キーワード](../cpp/keywords-cpp.md)
