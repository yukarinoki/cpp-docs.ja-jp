---
description: '詳細については、次を参照してください: _ReadWriteBarrier'
title: _ReadWriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadWriteBarrier
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
ms.openlocfilehash: ff537d4f3b117b52ba567bf0d130e51d0062965f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294120"
---
# <a name="_readwritebarrier"></a>_ReadWriteBarrier

**Microsoft 固有の仕様**

呼び出し場所全体にわたってメモリ アクセスの順序を変更できるコンパイラの最適化を制限します。

> [!CAUTION]
> コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨とらてているため、使用しないでください。 スレッド間通信には、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)で定義されている[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)や[ \<T> std:: atomic](../standard-library/atomic.md)などの機構を使用します。 ハードウェアアクセスの場合は、 [volatile](../cpp/volatile-cpp.md)キーワードと共に[/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラオプションを使用します。

## <a name="syntax"></a>構文

```C
void _ReadWriteBarrier(void);
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_ReadWriteBarrier`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`_ReadWriteBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセスを削除または順序変更できるコンパイラの最適化を制限します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_ReadBarrier](../intrinsics/readbarrier.md)\
[_WriteBarrier](../intrinsics/writebarrier.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[キーワード](../cpp/keywords-cpp.md)
