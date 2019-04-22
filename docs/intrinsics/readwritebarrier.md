---
title: _ReadWriteBarrier
ms.date: 11/04/2016
f1_keywords:
- _ReadWriteBarrier
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
ms.openlocfilehash: 9da26b685be90bd349d6bfe56c4ad980541d09c0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026754"
---
# <a name="readwritebarrier"></a>_ReadWriteBarrier

**Microsoft 固有の仕様**

呼び出し場所全体にわたってメモリ アクセスの順序を変更できるコンパイラの最適化を制限します。

> [!CAUTION]
>  コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨とらてているため、使用しないでください。 スレッド間の通信の場合などのメカニズムを使用して[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)と[std::atomic\<T >](../standard-library/atomic.md)で定義されている、 [ C++標準ライブラリ](../standard-library/cpp-standard-library-reference.md). ハードウェアへのアクセスを使用して、 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプションと組み合わせて、[揮発性](../cpp/volatile-cpp.md)キーワード。

## <a name="syntax"></a>構文

```
void _ReadWriteBarrier(void);
```

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_ReadWriteBarrier`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`_ReadWriteBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセスを削除または順序変更できるコンパイラの最適化を制限します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_ReadBarrier](../intrinsics/readbarrier.md)<br/>
[_WriteBarrier](../intrinsics/writebarrier.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[キーワード](../cpp/keywords-cpp.md)