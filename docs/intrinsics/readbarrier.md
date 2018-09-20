---
title: _ReadBarrier |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _ReadBarrier
dev_langs:
- C++
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b121a849f3f1678becb2175bd284d036b534e8e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441383"
---
# <a name="readbarrier"></a>_ReadBarrier

**Microsoft 固有の仕様**

呼び出し場所全体にわたってメモリ アクセス操作の順序を変更できるコンパイラの最適化を制限します。

> [!CAUTION]
>  コンパイラ組み込み関数 `_ReadBarrier`、`_WriteBarrier`、`_ReadWriteBarrier` と、`MemoryBarrier` マクロは、すべて非推奨とらてているため、使用しないでください。 スレッド間の通信の場合などのメカニズムを使用して[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)と[std::atomic\<T >](../standard-library/atomic.md)で定義されている、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md). ハードウェアへのアクセスを使用して、 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプションと組み合わせて、[揮発性](../cpp/volatile-cpp.md)キーワード。

## <a name="syntax"></a>構文

```
void _ReadBarrier(void);
```

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_ReadBarrier`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`_ReadBarrier` 組み込み関数は、呼び出し場所全体にわたってメモリ アクセス操作を削除または順序変更できるコンパイラの最適化を制限します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[キーワード](../cpp/keywords-cpp.md)