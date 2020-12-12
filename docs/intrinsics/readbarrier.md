---
description: '詳細については、次を参照してください: _ReadBarrier'
title: _ReadBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadBarrier
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
ms.openlocfilehash: 94ade7c8f602cf279ac75a5f0a56387c344d0fb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257494"
---
# <a name="_readbarrier"></a>_ReadBarrier

**Microsoft 固有の仕様**

呼び出し場所全体にわたってメモリ アクセス操作の順序を変更できるコンパイラの最適化を制限します。

> [!CAUTION]
> コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨とらてているため、使用しないでください。 スレッド間通信には、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)で定義されている[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)や[ \<T> std:: atomic](../standard-library/atomic.md)などの機構を使用します。 ハードウェアアクセスの場合は、 [volatile](../cpp/volatile-cpp.md)キーワードと共に[/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラオプションを使用します。

## <a name="syntax"></a>構文

```C
void _ReadBarrier(void);
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_ReadBarrier`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`_ReadBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセス操作を削除または順序変更できるコンパイラの最適化を制限します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[キーワード](../cpp/keywords-cpp.md)
