---
title: インライン アセンブリでの C++ 関数の呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4717ae24dc1a0b6f51f7a00f68f6569c2f988c65
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678945"
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C++ 関数の呼び出し

**Microsoft 固有の仕様**

`__asm`ブロックがないオーバー ロードされるグローバルの C++ 関数のみを呼び出すことができます。 オーバー ロードのグローバルな C++ 関数、または C++ メンバー関数を呼び出すと、コンパイラはエラーを発行します。

宣言された任意の関数を呼び出すこともできます**extern"C"** リンケージ。 これにより、 `__asm` 、C ライブラリ関数を呼び出すすべての標準ヘッダー ファイルがライブラリ関数を宣言するために、C++ プログラム内でブロック**extern"C"** リンケージ。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>