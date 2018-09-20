---
title: _WriteBarrier |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _WriteBarrier
dev_langs:
- C++
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0004a48a73ee0635f3d71b8b2ceee1ef90993c7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436573"
---
# <a name="writebarrier"></a>_WriteBarrier

**Microsoft 固有の仕様**

呼び出し場所全体にわたってメモリ アクセス操作の順序を変更できるコンパイラの最適化を制限します。

> [!CAUTION]
>  コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨とらてているため、使用しないでください。 スレッド間の通信の場合などのメカニズムを使用して[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)と[std::atomic\<T >](../standard-library/atomic.md)で定義されている、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md). ハードウェアへのアクセスを使用して、 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプションと組み合わせて、[揮発性](../cpp/volatile-cpp.md)キーワード。

## <a name="syntax"></a>構文

```
void _WriteBarrier(void);
```

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_WriteBarrier`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`_WriteBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセス操作を削除または順序変更できるコンパイラの最適化を制限します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_ReadBarrier](../intrinsics/readbarrier.md)<br/>
[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[キーワード](../cpp/keywords-cpp.md)