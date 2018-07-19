---
title: -O オプション (コードの最適化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
dev_langs:
- C++
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83ddebec9db7a02db40ef31c89c7ff48a66cf665
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376801"
---
# <a name="o-options-optimize-code"></a>/O オプション (コードの最適化)

**/O**さまざまなオプションを制御するための最適化が最高速度または最小サイズのコードを作成します。

- [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)最小サイズのコードを生成するための最適化の組み合わせを設定します。

- [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)最高速度でコードを最適化する最適化の組み合わせを設定します。

- [/Ob](../../build/reference/ob-inline-function-expansion.md)関数のインライン展開を制御します。

- [/Od](../../build/reference/od-disable-debug.md)を高速化するコンパイルおよびデバッグを簡略化の最適化を無効にします。

- [/Og](../../build/reference/og-global-optimizations.md)グローバルな最適化を有効にします。

- [/Oi](../../build/reference/oi-generate-intrinsic-functions.md)適切な関数の呼び出しのための組み込み関数を生成します。

- [/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)コンパイラが最適化の方法をサイズの最適化を最優先に指示します。

- [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) (既定の設定) のサイズの最適化で速度の最適化を優先するようにコンパイラに指示します。

- [/Ox](../../build/reference/ox-full-optimization.md)速度に重点を置いて、最適化のいくつかを選択する組み合わせオプションです。 厳密なサブセットでは、 **/O2**最適化します。

- [/Oy](../../build/reference/oy-frame-pointer-omission.md)方が手軽な関数の呼び出しの呼び出し履歴にフレーム ポインターの作成を抑制します。

## <a name="remarks"></a>コメント

複数を組み合わせることができます **/O**オプションを 1 つのオプションのステートメントにします。 たとえば、 **/Odi**と同じ **/Od/Oi**です。 特定のオプションは相互に排他的で一緒に使用する場合、コンパイラ エラーが発生します。 個々 の **/O**詳細については、オプションです。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)   
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)