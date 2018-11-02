---
title: malloc アライメント
ms.date: 11/04/2016
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
ms.openlocfilehash: 436033d4e99d42d0a1a9366377f928bc402ac974
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533550"
---
# <a name="malloc-alignment"></a>malloc アライメント

[malloc](../c-runtime-library/reference/malloc.md)メモリが割り当てられるメモリ量に合わせて基本的なアラインメントとを持つ任意のオブジェクトを格納するは、アラインメントを返すことが保証されます。 A*基本的なアラインメント*小さいアラインメントを指定せずに実装によってサポートされている最大の配置を配置します。 (Visual C++ の基本的なアラインメントは、`double` つまり 8 バイトに対して必要なアラインメントです。 64 ビット プラットフォームを対象としたコードでは 16 バイトです)。たとえば、4 バイト割り当ての場合、4 バイト以下のオブジェクトをサポートする境界上にアラインメントされます。

Visual C の許可を持つ型*拡張アラインメント*とも呼ばれるは*オーバーア ラインされた*型。 たとえば、SSE 型[_ _m128](../cpp/m128.md)と`__m256`を使用して宣言されている型と`__declspec(align( n ))`場所`n`8 より大きい値は、配置を拡張します。 オブジェクトで拡張アラインメントが必要な場合、そのオブジェクトに適した境界上でのメモリのアラインメントは、`malloc` によって保証されません。 オーバーア ラインされている型のメモリを割り当てるには、使用[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)および関連する関数。

## <a name="see-also"></a>関連項目

[スタックの使用](../build/stack-usage.md)<br/>
[align](../cpp/align-cpp.md)<br/>
[__declspec](../cpp/declspec.md)