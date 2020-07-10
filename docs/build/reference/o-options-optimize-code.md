---
title: /O オプション (コードの最適化)
description: MSVC/O コンパイラオプションでは、使用するコンパイラの最適化を指定します。
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
ms.openlocfilehash: 36ef582787a3ec2d7aee1e589c70b48712d9d552
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180878"
---
# <a name="o-options-optimize-code"></a>`/O`オプション (コードの最適化)

オプションは、 **`/O`** 最大速度または最小サイズのコードの作成に役立つさまざまな最適化を制御します。

- [`/O1`](o1-o2-minimize-size-maximize-speed.md)最小サイズのコードを生成する最適化の組み合わせを設定します。

- [`/O2`](o1-o2-minimize-size-maximize-speed.md)最大速度のためにコードを最適化する最適化の組み合わせを設定します。

- [`/Ob`](ob-inline-function-expansion.md)インライン関数の展開を制御します。

- [`/Od`](od-disable-debug.md)最適化を無効にして、コンパイルを高速化し、デバッグを簡略化します。

- [`/Og`](og-global-optimizations.md)(非推奨) グローバルな最適化を有効にします。

- [`/Oi`](oi-generate-intrinsic-functions.md)適切な関数呼び出しのための組み込み関数を生成します。

- [`/Os`](os-ot-favor-small-code-favor-fast-code.md)速度の最適化よりもサイズの最適化を優先するようにコンパイラに指示します。

- [`/Ot`](os-ot-favor-small-code-favor-fast-code.md)(既定の設定) は、サイズの最適化よりも最適化を優先するようにコンパイラに指示します。

- [`/Ox`](ox-full-optimization.md)は、速度を重視していくつかの最適化を選択する組み合わせオプションです。 **`/Ox`** は、最適化の厳密なサブセットです **`/O2`** 。

- [`/Oy`](oy-frame-pointer-omission.md)関数呼び出しを高速化するために、呼び出し履歴にフレームポインターを作成しないようにします。

## <a name="remarks"></a>解説

複数のオプションを組み合わせて **`/O`** 1 つの option ステートメントを作成できます。 たとえば、 **`/Odi`** はと同じ **`/Od /Oi`** です。 一部のオプションは相互に排他的であり、同時に使用するとコンパイラエラーが発生します。 詳細については、個別のオプションを参照してください **`/O`** 。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
