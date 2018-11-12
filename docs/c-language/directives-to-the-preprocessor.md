---
title: プリプロセッサへのディレクティブ
ms.date: 11/04/2016
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
ms.openlocfilehash: 0abc21f38f5776acd9167f0526160dc5e1bb8cbb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450059"
---
# <a name="directives-to-the-preprocessor"></a>プリプロセッサへのディレクティブ

"ディレクティブ" は、コンパイル前にプログラムのテキストに特定の操作を行うように C プリプロセッサに指示します。 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)の詳細については、「*プリプロセッサ リファレンス*」を参照してください。 `#define` プリプロセッサ ディレクティブの使用例を次に示します。

```
#define MAX 100
```

このステートメントは、コンパイル前に `MAX` で `100` を置き換えるようコンパイラに指示します。 C コンパイラのプリプロセッサ ディレクティブは次のとおりです。

|#define|#endif|#ifdef|#line|
|--------------|-------------|-------------|------------|
|`#elif`|`#error`|**#ifndef**|**#pragma**|
|`#else`|`#if`|`#include`|`#undef`|

## <a name="see-also"></a>参照

[ソース ファイルとソース プログラム](../c-language/source-files-and-source-programs.md)