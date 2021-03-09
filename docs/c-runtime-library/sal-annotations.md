---
title: SAL 注釈
description: Microsoft ソースコード注釈言語 (SAL) の簡単な説明。
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- __z annotation
- ref annotation
- _opt annotation
- __checkreturn annotatioin
- __deref_opt annotation
- deref_opt annotation
- __deref annotation
- __in annotation
- annotations [C++]
- z annotation
- _inout annotation
- __ref annotation
- full annotation
- _in annotation
- _ref annotation
- __out annotation
- _ecount annotation
- SAL annotations
- __opt annotation
- inout annotation
- in annotation
- _CA_SHOULD_CHECK_RETURN
- __bcount annotation
- _full annotation
- _bcount annotation
- deref annotation
- part annotation
- _out annotation
- __nz annotation
- __part annotation
- opt annotation
- __full annotation
- _nz annotation
- _z annotation
- out annotation
- __ecount annotation
- __inout annotation
- SAL annotations, _CA_SHOULD_CHECK_RETURN
- _deref_opt annotation
- _deref annotation
- nz annotation
- _part annotation
- ecount annotation
- bcount annotation
ms.assetid: 81893638-010c-41a0-9cb3-666fe360f3e0
ms.openlocfilehash: c4c75213daa69c433b379fb78a0649fa1473de1b
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514461"
---
# <a name="sal-annotations"></a>SAL 注釈

ライブラリ ヘッダー ファイルを調べると、`_In_z` や `_Out_z_cap_(_Size)` など、通常とは異なる注釈がいくつかあることに気付く場合があります。 これらは、Microsoft のソース コード注釈言語 (SAL) の例です。SAL は、関数が自身のパラメーターをどのように使用するかを記述する注釈のセットを提供します。つまり、これらの注釈は、たとえば関数がそのパラメーターについて何を前提としているか、または関数が終了時に何を保証するかを示します。 ヘッダーファイルは \<sal.h> 注釈を定義します。

Visual Studio での SAL 注釈の使用の詳細については、「[Using SAL Annotations to Reduce C/C++ Code Defects (SAL 注釈を使って C/C++ のコード障害を減らす方法)](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)」をご覧ください。

## <a name="see-also"></a>こちらもご覧ください

[C ランタイム (CRT) と C++ 標準ライブラリ (STL) `.lib` ファイル](../c-runtime-library/crt-library-features.md)
